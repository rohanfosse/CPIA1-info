---
section: Corbeille d'exercices
nav_order: 3
title: Corbeille d'exercices de Python
topics: Python; Exercices
---

{% include question.html header="Exercice 1 - Somme des Nombres" text="Écrivez un programme Python qui demande à l'utilisateur d'entrer deux nombres, puis affiche leur somme. Bonus : ajoutez une vérification pour s'assurer que l'utilisateur entre bien des nombres." solution="
```python
try:
    a = int(input('Entrez le premier nombre : '))
    b = int(input('Entrez le second nombre : '))
    print('La somme est :', a + b)
except ValueError:
    print('Veuillez entrer des nombres valides.')
```
Le bloc `try-except` vérifie si l'entrée est un entier et gère les erreurs si l'utilisateur entre autre chose.
" %}

---

{% include question.html header="Exercice 2 - Boucle et Multiplication" text="Écrivez un programme qui affiche la table de multiplication d'un nombre choisi par l'utilisateur, jusqu'à 10." solution="
```python
n = int(input('Entrez un nombre pour afficher sa table de multiplication : '))
for i in range(1, 11):  # Boucle de 1 à 10
    print(f'{n} x {i} = {n * i}')
```
La boucle `for` parcourt chaque valeur de 1 à 10 et calcule le produit en temps réel.
" %}

---

{% include question.html header="Exercice 3 - Trouver un Mot dans une Phrase" text="Demandez à l'utilisateur d'entrer une phrase et un mot. Vérifiez si le mot est présent dans la phrase et affichez un message approprié." solution="
```python
phrase = input('Entrez une phrase : ')
mot = input('Entrez un mot à chercher : ')
if mot in phrase:
    print('Le mot est présent dans la phrase.')
else:
    print('Le mot est absent.')
```
L'opérateur `in` permet de vérifier facilement si un mot est dans une phrase.
" %}

---

{% include question.html header="Exercice 4 - Moyenne d'une Liste" text="Créez un programme qui calcule la moyenne des nombres contenus dans une liste donnée par l'utilisateur." solution="
```python
nombres = input('Entrez des nombres séparés par des virgules : ').split(',')
nombres = [int(x) for x in nombres]  # Convertit chaque élément en entier
moyenne = sum(nombres) / len(nombres)
print('La moyenne est :', moyenne)
```
# `split(',')` divise la chaîne en liste, puis une compréhension de liste convertit chaque élément en entier.
" %}

---

{% include question.html header="Exercice 5 - Gestionnaire de Contacts" text="Créez un programme qui permet de stocker des contacts. Chaque contact doit contenir un nom et un numéro de téléphone. Permettez à l'utilisateur d'ajouter un contact, de le chercher ou de le supprimer." solution="
```python
contacts = {}

while True:
    print('1. Ajouter un contact')
    print('2. Rechercher un contact')
    print('3. Supprimer un contact')
    print('4. Quitter')
    choix = input('Choisissez une option : ')

    if choix == '1':  # Ajouter un contact
        nom = input('Entrez le nom : ')
        numero = input('Entrez le numéro : ')
        contacts[nom] = numero
        print(f'Contact ajouté : {nom} -> {numero}')
    elif choix == '2':  # Rechercher un contact
        nom = input('Entrez le nom à rechercher : ')
        print(contacts.get(nom, 'Contact introuvable.'))
    elif choix == '3':  # Supprimer un contact
        nom = input('Entrez le nom à supprimer : ')
        if contacts.pop(nom, None):
            print(f'Contact {nom} supprimé.')
        else:
            print('Contact introuvable.')
    elif choix == '4':  # Quitter
        break
    else:
        print('Option invalide.')
```
Le programme utilise un dictionnaire pour stocker les contacts et un menu interactif pour naviguer.
" %}

---

{% include question.html header="Exercice 6 - Tri d'une Liste" text="Demandez à l'utilisateur une liste de nombres et affichez-la triée dans l'ordre croissant et décroissant." solution="
```python
nombres = input('Entrez des nombres séparés par des virgules : ').split(',')
nombres = [int(x) for x in nombres]
print('Tri croissant :', sorted(nombres))
print('Tri décroissant :', sorted(nombres, reverse=True))
```
La fonction `sorted` retourne une liste triée, et l'option `reverse=True` inverse l'ordre.
" %}

---

{% include question.html header="Exercice 7 - Jeu de Deviner le Nombre" text="Créez un jeu où l'ordinateur génère un nombre aléatoire entre 1 et 100, et l'utilisateur doit le deviner en recevant des indices ('Trop grand' ou 'Trop petit')." solution="
```python
import random

nombre_a_deviner = random.randint(1, 100)
tentative = None

print('Devinez le nombre (entre 1 et 100) :')

while tentative != nombre_a_deviner:
    tentative = int(input('Votre proposition : '))
    if tentative < nombre_a_deviner:
        print('Trop petit.')
    elif tentative > nombre_a_deviner:
        print('Trop grand.')
    else:
        print('Bravo ! Vous avez deviné le nombre.')
```
Le module `random` génère un nombre aléatoire, et une boucle `while` continue jusqu'à ce que l'utilisateur devine.
" %}

---

{% include question.html header="Exercice 8 - Analyse de Fichiers" text="Créez un programme qui lit un fichier texte donné par l'utilisateur, compte le nombre de lignes et affiche les 5 premières lignes." solution="
```python
nom_fichier = input('Entrez le nom du fichier : ')
try:
    with open(nom_fichier, 'r') as fichier:
        lignes = fichier.readlines()
        print('Nombre de lignes :', len(lignes))
        print('Les 5 premières lignes :')
        for ligne in lignes[:5]:
            print(ligne.strip())
except FileNotFoundError:
    print('Fichier introuvable.')
```
Le mode `with open()` garantit que le fichier sera fermé après lecture, et `strip()` enlève les espaces superflus.
" %}

