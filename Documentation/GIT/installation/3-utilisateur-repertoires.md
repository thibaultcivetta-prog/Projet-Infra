# Utilisateur système et répertoires

## Objectif

Créer un utilisateur système dédié à Gitea et préparer les répertoires nécessaires à son fonctionnement.

## Création de l'utilisateur système

Un compte dédié est créé pour exécuter Gitea :

```
sudo adduser \
  --system \
  --shell /bin/bash \
  --gecos 'Git Version Control' \
  --group \
  --disabled-password \
  --home /home/git \
  git
```

L'utilisateur utilisé par Gitea est donc :
``` git ```

Création des répertoires
Création des dossiers nécessaires :
```
sudo mkdir -p /var/lib/gitea/{custom,data,log}
sudo mkdir -p /etc/gitea
```

Répertoires principaux :
```
/var/lib/gitea
/etc/gitea
```

Le premier contient les données de fonctionnement de Gitea.
Le second contient la configuration de l'application.
Résultat
Gitea dispose maintenant :
- d'un utilisateur système dédié ;
- d'un répertoire de données ;
- d'un répertoire de configuration.

## ETAPES SUIVANTES

4. [Gestion des droits](installation/4-droits.md)
5. [Création du service systemd](installation/5-services.md)
6. [Vérifications](installation/6-tests.md)
7. [← Retour à l'installation](../1-installation.md)
8. [← Retour](../README.md)