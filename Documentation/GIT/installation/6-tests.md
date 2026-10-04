## COMMANDES UTILES

### gitea

Redémarrer Gitea :
``` sudo systemctl restart gitea ```

Vérifier son état :
``` sudo systemctl status gitea ```

## Vérification du binaire

```
gitea --version
```

Vérification de PostgreSQL
```
sudo systemctl status postgresql
```
### TEST DE connexion
Un test de connexion peut également être effectué :
```
psql -h 127.0.0.1 -U gitea -d giteadb
```

Vérification du port
```
sudo ss -tlnp | grep 3001
```
Test local
```
curl http://127.0.0.1:3001
```


## ETAPES SUIVANTES

[← Retour à l'installation](../1-installation.md)
[← Retour](../README.md)