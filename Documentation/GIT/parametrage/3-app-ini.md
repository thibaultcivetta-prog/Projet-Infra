# Configuration de app.ini

Le fichier de configuration principal est modifié avec nano:

```
sudo nano /etc/gitea/app.ini
```

Section serveur
Les paramètres principaux utilisés sont :

```
[server]
DOMAIN = git.tssr.lab
ROOT_URL = https://git.tssr.lab/
LOCAL_ROOT_URL = http://localhost:3001/
HTTP_PORT = 3001
SSH_PORT = 2222

DOMAIN
DOMAIN = git.tssr.lab
```
## détail des paramètres

### ROOT_URL
Définit le nom DNS utilisé pour accéder au service Gitea.

```
ROOT_URL = https://git.tssr.lab/
```

Définit l’URL publique utilisée par Gitea.
Ce paramètre est important pour :
- les liens générés par Gitea ;
- les redirections ;
- les cookies de session ;
- les URL de clonage.

### LOCAL_ROOT_URL

Cette adresse est utilisée localement par Gitea

```
LOCAL_ROOT_URL = http://localhost:3001/  
```

### HTTP_PORT
Le service reste accessible directement sur le port 3001 depuis le serveur Debian.
```
HTTP_PORT = 3001
```
Gitea écoute sur le port 3001.
Le port 3000 est déjà utilisé par Wiki.js sur le même serveur.

### SSH_PORT
Le port SSH présenté par Gitea est défini sur 2222.
```
SSH_PORT = 2222
```

Cela évite un conflit avec le service SSH Debian qui utilise le port 22.

## Après modification du fichier :
```
sudo systemctl restart gitea
```

Vérification
Contrôle de l’état du service :
```
sudo systemctl status gitea
```

Vérification de l’écoute sur le port 3001 :
```
sudo ss -tlnp | grep 3001
```
[> Etape suivante](parametrage/4-ports-service.md)
[← Retour au parametrage](../2-parametrage.md)
[← Retour](../README.md)