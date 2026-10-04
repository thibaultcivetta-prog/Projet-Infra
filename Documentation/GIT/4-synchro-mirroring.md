# SYNCHRONISATION ET MIRRORING

## OBJECTIF

La gestion de GITEA est assurée sur le serveur local.
GitHub est utilisé comme interface internet pour présenter mon travail.

## MISE EN OEUVRE

Gitea reste la source principale.
GitHub sert de miroir externe et de vitrine publique du projet.

### Création du dépôt GitHub
Un dépôt vide est créé sur GitHub.

Aucun README ou licence n'est créé côté GitHub.

### Création du token GitHub

Un Personal Access Token est créé sur GitHub.
Le token est limité au dépôt concerné.

### Permission nécessaire :

Contents : Read and write

Le token est utilisé comme moyen d'authentification depuis Gitea.

### Configuration du miroir
Dans les paramètres du dépôt Gitea :
Paramètres
→ Miroirs
→ Ajouter un miroir push

#### URL du dépôt distant :
Gitea reste la source principale.
GitHub sert de miroir externe et de vitrine publique du projet.

## Configuration du miroir

Dans les paramètres du dépôt Gitea :
Paramètres
→ Miroirs
→ Ajouter un miroir push

URL du dépôt distant :

https://github.com/<utilisateur>/<depot>.git

Dans la section Autorisation :

Utilisateur : compte GitHub
Mot de passe : Token

L'option suivante est activée :

Synchroniser quand les révisions sont soumises

## Test
Une synchronisation manuelle est lancée depuis Gitea.
Le dépôt GitHub doit alors contenir les mêmes fichiers et commits que Gitea.

7. [← Retour au TLS](../3-TLS.md)
10. [← Retour](../README.md)