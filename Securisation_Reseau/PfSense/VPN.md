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

- [Sur PfSense, installation du Paquet Wireguard et paramétrage](VPN/Pfsense.md)
- Configuration du client WireGuard sous Windows
- Configuration du client WireGuard sur smartphone
- Création des règles pare-feu
- Tests de connectivité
- Vérification des accès au réseau interne
- Analyse éventuelle des échanges avec Wireshark
- Troubleshooting

### Authentification centralisée

L'utilisateur est identifié par un serveur RADIUS qui va autoriser la connexion.

Ce projet n'est pas encore réalisé mais il sera abordé plus tard.

[← Retour](../README.md)