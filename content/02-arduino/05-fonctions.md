---
section: Arduino
nav_order: 6
title: Fonctions
topics: Fonctions; Arduino; Déclaration; Paramètres; Valeur de retour
---

Les fonctions sont des blocs de code qui effectuent une tâche spécifique et peuvent être réutilisés plusieurs fois dans un programme. Utiliser des fonctions permet d'organiser le code, de le rendre plus lisible et d'éviter la répétition de blocs identiques. En Arduino, comme dans d'autres langages, on peut créer ses propres fonctions en plus des fonctions `setup()` et `loop()` qui sont exécutées par défaut dans chaque programme Arduino.

## Structure de base d'une fonction

Une fonction est définie par :
- **le type de retour** (le type de donnée que la fonction renvoie, comme `int`, `float`, `void` si elle ne renvoie rien),
- **le nom de la fonction**,
- **les paramètres** (des variables qui reçoivent des valeurs lorsque la fonction est appelée, entre parenthèses),
- **le corps de la fonction** (le code à exécuter, entre accolades `{}`).

Voici la structure de base d’une fonction en Arduino :

```cpp
type_retour nomFonction(parametres) {
  // Code à exécuter
  return valeur; // Optionnel, seulement si la fonction renvoie un résultat
}
```

Par exemple, une fonction qui additionne deux nombres entiers :

```cpp
int addition(int a, int b) {
  int resultat = a + b;
  return resultat;
}
```

Ici, la fonction `addition` prend deux entiers `a` et `b`, additionne leurs valeurs et renvoie le résultat.

## Appeler une fonction

Pour utiliser une fonction, il suffit de l'appeler par son nom et de lui fournir des **arguments** (les valeurs pour ses paramètres) :

```cpp
int somme = addition(5, 10); // Appel de la fonction addition avec 5 et 10 comme arguments
```

Dans cet exemple, la fonction `addition` renvoie la valeur `15`, qui est stockée dans la variable `somme`.

## Exemple de fonction sans valeur de retour (`void`)

Une fonction peut aussi ne rien renvoyer. Dans ce cas, le type de retour est `void`, ce qui signifie "aucune valeur de retour". Voici un exemple :

```cpp
void allumerLED() {
  digitalWrite(LED_BUILTIN, HIGH); // Allume la LED
}
```

Cette fonction `allumerLED` allume simplement la LED intégrée. Elle n’a pas de paramètres et ne renvoie aucune valeur.

Pour appeler cette fonction :

```cpp
allumerLED(); // Appelle la fonction pour allumer la LED
```

## Fonctions avec paramètres

Les paramètres permettent de rendre une fonction plus flexible en lui permettant de recevoir des informations différentes à chaque appel. Par exemple :

```cpp
void allumerLED(int delai) {
  digitalWrite(LED_BUILTIN, HIGH);
  delay(delai); // Attendre le nombre de millisecondes donné en paramètre
  digitalWrite(LED_BUILTIN, LOW);
}
```

Ici, `delai` est un paramètre de type `int` qui indique combien de temps la LED doit rester allumée. On peut maintenant contrôler la durée d’allumage de la LED à chaque appel :

```cpp
allumerLED(1000); // Allume la LED pendant 1 seconde
allumerLED(500);  // Allume la LED pendant 0,5 seconde
```

## Exemple pratique : fonction de calcul

Supposons que nous ayons besoin de calculer la moyenne de trois lectures de capteur. Nous pouvons écrire une fonction qui facilite ce calcul :

```cpp
float calculerMoyenne(int valeur1, int valeur2, int valeur3) {
  float moyenne = (valeur1 + valeur2 + valeur3) / 3.0;
  return moyenne;
}
```

Pour appeler cette fonction, on passe trois valeurs :

```cpp
int lecture1 = analogRead(A0);
int lecture2 = analogRead(A1);
int lecture3 = analogRead(A2);
float moyenne = calculerMoyenne(lecture1, lecture2, lecture3);
Serial.println(moyenne); // Affiche la moyenne des trois lectures
```

## Pourquoi utiliser des fonctions ?

Les fonctions sont très utiles en Arduino pour :
- **Éviter la répétition** : Si vous devez exécuter le même bloc de code plusieurs fois, une fonction rend votre code plus propre et plus court.
- **Organiser le code** : Avec des fonctions bien nommées, il est plus facile de comprendre ce que chaque partie du programme fait.
- **Faciliter le débogage** : Lorsqu'un problème survient, il est plus simple de tester une fonction isolément que de vérifier tout le programme.

## Exemple : Fonctions pour clignoter une LED

Créons deux fonctions pour contrôler le clignotement d’une LED : une pour allumer la LED et une pour l’éteindre après un délai spécifié.

```cpp
void clignoterLED(int delai) {
  allumerLED();
  delay(delai);
  eteindreLED();
  delay(delai);
}

void allumerLED() {
  digitalWrite(LED_BUILTIN, HIGH);
}

void eteindreLED() {
  digitalWrite(LED_BUILTIN, LOW);
}
```

Ensuite, dans la fonction `loop`, on peut appeler `clignoterLED` :

```cpp
void loop() {
  clignoterLED(1000); // Clignote la LED avec un délai de 1 seconde
}
```