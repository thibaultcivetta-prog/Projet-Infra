# Troubleshooting WireGuard

## 1. Erreur de clé publique invalide

### Symptôme

Lors de la configuration du client Windows, WireGuard retournait une erreur indiquant que la clé ne pouvait pas être décodée correctement.

Exemple :

```
Les clés doivent être décodées sur 32 octets
```

Cause
La clé publique pfSense avait été copiée depuis un affichage tronqué.
Résolution
Récupérer la clé publique complète directement dans la configuration du tunnel WireGuard sur pfSense puis la recopier dans la configuration du client Windows.
Vérification
Le tunnel peut ensuite être activé sans erreur de clé.


## 2. Handshake établi mais absence de connectivité
### Symptôme
Le statut WireGuard sur pfSense indiquait un handshake récent avec le client Windows.
Cependant, les équipements du réseau interne n'étaient pas joignables.
```
ping 192.168.60.11
ping 192.168.60.16
```

Les requêtes échouaient malgré l'établissement du tunnel.
### Cause
Le tunne### l WireGuard avait bien été créé mais l'interface pfSense associée au tunnel n'était pas activée.
### Résolution
Dans :
```Interfaces > Assignments```
Affecter tun_wg0 à une interface, puis activer celle-ci.
Configuration utilisée :
```
Interface : OPT2
IPv4 Configuration Type : Static IPv4
Adresse : 10.10.60.1/24
Gateway : None
```

### Résultat
Après activation de l'interface, le trafic entre le client VPN et le réseau interne a pu circuler.
## 3. Vérification des routes Windows
### Symptôme
Le tunnel est actif mais certaines destinations ne sont pas accessibles.
Vérification
Afficher la table de routage Windows :
```
route print
```

Les routes suivantes doivent être présentes :

```
10.10.60.0/24
192.168.60.0/24
```

et doivent utiliser l'interface WireGuard.
### Résolution
Vérifier la directive AllowedIPs dans la configuration du client :
```
AllowedIPs = 10.10.60.0/24, 192.168.60.0/24
```

WireGuard utilise cette directive pour déterminer les réseaux à acheminer dans le tunnel.
## 4. Vérification des règles pare-feu
### Symptôme
Le handshake fonctionne mais le trafic VPN reste bloqué.
### Vérification
Contrôler les règles associées :
- au WAN pfSense ;
- à l'interface WireGuard ;
- au réseau interne.
Le port utilisé par WireGuard doit être autorisé côté WAN :
```
Protocole : UDP
Port : 51820
Destination : WAN Address
```
L'interface WireGuard doit également autoriser le trafic vers le réseau du LAB.
## 5. WAN pfSense sur un réseau privé
### Symptôme
Le tunnel ne fonctionne pas correctement alors que pfSense utilise une adresse WAN privée.
Dans le LAB :
```
WAN pfSense : 192.168.1.18
```

### Cause possible
L'option de blocage des réseaux privés peut empêcher certains flux lorsque le WAN pfSense est connecté au réseau domestique 192.168.1.0/24.
### Résolution
Dans la configuration de l'interface WAN, vérifier que l'option de blocage des réseaux privés n'empêche pas la communication nécessaire au LAB.

1 - [Sur PfSense, installation du Paquet Wireguard et paramétrage](1-paquet.md)  
2 - [Configuratoin du VPN sur PFSENSE](2-tunnel.md)  
3 - [Configuration du client WireGuard sous Windows](3-windows.md)  
4 - [Configuration du client WireGuard sur smartphone](4-smartphone.md)  
5 - [Tests de connectivité](5-connectivite.md)  
6 - [Vérification des accès au réseau interne](6-verif.md)  
7 - [Analyse éventuelle des échanges avec Wireshark](7-echange.md)  
8 - [Troubleshooting](8-troubleshooting.md)  
[< RETOUR](../readme.md)
