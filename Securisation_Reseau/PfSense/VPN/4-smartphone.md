# CONFIGURATION WIREGUARD SMARTPHONE

## Etapes préalables

### Paramétrage de la box

L'accès au VPN se fait généralement depuis l'extérieur du réseau local.  
Cette étape ne concerne donc pas uniquement les smartphones, mais l'ensemble des connexions externes.

Lorsqu'une connexion WireGuard arrive sur la box Internet via le port UDP 51820, celle-ci doit savoir vers quel équipement du réseau local transmettre le trafic.

Une règle NAT/PAT est donc créée afin de rediriger le port UDP 51820 vers l'interface WAN de pfSense.

```
Nom : Wireguard
Port entrant : 51820
Port sortant : 51820
Protocole : UDP
Equipement : PFSENSE
Adresse externe : 192.168.1.18 
```

### Paramétrage DDNS pour un accès de l'extérieur

De l'extérieur, le Smartphone ou un PC a besoin de connaitre l'adresse publique du réseau.

La box est susceptible d'avoir une option "adresse publique fixe" ou alors on peut utiliser un servie tel que duckdns qui nous permet d'avoir un lien direct entre l'adresse public et l'adresse duckdns.

J'ai créé un compte duckdns, créé un domaine ici `cvtprojetvpn`. Il va me donner un tocken.

Je vais sur pfsense>services>dynamicdns puis dans les profils, je cherche `duckdns`, comme il n'y est pas `custom`.

J'indique sur l'url de mise à jour :

```
https://www.duckdns.org/update?domains=cvtprojetvpn&token=[numéro du token]ip=%IP%
```

## Paramétrage de pfSense
Le tunnel ayant déjà été configuré dans l'étape précédente, il nous reste à créer un nouveau "peer" sur pfsense.



## Paramétrage du smartphone

## Tests




1 - [Sur PfSense, installation du Paquet Wireguard et paramétrage](1-paquet.md)  
2 - [Configuratoin du VPN sur PFSENSE](2-tunnel.md)  
3 - [Configuration du client WireGuard sous Windows](3-windows.md)  
4 - [Configuration du client WireGuard sur smartphone](4-smartphone.md)  
5 - [Tests de connectivité](5-connectivite.md)  
6 - [Vérification des accès au réseau interne](6-verif.md)  
7 - [Analyse éventuelle des échanges avec Wireshark](7-echange.md)  
8 - [Troubleshooting](8-troubleshooting.md)  
[< RETOUR](../readme.md)
