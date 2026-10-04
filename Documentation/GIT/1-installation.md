# Installation de Gitea

## Objectif

Mettre en place un serveur Git auto-hébergé sur Debian afin de centraliser et documenter mes projets techniques.

Gitea est utilisé comme dépôt principal pour les fichiers, scripts et procédures associés au projet d’infrastructure.

---

## Environnement

L’installation repose sur les éléments suivants :

- Debian
- Gitea
- PostgreSQL
- Git
- systemd

Gitea est installé directement sur le serveur Debian sous forme de binaire.

---

## Installation des prérequis

Les paquets nécessaires sont installés sur Debian :

```bash
sudo apt update
sudo apt install git postgresql -y