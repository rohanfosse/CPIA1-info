---
section: Python
nav_order: 2
title: Types de Données et Variables
topics: Variables; Types de données; Opérations; Conversion de types
---
Python est un langage de programmation polyvalent et accessible, utilisé pour développer des applications web, des analyses de données, de l’intelligence artificielle, et bien plus encore. Grâce à sa syntaxe simple et lisible, Python est un excellent choix pour les débutants tout en restant puissant pour les experts. Ce cours introduit les bases de l’utilisation de Python, de l’installation aux premières lignes de code.

## Qu'est-ce que Python ?

Python est un langage de programmation caractérisé par :
1. **Une syntaxe simple et intuitive** : Sa syntaxe repose sur l’indentation, facilitant la lecture et l’organisation du code.
2. **Un environnement riche en bibliothèques** : Python dispose de nombreuses bibliothèques qui permettent de faire du développement web, du traitement d'images, des analyses de données, etc.
3. **Une grande communauté** : Avec une vaste communauté d’utilisateurs, Python dispose de nombreux supports, forums, et documentation pour accompagner les développeurs de tout niveau.

## Installation de Python

Pour programmer en Python, vous aurez besoin de :
1. **Installer Python** : Rendez-vous sur [python.org](https://www.python.org/downloads/) pour télécharger la dernière version de Python, compatible avec votre système d'exploitation.
2. **Choisir un éditeur de code** : Python peut être utilisé dans plusieurs environnements, mais **Jupyter Notebook** et **VS Code** sont recommandés pour débuter.

**Liens de téléchargement** :
- Python : [python.org](https://www.python.org/downloads/)
- Jupyter Notebook : [jupyter.org](https://jupyter.org/install)
- VS Code : [code.visualstudio.com](https://code.visualstudio.com/)

---

## Votre premier programme Python

1. **Ouvrir un éditeur de code** : Lancez l’éditeur que vous avez choisi (Jupyter Notebook ou VS Code).
2. **Créer un nouveau fichier Python** : Sauvegardez-le avec une extension `.py` pour les programmes Python.
3. **Écrire un code simple** pour afficher un message dans la console :

   ```python
   print("Bonjour, Python !")
   ```

4. **Exécuter le code** : Dans un terminal ou une console de votre éditeur, exécutez le programme pour voir le message s’afficher.

---

## La Syntaxe de base en Python

### Les commentaires

Les commentaires sont des lignes de code qui ne sont pas exécutées par Python mais qui permettent d’ajouter des notes pour documenter votre code :

```python
# Ceci est un commentaire
print("Hello, World!")  # Ceci est un commentaire en fin de ligne
```

### Les variables et types de données

En Python, vous n'avez pas besoin de déclarer explicitement le type d'une variable ; il est déterminé automatiquement en fonction de la valeur que vous lui assignez.

Exemple de types de données :
- **Entier** : `x = 10`
- **Flottant** : `y = 3.14`
- **Chaîne de caractères** : `texte = "Bonjour"`
- **Booléen** : `est_vrai = True`

---

## Premier programme interactif

Python permet de créer des programmes interactifs, où l’utilisateur peut entrer des informations via le terminal.

1. **Utiliser la fonction `input()`** pour demander un nom d’utilisateur :
   
   ```python
   nom = input("Entrez votre nom : ")
   print("Bonjour, " + nom + " !")
   ```

Ce programme affiche un message personnalisé avec le nom saisi.

---

## Utilisation du Terminal et des Commandes Python

Pour travailler efficacement avec Python, il est utile de comprendre certaines commandes de base pour gérer des scripts dans le terminal et comprendre l’organisation des fichiers.

1. **Exécuter un script Python** dans le terminal :

   ```bash
   python nom_du_fichier.py
   ```

2. **Accéder à l'aide et à la documentation** avec la commande `help()` dans un interpréteur Python :

   ```python
   help(print)
   ```

   - Cela affiche la documentation de la fonction `print`.

---

## Avantages de Python pour les débutants

- **Syntaxe simple** : Grâce à son langage lisible, Python facilite l’apprentissage de la programmation.
- **Riche en ressources** : Il existe de nombreux tutoriels et documentations pour accompagner votre progression.
- **Support de la communauté** : La communauté Python est vaste et dynamique, avec des forums et des groupes d'entraide.

---

## Résumé des commandes de base

| Commande               | Description                                    |
|------------------------|------------------------------------------------|
| `print()`              | Affiche un message dans la console             |
| `input()`              | Demande une saisie à l'utilisateur             |
| `# commentaire`        | Ajoute un commentaire dans le code             |
| `type(variable)`       | Affiche le type de la variable                 |
| `help(fonction)`       | Affiche l'aide pour la fonction                |

Ce premier chapitre vous initie aux bases de Python. Dans les chapitres suivants, nous explorerons les structures de contrôle, les fonctions, et les collections de données pour créer des programmes plus avancés.