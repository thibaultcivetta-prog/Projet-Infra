# Installation et préparation de PostgreSQL

## Objectif

Mettre en place une base de données PostgreSQL dédiée à Gitea.

Gitea utilise cette base pour stocker ses informations de fonctionnement, notamment les comptes, paramètres, dépôts et métadonnées associées.

## Installation de PostgreSQL

Installation du serveur PostgreSQL :

```bash
sudo apt update
sudo apt install postgresql -y
```

## Vérification du service :

``` text
sudo systemctl status postgresql
```

Le service doit être actif.

## Accès à PostgreSQL

Connexion à PostgreSQL avec le compte administrateur :
```
sudo -u postgres psql
```

L’invite PostgreSQL s’ouvre alors.
Création de l’utilisateur Gitea
Création d’un utilisateur dédié :

```
CREATE USER gitea WITH PASSWORD '********';
```

Cet utilisateur sera utilisé uniquement par Gitea pour accéder à sa base de données.
Création de la base
Création d’une base dédiée :
``` 
CREATE DATABASE giteadb OWNER gitea;
```

La base utilisée est donc :
Nom de la base : giteadb
Utilisateur : gitea

## Sortie de PostgreSQL
Pour quitter l’interface PostgreSQL :
```
\q
```

## Vérification de la connexion
Un test de connexion peut être réalisé depuis Debian :
```
psql -h 127.0.0.1 -U gitea -d giteadb
```

Le mot de passe défini précédemment est demandé.

Cette commande permet de vérifier que :
- l’utilisateur gitea existe ;
- la base giteadb existe ;
- l’utilisateur peut se connecter à la base ;
- PostgreSQL accepte la connexion locale via TCP.

## Résultat
Une base PostgreSQL dédiée à Gitea est maintenant disponible.
La configuration utilisée est :

```
Serveur : 127.0.0.1
Port : 5432
Base : giteadb
Utilisateur : gitea
```

## ETAPES SUIVANTES

3. [Création de l'utilisateur système et des répertoires](installation/3-utilisateur-repertoires.md)
4. [Gestion des droits](installation/4-droits.md)
5. [Création du service systemd](installation/5-services.md)
6. [Vérifications](installation/6-tests.md)