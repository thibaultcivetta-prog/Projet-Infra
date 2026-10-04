# Service Gitea

## Objectif

Lancer Gitea comme service système afin qu'il démarre automatiquement avec Debian.

## Création du service systemd

Le fichier suivant est créé :

```
/etc/systemd/system/gitea.service
```

Exemple :
```
[Unit]
Description=Gitea
After=network.target postgresql.service
```
```
[Service]
Type=simple
User=git
Group=git
WorkingDirectory=/var/lib/gitea
Environment=GITEA_WORK_DIR=/var/lib/gitea
ExecStart=/usr/local/bin/gitea web --config /etc/gitea/app.ini --port 3001 --install-port 3001
Restart=always
RestartSec=5
```

```
[Install]
WantedBy=multi-user.target
```

Activation
Prise en compte du nouveau service :
```
sudo systemctl daemon-reload
```

Activation au démarrage :
```
sudo systemctl enable gitea
```

Démarrage du service :
```
sudo systemctl start gitea
```

Commandes utiles
Redémarrer Gitea :
sudo systemctl restart gitea

Vérifier son état :
sudo systemctl status gitea

Résultat
Gitea fonctionne comme service système et peut démarrer automatiquement avec Debian.

## ETAPES SUIVANTES

6. [Vérifications](installation/6-tests.md)
7. [← Retour à l'installation](../1-installation.md)
8. [← Retour](../README.md)