---
section: Arduino
nav_order: 9
title: Exercices Complet Arduino
topics: Exercices; Arduino; Correction
---

## **Exercice 1 : Panneau lumineux dynamique avec LEDs et séquences complexes**

### **Partie 1 : Réalisation du schéma sur TinkerCAD**

1. **Objectif**
   Concevoir un circuit sur **TinkerCAD** comprenant 8 LEDs connectées à un Arduino UNO.

2. **Instructions**
   - **Ajoutez les composants nécessaires** :
     - 1 Arduino UNO.
     - 1 breadboard.
     - 8 LEDs (de différentes couleurs si possible).
     - 8 résistances (330Ω chacune).
     - Des câbles pour les connexions.

   - **Réalisez les connexions** :
     1. Connectez les **anodes (pattes longues)** des LEDs aux broches numériques suivantes de l’Arduino :
        - LED 1 → Broche numérique **2**.
        - LED 2 → Broche numérique **3**.
        - LED 3 → Broche numérique **4**.
        - LED 4 → Broche numérique **5**.
        - LED 5 → Broche numérique **6**.
        - LED 6 → Broche numérique **7**.
        - LED 7 → Broche numérique **8**.
        - LED 8 → Broche numérique **9**.
     2. Reliez les **cathodes (pattes courtes)** des LEDs à la **ligne GND** de la breadboard via des résistances de 330Ω.
     3. Reliez la ligne GND de la breadboard au **GND** de l’Arduino.

   - **Validez le montage** :
     Vérifiez que toutes les connexions sont bien réalisées avant de passer à la partie programmation.

---

#### **Partie 2 : Réalisation du code Arduino**

1. **Objectif**
   Écrire un programme Arduino pour allumer les LEDs selon des séquences lumineuses spécifiques.

2. **Instructions**
   - Utilisez le **squelette de code** fourni ci-dessous.
   - Complétez les fonctions pour programmer les trois séquences lumineuses :
     - Séquence 1 : Les LEDs s’allument une par une dans l’ordre.
     - Séquence 2 : Les LEDs s’allument en miroir (de l’extérieur vers l’intérieur).
     - Séquence 3 : Les LEDs clignotent de manière aléatoire.

---

#### **Squelette de code**

```cpp
// Définir un tableau contenant les broches des LEDs
const int leds[] = {2, 3, 4, 5, 6, 7, 8, 9};
const int numLeds = sizeof(leds) / sizeof(leds[0]); // Nombre total de LEDs

void setup() {
  // Initialiser toutes les broches des LEDs comme sorties
  for (int i = 0; i < numLeds; i++) {
    pinMode(leds[i], OUTPUT);
  }
}

void loop() {
  // Appeler les séquences lumineuses
}

// Séquence 1 : LEDs s’allument une par une dans l’ordre
void sequenceOne() {
  // Complétez cette fonction pour allumer chaque LED dans l’ordre.
}

// Séquence 2 : LEDs s’allument en miroir (gauche et droite en même temps)
void sequenceTwo() {
  // Complétez cette fonction pour allumer les LEDs de l'extérieur vers l'intérieur.
}

// Séquence 3 : LEDs clignotent de manière aléatoire
void sequenceThree() {
  // Complétez cette fonction pour allumer des LEDs au hasard.
}
```

---

## **Exercice 2 : Contrôle de la luminosité d’une LED avec un potentiomètre**

### **Partie 1 : Réalisation du schéma sur TinkerCAD**

1. **Objectif**
   Créer un circuit sur **TinkerCAD** permettant de contrôler la luminosité d’une LED à l’aide d’un potentiomètre.

2. **Instructions**
    - **Ajoutez les composants nécessaires** :
      - 1 Arduino UNO.
      - 1 breadboard.
      - 1 LED.
      - 1 potentiomètre.
      - 1 résistance de 220Ω.
      - Des câbles pour les connexions.

    - **Réalisez les connexions** :
        1. Connectez la **patte longue** de la LED à la broche **9** de l’Arduino via une résistance de 220Ω.
        2. Connectez la **patte courte** de la LED à la **ligne GND** de la breadboard.
        3. Connectez le **milieu** du potentiomètre à la **broche analogique A0** de l’Arduino.
        4. Connectez les **deux autres pattes** du potentiomètre à la **ligne 5V** et à la **ligne GND** de la breadboard.

    - **Validez le montage** :
        Vérifiez que toutes les connexions sont correctes avant de passer à la partie programmation.

---

### **Partie 2 : Réalisation du code Arduino**

1. **Objectif**
   Écrire un programme Arduino pour contrôler la luminosité de la LED en fonction de la valeur du potentiomètre.

2. **Instructions**
    - Utilisez le **squelette de code** fourni ci-dessous.
    - Complétez la fonction `controlBrightness()` pour ajuster la luminosité de la LED en fonction de la valeur du potentiomètre.

---

#### **Squelette de code**

```cpp
const int ledPin = 9; // Broche de la LED
const int potPin = A0; // Broche du potentiomètre

void setup() {
  pinMode(ledPin, OUTPUT); // Initialiser la broche de la LED en sortie
}

void loop() {
  controlBrightness(); // Appeler la fonction de contrôle de luminosité
}

void controlBrightness() {
  // Complétez cette fonction pour ajuster la luminosité de la LED
}
```

---

## **Exercice 3 : Simulation d’un feu de circulation avec LEDs RVB**

### **Partie 1 : Réalisation du schéma sur TinkerCAD**

1. **Objectif**
   Concevoir un circuit sur **TinkerCAD** simulant un feu de circulation avec des LEDs RVB.

2. **Instructions**
    - **Ajoutez les composants nécessaires** :
      - 1 Arduino UNO.
      - 1 breadboard.
      - 3 LEDs RVB (rouge, jaune, vert).
      - 3 résistances de 220Ω.
      - Des câbles pour les connexions.

    - **Réalisez les connexions** :
        1. Connectez les **anodes** des LEDs RVB aux broches numériques suivantes de l’Arduino :
            - LED rouge → Broche numérique **9**.
            - LED jaune → Broche numérique **10**.
            - LED vert → Broche numérique **11**.
        2. Reliez les **cathodes** des LEDs RVB à la **ligne GND** de la breadboard via des résistances de 220Ω.
        3. Reliez la ligne GND de la breadboard au **GND** de l’Arduino.

    - **Validez le montage** :
        Assurez-vous que toutes les connexions sont correctes avant de passer à la partie programmation.

---

### **Partie 2 : Réalisation du code Arduino**

1. **Objectif**
   Écrire un programme Arduino pour simuler un feu de circulation avec les LEDs RVB.

2. **Instructions**
    - Utilisez le **squelette de code** fourni ci-dessous.
    - Complétez les fonctions pour programmer les trois états du feu de circulation :
        - État 1 : Feu rouge allumé.
        - État 2 : Feu jaune allumé.
        - État 3 : Feu vert allumé.

---

#### **Squelette de code**

```cpp
const int redPin = 9; // Broche de la LED rouge
const int yellowPin = 10; // Broche de la LED jaune
const int greenPin = 11; // Broche de la LED verte

void setup() {
  pinMode(redPin, OUTPUT); // Initialiser la broche de la LED rouge en sortie
  pinMode(yellowPin, OUTPUT); // Initialiser la broche de la LED jaune en sortie
  pinMode(greenPin, OUTPUT); // Initialiser la broche de la LED verte en sortie
}

void loop() {
  // Appeler les états du feu de circulation
}

// État 1 : Feu rouge allumé
void redLight() {
  // Complétez cette fonction pour allumer la LED rouge et éteindre les autres.
}

// État 2 : Feu jaune allumé
void yellowLight() {
  // Complétez cette fonction pour allumer la LED jaune et éteindre les autres.
}

// État 3 : Feu vert allumé
void greenLight() {
  // Complétez cette fonction pour allumer la LED verte et éteindre les autres.
}
```

