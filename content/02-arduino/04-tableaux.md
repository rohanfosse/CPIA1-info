---
section: Arduino
nav_order: 5
title: Tableaux
topics: Tableaux; Arduino; Arrays; Indexation
---

Les tableaux sont des structures de données qui permettent de stocker plusieurs valeurs dans une seule variable. En Arduino, un tableau est une séquence de valeurs de même type, accessibles par des indices. Les tableaux sont utiles pour organiser et manipuler des collections de données, comme des lectures de capteurs ou une série de valeurs numériques.

## Déclaration d'un tableau

Pour déclarer un tableau en Arduino, on doit spécifier le type des éléments et la taille (nombre d'éléments) du tableau entre crochets. Voici la structure de base :

```cpp
type nomTableau[taille];
```

Par exemple, pour déclarer un tableau de 5 entiers :

```cpp
int valeurs[5];
```

## Initialisation d'un tableau

On peut initialiser un tableau avec des valeurs prédéfinies au moment de la déclaration :

```cpp
int valeurs[5] = {1, 2, 3, 4, 5};
```

Dans cet exemple, le tableau `valeurs` contient 5 entiers initialisés aux valeurs 1, 2, 3, 4, et 5.

Si la taille du tableau est omise, Arduino la déduit du nombre d'éléments fournis :

```cpp
int valeurs[] = {1, 2, 3, 4, 5}; // Tableau de taille 5
```

## Accès aux éléments d'un tableau

Les éléments d'un tableau sont accessibles par leur **indice**, qui commence à 0. Par exemple, pour accéder au premier élément du tableau `valeurs` :

```cpp
int premier = valeurs[0]; // premier = 1
```

On peut modifier les éléments d'un tableau en utilisant leur indice :

```cpp
valeurs[2] = 10; // Modifie le troisième élément du tableau
```

## Exemple avec une boucle `for`

Les boucles `for` sont souvent utilisées pour parcourir les éléments d'un tableau. Voici un exemple qui affiche tous les éléments du tableau `valeurs` dans le moniteur série :

```cpp
int valeurs[] = {1, 2, 3, 4, 5};

for (int i = 0; i < 5; i++) {
  Serial.println(valeurs[i]);
}
```

## Tableaux de grandes tailles

En Arduino, la mémoire est limitée. Il est donc recommandé de limiter la taille des tableaux et de s'assurer que le nombre d'éléments n'excède pas la capacité de la mémoire disponible. Les types `byte` ou `bool` sont souvent utilisés pour optimiser l'espace lorsque des valeurs plus petites sont suffisantes.

## Exemples pratiques de tableaux

### Stockage de valeurs de capteurs

Voici un exemple où un tableau est utilisé pour stocker les lectures d'un capteur :

```cpp
int lectures[10];

for (int i = 0; i < 10; i++) {
  lectures[i] = analogRead(A0); // Lecture du capteur sur le port A0
  delay(100);
}
```

Dans cet exemple, le tableau `lectures` stocke les 10 dernières valeurs lues du capteur.

### Calcul de la moyenne avec un tableau

On peut utiliser un tableau pour calculer la moyenne de plusieurs lectures de capteurs :

```cpp
int lectures[5] = {10, 20, 30, 40, 50};
int somme = 0;

for (int i = 0; i < 5; i++) {
  somme += lectures[i];
}

int moyenne = somme / 5;
Serial.println(moyenne); // Affiche la moyenne
```
