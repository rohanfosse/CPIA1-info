---
section: Arduino
nav_order: 10
title: Cheat Sheet Arduino
topics: Exercices; Arduino; Correction
---

### 1. Structure de base

```cpp
void setup() {
  // Code exécuté une seule fois au démarrage
}

void loop() {
  // Code exécuté en boucle
}
```

---

### 2. Fonctions de base

#### Configurer une broche

```cpp
pinMode(pin, mode);
```

- `pin` : Numéro de la broche (ex : 2, 3, 13).
- `mode` : `OUTPUT` (sortie) ou `INPUT` (entrée).

#### Écrire une valeur sur une broche

```cpp
digitalWrite(pin, value);
```

- `value` : `HIGH` (5V) ou `LOW` (0V).

#### Lire une valeur numérique sur une broche

```cpp
int value = digitalRead(pin);
```

- Retourne `HIGH` ou `LOW`.

#### Lire une valeur analogique

```cpp
int value = analogRead(pin);
```

- Retourne une valeur entre 0 et 1023.

#### Écrire une valeur analogique (PWM)

```cpp
analogWrite(pin, value);
```

- `value` : Entre 0 (0%) et 255 (100%) (nécessite une broche PWM).

---

### 3. Types de données

| Type      | Taille   | Plage                           |
| --------- | -------- | ------------------------------- |
| `int`     | 2 octets | -32,768 à 32,767                |
| `float`   | 4 octets | ±3.4028235E+38 (7 chiffres max) |
| `boolean` | 1 bit    | `true` ou `false`               |
| `char`    | 1 octet  | -128 à 127 (ou un caractère)    |
| `byte`    | 1 octet  | 0 à 255                         |
| `long`    | 4 octets | -2,147,483,648 à 2,147,483,647  |

---

### 4. Fonctions de contrôle

#### Delai

```cpp
delay(ms);
```

- Pause le programme pendant `ms` millisecondes.

#### Delai sans bloquer

```cpp
unsigned long previousMillis = 0;

void loop() {
  unsigned long currentMillis = millis();
  if (currentMillis - previousMillis >= interval) {
    previousMillis = currentMillis;
    // Action à réaliser
  }
}
```

#### Boucles

```cpp
for (int i = 0; i < 10; i++) {
  // Répéter 10 fois
}

while (condition) {
  // Répéter tant que la condition est vraie
}
```

#### Conditions

```cpp
if (condition) {
  // Exécuter si condition vraie
} else {
  // Sinon
}

switch (variable) {
  case valeur1:
    // Code
    break;
  case valeur2:
    // Code
    break;
  default:
    // Code par défaut
}
```

---

### 5. Fonctions utiles

#### Générer un nombre aléatoire

```cpp
randomSeed(analogRead(A0)); // Initialisation
int r = random(min, max);   // Min inclus, max exclu
```

#### Mapper une valeur

```cpp
long mappedValue = map(value, fromLow, fromHigh, toLow, toHigh);
```

- Convertit `value` d'une plage [fromLow, fromHigh] à [toLow, toHigh].

#### Conversion analogique-numérique

```cpp
int digitalValue = (analogValue > seuil) ? HIGH : LOW;
```

---

### 6. Entrées et sorties

#### Bouton poussoir

```cpp
const int buttonPin = 2;
int buttonState;

void setup() {
  pinMode(buttonPin, INPUT);
}

void loop() {
  buttonState = digitalRead(buttonPin);
  if (buttonState == HIGH) {
    // Action si bouton pressé
  }
}
```

#### PWM pour LED

```cpp
const int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  for (int brightness = 0; brightness <= 255; brightness++) {
    analogWrite(ledPin, brightness); // Augmente la luminosité
    delay(10);
  }
  for (int brightness = 255; brightness >= 0; brightness--) {
    analogWrite(ledPin, brightness); // Diminue la luminosité
    delay(10);
  }
}
```

---

### 7. Communication série

#### Initialisation

```cpp
Serial.begin(9600); // Démarre la communication à 9600 bauds
```

#### Envoyer des données

```cpp
Serial.print("Message");  // Affiche sans saut de ligne
Serial.println("Message"); // Affiche avec saut de ligne
```

#### Lire des données

```cpp
if (Serial.available() > 0) {
  int data = Serial.read(); // Lit un caractère
}
```

---

### 8. Capteurs

#### Capteur de température LM35

```cpp
const int tempPin = A0;

void setup() {
  Serial.begin(9600);
}

void loop() {
  int value = analogRead(tempPin);
  float voltage = value * (5.0 / 1023.0); // Conversion en tension
  float temperature = voltage * 100.0;   // Conversion en °C
  Serial.println(temperature);
  delay(1000);
}
```

#### Capteur ultrason HC-SR04

```cpp
const int trigPin = 9;
const int echoPin = 10;

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  Serial.begin(9600);
}

void loop() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  long duration = pulseIn(echoPin, HIGH);
  float distance = (duration * 0.034) / 2; // Distance en cm
  Serial.println(distance);
  delay(500);
}
```

---

### 9. Débogage

- Ajoutez des messages pour vérifier les étapes :

```cpp
Serial.println("Entrée dans la boucle");
Serial.print("Valeur : ");
Serial.println(value);
```

---

### 10. Bonnes pratiques

1. Commentez votre code pour expliquer son fonctionnement.
2. Évitez les délais longs avec `delay()` si possible.
3. Testez étape par étape, surtout dans des projets complexes.
4. Organisez votre code en fonctions pour plus de lisibilité.

---

### 11. Liens utiles

- [Site officiel Arduino](https://www.arduino.cc/)
- [Tutoriels Arduino](https://www.arduino.cc/en/Tutorial)
