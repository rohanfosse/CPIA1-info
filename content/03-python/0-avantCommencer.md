---
section_id: Python
nav_order: 3
title: Installation de Python et VSCode
topics: Python; Programmation; Installation; Syntaxe de base
---

Python est un langage de programmation puissant, simple à apprendre et largement utilisé dans le développement logiciel, l'analyse de données, l'intelligence artificielle, et bien d'autres domaines. Pour commencer à utiliser Python, vous devez l’installer sur votre machine. Ce guide vous explique comment installer Python 3.11 sur **Windows** et **Mac**.

---

## Installation de Python

### Installation de Python sur Windows

1. **Téléchargement** :
   - Rendez-vous sur le site officiel de Python à cette adresse : [Télécharger Python pour Windows](https://www.python.org/downloads/).
   - Cliquez sur **Download Python 3.11**.

2. **Installation** :
   - Lancez le fichier téléchargé (`python-3.11.x-amd64.exe`).
   - Sur la fenêtre d’installation, cochez l’option **Add Python to PATH** pour configurer Python dans les variables d’environnement (indispensable pour l'utiliser dans le terminal).
   - Cliquez sur **Install Now** pour une installation par défaut.

3. **Vérification de l'installation** :
   - Ouvrez une invite de commande (`cmd` dans le champ de recherche Windows).
   - Tapez la commande suivante pour vérifier la version de Python :
     ```bash
     python --version
     ```
     Cela devrait afficher quelque chose comme : `Python 3.11.x`.

---

### Installation de Python sur macOS

1. **Téléchargement et installation** :
   - macOS inclut souvent une version de Python préinstallée, mais elle est généralement obsolète. Il est recommandé d’installer la dernière version de Python 3.11 depuis le site officiel.
   - Rendez-vous sur [https://www.python.org/downloads/](https://www.python.org/downloads/).
   - Cliquez sur **Download Python 3.11**.
   - Téléchargez le fichier `.pkg` correspondant à macOS.

2. **Exécution de l’installation** :
   - Ouvrez le fichier téléchargé (`python-3.11.x-macos.pkg`) et suivez les instructions à l’écran.
   - Une fois l'installation terminée, Python sera installé dans `/usr/local/bin/`.

3. **Vérification de l'installation** :
   - Ouvrez une application Terminal (recherchez "Terminal" dans Spotlight ou depuis Applications > Utilitaires).
   - Tapez la commande suivante pour vérifier que Python est installé :
     ```bash
     python3 --version
     ```
     Cela devrait afficher la version 3.11.x.

4. **Configurer Homebrew (optionnel)** :
   - Une méthode populaire pour gérer les installations sur macOS est d’utiliser **Homebrew**, un gestionnaire de paquets.
   - Installez Homebrew si ce n'est pas encore fait :
     ```bash
     /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
     ```
   - Installez Python via Homebrew :
     ```bash
     brew install python@3.11
     ```
   - Vérifiez l'installation :
     ```bash
     python3 --version
     ```

---

## Installation de vsCode

### Pourquoi utiliser VSCode et l'importance d'un environnement de développement

Un environnement de développement comme **Visual Studio Code (VSCode)** facilite l'écriture, l'exécution et le débogage du code grâce à des outils intégrés et une interface intuitive. Il est particulièrement adapté aux débutants grâce à sa simplicité et à ses nombreuses extensions personnalisables.

---

### Installation de Visual Studio Code

1. **Téléchargement** :
   - Rendez-vous sur le site officiel : [Télécharger VSCode](https://code.visualstudio.com/).
   - Cliquez sur **Download for Windows** (ou sélectionnez la version macOS si nécessaire).

2. **Installation** :
   - Lancez l'installateur (`VSCodeSetup-x.x.x.exe` ou `.dmg`).
   - Acceptez les termes et suivez les étapes.
   - **Cochez les options importantes** (Windows) :
     - "Ajouter à PATH".
     - "Ajouter une option 'Ouvrir avec Code' au menu contextuel".
   - Cliquez sur **Installer**.

---

###  Installation de l’extension Jupyter et Python

1. **Ouvrir le gestionnaire d’extensions** :
   - Dans VSCode, cliquez sur l'onglet **Extensions** (icône des 4 carrés dans la barre latérale gauche ou `Ctrl+Shift+X`).

2. **Installer l’extension Python** :
   - Recherchez "Python".
   - Installez l'extension officielle **Python** (développée par Microsoft).

3. **Installer l’extension Jupyter** :
   - Recherchez "Jupyter".
   - Installez l'extension officielle **Jupyter** (développée par Microsoft).

---

## Utilisation de Python dans VSCode

### Comment lancer un code Python avec VSCode

1. **Créer un fichier Python** :
   - Cliquez sur **File > New File** et sauvegardez-le avec l’extension `.py` (par exemple, `example.py`).

2. **Écrire un script Python** :
   Ajoutez ce code simple dans le fichier :
   ```python
   # Exemple de script Python
   def salutation(nom):
       return f"Bonjour, {nom} !"

   nom_utilisateur = input("Entrez votre nom : ")
   print(salutation(nom_utilisateur))
   ```

3. **Choisir l’interpréteur Python** :
   - Appuyez sur `Ctrl+Shift+P` (ou `Cmd+Shift+P` sur Mac).
   - Recherchez et sélectionnez **Python: Select Interpreter**.
   - Choisissez l'installation de Python 3.11.

4. **Exécuter le code** :
   - Méthode 1 : Cliquez sur le bouton **Exécuter** (icône ▶) en haut à droite de VSCode.
   - Méthode 2 : Ouvrez le terminal intégré (`Ctrl+`) et tapez :
     ```bash
     python example.py
     ```

---

### Lancer un notebook Jupyter dans VSCode

1. **Créer un fichier Jupyter Notebook** :
   - Sauvegardez un nouveau fichier avec l’extension `.ipynb` (par exemple, `example.ipynb`).

2. **Ajouter et exécuter une cellule** :
   - Cliquez sur `+` pour créer une cellule.
   - Ajoutez ce code dans la cellule :
     ```python
     rayon = 5
     aire = 3.14 * rayon**2
     f"L'aire d'un cercle de rayon {rayon} est {aire:.2f}"
     ```
   - Cliquez sur **▶** à gauche de la cellule pour exécuter.

---
