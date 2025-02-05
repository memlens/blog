+++
date = '2025-02-04T04:07:11+01:00'
draft = false
author = 'Ayedoun Châ-Fine ADEBI'
description = "Choisir sa distribution linux"
tags = ["Linux", "Void Linux", "Tutoriel", "Débutant"]
categories = ["Linux"]
lang = "fr"
title = 'Choisir sa Distribution Linux et Installer Ubuntu sur VirtualBox'
+++



## **Pourquoi Linux ?** 🐧  
<img src="/images/choisir-sa-distro-linux/pourquoi-linux.jpg" width="200px">

Quand on entend parler de Linux pour la première fois, on imagine souvent un hacker masqué dans un film hollywoodien... **Mais en réalité, Linux est bien plus que ça !**  
<img src="/media/posts/2025/02/choisir-sa-distro-linux/hacker.webp" width="200px" > 
Imaginez Linux comme **une grande famille de systèmes d'exploitation** :  
- **Le noyau Linux** → Le "coeur" commun à tous (comme le scénario d'une série)  
- **Les distributions** → Les déclinaisons avec leurs personnalités uniques (comme les personnages)  

Contrairement à Windows/macOS, Linux vous offre :  
🔓 **Liberté totale** : Personnalisez *tout* (interface, sécurité, performances)  
🚀 **Légèreté** : Redonnez vie à un vieux PC (ex: avec Lubuntu)  
🛡️ **Sécurité** : Moins de virus grâce à l'open source et aux droits utilisateurs  

> "*Choisir Linux, c'est comme passer de la télévision par câble à Netflix : vous décidez quoi, quand et comment l'utiliser.*"  

**Mon coup de cœur perso** : [Pourquoi j'ai abandonné Windows pour Void Linux]({{< relref "pourquoi-j-ai-choisi-linux" >}})  

---

## **1. Choisir sa Distribution Linux** 🎯  

### **Le Top 6 des Distros pour Débutants**  
| Distribution      | Points Forts                                   | Public Cible                    | Lien |
|-------------------|-----------------------------------------------|---------------------------------|------|
| **Linux Mint**    | Interface Windows-like, ultra-stable          | Anciens utilisateurs Windows    | [📥](https://linuxmint.com) |
| **Ubuntu**        | Support long terme, communauté massive        | Écoles/entreprises, débutants   | [📥](https://ubuntu.com) |
| **Zorin OS**      | Design épuré, mode "Windows" activable        | Designers, utilisateurs grand public | [📥](https://zorin.com/os/) |
| **Fedora**        | Technologies de pointe (Wayland, PipeWire)    | Développeurs, tech enthusiasts  | [📥](https://getfedora.org) |
| **Pop!_OS**       | Optimisé gaming/NVIDIA, gestion énergie       | Gamers, créateurs de contenu    | [📥](https://pop.system76.com) |
| **MX Linux**      | Léger, outils de dépannage intégrés           | Vieilles machines, bidouilleurs | [📥](https://mxlinux.org) |

🔍 **Besoin d'aide pour choisir ?** Explorez [DistroWatch](https://distrowatch.com), le "IMDb des distributions Linux" !


---

## **2. Préparer l’Installation sur VirtualBox** 🖥️  

### **VirtualBox : Qu'est-ce que c'est ?**  
VirtualBox est un logiciel **gratuit** qui permet de créer des *machines virtuelles* (VM) :  
- 🖥️ **Machine virtuelle** = Un PC simulé dans votre PC actuel  
- 🛡️ **Avantage** : Tester Linux sans toucher à votre système principal  

### ✅ **Checklist avant installation**  
1. **Télécharger Ubuntu LTS** ([lien officiel](https://ubuntu.com/download/desktop))  
   → *Pourquoi LTS ?* = Version Long Term Support (mises à jour garanties sur une longue période).  
  <img src="/media/posts/2025/02/choisir-sa-distro-linux/down-ubun.png" width="400px">
2. **Installer VirtualBox** ([Windows](https://download.virtualbox.org/virtualbox/7.0.14/VirtualBox-7.0.14-161095-Win.exe) / [macOS](https://download.virtualbox.org/virtualbox/7.0.14/VirtualBox-7.0.14-161095-OSX.dmg))  
   → *Procédure d'installation* : Double-cliquez sur le fichier téléchargé et suivez les instructions.  
  - Exemple de Windows:
  
    - Lancez l'installation en double-cliquant sur le fichier 
      <img src="/media/posts/2025/02/choisir-sa-distro-linux/VirtualBox-Windows-Installation-01.png" width="400px">
    - Sélectionnez le repertoire ou sera installé virtualbox  
      <img src="/media/posts/2025/02/choisir-sa-distro-linux/VirtualBox-Windows-Installation-02.png" width="400px">
    - Sélectionnez les racourcis que vous souhaitez (un seul racourcis serais idéal, celui dans le menu de démarrage par exemple.)
      <img src="/media/posts/2025/02/choisir-sa-distro-linux/VirtualBox-Windows-Installation-03.png" width="400px">
    - Lancez le processus d'installation
      <img src="/media/posts/2025/02/choisir-sa-distro-linux/VirtualBox-Windows-Installation-04.png" width="400px">    
    - Installer les certificats
    <img src="/media/posts/2025/02/choisir-sa-distro-linux/VirtualBox-Windows-Installation-05.png" width="400px">    
    - Installtion terminée
    <img src="/media/posts/2025/02/choisir-sa-distro-linux/VirtualBox-Windows-Installation-06.png" width="400px">    

    - Interface de virtualbox box 
    <img src="/media/posts/2025/02/choisir-sa-distro-linux/VirtualBox-Windows-Installation-07.png" width="400px">    


3. **Vérifier l'espace disque** :  
   - 20 Go minimum pour Ubuntu  
   - 2 Go de RAM libre recommandés  


---

### **Créer sa Machine Virtuelle en 5 étapes**  

#### **Étape 1 : Lancer VirtualBox et cliquer sur "Nouvelle"**  

<img src="/media/posts/2025/02/choisir-sa-distro-linux/Ubuntu-VirtualBox-Installation-00.png" width="400px" >

#### **Étape 2 : Configurer les paramètres de base**  
- **Nom** : `Ubuntu-Tutoriel` (sans espaces)  
- **Type** : Linux  
- **Version** : Ubuntu (64-bit)  
<img src="/media/posts/2025/02/choisir-sa-distro-linux/Ubuntu-VirtualBox-Installation-011.png" width="400px" >

#### **Étape 3 : Allouer la mémoire RAM**  
- Minimum : 2048 Mo (2 Go)  
- Recommandé : 4096 Mo (4 Go)  
<img src="/media/posts/2025/02/choisir-sa-distro-linux/Ubuntu-VirtualBox-Installation-02.png" width="400px" >

#### **Étape 4 : Créer le disque dur virtuel**  
- Choisir **VDI** (format natif VirtualBox)  
- Sélectionner **Dynamiquement alloué** (le disque grossit selon vos besoins)  
- Taille : 20 Go minimum  
<img src="/media/posts/2025/02/choisir-sa-distro-linux/Ubuntu-VirtualBox-Installation-03.png" width="400px" >

<img src="/media/posts/2025/02/choisir-sa-distro-linux/Ubuntu-VirtualBox-Installation-04.png" width="400px" >

<img src="/media/posts/2025/02/choisir-sa-distro-linux/Ubuntu-VirtualBox-Installation-05.png" width="400px" >

<img src="/media/posts/2025/02/choisir-sa-distro-linux/Ubuntu-VirtualBox-Installation-061.png" width="400px" >


#### **Étape 5 : Monter l'ISO d'Ubuntu**  
1. Sélectionnez votre VM → **Configuration** → **Stockage**  
2. Cliquez sur l'icône 📀 sous "Contrôleur IDE" → **Choisir un fichier de disque**  
3. Sélectionnez votre fichier `ubuntu-XX.XX-lts.iso`  
<img src="/media/posts/2025/02/choisir-sa-distro-linux/Ubuntu-VirtualBox-Installation-071.png" width="400px" >

![Montage de l'ISO dans VirtualBox](lien-image-montage-iso)  

---

## **3. Installation d’Ubuntu** 🛠️  

### **Guide Visuel Pas à Pas**  
1. **Lancez la VM** → Cliquez sur "Démarrer"  
2. **Choix de la langue** → Français  
![Écran de bienvenue Ubuntu](lien-image-langue)  

3. **Options d'installation** :  
   - ☑️ *Installation normale* (navigateur, suite bureautique, outils multimédias)  
   - ☑️ *Télécharger les mises à jour maintenant*  

4. **Partitionnement** → *Effacer le disque et installer Ubuntu*  
   → **⚠️ Sans danger** : Ceci n'affecte pas votre vrai disque dur !  

5. **Configuration utilisateur** :  
   - Nom : `votre-pseudo`  
   - Mot de passe : **Minimum 8 caractères** (ex: `LinuxR0cks!`)  

6. **Patientez 10-20 min** → Ubuntu s'installe automatiquement  
![Progression de l'installation](lien-image-progression-install)  

---

### **Bonus : Personnalisation Post-Installation**  
Après le redémarrage :  
1. Installez les **Guest Additions** (pour le copier-coller et le plein écran) :  
   ```bash
   sudo apt install virtualbox-guest-utils -y
   ```  
2. Activez le **mode sombre** dans *Paramètres > Apparence*  
3. Ajoutez des raccourcis pratiques dans la barre latérale  

---

### **FAQ : Problèmes Fréquents**  

#### **🖥️ La VM est trop lente ?**  
- Augmentez la RAM à 4 Go dans *Configuration > Système*  
- Activez l'accélération 3D dans *Affichage > Écran*  

#### **⌨️ Mon clavier ne répond pas dans la VM ?**  
Cliquez dans la fenêtre VirtualBox et appuyez sur **Ctrl + Alt + Suppr** pour libérer le focus.  

#### **📁 Comment transférer des fichiers ?**  
Utilisez le **glisser-déposer** activé via *Périphériques > Glisser-déposer > Bidirectionnel*.  

