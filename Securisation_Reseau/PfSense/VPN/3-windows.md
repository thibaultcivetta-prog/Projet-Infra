# CONFIGURATION WIREGUARD SUR WINDOWS


## Installation

Télécharger et installer l'application WireGuard pour Windows.

Créer ensuite un nouveau tunnel vide afin de générer automatiquement une paire de clés.

La clé privée reste uniquement sur le poste Windows.

La clé publique du poste est copiée dans le peer correspondant sur pfSense.

## Configuration

Exemple de configuration utilisée :

```
[Interface]
PrivateKey = <clé privée du PC>
Address = 10.10.60.2/24
```
```[Peer]
PublicKey = <clé publique pfSense>
AllowedIPs = 10.10.60.0/24, 192.168.60.0/24
Endpoint = 192.168.1.18:51820
```

Paramètres
```
Adresse VPN du PC : 10.10.60.2/24
Réseau VPN        : 10.10.60.0/24
Réseau LAB        : 192.168.60.0/24
Endpoint pfSense  : 192.168.1.18:51820
```

Fonctionnement
Le paramètre AllowedIPs indique quels réseaux doivent passer dans le tunnel WireGuard.
Dans cette configuration :
```
10.10.60.0/24
192.168.60.0/24
```

seuls le réseau VPN et le réseau du LAB sont routés dans le tunnel.
La connexion Internet classique du poste continue à utiliser sa passerelle habituelle.
Vérification
Après activation du tunnel, vérifier l'adresse et les routes avec :
```
ipconfig
route print
```

On doit voir apparaitre ce genre de table de routage avec les plages prévues dans le VPN :
```
IPv4 Table de routage
===========================================================================
Itinéraires actifs :
Destination réseau    Masque réseau  Adr. passerelle   Adr. interface Métrique
          0.0.0.0          0.0.0.0      192.168.1.1     192.168.1.15     30
         10.0.2.0    255.255.255.0         On-link          10.0.2.0    281
         10.0.2.0  255.255.255.255         On-link          10.0.2.0    281
       10.0.2.255  255.255.255.255         On-link          10.0.2.0    281
       10.10.60.0    255.255.255.0         On-link        10.10.60.2      5
       10.10.60.2  255.255.255.255         On-link        10.10.60.2    261
     10.10.60.255  255.255.255.255         On-link        10.10.60.2    261
        127.0.0.0        255.0.0.0         On-link         127.0.0.1    331
        127.0.0.1  255.255.255.255         On-link         127.0.0.1    331
  127.255.255.255  255.255.255.255         On-link         127.0.0.1    331
      192.168.1.0    255.255.255.0         On-link      192.168.1.15    286
     192.168.1.15  255.255.255.255         On-link      192.168.1.15    286
    192.168.1.255  255.255.255.255         On-link      192.168.1.15    286
     192.168.35.0    255.255.255.0         On-link      192.168.35.1    281
     192.168.35.1  255.255.255.255         On-link      192.168.35.1    281
   192.168.35.255  255.255.255.255         On-link      192.168.35.1    281
     192.168.56.0    255.255.255.0         On-link      192.168.56.1    281
     192.168.56.1  255.255.255.255         On-link      192.168.56.1    281
   192.168.56.255  255.255.255.255         On-link      192.168.56.1    281
     192.168.60.0    255.255.255.0         On-link        10.10.60.2      5
   192.168.60.255  255.255.255.255         On-link        10.10.60.2IPv4 Table de routage
===========================================================================
Itinéraires actifs :
Destination réseau    Masque réseau  Adr. passerelle   Adr. interface Métrique
          0.0.0.0          0.0.0.0      192.168.1.1     192.168.1.15     30
         10.0.2.0    255.255.255.0         On-link          10.0.2.0    281
         10.0.2.0  255.255.255.255         On-link          10.0.2.0    281
       10.0.2.255  255.255.255.255         On-link          10.0.2.0    281
       10.10.60.0    255.255.255.0         On-link        10.10.60.2      5
       10.10.60.2  255.255.255.255         On-link        10.10.60.2    261

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





