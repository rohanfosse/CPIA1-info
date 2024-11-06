---
section_id: Arduino
nav_order: 1
title: Variables
topics: Variables; Arduino; Types; Declaration
---


## Declaration des variables en Arduino

Les variables sont des espaces de mémoire qui stockent des valeurs. En Arduino, les variables sont déclarées en fonction de leur type et de leur nom. Les types de variables les plus courants sont les entiers, les décimaux et les caractères.

Voici un tableau récapitulatif des types de variables les plus courants en Arduino :

| Nom (Français) | Nom (Arduino) |
|----------------|---------------|
| Entier         | int           |
| Décimal        | float         |
| Caractère      | char          |
| Booléen        | bool          |
|----------------|---------------|

En Arduino, les variables sont déclarées en fonction de leur type et de leur nom. Voici un exemple de déclaration de variables en Arduino :

```cpp
int entier = 10;
float decimal = 3.14;
char caractere = 'A';
bool booleen = true;
```

Dans cet exemple, nous avons déclaré quatre variables de types différents : un entier, un décimal, un caractère et un booléen. Chaque variable est initialisée avec une valeur spécifique. Les variables peuvent être modifiées à tout moment en leur attribuant une nouvelle valeur. Par exemple :

```cpp
entier = 20;
decimal = 6.28;
caractere = 'B';
booleen = false;
```

Il est important de noter que les variables en Arduino sont sensibles à la casse, c'est-à-dire qu'elles doivent être écrites exactement de la même manière à chaque fois que vous les utilisez. Par exemple, les variables `entier`, `Entier` et `ENTIER` sont considérées comme trois variables différentes en Arduino.

De plus, les noms de variables en Arduino doivent commencer par une lettre (a-z, A-Z) ou un trait de soulignement (_) et ne peuvent pas contenir d'espaces ou de caractères spéciaux (à l'exception du trait de soulignement). Les noms de variables en Arduino sont également limités à 31 caractères.

Enfin, il est important de noter que les variables en Arduino ont une portée locale par défaut, ce qui signifie qu'elles ne sont accessibles que dans la fonction dans laquelle elles sont déclarées. Si vous souhaitez qu'une variable soit accessible dans plusieurs fonctions, vous devez la déclarer en tant que variable globale en dehors de toute fonction. Par exemple :

```cpp
int entier_global;

void setup() {
  entier_global = 10;
}

void loop() {
  // Utiliser la variable globale ici
}
```

## Opérations sur les variables

Les variables en Arduino peuvent être utilisées dans des opérations mathématiques telles que l'addition, la soustraction, la multiplication et la division. Voici un exemple d'opérations sur les variables en Arduino :

```cpp
int a = 10;
int b = 5;
int c;

c = a + b; // Addition
c = a - b; // Soustraction
c = a * b; // Multiplication
c = a / b; // Division
```

### Incrémentation et décrémentation

En Arduino, il est possible d'incrémenter, c'est à dire d'ajouter 1 à une variable, ou de décrémenter, c'est à dire de soustraire 1 à une variable. Voici un exemple d'incrémentation et de décrémentation en Arduino :

```cpp
int a = 10;

a++; // Incrémentation
a--; // Décrémentation
```

Dans cet exemple, la variable `a` est incrémentée de 1, puis décrémentée de 1.
