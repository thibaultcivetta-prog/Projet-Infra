# Paramétrage de Gitea

## Objectif

Configurer Gitea pour son utilisation dans l'infrastructure du projet.

## Paramètres utilisés

Les informations de connexion utilisées par Gitea sont :

### Rappel
```
Type de base : PostgreSQL
Serveur : 127.0.0.1:5432
Utilisateur : gitea
Base : giteadb
SSL : désactivé```
```

Le mot de passe utilisé est celui défini lors de la création de l’utilisateur PostgreSQL.

Saisie dans l’assistant Gitea en me connectant à l'adresse de Gitea (ici ``` 192.168.60.16:3001 ```)
Lors du premier accès à l’interface d’installation de Gitea, les paramètres suivants sont renseignés :
```
Type de base : PostgreSQL
Hôte : 127.0.0.1:5432
Nom d’utilisateur : gitea
Mot de passe : ********
Nom de la base : giteadb
SSL : Disable
```

Le schéma PostgreSQL est laissé sur la valeur par défaut.
Vérification
Après validation de l’installation, Gitea doit pouvoir accéder à la base sans erreur.
La connexion peut également être contrôlée depuis Debian avec :
``` psql -h 127.0.0.1 -U gitea -d giteadb ```

Résultat
Gitea est désormais relié à sa base PostgreSQL dédiée.
La base de données sera utilisée pour stocker les informations nécessaires au fonctionnement de l’application.

## Étapes

1. [Paramétrage de la base de données](parametrage/1-bdd.md)
2. [Création du compte administrateur](parametrage/2-admin.md)
3. [Configuration du fichier app.ini](parametrage/3-app-ini.md)
4. [Configuration des ports et services](parametrage/4-ports-services.md)
5. [Configuration DNS](parametrage/5-dns.md)
6. [Création des dépôts et organisation des projets](parametrage/6-depots-tests.md)
7. [← Retour Installation](1-installation.md)
8. [← Retour](../README.md)
