# Création du tunnel et du peer WireGuard sur pfSense

## Création du tunnel

Dans pfSense :

`VPN > WireGuard > Tunnels > Add Tunnel`

Paramètres utilisés :

```
Description : MonVPN
Listen Port : 51820
Adresse VPN : 10.10.60.1/24
```

Une paire de clés est générée pour le tunnel.
La clé privée reste sur pfSense.
La clé publique sera utilisée plus tard dans la configuration du client Windows.
Affectation du tunnel à une interface
Le tunnel est ensuite associé à une interface pfSense :
```Interfaces > Assignments```
Le tunnel tun_wg0 est affecté à OPT2.
Configuration de l'interface :
```
Enable interface : Oui
IPv4 Configuration Type : Static IPv4
IPv4 Address : 10.10.60.1/24
Gateway : None
```
L'interface doit être activée pour permettre le passage du trafic VPN.
Création du peer Windows
Dans :
```VPN > WireGuard > Peers > Add Peer```
Paramètres utilisés :
```
Description : PC-Windows
Tunnel : MonVPN
Public Key : clé publique du poste Windows
Allowed IPs : 10.10.60.2/32
Endpoint : vide
```

L'adresse ```10.10.60.2``` est réservée au client Windows dans le réseau VPN.
Principe des clés
WireGuard utilise une paire de clés publique / privée sur chaque équipement.
PC Windows
```
Clé privée  → reste sur le PC
Clé publique → copiée dans le peer pfSense
```

pfSense
```
Clé privée  → reste sur pfSense
Clé publique → copiée dans le client Windows
```

1 - [Sur PfSense, installation du Paquet Wireguard et paramétrage](1-paquet.md)  
2 - [Configuratoin du VPN sur PFSENSE](2-tunnel.md)  
3 - [Configuration du client WireGuard sous Windows](2-windows.md)  
4 - [Configuration du client WireGuard sur smartphone](3-smartphone.md)  
5 - [Tests de connectivité](5-connectivite.md)  
6 - [Vérification des accès au réseau interne](6-verif.md)  
7 - [Analyse éventuelle des échanges avec Wireshark](7-echange.md)  
8 - [Troubleshooting](8-troubleshooting.md)  
[< RETOUR](../readme.md)