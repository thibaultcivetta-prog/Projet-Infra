# Ports et services

## Objectif

Identifier les principaux ports utilisés par Gitea et les services associés.

## Ports utilisés

```
22    : SSH Debian
2222  : SSH Gitea
3000  : Wiki.js
3001  : Gitea
80    : HTTP via Nginx
443   : HTTPS via Nginx
5432  : PostgreSQL
```

Services principaux
Gitea dépend notamment de :
- PostgreSQL pour la base de données ;
- systemd pour le démarrage du service ;
- Nginx pour l’accès Web en HTTP/HTTPS ;
- SSH pour les opérations Git via SSH.

Vérification
Pour Gitea :
```
sudo ss -tlnp | grep 3001
```

Résultat
Les ports utilisés par Gitea et les services associés sont identifiés et peuvent être contrôlés facilement.

[>Suivant](dns.md)
[← Retour au parametrage](../2-parametrage.md)
[← Retour](../README.md)