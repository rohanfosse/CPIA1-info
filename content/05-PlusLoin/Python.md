---
section_id: Pour aller plus loin
nav_order: 5
title: Notions Avancées de Python
topics: Décorateurs; Générateurs; Métaclasses; Concurrence; Context Managers
---

Python offre de nombreuses fonctionnalités avancées qui permettent de développer des programmes complexes et performants. Ce chapitre explore ces notions et fournit des exercices pour maîtriser ces concepts.

---

## Décorateurs

Les décorateurs sont des fonctions qui modifient le comportement d'autres fonctions. Ils sont souvent utilisés pour ajouter des fonctionnalités supplémentaires à une fonction existante. Les décorateurs sont définis avec le symbole `@`. 


#### Syntaxe

```python
def decorateur(fonction):
    def wrapper(*args, **kwargs):
        print("Avant l'exécution")
        result = fonction(*args, **kwargs)
        print("Après l'exécution")
        return result
    return wrapper

@decorateur
def dire_bonjour():
    print("Bonjour!")

dire_bonjour()
```

#### Application : Vérifier les Arguments

```python
def verifier_arguments(fonction):
    def wrapper(*args, **kwargs):
        if all(isinstance(arg, int) for arg in args):
            return fonction(*args, **kwargs)
        else:
            raise TypeError("Les arguments doivent être des entiers")
    return wrapper

@verifier_arguments
def addition(a, b):
    return a + b

# Testez avec addition(2, 3)
```

#### Application : Mesurer le Temps d'Exécution

```python
import time

def timer(fonction):
    def wrapper(*args, **kwargs):
        debut = time.time()
        result = fonction(*args, **kwargs)
        fin = time.time()
        print(f"Temps d'exécution: {fin - debut} secondes")
        return result
    return wrapper

@timer
def calcul_lourd():
    time.sleep(2)
    return "Fini!"

calcul_lourd()
```

---

## Générateurs

Les générateurs permettent de produire des données à la demande au lieu de les stocker toutes en mémoire. Ils sont définis avec le mot-clé `yield`.

#### Exemple Simple

```python
def compteur():
    for i in range(5):
        yield i

for nombre in compteur():
    print(nombre)
```

#### Générateurs et Mémoire

Les générateurs sont idéaux pour traiter des flux de données volumineux, comme des fichiers ou des résultats d'une base de données. Ils économisent de la mémoire en produisant des éléments un par un.

**Exemple : Lire un fichier ligne par ligne**

```python
def lire_fichier(fichier):
    with open(fichier, 'r') as f:
        for ligne in f:
            yield ligne.strip()
```

---

## Métaclasses

Les métaclasses contrôlent la création des classes. Elles permettent de modifier dynamiquement le comportement des classes.

#### Exemple de Métaclasse

```python
class Meta(type):
    def __new__(cls, name, bases, dct):
        print(f"Création de la classe {name}")
        return super().__new__(cls, name, bases, dct)

class MaClasse(metaclass=Meta):
    pass
```

**Résultat** : Lors de la création de `MaClasse`, un message s'affiche grâce à la métaclasse.

---

## Concurrence

Python offre plusieurs outils pour gérer la concurrence : les threads, les processus et l'asynchrone.

#### Threads

Les threads permettent d'exécuter plusieurs tâches simultanément dans le même processus.

```python
import threading

def dire_bonjour():
    print("Bonjour!")

thread = threading.Thread(target=dire_bonjour)
thread.start()
thread.join()
```

#### Asynchrone avec `async` et `await`

L'asynchrone est particulièrement utile pour des opérations d'E/S non bloquantes.

```python
import asyncio

async def dire_bonjour():
    await asyncio.sleep(1)
    print("Bonjour!")

asyncio.run(dire_bonjour())
```

---

## Context Managers

Les context managers gèrent les ressources automatiquement, comme l'ouverture et la fermeture de fichiers.

#### Exemple avec `with`

```python
with open('fichier.txt', 'r') as f:
    contenu = f.read()
    print(contenu)
```

#### Créer un Context Manager

```python
class MonContext:
    def __enter__(self):
        print("Entrée dans le contexte")
        return self

    def __exit__(self, exc_type, exc_value, traceback):
        print("Sortie du contexte")

with MonContext() as ctx:
    print("Dans le contexte")
```

---

## Exercices Avancés

#### Exercice 1 : Décorateur pour les Tentatives

Écrivez un décorateur `reessayer` qui tente d'exécuter une fonction jusqu'à 3 fois si une exception est levée.

```python
@reessayer
def division(a, b):
    return a / b

# Testez avec division(1, 0)
```

---

#### Exercice 2 : Générateur de Nombres Premiers

Créez un générateur qui produit les \( n \)-premiers nombres premiers.

**Exemple** :

```python
for nombre in generateur_premiers(10):
    print(nombre)
```

---

#### Exercice 3 : Métaclasse pour Enregistrer les Classes

Créez une métaclasse `Enregistreur` qui garde une trace de toutes les classes créées avec elle.

**Exemple** :

```python
class Enregistreur(type):
    classes = []

    def __new__(cls, name, bases, dct):
        cls.classes.append(name)
        return super().__new__(cls, name, bases, dct)

class MaClasse(metaclass=Enregistreur):
    pass

print(Enregistreur.classes)  # Affiche ["MaClasse"]
```

---

#### Exercice 4 : Gestionnaire de Contexte pour Logger

Créez un gestionnaire de contexte `Logger` qui enregistre automatiquement le début et la fin d'une tâche dans un fichier.

**Exemple** :

```python
with Logger('log.txt') as logger:
    print("Tâche en cours...")
```

---

#### Exercice 5 : Fonction Asynchrone avec Multiples Tâches

Écrivez une fonction asynchrone qui effectue plusieurs requêtes HTTP simulées et affiche les résultats.

**Exemple** :

```python
async def requete_http(url):
    # Simuler une requête
    await asyncio.sleep(1)
    return f"Résultat pour {url}"

urls = ["http://example.com", "http://example.org"]
resultats = asyncio.run(gestion_requetes(urls))
print(resultats)
```

---

## Résumé

| Concept                 | Description                                    |
|-------------------------|------------------------------------------------|
| **Décorateurs**         | Modifier le comportement d'une fonction        |
| **Générateurs**         | Produire des données à la demande              |
| **Métaclasses**         | Contrôler la création des classes              |
| **Concurrence**         | Exécuter plusieurs tâches simultanément        |
| **Context Managers**    | Gérer les ressources automatiquement           |
