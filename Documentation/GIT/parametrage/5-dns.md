## Objectif

Je veux pouvoir accéder en interne à une adresse ``` git.tssr.lab ``` et non pas une adresse IP avec un port.

## Nom DNS utilisé

Une entrée DNS est créée sur le serveur DNS Windows.

Elle pointe vers l’adresse du serveur Debian hébergeant Gitea.

### Vérification

Depuis un poste du LAB :
```
nslookup git.tssr.lab
```

ou :
```
ping git.tssr.lab
```
Le ping fonctionne et nslookup montre l'adresse Ip du serveur debian.

### Poste physique

Le poste physique n’utilisant pas directement le DNS interne du LAB, une entrée locale peut être ajoutée dans :
C:\Windows\System32\drivers\etc\hosts


Exemple :

```
192.168.1.17 git.tssr.lab
```

Puis :
```
ipconfig /flushdns
```

Le site est désormais directement accessible en interne avec l'adresse ``` git.tssr.lab ```

Ce nom est ensuite utilisé pour l’accès HTTPS et les opérations Git.


[> Suivant](6-depots-tests.md)
[← Retour au parametrage](../2-parametrage.md)
[← Retour](../README.md)