+++
date = '2025-02-09T01:27:32+01:00'
draft = false
title = 'Bienvenue sur Linux 5 : Maîtriser la Redirection & les Pipelines'
description = "Prenez le contrôle du flux de données dans le terminal ! Apprenez à rediriger les entrées, sorties et erreurs, et à combiner les commandes avec des pipelines pour des flux de travail efficaces."
tags = ["Linux", "Redirection", "Pipelines", "Commandes Linux", "Terminal", "Ligne de commande"]
categories = ["Tutoriels Linux", "Bienvenue sur Linux"]
+++

### **1. Introduction : Contrôlez le flux de données comme un pro !** 🚀

Maintenant que vous savez naviguer dans le système de fichiers et travailler avec des fichiers, il est temps de **libérer toute la puissance de la ligne de commande** en maîtrisant la **redirection** et les **pipelines**. Ces fonctionnalités vous permettent de contrôler où vont les sorties, comment gérer les erreurs et comment les commandes interagissent entre elles.

Prêt ? Allons-y ! 🔥

---

### **2. Flux d'entrée, sortie et erreurs standard**

Chaque commande sous Linux interagit avec trois flux de données :

| **Flux**     | **Description**                              | **Descripteur de fichier** |
|--------------|----------------------------------------------|----------------------------|
| **stdin**    | Entrée standard (clavier ou fichier)         | `0`                        |
| **stdout**   | Sortie standard (par défaut : terminal)      | `1`                        |
| **stderr**   | Messages d'erreur                            | `2`                        |

Vous pouvez **rediriger** ces flux à l’aide d’opérateurs spéciaux.

---

### **3. Rediriger la sortie : Sauvegarder les résultats des commandes dans un fichier**

#### **3.1 Remplacer la sortie (`>`)**
Rediriger la sortie d’une commande vers un fichier (en écrasant le contenu existant) :
```bash
$ ls > fichiers.txt  # Sauvegarde la sortie de 'ls' dans fichiers.txt
```
Maintenant, `fichiers.txt` contient la liste des fichiers du répertoire.

#### **3.2 Ajouter à la sortie (`>>`)**
Utilisez `>>` pour **ajouter** la sortie à un fichier existant au lieu de l'écraser :
```bash
$ echo "Nouvelle entrée de journal" >> logs.txt
```

---

### **4. Rediriger l’entrée : Utiliser un fichier comme entrée de commande (`<`)**
Certaines commandes acceptent l'entrée d'un fichier au lieu du clavier :
```bash
$ sort < noms.txt  # Trie le contenu de noms.txt
```
Cela envoie `noms.txt` en entrée à `sort`, qui affiche ensuite les résultats triés.

---

### **5. Rediriger les erreurs : Gérer les messages d'erreur (`2>`, `2>>`)** 🚨
#### **5.1 Rediriger les erreurs vers un fichier**
Parfois, les erreurs encombrent votre écran. Redirigez-les vers un fichier :
```bash
$ ls /inexistant 2> erreur.log  # Sauvegarde le message d'erreur dans erreur.log
```
#### **5.2 Rediriger les erreurs et la sortie ensemble (`&>` ou `2>&1`)**
Pour **sauvegarder à la fois la sortie et les erreurs** dans le même fichier :
```bash
$ commande &> sortie.log
```
Ou :
```bash
$ commande > sortie.log 2>&1
```

---

### **6. La puissance des Pipelines (`|`) : Connecter les commandes** 🔗
Un pipeline (`|`) **connecte plusieurs commandes**, en passant la sortie d’une commande comme entrée à une autre.

#### **6.1 Exemple : Compter les fichiers**
```bash
$ ls | wc -l  # Compte le nombre de fichiers dans un répertoire
```
- `ls` liste les fichiers.
- `wc -l` compte le nombre de lignes.

#### **6.2 Exemple : Filtrer la sortie avec `grep`**
```bash
$ ps aux | grep firefox  # Trouver les processus Firefox en cours
```
- `ps aux` liste tous les processus.
- `grep firefox` filtre les processus liés à Firefox.

#### **6.3 Exemple : Trier et supprimer les doublons**
```bash
$ cat noms.txt | sort | uniq
```
- `sort` trie les lignes par ordre alphabétique.
- `uniq` supprime les entrées en double.

---

### **7. Utiliser `tee` : Voir et sauvegarder la sortie simultanément** 📄
Normalement, lorsque vous redirigez la sortie vers un fichier, vous **ne la voyez pas** dans le terminal. La commande `tee` **affiche la sortie tout en la sauvegardant** :
```bash
$ ls | tee liste_fichiers.txt
```
Vous pouvez maintenant voir la liste **et** la sauvegarder dans `liste_fichiers.txt`.

---

### **8. Ignorer la sortie indésirable (`/dev/null`)**
Pour **supprimer** la sortie, redirigez-la vers `/dev/null` :
```bash
$ commande > /dev/null 2>&1  # Ignore la sortie et les erreurs
```
Cela est utile dans les scripts lorsque vous **ne vous souciez que du succès/de l’échec**.

---

### **9. Exemples pratiques** 🛠️

#### **9.1 Trouver le mot le plus fréquent dans un fichier**
```bash
$ cat fichier.txt | tr ' ' '\n' | sort | uniq -c | sort -nr | head -10
```
- `tr ' ' '\n'` remplace les espaces par des nouvelles lignes.
- `sort` trie les mots.
- `uniq -c` compte les occurrences.
- `sort -nr` trie par fréquence.
- `head -10` affiche les 10 premiers mots.

#### **9.2 Surveiller l'utilisation des ressources système**
```bash
$ ps aux | sort -rk 3,3 | head -5
```
Cela trie les processus par utilisation CPU (`-rk 3,3`) et affiche les 5 premiers.

---

### **10. Prochaines étapes : Passer à la vitesse supérieure !** 🚀
Maintenant que vous savez **rediriger la sortie, gérer les erreurs et enchaîner les commandes avec des pipelines**, il est temps de passer à la gestion des processus. Nous verrons comment contrôler efficacement les programmes en cours d'exécution. Restez connecté ! 🎯
