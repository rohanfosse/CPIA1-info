---
section: Arduino
nav_order: 7
title: Exercices Corrigés
topics: Exercices; Arduino; Correction
---

### Exercice 1 : Manipulation de variables

**Objectif** : Se familiariser avec les types de variables et leur manipulation.

1. Déclarez une variable `temperature` de type `int` et affectez-lui la valeur `25`.
2. Déclarez une variable `humidite` de type `float` et affectez-lui la valeur `60.5`.
3. Affichez les valeurs de `temperature` et `humidite` dans le moniteur série.
4. Modifiez les valeurs de `temperature` et `humidite` à `30` et `55.0` respectivement, et affichez-les à nouveau dans le moniteur série.

**Correction** :

```cpp
void setup() {
  Serial.begin(9600);
  
  int temperature = 25;
  float humidite = 60.5;
  
  Serial.print("Temperature: ");
  Serial.println(temperature);
  Serial.print("Humidite: ");
  Serial.println(humidite);
  
  temperature = 30;
  humidite = 55.0;
  
  Serial.print("Temperature mise a jour: ");
  Serial.println(temperature);
  Serial.print("Humidite mise a jour: ");
  Serial.println(humidite);
}

void loop() {
  // Rien ici pour cet exercice
}
```

---

### Exercice 2 : Condition simple pour contrôler une LED

**Objectif** : Utiliser une condition pour allumer ou éteindre une LED en fonction d’une variable.

1. Déclarez une variable `luminosite` de type `int` et affectez-lui une valeur.
2. Si la `luminosite` est supérieure à `50`, allumez la LED intégrée, sinon éteignez-la.

**Correction** :

```cpp
void setup() {
  pinMode(LED_BUILTIN, OUTPUT);
  int luminosite = 30;

  if (luminosite > 50) {
    digitalWrite(LED_BUILTIN, HIGH); // Allume la LED
  } else {
    digitalWrite(LED_BUILTIN, LOW); // Éteint la LED
  }
}

void loop() {
  // Rien ici pour cet exercice
}
```

---

### Exercice 3 : Boucle pour faire clignoter une LED

**Objectif** : Utiliser une boucle pour faire clignoter la LED plusieurs fois.

1. Utilisez une boucle `for` pour faire clignoter la LED intégrée 5 fois, avec une pause d'une seconde entre chaque allumage/extinction.

**Correction** :

```cpp
void setup() {
  pinMode(LED_BUILTIN, OUTPUT);
  
  for (int i = 0; i < 5; i++) {
    digitalWrite(LED_BUILTIN, HIGH);
    delay(1000);
    digitalWrite(LED_BUILTIN, LOW);
    delay(1000);
  }
}

void loop() {
  // Rien ici pour cet exercice
}
```

---

### Exercice 4 : Stocker des valeurs de capteur dans un tableau

**Objectif** : Utiliser un tableau pour stocker des lectures de capteur.

1. Déclarez un tableau de `10` entiers appelé `lectures`.
2. Dans `setup()`, remplissez chaque élément du tableau avec la lecture du capteur analogique `A0`.
3. Affichez chaque valeur dans le moniteur série.

**Correction** :

```cpp
int lectures[10];

void setup() {
  Serial.begin(9600);
  
  for (int i = 0; i < 10; i++) {
    lectures[i] = analogRead(A0); // Lecture du capteur
    Serial.print("Lecture ");
    Serial.print(i);
    Serial.print(": ");
    Serial.println(lectures[i]);
    delay(500); // Pause pour chaque lecture
  }
}

void loop() {
  // Rien ici pour cet exercice
}
```

---

### Exercice 5 : Calculer la moyenne des valeurs dans un tableau

**Objectif** : Calculer la moyenne des lectures dans un tableau.

1. Utilisez le tableau `lectures` de l'exercice précédent.
2. Créez une fonction `calculerMoyenne` qui prend un tableau et sa taille en paramètres et retourne la moyenne des valeurs.
3. Affichez la moyenne dans le moniteur série.

**Correction** :

```cpp
int lectures[10];

void setup() {
  Serial.begin(9600);
  
  for (int i = 0; i < 10; i++) {
    lectures[i] = analogRead(A0);
    delay(500);
  }

  float moyenne = calculerMoyenne(lectures, 10);
  Serial.print("Moyenne: ");
  Serial.println(moyenne);
}

void loop() {
  // Rien ici pour cet exercice
}

float calculerMoyenne(int tableau[], int taille) {
  int somme = 0;
  for (int i = 0; i < taille; i++) {
    somme += tableau[i];
  }
  return (float)somme / taille;
}
```

---

### Exercice 6 : Clignotement avec une fonction personnalisée

**Objectif** : Créer une fonction pour clignoter une LED avec un délai variable.

1. Créez une fonction `clignoterLED` qui prend un paramètre `delai`.
2. La fonction allume et éteint la LED avec ce délai.
3. Appelez `clignoterLED` dans `loop()` avec différents délais.

**Correction** :

```cpp
void setup() {
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop() {
  clignoterLED(500);
  delay(1000);
  clignoterLED(100);
  delay(1000);
}

void clignoterLED(int delai) {
  digitalWrite(LED_BUILTIN, HIGH);
  delay(delai);
  digitalWrite(LED_BUILTIN, LOW);
  delay(delai);
}
```

---

### Exercice 7 : Mesurer et comparer les lectures de capteur

**Objectif** : Utiliser une condition pour analyser plusieurs lectures d’un capteur.

1. Lisez les valeurs de deux capteurs analogiques `A0` et `A1`.
2. Comparez les valeurs et allumez la LED intégrée si `A0` est supérieur à `A1`.
3. Si `A1` est supérieur, affichez "A1 est plus grand" dans le moniteur série.

**Correction** :

```cpp
void setup() {
  Serial.begin(9600);
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop() {
  int lectureA0 = analogRead(A0);
  int lectureA1 = analogRead(A1);

  if (lectureA0 > lectureA1) {
    digitalWrite(LED_BUILTIN, HIGH);
  } else {
    digitalWrite(LED_BUILTIN, LOW);
    Serial.println("A1 est plus grand");
  }

  delay(1000);
}
```

---

### Exercice 8 : Contrôler une LED avec un bouton et des fonctions

**Objectif** : Créer une fonction pour vérifier l’état d’un bouton et contrôler la LED.

1. Connectez un bouton au pin `2` de l’Arduino.
2. Créez une fonction `etatBouton` qui lit le bouton et retourne `true` si le bouton est appuyé.
3. Utilisez cette fonction dans `loop()` pour allumer ou éteindre la LED en fonction de l’état du bouton.

**Correction** :

```cpp
const int boutonPin = 2;
const int ledPin = LED_BUILTIN;

void setup() {
  pinMode(boutonPin, INPUT);
  pinMode(ledPin, OUTPUT);
}

void loop() {
  if (etatBouton()) {
    digitalWrite(ledPin, HIGH);
  } else {
    digitalWrite(ledPin, LOW);
  }
}

bool etatBouton() {
  return digitalRead(boutonPin) == HIGH;
}
```