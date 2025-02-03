---
title: "CCTLs Signal - Modulation, Démodulation et Codage des Signaux"
layout: lesson-content
permalink: /CCTL-signal.html
---

## Définitions

Avant d’aborder les concepts de modulation et de codage, il est essentiel de définir quelques notions clés :

- **Signal** : Une grandeur physique variant en fonction du temps, utilisée pour transmettre de l'information. Les signaux peuvent être électriques, acoustiques ou optiques.
- **Signal analogique** : Signal continu dans le temps et dans l’amplitude, souvent représenté par une fonction sinusoïdale. Exemple : une onde sonore avec une fréquence de 1 kHz et une amplitude de 2 V.
- **Signal numérique** : Signal discret, prenant un nombre fini de valeurs. Exemple : un signal binaire avec des niveaux 0V et 5V.
- **Fréquence (\( f \))** : Nombre d’oscillations par seconde d’un signal périodique, exprimée en Hertz (Hz). Exemple : la fréquence du secteur électrique est de 50 Hz en Europe.
- **Amplitude** : Hauteur du signal, représentant l’intensité de l’onde. Exemple : un signal radio avec une amplitude de 10 mV.
- **Phase (\( \phi \))** : Décalage temporel d’un signal par rapport à une référence. Exemple : deux signaux sinusoïdaux en quadrature de phase sont décalés de 90°.
- **Bande passante** : Plage de fréquences qu’un signal peut occuper. Exemple : une connexion Wi-Fi utilise une bande passante de 20 MHz.
- **Modulation** : Technique consistant à modifier un signal porteur pour transmettre de l’information. Exemple : la radio FM (modulation de fréquence) utilise une porteuse de 100 MHz.
- **Démodulation** : Procédé inverse permettant d’extraire l’information du signal modulé. Exemple : un récepteur radio récupère la voix transmise en AM.
- **Codage** : Représentation des données pour faciliter leur transmission ou stockage. Exemple : le code ASCII pour la transmission de texte.
- **Décodage** : Récupération des données originales après transmission. Exemple : un fichier audio MP3 est décodé avant lecture.

---

## Modulation et Démodulation

### Définition

La **modulation** est le processus qui consiste à modifier un signal porteur (une onde sinusoïdale) en fonction des informations à transmettre. Elle permet d’adapter le signal aux caractéristiques du canal de transmission, en augmentant la portée et en minimisant les interférences. La **démodulation** est l’opération inverse permettant d’extraire l’information originale du signal modulé.

Mathématiquement, un signal modulé peut être représenté par :

\[ s(t) = A(t) \sin(2 \pi f_c t + \phi(t)) \]

où :

- \( A(t) \) est l’amplitude du signal modulant,
- \( f_c \) est la fréquence de la porteuse,
- \( \phi(t) \) est la phase du signal modulant.

Le choix de la modulation dépend de plusieurs facteurs :

- **La bande passante disponible** : certaines modulations nécessitent plus de spectre que d'autres.
- **La robustesse aux interférences** : certains environnements sont plus bruités que d'autres.
- **L'efficacité énergétique** : certaines techniques de modulation nécessitent plus de puissance pour être correctement interprétées à la réception.

### Types de modulation

Il existe trois principaux types de modulation :

#### Modulation d'Amplitude (AM)

La modulation d’amplitude est une technique de modulation dans laquelle l’amplitude du signal porteur est modifiée en fonction du signal modulant. C’est la technique la plus simple de modulation.

- **Principe** : L’amplitude du signal porteur varie en fonction du signal modulant.
- **Équation mathématique** :

  \[ s\_{AM}(t) = [1 + m \sin(2 \pi f_m t)] \sin(2 \pi f_c t) \]

  où \( m \) est l’indice de modulation et \( f_m \) la fréquence du signal modulant.

- **Avantages** : Simple à implémenter, utilisé en radiodiffusion.
- **Inconvénients** : Sensible aux interférences et inefficace en termes de puissance.
- **Exemple** : La radio AM fonctionne avec une fréquence porteuse de 1 MHz et une largeur de bande de 10 kHz.

#### Modulation de Fréquence (FM)

La modulation de fréquence est une technique de modulation dans laquelle la fréquence du signal porteur est modifiée en fonction du signal modulant. La fréquence du signal modulé est directement proportionnelle à l'amplitude du signal modulant.

- **Principe** : La fréquence du signal porteur est modifiée selon le signal d’entrée.
- **Équation mathématique** :

  \[ s\_{FM}(t) = A \sin(2 \pi f_c t + \beta \sin(2 \pi f_m t)) \]

  où \( \beta \) est l’indice de modulation FM.

- **Avantages** : Meilleure résistance aux interférences que l’AM.
- **Inconvénients** : Nécessite une plus grande bande passante.
- **Exemple** : La radio FM utilise des fréquences comprises entre 88 et 108 MHz.

#### Modulation de Phase (PM)

La modulation de phase est une technique de modulation dans laquelle la phase du signal porteur est modifiée en fonction du signal modulant. Elle est souvent utilisée en communications numériques pour transmettre des données binaires.

- **Principe** : La phase du signal porteur est modifiée proportionnellement au signal modulant.
- **Équation mathématique** :

  \[ s\_{PM}(t) = A \sin(2 \pi f_c t + k_p m(t)) \]

  où \( k_p \) est un coefficient de modulation en phase.

- **Avantages** : Utilisé en communications numériques (QPSK, PSK, etc.).
- **Inconvénients** : Plus complexe à mettre en œuvre.
- **Exemple** : Le Wi-Fi utilise la modulation PSK (Phase Shift Keying) pour transmettre les données.

---

## Codage et Décodage des Signaux

Le **codage des signaux** est un processus essentiel en télécommunications et en informatique permettant de représenter l'information de manière efficace et fiable. Le codage vise à convertir les données sous une forme adaptée à la transmission et à la réception, en réduisant les erreurs et en optimisant l’utilisation du spectre disponible.

Ce cours aborde les principes du codage en transmission numérique et détaille deux méthodes fondamentales : **le codage NRZ (Non-Return-to-Zero)** et **le codage Manchester**.

---

### Principes du Codage en Transmission Numérique

Le codage des signaux binaires vise principalement à :

- **Garantir la transmission correcte des données** en minimisant les erreurs.
- **Faciliter la récupération de l’horloge** en assurant une synchronisation fiable.
- **Optimiser l'utilisation du spectre** et réduire la consommation d’énergie.

Il existe plusieurs types de codages en transmission numérique, parmi lesquels :

- **Codage unipolaire et bipolaire**.
- **Codage en bande de base** (NRZ, NRZI, Manchester, etc.).
- **Codage en modulation** (ASK, FSK, PSK).

Nous allons étudier en détail **le NRZ et le Manchester**, qui sont couramment utilisés dans les communications numériques.

---

### Codage NRZ (Non-Return-to-Zero)

#### Définition

Le **codage NRZ** est une technique simple où les niveaux logiques sont directement représentés par un signal binaire.

- **NRZ-L (Non-Return-to-Zero Level)** : Le niveau de tension est constant pour chaque bit.
  - `1` → Niveau haut (ex : +5V).
  - `0` → Niveau bas (ex : 0V).
- **NRZI (Non-Return-to-Zero Inverted)** : Un changement d’état du signal indique un `1`, alors qu’une absence de changement indique un `0`.

#### Exemple réel

Le codage NRZ est souvent utilisé dans les connexions USB et RS-232.

#### Exemple : Transmission d’un signal binaire `1011001` en NRZ-L

| Bit transmis | 1   | 0   | 1   | 1   | 0   | 0   | 1   |
| ------------ | --- | --- | --- | --- | --- | --- | --- |
| Signal NRZ   | H   | L   | H   | H   | L   | L   | H   |

#### Implémentation en Python

```python
# Fonction d'encodage NRZ
def encode_nrz(data):
    encoded = []
    for bit in data:
        encoded.append(1 if bit == '1' else 0)
    return encoded

# Fonction de décodage NRZ
def decode_nrz(encoded_data):
    decoded = ''
    for bit in encoded_data:
        decoded += '1' if bit == 1 else '0'
    return decoded

# Exemple d'utilisation
data = "1011001"
nrz_signal = encode_nrz(data)
decoded_data = decode_nrz(nrz_signal)
print("Signal NRZ encodé:", nrz_signal)
print("Données décodées:", decoded_data)
```

---

### Codage Manchester

#### Définition

Le **codage Manchester** est une méthode qui garantit une transition à chaque bit transmis, ce qui facilite la synchronisation.

- **Manchester IEEE 802.3 (Ethernet)** :
  - `1` → Transition bas → haut.
  - `0` → Transition haut → bas.
- **Manchester différentiel** :
  - `1` → Pas de transition au début du bit, transition au milieu.
  - `0` → Transition au début du bit, transition au milieu.

#### 4.2. Exemple réel

Le codage Manchester est utilisé dans **les réseaux Ethernet** et dans certaines **cartes à puce**.

##### Exemple : Transmission de `1011001` en Manchester IEEE 802.3

| Bit transmis | 1   | 0   | 1   | 1   | 0   | 0   | 1   |
| ------------ | --- | --- | --- | --- | --- | --- | --- |
| Signal       | ⬆   | ⬇   | ⬆   | ⬆   | ⬇   | ⬇   | ⬆   |

#### Implémentation en Python

```python
# Fonction d'encodage Manchester
# Transition bas → haut pour '1', haut → bas pour '0'
def encode_manchester(data):
    encoded = []
    for bit in data:

        encoded.append((0,1) if bit == '1' else (1,0)) # Si le bit est 1, on ajoute (0,1), sinon (1,0) 
    return encoded

# Fonction de décodage Manchester
# On décode en '1' si la transition est de bas en haut, '0' sinon
def decode_manchester(encoded_data):
    decoded = ''
    for pair in encoded_data:
        decoded += '1' if pair == (0,1) else '0'
    return decoded

# Exemple d'utilisation
data = "1011001"
manchester_signal = encode_manchester(data)
decoded_data = decode_manchester(manchester_signal)
print("Signal Manchester encodé:", manchester_signal)
print("Données décodées:", decoded_data)
```
