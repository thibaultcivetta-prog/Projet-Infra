# INSTALLATION DU PAQUET WIREGUARD SUR PFSENSE


## Installation du paquet

Dans pfSense :

`System > Package Manager > Available Packages`

Rechercher :

`WireGuard`

Puis installer le paquet officiel WireGuard.

Après installation, le menu suivant devient disponible :

`VPN > WireGuard`

## Création du tunnel

Créer un nouveau tunnel dans :

`VPN > WireGuard > Tunnels`

Paramètres utilisés :

```
Description : MonVPN
Listen Port : 51820
Interface WireGuard : 10.10.60.1/24
```

Puis :
```
- génération des clés ;
- assignation à `OPT2` ;
- activation de l’interface ;
- `10.10.60.1/24` ;
- gateway `None`.
```



1 - [Sur PfSense, installation du Paquet Wireguard et paramétrage](1-paquet.md)  
2 - [Configuratoin du VPN sur PFSENSE](2-tunnel.md)  
3 - [Configuration du client WireGuard sous Windows](3-windows.md)  
4 - [Configuration du client WireGuard sur smartphone](4-smartphone.md)  
5 - [Tests de connectivité](5-connectivite.md)  
6 - [Vérification des accès au réseau interne](6-verif.md)  
7 - [Analyse éventuelle des échanges avec Wireshark](7-echange.md)  
8 - [Troubleshooting](8-troubleshooting.md)  
[< RETOUR](../readme.md)
