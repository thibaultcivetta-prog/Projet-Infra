# CONFIGURATION WIREGUARD SMARTPHONE

## Etape préalable

L'accès se fait le plus généralement de l'extérieur. Cette étape ne se destine pas qu'aux smartphones mais à tous les accès depuis l'extérieur.

Avec le VPN, la box ne sait pas où orienter à l'arrivée de l'information. Comme la demande d'ouverture de connexion passe par le port 51820, on indique à la box de transférer vers PfSense.

On va paramétrer le NAT sur la Box.



1 - [Sur PfSense, installation du Paquet Wireguard et paramétrage](1-paquet.md)  
2 - [Configuratoin du VPN sur PFSENSE](2-tunnel.md)  
3 - [Configuration du client WireGuard sous Windows](3-windows.md)  
4 - [Configuration du client WireGuard sur smartphone](4-smartphone.md)  
5 - [Tests de connectivité](5-connectivite.md)  
6 - [Vérification des accès au réseau interne](6-verif.md)  
7 - [Analyse éventuelle des échanges avec Wireshark](7-echange.md)  
8 - [Troubleshooting](8-troubleshooting.md)  
[< RETOUR](../readme.md)
