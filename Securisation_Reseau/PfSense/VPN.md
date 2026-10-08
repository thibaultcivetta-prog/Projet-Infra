# VIRTUAL PRIVATE NETWORK / VPN

## Objectif 

Créer un VPN accessible de l'extérieur

## Réalisation

### Authentification par clé

L'utilisateur est identifié par une clé privée et publique.

#### Outils

- PfSense
- Wireshark
- Un PC sous Windows 11
- Un Smartphone (Iphone ou Android)

#### Installation et Configuration

1 - [Sur PfSense, installation du Paquet Wireguard et paramétrage](VPN/1-paquet.md)  
2 - [Création des règles pare-feu](VPN/2-tunnel.md)  
3 - [Configuration du client WireGuard sous Windows](VPN/3-windows.md)  
4 - [Configuration du client WireGuard sur smartphone](VPN/4-smartphone.md)  
5 - [Tests de connectivité](VPN/5-connectivite.md)  
6 - [Vérification des accès au réseau interne](VPN/6-verif.md)  
7 - [Analyse éventuelle des échanges avec Wireshark](VPN/7-echange.md)  
8 - [Troubleshooting](VPN/8-troubleshooting.md)  
[< RETOUR](../readme.md)

### Authentification centralisée

L'utilisateur est identifié par un serveur RADIUS qui va autoriser la connexion.

Ce projet n'est pas encore réalisé mais il sera abordé plus tard.

[← Retour](../README.md)