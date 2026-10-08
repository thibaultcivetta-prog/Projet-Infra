# TESTS DE CONNECTIVITE

Vérification
Après activation du tunnel, vérifier l'adresse et les routes avec :
```
ipconfig
```
```
route print
```

Puis tester :
```
ping 10.10.60.1
ping 192.168.60.1
ping 192.168.60.11
ping 192.168.60.16

EXEMPLE RESULTATS : 

```

C:\Users\Thiba>IPCONFIG

Configuration IP de Windows


Carte inconnue VPN_Maison :

   Suffixe DNS propre à la connexion. . . :
   Adresse IPv6 de liaison locale. . . . .: fe80::6109:4177:1b30:1e0c%4
   Adresse IPv4. . . . . . . . . . . . . .: 10.10.60.2
   Masque de sous-réseau. . . . . . . . . : 255.255.255.255
   Passerelle par défaut. . . . . . . . . :

```
```
C:\Users\Thiba>ping 10.10.60.1

Envoi d’une requête 'Ping'  10.10.60.1 avec 32 octets de données :
Réponse de 10.10.60.1 : octets=32 temps=2 ms TTL=64
Réponse de 10.10.60.1 : octets=32 temps=3 ms TTL=64
Réponse de 10.10.60.1 : octets=32 temps=1 ms TTL=64
Réponse de 10.10.60.1 : octets=32 temps=1 ms TTL=64

Statistiques Ping pour 10.10.60.1:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 1ms, Maximum = 3ms, Moyenne = 1ms

C:\Users\Thiba>ping 192.168.60.11

Envoi d’une requête 'Ping'  192.168.60.11 avec 32 octets de données :
Réponse de 192.168.60.11 : octets=32 temps=5 ms TTL=127
Réponse de 192.168.60.11 : octets=32 temps=4 ms TTL=127
Réponse de 192.168.60.11 : octets=32 temps=3 ms TTL=127
Réponse de 192.168.60.11 : octets=32 temps=4 ms TTL=127
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
