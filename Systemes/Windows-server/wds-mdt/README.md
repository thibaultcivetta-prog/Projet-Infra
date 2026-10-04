# DEPLOIEMENT DE POSTE WINDOWS 11 PRO AVEC PXE

## OBJECTIF

Faire démarrer l'installation de Windows 11 Pro sur un poste distant en utilisant WDS et PXE.

## ENVIRONNEMENT

Serveur MS Windows 22
Poste WINDOWS 11 PRO pour Faire le Master

Autres outils : MDT / Windows ADK et WinPE

## DUREE

3H

## PRINCIPES

WDS initie le démarrage, MDT gère le déploiement

## ETAPES
- installation du Role WDS
- installation Windows ADK et WInPE
- Installation de MDT
- création du "deployement share"
- import de Windows 11 Pro
- Génération de l'image de boot
- ajout dans WDS
- Test PXE
- Import de l'image sur une VM Cliente
  
 ## DIFFICULTES

L'installation du poste où est fait le master est installé en local - pas de WIFI - Pas de cable ethernet branché
Déchiffrement à faire du DD du Master avant sysrep
L'utilisation de MDT est nécessaire pour WDS - même si MDT n'est plus supporté par MS

## RESULTAT

Installation ok, 