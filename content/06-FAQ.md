---
section_id: FAQ
nav_order: 6
title: Foire Aux Questions
topics: FAQ; Questions; Réponses
---

<style>
/* Style général de la FAQ */
.faq-container {
  max-width: 900px;
  margin: 0 auto;
  padding: 20px;
  font-family: 'Roboto', sans-serif;
}

.faq-title {
  font-size: 32px;
  color: #2a9df4;
  text-align: center;
  margin-bottom: 40px;
}

/* Style des sections */
.faq-section {
  margin-bottom: 20px;
  border-left: 5px solid #2a9df4; /* Bande colorée */
  background: #fff;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

.faq-section-title {
  font-size: 20px;
  font-weight: bold;
  padding: 15px 20px;
  color: #333;
  cursor: pointer;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #f9f9f9;
  border-bottom: 1px solid #ddd;
  transition: background-color 0.3s ease;
}

.faq-section-title:hover {
  background-color: #f0f0f0;
}

.faq-section-title .arrow {
  font-size: 16px;
  transform: rotate(0deg);
  transition: transform 0.3s ease;
}

.faq-section.collapsed .faq-section-title .arrow {
  transform: rotate(-90deg);
}

.faq-content {
  padding: 20px;
  display: none;
  background-color: #fff;
  transition: all 0.3s ease;
}

/* Questions et réponses */
.faq-item {
  margin-bottom: 15px;
  overflow: hidden;
}

.faq-question {
  font-size: 18px;
  font-weight: bold;
  color: #2a9df4;
  margin-bottom: 5px;
}

.faq-answer {
  font-size: 16px;
  color: #555;
  line-height: 1.6;
}

/* Couleurs spécifiques aux sections */
.faq-section.excel {
  border-left-color: #1d6f42;
}
.faq-section.flowgorithm {
  border-left-color: #ff8c42;
}
.faq-section.arduino {
  border-left-color: #0072ce;
}
.faq-section.python {
  border-left-color: #f4c542;
}

/* Responsive Design */
@media (max-width: 768px) {
  .faq-title {
    font-size: 24px;
  }

  .faq-section-title {
    font-size: 18px;
  }

  .faq-question {
    font-size: 16px;
  }

  .faq-answer {
    font-size: 14px;
  }
}
</style>

<div class="faq-container">
  <h1 class="faq-title">FAQ - Questions Fréquentes</h1>

  <!-- Section Excel -->
  <div class="faq-section excel">
    <div class="faq-section-title">
      Excel
      <span class="arrow">▼</span>
    </div>
    <div class="faq-content">
      <div class="faq-item">
        <div class="faq-question">Question : Où télécharger Excel et comment l’installer ?</div>
        <div class="faq-answer">Réponse : Vous pouvez télécharger Excel depuis le site officiel de Microsoft ou via votre compte Office 365. Suivez les instructions d'installation après l'achat ou la connexion à votre compte.</div>
      </div>
      <div class="faq-item">
        <div class="faq-question">Question : Que faire si Excel ne démarre pas ou plante au lancement ?</div>
        <div class="faq-answer">Réponse : Essayez de réparer l’installation via le panneau de configuration de Windows ou mettez à jour le logiciel. Assurez-vous également que votre système d’exploitation est à jour.</div>
      </div>
    </div>
  </div>

  <!-- Section Flowgorithm -->
  <div class="faq-section flowgorithm">
    <div class="faq-section-title">
      Flowgorithm
      <span class="arrow">▼</span>
    </div>
    <div class="faq-content">
      <div class="faq-item">
        <div class="faq-question">Question : Où télécharger Flowgorithm et comment l’installer ?</div>
        <div class="faq-answer">Réponse : Flowgorithm est téléchargeable gratuitement sur le site officiel flowgorithm.org. Après le téléchargement, double-cliquez sur le fichier d’installation et suivez les instructions.</div>
      </div>
      <div class="faq-item">
        <div class="faq-question">Question : Pourquoi Flowgorithm ne s'ouvre pas ?</div>
        <div class="faq-answer">Réponse : Assurez-vous que Java est installé sur votre système. Flowgorithm nécessite Java pour fonctionner correctement. Mettez également à jour votre système.</div>
      </div>
    </div>
  </div>

  <!-- Section Arduino -->
  <div class="faq-section arduino">
    <div class="faq-section-title">
      Arduino
      <span class="arrow">▼</span>
    </div>
    <div class="faq-content">
      <div class="faq-item">
        <div class="faq-question">Question : Où télécharger l’IDE Arduino et comment l’installer ?</div>
        <div class="faq-answer">Réponse : Téléchargez l’IDE Arduino depuis le site officiel arduino.cc. Installez-le en suivant les instructions fournies après le téléchargement.</div>
      </div>
      <div class="faq-item">
        <div class="faq-question">Question : Pourquoi l’IDE Arduino ne détecte-t-il pas ma carte ?</div>
        <div class="faq-answer">Réponse : Assurez-vous que la carte est correctement connectée avec un câble USB fonctionnel. Vérifiez aussi que le bon port COM est sélectionné dans le menu Outils > Port.</div>
      </div>
    </div>
  </div>

  <!-- Section Python -->
  <div class="faq-section python">
    <div class="faq-section-title">
      Python
      <span class="arrow">▼</span>
    </div>
    <div class="faq-content">
      <div class="faq-item">
        <div class="faq-question">Question : Où télécharger Python et comment l’installer ?</div>
        <div class="faq-answer">Réponse : Téléchargez Python depuis le site officiel python.org. Pendant l'installation, cochez l'option Add Python to PATH pour faciliter son utilisation dans la ligne de commande.</div>
      </div>
      <div class="faq-item">
        <div class="faq-question">Question : Que faire si je vois l’erreur "ModuleNotFoundError" ?</div>
        <div class="faq-answer">Réponse : Cela signifie que le module que vous essayez d’importer n’est pas installé. Installez-le en utilisant la commande pip install nom_du_module.</div>
      </div>
    </div>
  </div>
</div>

<script>
document.addEventListener("DOMContentLoaded", function () {
  const sectionTitles = document.querySelectorAll(".faq-section-title");

  sectionTitles.forEach((title) => {
    title.addEventListener("click", function () {
      const section = this.parentElement;
      section.classList.toggle("collapsed");
      const content = section.querySelector(".faq-content");
      if (content.style.display === "block") {
        content.style.display = "none";
      } else {
        content.style.display = "block";
      }
    });
  });
});
</script>
