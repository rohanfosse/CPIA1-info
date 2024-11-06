---
section: Arduino
nav_order: 7
title: Commandes de base Arduino
topics: Commandes; Arduino; Digital; Analogique; Lecture; Écriture
---

Les commandes de base en Arduino permettent de contrôler les composants et d'interagir avec les capteurs. Ce cours présente les principales commandes pour la manipulation des broches numériques et analogiques, les fonctions de base pour configurer les broches, lire des valeurs, écrire des valeurs, et utiliser les délais.

## Configuration des broches avec `pinMode()`

La fonction `pinMode()` est utilisée pour configurer une broche en mode `INPUT` (entrée) ou `OUTPUT` (sortie). La configuration des broches est généralement faite dans la fonction `setup()`.

```cpp
pinMode(numeroBroche, mode);
```

- **numeroBroche** : le numéro de la broche à configurer.
- **mode** : le mode de la broche, soit `INPUT` pour la lecture (par exemple, un capteur) ou `OUTPUT` pour la commande (par exemple, une LED).

**Exemple** :

```cpp
void setup() {
  pinMode(LED_BUILTIN, OUTPUT); // Configure la LED intégrée comme sortie
  pinMode(2, INPUT);             // Configure la broche 2 comme entrée
}
```

## Lecture numérique avec `digitalRead()`

La fonction `digitalRead()` permet de lire l'état d'une broche configurée en `INPUT`. Elle retourne `HIGH` si la broche est à un niveau logique élevé (5V sur la plupart des Arduino) et `LOW` si elle est à un niveau logique bas (0V).

```cpp
int etat = digitalRead(numeroBroche);
```

- **numeroBroche** : le numéro de la broche à lire.

**Exemple** :

```cpp
int boutonPin = 2;
void setup() {
  pinMode(boutonPin, INPUT);
  Serial.begin(9600);
}

void loop() {
  int etatBouton = digitalRead(boutonPin);
  Serial.println(etatBouton);
}
```

Dans cet exemple, l’état du bouton est affiché dans le moniteur série.

## Écriture numérique avec `digitalWrite()`

La fonction `digitalWrite()` permet de définir l'état d'une broche configurée en `OUTPUT`. On peut définir l'état à `HIGH` pour envoyer 5V (ou 3.3V sur certaines cartes) ou `LOW` pour envoyer 0V.

```cpp
digitalWrite(numeroBroche, valeur);
```

- **numeroBroche** : le numéro de la broche à modifier.
- **valeur** : soit `HIGH` (pour allumer par exemple une LED) ou `LOW` (pour l’éteindre).

**Exemple** :

```cpp
int ledPin = LED_BUILTIN;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  digitalWrite(ledPin, HIGH); // Allume la LED
  delay(1000);                // Pause de 1 seconde
  digitalWrite(ledPin, LOW);  // Éteint la LED
  delay(1000);                // Pause de 1 seconde
}
```

Ce code fait clignoter la LED intégrée en l’allumant et l’éteignant chaque seconde.

## Lecture analogique avec `analogRead()`

La fonction `analogRead()` lit la valeur d'une broche analogique (généralement `A0` à `A5` sur Arduino Uno). Elle retourne une valeur entre 0 (0V) et 1023 (5V), permettant de lire des valeurs de capteurs analogiques.

```cpp
int valeur = analogRead(numeroBroche);
```

- **numeroBroche** : le numéro de la broche analogique (par exemple, `A0`).

**Exemple** :

```cpp
int capteurPin = A0;

void setup() {
  Serial.begin(9600);
}

void loop() {
  int valeurCapteur = analogRead(capteurPin);
  Serial.println(valeurCapteur);
  delay(500); // Pause pour éviter de saturer le moniteur série
}
```

Ce code lit la valeur du capteur analogique connecté à `A0` et l'affiche dans le moniteur série.

## Écriture analogique avec `analogWrite()`

La fonction `analogWrite()` permet de simuler une sortie analogique en utilisant le **PWM** (Pulse Width Modulation) sur certaines broches numériques (généralement marquées avec un symbole `~`). La valeur peut être réglée entre 0 (0V) et 255 (5V ou 3.3V).

```cpp
analogWrite(numeroBroche, valeur);
```

- **numeroBroche** : le numéro de la broche avec capacité PWM.
- **valeur** : une valeur entre 0 et 255, où 0 est équivalent à `LOW` et 255 équivalent à `HIGH`.

**Exemple** :

```cpp
int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  analogWrite(ledPin, 128); // LED à 50 % de luminosité
  delay(1000);
  analogWrite(ledPin, 0);   // LED éteinte
  delay(1000);
}
```

Ce code contrôle l'intensité lumineuse d'une LED connectée à la broche `9`.

## Utilisation des délais avec `delay()`

La fonction `delay()` provoque une pause dans l'exécution du programme pour une durée donnée (en millisecondes).

```cpp
delay(duree);
```

- **duree** : la durée de la pause, en millisecondes (1000 ms = 1 seconde).

**Exemple** :

```cpp
void setup() {
  Serial.begin(9600);
}

void loop() {
  Serial.println("Attente de 2 secondes...");
  delay(2000); // Pause de 2 secondes
}
```

## `delayMicroseconds()` pour les pauses courtes

Si des pauses très courtes sont nécessaires, `delayMicroseconds()` permet d’attendre un nombre de microsecondes (1 microseconde = 0,001 milliseconde).

```cpp
delayMicroseconds(dureeMicro);
```

- **dureeMicro** : la durée de la pause en microsecondes.

**Exemple** :

```cpp
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);
  delayMicroseconds(500); // Pause de 500 microsecondes
  digitalWrite(LED_BUILTIN, LOW);
  delayMicroseconds(500);
}
```

Ce code fait clignoter la LED à une fréquence très rapide.

## Résumé des commandes de base

| Commande             | Description                                                   |
|----------------------|---------------------------------------------------------------|
| `pinMode()`          | Configure une broche en entrée ou sortie                      |
| `digitalRead()`      | Lit l’état d’une broche numérique                             |
| `digitalWrite()`     | Modifie l’état d’une broche numérique                         |
| `analogRead()`       | Lit la valeur d’une broche analogique                         |
| `analogWrite()`      | Simule une sortie analogique sur une broche PWM               |
| `delay()`            | Pause en millisecondes                                        |
| `delayMicroseconds()`| Pause en microsecondes                                        |
