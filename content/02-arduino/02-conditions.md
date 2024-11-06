---
section_id: Arduino
nav_order: 3
title: Conditions
topics: Conditions; Arduino; if; else; switch
---

## Conditions en Arduino

Les conditions permettent de contrôler le flux d'exécution d'un programme en fonction de certaines conditions ou valeurs. En Arduino, les conditions sont principalement utilisées avec les instructions `if`, `else if`, `else` et `switch`. Ces instructions permettent d'exécuter du code uniquement si certaines conditions sont remplies.

### Structure de base des conditions

La structure de base d'une condition `if` en Arduino est la suivante :

```cpp
if (condition) {
  // Code à exécuter si la condition est vraie
}
```

Pour ajouter des options supplémentaires, on peut utiliser `else if` et `else` :

```cpp
if (condition1) {
  // Code si condition1 est vraie
} else if (condition2) {
  // Code si condition1 est fausse et condition2 est vraie
} else {
  // Code si toutes les conditions précédentes sont fausses
}
```

### Exemple de condition `if`

Voici un exemple d'utilisation d'une condition `if` en Arduino :

```cpp
int temperature = 25;

if (temperature > 30) {
  // Si la température est supérieure à 30, allumer le ventilateur
  digitalWrite(ventilateur, HIGH);
} else {
  // Sinon, éteindre le ventilateur
  digitalWrite(ventilateur, LOW);
}
```

Dans cet exemple, le ventilateur s'allume seulement si la température dépasse 30.

### Conditions avec `switch`

L'instruction `switch` est utilisée pour tester la valeur d'une variable contre plusieurs cas possibles. C'est une alternative efficace à plusieurs conditions `if` quand on doit comparer une variable à de nombreuses valeurs spécifiques.

Voici la structure de base d'un `switch` en Arduino :

```cpp
switch (variable) {
  case valeur1:
    // Code si variable == valeur1
    break;
  case valeur2:
    // Code si variable == valeur2
    break;
  default:
    // Code si aucun des cas précédents n'est satisfait
    break;
}
```

### Exemple de condition `switch`

Supposons que nous ayons une variable `mode` qui peut prendre plusieurs valeurs :

```cpp
int mode = 2;

switch (mode) {
  case 1:
    // Mode 1 : allumer LED1
    digitalWrite(LED1, HIGH);
    break;
  case 2:
    // Mode 2 : allumer LED2
    digitalWrite(LED2, HIGH);
    break;
  default:
    // Autres cas : éteindre toutes les LED
    digitalWrite(LED1, LOW);
    digitalWrite(LED2, LOW);
    break;
}
```

Dans cet exemple, la LED correspondante s'allume selon la valeur de `mode`.

## Opérateurs de comparaison et logiques

Les conditions utilisent des opérateurs de comparaison et logiques pour évaluer les expressions. Voici un tableau des opérateurs les plus courants :

| Opérateur     | Signification               |
|---------------|-----------------------------|
| `==`          | Égal à                      |
| `!=`          | Différent de                |
| `>`           | Supérieur à                 |
| `<`           | Inférieur à                 |
| `>=`          | Supérieur ou égal à         |
| `<=`          | Inférieur ou égal à         |
| `&&`          | ET logique                  |
| `||`          | OU logique                  |
| `!`           | NON logique (négation)      |

Par exemple, pour tester si une variable `x` est entre 10 et 20 :

```cpp
if (x > 10 && x < 20) {
  // Code à exécuter si x est entre 10 et 20
}
```

### Exemple avec plusieurs conditions

Voici un exemple qui utilise plusieurs conditions logiques pour allumer une LED uniquement si deux conditions sont vraies :

```cpp
int temperature = 28;
int humidite = 70;

if (temperature > 25 && humidite > 60) {
  // Allumer la LED si la température est supérieure à 25 et l'humidité supérieure à 60
  digitalWrite(LED, HIGH);
} else {
  // Éteindre la LED sinon
  digitalWrite(LED, LOW);
}
```

Dans cet exemple, la LED s'allume seulement si les deux conditions sont vraies.

## Utilisation des variables booléennes

Les variables de type `bool` peuvent être utilisées pour simplifier les conditions complexes. Par exemple :

```cpp
bool estChaud = temperature > 25;
bool estHumide = humidite > 60;

if (estChaud && estHumide) {
  digitalWrite(LED, HIGH);
} else {
  digitalWrite(LED, LOW);
}
```

Dans cet exemple, les variables `estChaud` et `estHumide` facilitent la compréhension de la condition.