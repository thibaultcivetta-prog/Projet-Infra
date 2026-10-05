# Paramétrage de la base de données

## Objectif

Configurer Gitea pour utiliser la base PostgreSQL créée lors de l’installation.

## Paramètres utilisés

Les informations de connexion utilisées par Gitea sont :

```
Type de base : PostgreSQL
Serveur : 127.0.0.1:5432
Utilisateur : gitea
Base : giteadb
SSL : désactivé
```

Le mot de passe utilisé est celui défini lors de la création de l’utilisateur PostgreSQL.

Saisie dans l’assistant Gitea
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
```
psql -h 127.0.0.1 -U gitea -d giteadb
```



[> Suivant](2-admin.md)
[← Retour au parametrage](../2-parametrage.md)
[← Retour](../README.md)