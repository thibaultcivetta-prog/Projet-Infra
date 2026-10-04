## Objectif

Sécuriser l'accès à Gitea en HTTPS.

Gitea fonctionne localement sur le port `3001` et Nginx est utilisé comme reverse proxy afin de publier le service en HTTPS.

## Architecture

Le service est accessible avec le nom :
``` git.tssr.lab ```

Génération du certificat

Un certificat auto-signé a été créé pour ``` git.tssr.lab ```

```
sudo openssl req -x509 -nodes -days 365 \
-newkey rsa:2048 \
-keyout /etc/nginx/certs/git.key \
-out /etc/nginx/certs/git.crt \
-subj "/C=FR/ST=France/L=93150/O=TSSR/OU=LAB/CN=git.tssr.lab" \
-addext "subjectAltName=DNS:git.tssr.lab"
```

Les fichiers générés sont :

```
/etc/nginx/certs/git.crt
/etc/nginx/certs/git.key
```

La clé privée reste uniquement sur le serveur.

Configuration Nginx
Nginx redirige les connexions HTTP vers HTTPS puis transmet les requêtes vers Gitea.

```
server {
    listen 80;
    server_name git.tssr.lab;

    return 301 https://$host$request_uri;
}

server {
    listen 443 ssl;
    server_name git.tssr.lab;

    ssl_certificate /etc/nginx/certs/git.crt;
    ssl_certificate_key /etc/nginx/certs/git.key;

    location / {
        proxy_pass http://127.0.0.1:3001;
        proxy_http_version 1.1;

        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto https;
    }
}
```

Paramétrage Gitea
Dans ``` /etc/gitea/app.ini ``` :

```
[server]
DOMAIN = git.tssr.lab
ROOT_URL = https://git.tssr.lab/
LOCAL_ROOT_URL = http://localhost:3001/
HTTP_PORT = 3001
```

Après modification :

```
sudo systemctl restart gitea
sudo nginx -t
sudo systemctl reload nginx
```

Confiance du certificat

Je récupère le certificat avec la fonction cp et je l'envoie sur mon poste Windows.

Le certificat auto-signé est importé dans les autorités de certification de confiance du poste Windows.
Git utilise le magasin de certificats Windows sans désactiver la vérification TLS.

Résultat
Gitea est accessible en HTTPS via :
```
https://git.tssr.lab
```

Les échanges entre le client et Nginx sont chiffrés.

[← Retour au parametrage](../2-parametrage.md)
[← Retour](../README.md)