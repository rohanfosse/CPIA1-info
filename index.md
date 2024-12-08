---
title: Accueil
layout: lesson-content
---

<style>
/* Zones cliquables */
.clickable-zones {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-top: 20px;
}

.zone {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-decoration: none;
  background: white;
  box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.1), -5px -5px 15px rgba(255, 255, 255, 0.7);
  border-radius: 12px;
  padding: 20px;
  width: 120px;
  height: 140px;
  transition: transform 0.3s, box-shadow 0.3s;
  opacity: 0;
  transform: translateY(20px);
  animation: fadeIn 0.5s ease-in-out forwards;
}

.zone:nth-child(1) { animation-delay: 0.1s; }
.zone:nth-child(2) { animation-delay: 0.2s; }
.zone:nth-child(3) { animation-delay: 0.3s; }
.zone:nth-child(4) { animation-delay: 0.4s; }

.zone:hover {
  transform: translateY(-5px);
  box-shadow: 5px 5px 20px rgba(0, 0, 0, 0.2), -5px -5px 20px rgba(255, 255, 255, 0.9);
}

.zone .icon {
  width: 60px;
  height: 60px;
  margin-bottom: 10px;
}

.zone .icon img {
  width: 100%;
  height: auto;
}

.zone p {
  font-family: 'Roboto', sans-serif;
  color: #333;
  font-size: 16px;
  font-weight: bold;
  text-align: center;
}

@media (max-width: 768px) {
  .clickable-zones {
    flex-wrap: wrap;
    gap: 10px;
  }

  .zone {
    width: 100px;
    height: 120px;
    padding: 15px;
  }

  .zone .icon {
    width: 50px;
    height: 50px;
  }

  .zone p {
    font-size: 14px;
  }
}

/* Alertes */
.alert {
  border-left: 5px solid #007bff;
  background-color: #f8f9fa;
  padding: 10px;
  font-family: 'Roboto', sans-serif;
  margin-bottom: 20px;
}

/* Footer */
.footer {
  text-align: center;
  margin-top: 40px;
  font-size: 14px;
  color: #666;
  padding: 20px;
  border-top: 1px solid #ddd;
}

.footer a {
  color: #007bff;
  text-decoration: none;
}

.footer a:hover {
  text-decoration: underline;
}

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

<div class="clickable-zones">
  <a href="content/00-Excel/01-Cours.html" class="zone">
    <div class="icon">
      <img src="images/excel.png" alt="Excel Icon">
    </div>
    <p>Excel</p>
  </a>
  <a href="content/01-flowgorithme/00-Introduction.html" class="zone">
    <div class="icon">
      <img src="images/flowgorithm.png" alt="Flowgorithm Icon">
    </div>
    <p>Flowgorithm</p>
  </a>
  <a href="content/02-arduino/00-Introduction.html" class="zone">
    <div class="icon">
      <img src="images/arduino.png" alt="Arduino Icon">
    </div>
    <p>Arduino</p>
  </a>
  <a href="content/03-python/0-avantCommencer.html" class="zone">
    <div class="icon">
      <img src="images/python.png" alt="Python Icon">
    </div>
    <p>Python</p>
  </a>
</div>

<footer class="footer">
  <p>© Rohan Fossé, Enseignant Responsable Pédagogique, CESI Montpellier, 2024</p>
  <p><a href="https://github.com/rohanfosse/CPIA1-info">Code source du site</a></p>
</footer>
