---
section_id: Arduino
nav_order: 2
title: Introduction à Arduino et Tinkercad
topics: Arduino; Tinkercad; Électronique; Programmation
---

## Introduction à Arduino et Tinkercad

Arduino est une plateforme de développement électronique open-source qui permet de créer des projets interactifs en combinant matériel et logiciel. Grâce à sa simplicité, Arduino est utilisé par des débutants en électronique et des experts pour des projets allant de simples montages à des systèmes avancés de domotique, de robotique et de prototypage. Ce cours introduit les bases de l'utilisation d'Arduino avec Tinkercad, un simulateur en ligne qui permet de tester des montages sans matériel.

### Qu'est-ce qu'Arduino ?

Arduino est une plateforme qui repose sur :
1. **Une carte microcontrôleur** (comme l'Arduino Uno) qui exécute des programmes pour interagir avec des composants électroniques (capteurs, LED, moteurs).
2. **Un environnement de développement (IDE)**, où l’on écrit le code pour la carte. Le langage Arduino est basé sur le C/C++ et est simplifié pour une prise en main rapide.

Les cartes Arduino peuvent être programmées pour lire des capteurs (comme la température), envoyer des signaux à des composants (comme des LED), ou même contrôler des objets plus complexes (comme des robots).

### Qu'est-ce que Tinkercad ?

Tinkercad est un outil en ligne gratuit de modélisation 3D et de simulation électronique. Dans Tinkercad, il est possible de :
- Créer et simuler des circuits électroniques avec Arduino sans matériel.
- Programmer Arduino en utilisant le code ou des blocs visuels.
- Visualiser et tester un projet avant de le réaliser en vrai.

**Lien vers Tinkercad** : [tinkercad.com](https://www.tinkercad.com/)

---

## Premier projet avec Arduino et Tinkercad

1. **Créer un compte sur Tinkercad** et accéder à la section "Circuits".
2. **Ajouter une carte Arduino Uno** dans l'espace de travail.
3. **Ajouter une LED** et une résistance (330Ω ou 220Ω).
4. **Connecter la LED** : reliez la patte longue (anode) à une broche numérique (ex. : `D3`) et la patte courte (cathode) à la masse (GND) via la résistance.
5. **Écrire un code simple** pour allumer la LED :
   - Dans la fenêtre de code de Tinkercad, sélectionnez "Code texte" pour écrire le code en C++.

**Exemple de code pour allumer une LED** :

```cpp
void setup() {
  pinMode(3, OUTPUT); // Configure la broche 3 comme sortie
}

void loop() {
  digitalWrite(3, HIGH); // Allume la LED
  delay(1000);           // Pause de 1 seconde
  digitalWrite(3, LOW);  // Éteint la LED
  delay(1000);           // Pause de 1 seconde
}
```

Ce code fait clignoter la LED toutes les secondes.

6. **Simuler le circuit** en cliquant sur "Démarrer la simulation".

### Avantages de Tinkercad pour les débutants

- **Sans matériel** : idéal pour découvrir l'électronique sans investir dans du matériel.
- **Visualisation des circuits** : voir comment connecter des composants et simuler leur comportement.
- **Correction d’erreurs** : le simulateur indique les erreurs de connexion et de code, ce qui est parfait pour apprendre.

---

## Commandes de base utiles en Arduino (mode terminal et gestion)

Arduino comprend certaines commandes de base pour le **moniteur série** (interface de communication) et la **gestion de programmes**.

### Utiliser le Moniteur Série

Le **moniteur série** est un outil de l’IDE Arduino qui affiche les messages envoyés depuis la carte, permettant de visualiser les données en temps réel (comme la lecture d’un capteur) ou d’afficher des informations pour déboguer le code.

**Commandes de base pour le moniteur série** :

1. **Initialiser le moniteur série** :
   ```cpp
   Serial.begin(9600); // Initialise le moniteur série à une vitesse de 9600 bauds
   ```
   - Cette commande est placée dans `setup()` et ouvre la communication série entre l'Arduino et l'ordinateur.

   #### Utilisation de `Serial.begin()` et communication série en Arduino

La commande `Serial.begin()` est essentielle pour utiliser le **moniteur série** en Arduino, un outil qui permet à la carte Arduino de **communiquer avec un ordinateur**. Cette communication série est un canal de dialogue qui permet de **voir des messages** envoyés par Arduino ou de **recevoir des instructions** depuis l'ordinateur.

#### Qu'est-ce que `Serial.begin()` ?

`Serial.begin(vitesse);` est une commande qui initialise la communication série entre Arduino et l'ordinateur. La **vitesse** est indiquée en bauds (ou "baud rate") et définit le nombre de bits transférés par seconde. En général, on utilise une vitesse de **9600 bauds** pour des projets simples, mais d'autres vitesses comme 115200 bauds peuvent être utilisées pour des projets plus rapides.

**Syntaxe :**

```cpp
Serial.begin(9600); // Initialise la communication série à 9600 bauds
```

#### Pourquoi utiliser `Serial.begin()` ?

1. **Pour afficher des messages** : Une fois `Serial.begin()` configuré, vous pouvez envoyer des messages au **moniteur série** de l’IDE Arduino (par exemple, pour afficher des valeurs de capteurs, des états de variables ou des messages de débogage).
2. **Pour tester le code** : Le moniteur série vous permet de vérifier que les variables évoluent comme prévu ou que les conditions se déclenchent correctement.
3. **Pour recevoir des données** : `Serial.begin()` permet aussi de recevoir des informations envoyées par l’ordinateur vers l’Arduino, comme des commandes d’action ou des valeurs de paramètres.

#### Comment fonctionne la communication série ?

Quand `Serial.begin()` est appelée dans le `setup()`, Arduino et l'ordinateur "ouvrent un canal de dialogue". Par exemple, avec `Serial.print()` et `Serial.println()`, on peut envoyer des messages que l’on verra s’afficher dans le moniteur série. C'est comme un "chat" entre l'Arduino et l'ordinateur, mais avec des données et des messages de débogage !

Voici un petit programme qui utilise `Serial.begin()` pour afficher un message toutes les secondes :

```cpp
void setup() {
  Serial.begin(9600); // Initialise la communication série à 9600 bauds
}

void loop() {
  Serial.println("Bonjour, Arduino communique !");
  delay(1000); // Pause de 1 seconde
}
```

#### Explication de la "vitesse" de transmission

La valeur `9600` dans `Serial.begin(9600);` est une fréquence qui indique le nombre de bits échangés chaque seconde, appelée **baud rate**. La vitesse courante de 9600 bauds est généralement suffisante pour transmettre des informations simples (texte, valeurs de capteurs), mais on peut ajuster cette vitesse selon les besoins.


2. **Envoyer un message au moniteur série** :
   ```cpp
   Serial.print("Message");     // Affiche un message sans saut de ligne
   Serial.println("Message");   // Affiche un message avec saut de ligne
   ```
   - `print` affiche le texte sans sauter de ligne, tandis que `println` saute une ligne après le texte.

3. **Lire des données du moniteur série** :
   ```cpp
   if (Serial.available() > 0) { // Vérifie s'il y a des données à lire
     int data = Serial.read();   // Lit un octet de données
   }
   ```
   - Cette commande est utile pour recevoir des informations envoyées depuis l’ordinateur vers Arduino, comme des commandes ou des valeurs de capteurs.

**Exemple d’utilisation** :

```cpp
void setup() {
  Serial.begin(9600); // Initialise le moniteur série
}

void loop() {
  Serial.println("Arduino est prêt !");
  delay(1000); // Affiche le message toutes les secondes
}
```

### Gestion des Délais et Chronométrage

Pour créer des pauses ou vérifier des durées, Arduino propose des commandes spécifiques :

1. **`delay()`** :
   ```cpp
   delay(temps);
   ```
   - Fait une pause en millisecondes, où `temps` est le nombre de millisecondes (ex. : `delay(1000);` pour une pause de 1 seconde).

2. **`millis()`** :
   ```cpp
   unsigned long t = millis();
   ```
   - Retourne le nombre de millisecondes écoulées depuis le démarrage de la carte. Idéal pour chronométrer des durées sans bloquer le programme avec `delay()`.

**Exemple avec `millis()`** :

```cpp
unsigned long previousMillis = 0; // Stocke le temps de la dernière mise à jour
const long interval = 1000;       // Intervalle d'une seconde

void setup() {
  Serial.begin(9600);
}

void loop() {
  unsigned long currentMillis = millis();

  if (currentMillis - previousMillis >= interval) {
    previousMillis = currentMillis;
    Serial.println("Une seconde s'est écoulée");
  }
}
```

### Commandes pour les LEDs et autres composants de base

Ces commandes permettent de contrôler des composants simples comme les LED, les boutons et les capteurs.

1. **`digitalRead()` et `digitalWrite()`** :
   - `digitalRead(pin)` lit l’état (HIGH ou LOW) d’une broche numérique.
   - `digitalWrite(pin, valeur)` définit l’état (HIGH ou LOW) d’une broche numérique configurée en sortie.

2. **`analogRead()` et `analogWrite()`** :
   - `analogRead(pin)` lit une valeur analogique de 0 à 1023 sur une broche analogique (ex. : `A0`).
   - `analogWrite(pin, valeur)` envoie un signal PWM (entre 0 et 255) sur une broche de sortie compatible PWM (ex. : `~3`).

---

### Résumé des commandes de base

| Commande                | Description                                    |
|-------------------------|------------------------------------------------|
| `Serial.begin()`        | Initialise le moniteur série                   |
| `Serial.print()`        | Envoie un message au moniteur série            |
| `Serial.read()`         | Lit les données du moniteur série              |
| `delay()`               | Pause le programme en millisecondes            |
| `millis()`              | Retourne le temps écoulé en millisecondes      |
| `digitalRead()`         | Lit l’état d’une broche numérique              |
| `digitalWrite()`        | Modifie l’état d’une broche numérique          |
| `analogRead()`          | Lit une valeur sur une broche analogique       |
| `analogWrite()`         | Envoie un signal PWM sur une broche            |

---