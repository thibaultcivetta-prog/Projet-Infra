# Création d'un dépot et architecture

## Création du dépôt principal

Le dépôt principal est créé dans Gitea.

Nom utilisé :

```
Mon-projet-Infra
```

Le dépôt est utilisé comme point central pour l’ensemble du projet d’infrastructure.

```
## Contenu du dépôt
Le dépôt contient notamment :
- les procédures d’installation ;
- les fichiers de configuration ;
- les scripts ;
- les commandes utiles ;
- les documents techniques ;
- les différentes briques du projet.
```
## Organisation
```
Le dépôt est structuré par grands domaines :
Systemes/
Securisation_Reseau/
Cybersecurite/
Intelligence_Artificielle/
Documentation/
```

Chaque dossier contient ensuite ses propres sous-rubriques.

```
Exemple :
Systemes/
├── Windows-server/
└── Linux/
```

## Documentation

Les fichiers Markdown sont utilisés pour documenter les différentes étapes du projet.

Chaque rubrique possède un fichier README.md permettant :
- de présenter le contenu du dossier ;
- de créer un sommaire ;
- de naviguer vers les sous-parties ;
- de revenir vers les niveaux supérieurs.

## Résultat
Le dépôt Gitea devient le point central du projet.
Il permet de regrouper et versionner :
- la documentation ;
- les scripts ;
- les configurations ;
- les procédures ;
- les évolutions du projet.

[GIT / TLS](../3-TLS.md)
[← Retour au parametrage](../2-parametrage.md)
[← Retour](../README.md)