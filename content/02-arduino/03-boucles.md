---
section: Arduino
nav_order: 4
title: Boucles
topics: Boucles; Arduino; for; while; do-while
---

## Boucles en Arduino

Les boucles permettent d'exécuter un bloc de code plusieurs fois de manière répétitive, ce qui est essentiel pour automatiser des actions en programmation. En Arduino, les boucles les plus courantes sont `for`, `while` et `do-while`.

### Boucle `for`

La boucle `for` est utilisée lorsqu'on sait d'avance combien de fois une action doit être répétée. Elle suit la structure suivante :

```cpp
for (initialisation; condition; incrémentation) {
  // Code à exécuter à chaque itération
}
```

- **initialisation** : initialise une variable de contrôle.
- **condition** : vérifie si la boucle doit continuer.
- **incrémentation** : modifie la variable de contrôle après chaque itération.

### Exemple de boucle `for`

Voici un exemple qui allume et éteint une LED 10 fois :

```cpp
for (int i = 0; i < 10; i++) {
  digitalWrite(LED_BUILTIN, HIGH); // Allume la LED
  delay(500);                       // Pause de 500 ms
  digitalWrite(LED_BUILTIN, LOW);   // Éteint la LED
  delay(500);                       // Pause de 500 ms
}
```

Dans cet exemple, la LED clignote 10 fois, chaque cycle prenant 1 seconde (500 ms allumée, 500 ms éteinte).

### Boucle `while`

La boucle `while` est utilisée lorsqu'on ne sait pas d'avance combien de fois le code doit être exécuté, mais on souhaite continuer tant qu'une condition est vraie.

```cpp
while (condition) {
  // Code à exécuter tant que la condition est vraie
}
```

### Exemple de boucle `while`

Dans cet exemple, une LED continue de clignoter tant qu'un bouton reste enfoncé :

```cpp
while (digitalRead(boutonPin) == HIGH) {
  digitalWrite(LED_BUILTIN, HIGH); // Allume la LED
  delay(500);
  digitalWrite(LED_BUILTIN, LOW);  // Éteint la LED
  delay(500);
}
```

La LED clignote tant que le bouton est pressé.

### Boucle `do-while`

La boucle `do-while` est similaire à `while`, mais le code s'exécute au moins une fois avant de vérifier la condition, ce qui est utile lorsque l'on veut garantir une exécution initiale.

```cpp
do {
  // Code à exécuter au moins une fois
} while (condition);
```

### Exemple de boucle `do-while`

Ici, une LED clignote au moins une fois, puis continue de clignoter si un bouton est enfoncé :

```cpp
do {
  digitalWrite(LED_BUILTIN, HIGH); // Allume la LED
  delay(500);
  digitalWrite(LED_BUILTIN, LOW);  // Éteint la LED
  delay(500);
} while (digitalRead(boutonPin) == HIGH);
```

### Contrôle des boucles avec `break` et `continue`

- **break** : interrompt une boucle et sort immédiatement de celle-ci.
- **continue** : passe immédiatement à l'itération suivante sans exécuter le code restant.

### Exemple avec `break`

Voici un exemple d'utilisation de `break` dans une boucle `for` :

```cpp
for (int i = 0; i < 10; i++) {
  if (digitalRead(boutonPin) == HIGH) {
    break; // Sort de la boucle si le bouton est pressé
  }
  digitalWrite(LED_BUILTIN, HIGH);
  delay(500);
  digitalWrite(LED_BUILTIN, LOW);
  delay(500);
}
```

La boucle se termine si le bouton est pressé.

### Exemple avec `continue`

Dans cet exemple, nous ignorons certaines valeurs dans une boucle :

```cpp
for (int i = 0; i < 10; i++) {
  if (i % 2 == 0) {
    continue; // Passe aux nombres impairs
  }
  Serial.println(i); // Affiche uniquement les nombres impairs
}
```