# TROUBLESHOOTING

## Certificat TLS non reconnu lors du clone

### Erreur

```
SEC_E_UNTRUSTED_ROOT
```

#### Cause
Le certificat auto-signé utilisé par git.tssr.lab n'était pas reconnu comme certificat de confiance par Windows / Git.
#### Solution

Importer le certificat dans les autorités de certification racines de confiance de Windows.
Puis configurer Git pour utiliser le magasin de certificats Windows :
``` 
git config --global http.sslBackend schannel
```

## Impossible de créer un commit

### Erreur
```
Author identity unknown
```

### Cause

Git ne connaissait pas encore l'identité de l'utilisateur.

### Solution

```
git config --global user.name "Thibault Civetta"
git config --global user.email "adresse@email.com"
```

## Erreur lors du push sur la branche main

### Erreur
```
refspec main does not match any
```

### Cause

Le dépôt était vide et aucun commit n'avait encore été créé.

### Solution

Créer un fichier puis effectuer le premier commit :
```
git add README.md
git commit -m "Création du README"
git push -u origin main
```


## Échec d'authentification
### Erreur
```
Failed to authenticate user
Authentication failed
```

### Cause

Les informations d'authentification utilisées par Git n'étaient pas valides.

### Solution
Vérifier les identifiants enregistrés par Git Credential Manager et relancer le push.

## Clone d'un dépôt vide
### Message

```
warning: You appear to have cloned an empty repository.
```

### Explication
Ce message n'est pas une erreur.
Le dépôt Gitea ne contenait simplement encore aucun fichier ni commit.

## Résolution DNS de git.tssr.lab
### Problème
Le poste physique pouvait joindre le serveur Debian par son adresse IP mais ne résolvait pas :
```
git.tssr.lab
```

### Solution
Ajout d'une entrée locale dans le fichier Windows :
```
C:\Windows\System32\drivers\etc\hosts
```

Exemple :
```
192.168.1.17 git.tssr.lab
```

Puis :
```
ipconfig /flushdns
```

[1- Installation](1-installation.md)  
[2- Paramétrage](2-parametrage.md)  
[3- TLS](3-TLS.md)  
[4- Synchro et Services](4-synchro-mirroring.md)  
[5- Liens](5-liens.md)  
[6- Commandes Utiles](6-commandes.md)  
[7 - Troubleshooting](7-Troubleshooting.md)  

[← Retour au parametrage](../2-parametrage.md)  

[← Retour](../README.md)