---
title: Accueil
layout: lesson-content
---

<style>
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
  background: linear-gradient(145deg, #f0f0f0, #dcdcdc);
  box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.1), -5px -5px 15px rgba(255, 255, 255, 0.7);
  border-radius: 12px;
  padding: 20px;
  width: 120px;
  height: 140px;
  transition: transform 0.3s, box-shadow 0.3s;
}

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
</style>

Bienvenue sur le site dédié aux ETS des CPIA1 du CESI de Montpellier. Ce site a pour but de vous accompagner dans votre apprentissage de la programmation en vous proposant des cours et des exercices.

{% include alert.html text="Ce site est en cours de construction. Pensez à revenir régulièrement pour découvrir de nouveaux contenus." type="info" %}

<div class="clickable-zones">
  <a href="/excel/" class="zone">
    <div class="icon">
      <img src="/assets/images/excel-icon.png" alt="Excel Icon">
    </div>
    <p>Excel</p>
  </a>
  <a href="/flowgorithm/" class="zone">
    <div class="icon">
      <img src="/assets/images/flowgorithm-icon.png" alt="Flowgorithm Icon">
    </div>
    <p>Flowgorithm</p>
  </a>
</div>


{% include template/credits.html %}

