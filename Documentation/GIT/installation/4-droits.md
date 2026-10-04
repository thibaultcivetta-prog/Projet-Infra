# Gestion des droits

## Objectif

Attribuer les permissions nécessaires aux répertoires utilisés par Gitea.

## Répertoire de données

L'utilisateur `git` doit pouvoir accéder aux données de Gitea :

```
sudo chown -R git:git /var/lib/gitea
sudo chmod -R 750 /var/lib/gitea
```

Répertoire de configuration
Le répertoire /etc/gitea est préparé pour permettre la création initiale du fichier de configuration :

```
sudo chown root:git /etc/gitea
sudo chmod 775 /etc/gitea
```

Après l'installation
Une fois l'installation terminée, les droits peuvent être restreints :
```
sudo chown root:git /etc/gitea/app.ini
sudo chmod 640 /etc/gitea/app.ini
sudo chmod 750 /etc/gitea
```

Objectif de sécurité
Ces permissions permettent :
- à Gitea de lire sa configuration ;
- à l'utilisateur git d'accéder aux données nécessaires ;
- de limiter les modifications non autorisées.

## ETAPES SUIVANTES

5. [Création du service systemd](installation/5-services.md)
6. [Vérifications](installation/6-tests.md)
7. [← Retour à l'installation](../1-installation.md)
8. [← Retour](../README.md)