---
title: "Les transformées de Fourier en python"
layout: lesson-content
permalink: /Fourier.md
---

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex/dist/katex.min.css">
<script defer src="https://cdn.jsdelivr.net/npm/katex/dist/katex.min.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex/dist/contrib/auto-render.min.js"
    onload="renderMathInElement(document.body);"></script>

## Bases du traitement du signal

Le traitement du signal est une discipline fondamentale pour l’analyse et la manipulation des données. Un signal peut être vu comme une fonction du temps (ou de toute autre variable indépendante) décrivant un phénomène physique.

### Applications du traitement du signal

- Son et audio : Compression MP3, égaliseurs audio, réduction de bruit.
- Imagerie : Compression JPEG, amélioration d’images, imagerie médicale (IRM).
- Télécommunications : Transmission de données, modulation, filtrage.
- Physiologie : Analyse des signaux ECG, EEG.

### Numérisation d’un signal

La numérisation transforme un signal analogique (continu) en signal numérique (discret) en trois étapes :

1. Échantillonnage : Prise de mesures régulières dans le temps.
2. Quantification : Arrondi des valeurs mesurées à des niveaux discrets.
3. Codage : Conversion en valeurs binaires.

Exemple quotidien : Lorsque vous écoutez une chanson enregistrée, un microphone transforme les vibrations sonores en signaux numériques pour stockage ou transmission.

---

## Échantillonnage

L'échantillonnage consiste à prélever des valeurs d’un signal continu à des intervalles de temps réguliers (\( \Delta t \)) :

\[
t_k = k \cdot \Delta t, \quad k \in \mathbb{Z}
\]

### Théorème de Shannon-Nyquist

Un signal est parfaitement reconstruisible si la fréquence d’échantillonnage \( F*e \) satisfait :
\[
F_e \geq 2 f*{max}
\]
où \( f\_{max} \) est la fréquence maximale du signal. Sinon, un phénomène d'aliasing se produit, où les hautes fréquences sont mal représentées.

### Exemple concret

Un appareil photo numérique échantillonne une scène en capturant des pixels. Si la résolution est trop basse, les détails fins (hautes fréquences) sont perdus.

### Code Python : Effet de l'échantillonnage

```python
import numpy as np
import matplotlib.pyplot as plt

# Signal continu (10 Hz)
f = 10
t_continu = np.linspace(0, 1, 1000)  # Signal de haute résolution
signal_continu = np.sin(2 * np.pi * f * t_continu)

# Échantillonnage à différentes fréquences
Fe_values = [30, 15, 5]  # Hz
plt.figure(figsize=(12, 6))

for Fe in Fe_values:
    t_sampled = np.arange(0, 1, 1/Fe)
    signal_sampled = np.sin(2 * np.pi * f * t_sampled)
    plt.plot(t_sampled, signal_sampled, 'o-', label=f"Fe = {Fe} Hz")

plt.plot(t_continu, signal_continu, label="Signal continu", alpha=0.5)
plt.legend()
plt.title("Effet de l'échantillonnage sur un signal sinusoïdal")
plt.xlabel("Temps (s)")
plt.ylabel("Amplitude")
plt.grid()
plt.show()
```

---

## 3. Quantification

La quantification consiste à arrondir les amplitudes continues d’un signal à des valeurs discrètes. Cela entraîne une perte d’information appelée erreur de quantification.

### Concepts clés

- Pas de quantification (\( \Delta V \)) :
  \[
  \Delta V = \frac{\text{Amplitude maximale} - \text{Amplitude minimale}}{2^n}
  \]
  où \( n \) est le nombre de bits de la quantification.
- Exemple quotidien : En imagerie numérique, la profondeur de couleur (8 bits = 256 niveaux) influence la qualité de l'image.

### Code Python : Quantification

```python
# Signal continu
t = np.linspace(0, 1, 1000)
signal_continu = np.sin(2 * np.pi * 5 * t)

# Quantification à différents niveaux
quant_levels = [2, 4, 8]  # Niveaux de quantification
plt.figure(figsize=(10, 8))

for i, q in enumerate(quant_levels, 1):
    delta = 2 / q
    signal_quantifie = np.round(signal_continu / delta) * delta
    plt.subplot(3, 1, i)
    plt.plot(t, signal_continu, label="Signal continu", alpha=0.7)
    plt.step(t, signal_quantifie, label=f"Quantifié ({q} niveaux)", where='mid')
    plt.legend()
    plt.grid()

plt.tight_layout()
plt.show()
```

---

## 4. Transformée de Fourier

La transformée de Fourier (TF) convertit un signal du domaine temporel au domaine fréquentiel. Elle décompose un signal en une somme de sinusoïdes de différentes fréquences.

### Applications

- Analyse spectrale (identifier les composantes fréquentielles).
- Compression audio (MP3) et vidéo (MPEG).
- Réduction de bruit dans les signaux.

### Série de Fourier

Pour un signal périodique \( s(t) \), la décomposition est donnée par :
\[
s(t) = a*0 + \sum*{k=1}^\infty \left( a_k \cos(2 \pi k f_0 t) + b_k \sin(2 \pi k f_0 t) \right)
\]

### Code Python : Analyse fréquentielle

```python
from scipy.signal import periodogram

# Signal avec deux fréquences
f1, f2 = 10, 40
signal = np.sin(2 * np.pi * f1 * t) + 0.5 * np.sin(2 * np.pi * f2 * t)

# Transformée de Fourier
frequencies, power = periodogram(signal, fs=1000)

# Affichage
plt.plot(frequencies, power)
plt.title("Analyse spectrale (Transformée de Fourier)")
plt.xlabel("Fréquence (Hz)")
plt.ylabel("Amplitude")
plt.xlim(0, 50)
plt.grid()
plt.show()
```

---

## 5. Filtrage numérique

Le filtrage numérique permet d'isoler ou de supprimer certaines fréquences dans un signal.

### Types de filtres

1. Passe-bas : Laisse passer les basses fréquences (\( f < f_c \)).
2. Passe-haut : Laisse passer les hautes fréquences (\( f > f_c \)).
3. Passe-bande : Laisse passer une plage de fréquences.

### Exemple quotidien

Les casques antibruit utilisent un filtre actif pour annuler les bruits basse fréquence.

### Code Python : Filtre passe-bas

```python
from scipy.signal import butter, filtfilt

# Signal bruité (50 Hz de bruit ajouté)
signal_bruite = signal + np.sin(2 * np.pi * 50 * t)

# Conception du filtre passe-bas
fc = 20  # Fréquence de coupure
b, a = butter(4, fc / (1000 / 2), btype='low')  # Filtre passe-bas d'ordre 4
signal_filtre = filtfilt(b, a, signal_bruite)

# Affichage
plt.figure(figsize=(10, 6))
plt.plot(t, signal_bruite, label="Signal bruité", alpha=0.7)
plt.plot(t, signal_filtre, label="Signal filtré (passe-bas)", linewidth=2)
plt.title("Filtrage passe-bas")
plt.xlabel("Temps (s)")
plt.ylabel("Amplitude")
plt.legend()
plt.grid()
plt.show()
```

---

## 6. Synthèse de signaux complexes

### Combinaison de signaux

Un signal complexe peut être généré en combinant plusieurs signaux simples (somme ou produit).

### Exemple quotidien

Les synthétiseurs audio utilisent la synthèse additive (somme de signaux) pour produire des sons musicaux.

### Code Python : Synthèse additive

```python
# Combinaison de deux signaux
s1 = np.sin(2 * np.pi * 10 * t)  # Signal 1
s2 = 0.5 * np.sin(2 * np.pi * 25 * t)  # Signal 2
signal_combine = s1 + s2

# Affichage
plt.plot(t, signal_combine)
plt.title("Combinaison de deux signaux sinusoïdaux")
plt.xlabel("Temps (s)")
plt.ylabel("Amplitude")
plt.grid()
plt.show()
```
