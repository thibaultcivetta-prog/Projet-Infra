# Installation du binaire Gitea

## Objectif

Installer le binaire Gitea sur le serveur Debian afin de disposer de l’exécutable nécessaire au fonctionnement du service Git auto-hébergé.

## Téléchargement

La version Linux AMD64 de Gitea est utilisée.

Le binaire est téléchargé depuis le site officiel de Gitea puis placé dans le répertoire :

```text
/usr/local/bin/
```
## Attribution des droits d’exécution

sudo chmod +x /usr/local/bin/gitea

## Vérification de l’installation

La présence et le bon fonctionnement du binaire sont vérifiés avec :

gitea --version

Résultat obtenu :

Gitea version 28.0.0

Cette commande permet de confirmer que :
- le binaire est correctement installé ;
- il est exécutable ;
- il est accessible depuis le système ;
- la version installée est connue.

## Emplacement du binaire
Le choix de /usr/local/bin/ permet de conserver Gitea dans un emplacement standard pour les applications installées manuellement.
Cela permet également d’appeler simplement :
gitea

sans avoir à préciser le chemin complet à chaque commande.

## Résultat
Le binaire Gitea est installé et exécutable sur Debian.
À ce stade, l’application n’est pas encore configurée.

## Les étapes suivantes concernent notamment :
2. [Installation et préparation de PostgreSQL](installation/2-Postgresql.md)
3. [Création de l'utilisateur système et des répertoires](installation/3-utilisateur-repertoires.md)
4. [Gestion des droits](installation/4-droits.md)
5. [Création du service systemd](installation/5-services.md)
6. [Vérifications](installation/6-tests.md)