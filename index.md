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
  background-color: #f9f9f9;
}

/* Zones cliquables */
.clickable-zones {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
  margin-top: 30px;
}

.zone {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-decoration: none;
  background: linear-gradient(145deg, #ffffff, #f0f0f0);
  box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.1), -4px -4px 10px rgba(255, 255, 255, 0.7);
  border-radius: 12px;
  padding: 20px;
  width: 150px;
  height: 170px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  opacity: 0;
  transform: translateY(20px);
  animation: fadeIn 0.5s ease-in-out forwards;
}

.zone:nth-child(1) { animation-delay: 0.1s; }
.zone:nth-child(2) { animation-delay: 0.2s; }
.zone:nth-child(3) { animation-delay: 0.3s; }
.zone:nth-child(4) { animation-delay: 0.4s; }

.zone:hover {
  transform: scale(1.05) translateY(-8px);
  box-shadow: 6px 6px 15px rgba(0, 0, 0, 0.2), -6px -6px 15px rgba(255, 255, 255, 0.9);
}

.zone .icon {
  width: 70px;
  height: 70px;
  margin-bottom: 10px;
  transition: transform 0.3s ease, filter 0.3s ease;
}

.zone:hover .icon {
  transform: scale(1.1);
  filter: brightness(1.1);
}

.zone .icon img {
  width: 100%;
  height: auto;
}

.zone p {
  color: #333;
  font-size: 16px;
  font-weight: bold;
  text-align: center;
  margin: 0;
}

@media (max-width: 768px) {
  .zone {
    width: 120px;
    height: 140px;
    padding: 15px;
  }

  .zone .icon {
    width: 60px;
    height: 60px;
  }

  .zone p {
    font-size: 14px;
  }
}

/* Alertes */
.alert {
  border-left: 5px solid #007bff;
  background-color: #f1f7ff;
  padding: 15px;
  font-size: 14px;
  margin-bottom: 20px;
  border-radius: 5px;
  transition: background-color 0.3s ease;
}

.alert:hover {
  background-color: #e7f1ff;
}

.new-alert {
  border-left: 5px solid #28a745;
  background-color: #e8f8ee;
  padding: 15px;
  font-size: 14px;
  margin-bottom: 20px;
  border-radius: 5px;
  transition: background-color 0.3s ease;
}

.new-alert:hover {
  background-color: #dff3e8;
}

/* Footer */
.footer {
  text-align: center;
  margin-top: 40px;
  font-size: 14px;
  color: #666;
  padding: 20px;
  border-top: 1px solid #ddd;
  background-color: #fafafa;
}

.footer a {
  color: #007bff;
  text-decoration: none;
}

.footer a:hover {
  text-decoration: underline;
}

/* Animations */
@keyframes fadeIn {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>

<div class="intro-text">
  <p>Bienvenue sur le site dédié aux ETS des CPIA1 du CESI de Montpellier. Ce site a pour but de vous accompagner dans votre apprentissage de la programmation en vous proposant des cours et des exercices.</p>
</div>

{% include alert.html text="Ce site est en cours de construction. Pensez à revenir régulièrement pour découvrir de nouveaux contenus." type="info" %}

{% include alert.html text="Nouveau contenu : cours sur les bases de données (BDD)." type="new" %}

<div class="clickable-zones">
  <a href="content/00-Excel/01-Cours.html" class="zone" aria-label="Accéder au cours Excel">
    <div class="icon">
      <img src="images/excel.png" alt="Icône Excel">
    </div>
    <p>Excel</p>
  </a>
  <a href="content/01-flowgorithme/00-Introduction.html" class="zone" aria-label="Accéder au cours Flowgorithm">
    <div class="icon">
      <img src="images/flowgorithm.png" alt="Icône Flowgorithm">
    </div>
    <p>Flowgorithm</p>
  </a>
  <a href="content/02-arduino/00-Introduction.html" class="zone" aria-label="Accéder au cours Arduino">
    <div class="icon">
      <img src="images/arduino.png" alt="Icône Arduino">
    </div>
    <p>Arduino</p>
  </a>
  <a href="content/03-python/0-avantCommencer.html" class="zone" aria-label="Accéder au cours Python">
    <div class="icon">
      <img src="images/python.png" alt="Icône Python">
    </div>
    <p>Python</p>
  </a>
    <a href="content/08-BDD/00-Introduction-SI.md" class="zone" aria-label="Accéder au cours sur la BDD">
    <div class="icon">
      <img src="images/icon_bdd.png" alt="Icône BDD">
    </div>
    <p>BDD</p>
  </a>
</div>

<footer class="footer">
  <p>© Rohan Fossé, Enseignant Responsable Pédagogique, CESI Montpellier, 2024</p>
  <p><a href="https://github.com/rohanfosse/CPIA1-info">Code source du site</a></p>
</footer>
