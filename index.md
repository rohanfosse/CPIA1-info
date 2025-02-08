---
title: Accueil
layout: lesson-content
---

<style>
/* Styles principaux */
body {
    font-family: 'Lato', sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
    color: #333;
}

.container {
    max-width: 960px;
    margin: 20px auto;
    padding: 20px;
}

h1 {
    text-align: center;
    margin-bottom: 20px;
    color: #007bff;
}

/* Zones cliquables */
.clickable-zones {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: 20px;
}

.zone {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-decoration: none;
    background-color: #fff;
    border-radius: 12px;
    padding: 20px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s ease, box-shadow 0.2s ease;
    overflow: hidden;
    position: relative;
}

.zone:hover {
    transform: translateY(-5px);
    box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
}

.zone .icon {
    width: 80px;
    height: 80px;
    margin-bottom: 10px;
}

.zone p {
    font-size: 16px;
    font-weight: 500;
    text-align: center;
    margin: 0;
}

/* Section "Signal" */
.signal-section {
    background-color: #fff;
    border-radius: 12px;
    padding: 20px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    margin-bottom: 20px;
}

.signal-section h2 {
    color: #007bff;
    margin-bottom: 10px;
}

.signal-section img {
    max-width: 100%;
    height: auto;
    border-radius: 8px;
    margin-bottom: 10px;
}

.signal-links {
    display: flex;
    flex-direction: column;
    gap: 10px;
}

.signal-links a {
    background-color: #007bff;
    color: #fff;
    padding: 10px 15px;
    border-radius: 5px;
    text-decoration: none;
    transition: background-color 0.2s;
}

.signal-links a:hover {
    background-color: #0056b3;
}

/* Alertes */
.alert {
    padding: 15px;
    margin-bottom: 20px;
    border-radius: 8px;
    background-color: #e9f0f8;
    border: 1px solid #c8d3e1;
    color: #337ab7;
    transition: background-color 0.2s;
}

.alert:hover {
    background-color: #d8e1ec;
}

.new-alert {
    background-color: #dff0d8;
    border-color: #c5e0c5;
    color: #3c763d;
}

.new-alert:hover {
    background-color: #cee7c9;
}

/* Footer */
.footer {
    text-align: center;
    margin-top: 40px;
    font-size: 14px;
    color: #777;
    padding: 20px;
    border-top: 1px solid #eee;
    background-color: #f9f9f9;
}

.footer a {
    color: #007bff;
    text-decoration: none;
}

.footer a:hover {
    text-decoration: underline;
}

/* Styles spécifiques pour l'intro */
.intro-text {
  text-align: center;
  margin-bottom: 20px;
}

</style>

<div class="container">
  <h1>CPIA 24/25 - Informatique</h1>

  <div class="intro-text">
    <p>Bienvenue sur le site dédié aux ETS des CPIA1 du CESI de Montpellier. Ce site a pour but de vous accompagner dans votre apprentissage de la programmation en vous proposant des cours et des exercices.</p>
  </div>

  {% include alert.html text="Ce site est en cours de construction. Pensez à revenir régulièrement pour découvrir de nouveaux contenus." type="info" %}

  <div class="intro-text">
    <a href="EI-python.html" class="alert">Cliquez ici pour l'Entrainement et conseils pour l'EI Python</a>
  </div>

  <div class="intro-text">
    <a href="Renforcement.html" class="alert">Cliquez ici pour le sujet étudié pendant le renforcement.</a>
    <a href="Renforcement-corrige.html"> La correction est disponible ici.</a>
  </div>

  <div class="intro-text">
    <a href="ExamBlanc-EI.html" class="alert">Cliquez ici pour l'exam blanc de l'EI pour s'entrainer</a>
  </div>

  <div class="intro-text">
    <a href="Courant-alternatif.html" class="new-alert">Cliquez ici pour la révision du CCTL Courant Alternatif.</a>
  </div>

  <div class="signal-section">
    <h2>Signal</h2>
    <img src="images/signal-image.png" alt="Image de signal">
    <div class="signal-links">
      <a href="lien1.html">Cours sur le signal</a>
      <a href="lien2.html">Exercices sur le signal</a>
      <a href="lien3.html">Simulateur de signal</a>
    </div>
  </div>

  <div class="clickable-zones">
    <a href="content/00-Excel/01-Cours.html" class="zone">
      <div class="icon"><img src="images/excel.png" alt="Icône Excel"></div>
      <p>Excel</p>
    </a>
    <a href="content/01-flowgorithme/00-Introduction.html" class="zone">
      <div class="icon"><img src="images/flowgorithm.png" alt="Icône Flowgorithm"></div>
      <p>Flowgorithm</p>
    </a>
    <a href="content/02-arduino/00-Introduction.html" class="zone">
      <div class="icon"><img src="images/arduino.png" alt="Icône Arduino"></div>
      <p>Arduino</p>
    </a>
    <a href="content/03-python/0-avantCommencer.html" class="zone">
      <div class="icon"><img src="images/python.png" alt="Icône Python"></div>
      <p>Python</p>
    </a>
  </div>
</div>

<footer class="footer">
    <p>© Rohan Fossé, Enseignant Responsable Pédagogique, CESI Montpellier, 2024</p>
    <p><a href="https://github.com/rohanfosse/CPIA1-info">Code source du site</a></p>
</footer>