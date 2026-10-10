# VERIFICATION DES ACCES

Une fois le tunnel WireGuard configuré, je vérifie que les clients VPN peuvent accéder au réseau interne.

Les principaux tests portent sur :

- l'accès à pfSense ;
- l'accès au serveur Windows `192.168.60.11` ;
- l'accès au serveur Debian `192.168.60.16` ;
- la résolution DNS interne ;
- l'accès à Gitea et Wiki.js.

Lors du paramétrage du smartphone, la connexion WireGuard ne fonctionnait pas correctement.

J'ai utilisé les outils de diagnostic intégrés à pfSense, notamment :

- `VPN > WireGuard > Status` pour vérifier le handshake et les compteurs RX/TX ;
- `Diagnostics > Ping` pour tester la connectivité ;
- `Diagnostics > Packet Capture` pour observer les échanges UDP sur le port `51820`.

La capture réseau a permis de confirmer que le smartphone envoyait bien des paquets vers pfSense, ce qui a permis d'orienter le diagnostic vers la configuration du peer WireGuard.

Après correction de la configuration du smartphone, le handshake et les échanges RX/TX sont devenus fonctionnels.

Les accès au réseau interne et à Internet ont ensuite été validés depuis le Wi-Fi puis depuis le réseau 4G/5G.


1 - [Sur PfSense, installation du Paquet Wireguard et paramétrage](1-paquet.md)  
2 - [Configuratoin du VPN sur PFSENSE](2-tunnel.md)  
3 - [Configuration du client WireGuard sous Windows](3-windows.md)  
4 - [Configuration du client WireGuard sur smartphone](4-smartphone.md)  
5 - [Tests de connectivité](5-connectivite.md)  
6 - [Vérification des accès au réseau interne](6-verif.md)  
7 - [Analyse éventuelle des échanges avec Wireshark](7-echange.md)  
8 - [Troubleshooting](8-troubleshooting.md)  
[< RETOUR](../readme.md)
