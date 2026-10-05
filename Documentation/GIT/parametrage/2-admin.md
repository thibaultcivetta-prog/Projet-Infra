## Objectif

Lors de la première connexion à Gitea, la documentation d'installation précise que le premier utilisateur créé sera l'administrateur.

## Création du compte

Lors de l’installation initiale depuis l’interface Web, un compte administrateur est créé.

Les informations renseignées sont :

```
Nom d’utilisateur : dark
Adresse e-mail : adresse utilisée pour le compte administrateur
Mot de passe : ********
```

Ce compte dispose des droits d’administration de l’instance Gitea.
Rôle du compte administrateur

```
Le compte administrateur permet notamment de :
- créer et gérer les dépôts ;
- gérer les utilisateurs ;### 
- accéder aux paramètres du site ;
- gérer les projets, tickets et jalons ;
- configurer les fonctionnalités de l’instance ;
- administrer les miroirs et intégrations.
```

### Sécurité
Il conviendra de créer un deuxième utilisateur sans droit administrateur pour gérer la publication des dépots.

Résultat
Le premier compte administrateur est opérationnel et permet de finaliser la configuration de Gitea.

7. [← Retour au parametrage](../2-parametrage.md)
10. [← Retour](../README.md)