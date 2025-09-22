+++
title = 'Soutien Informatique'
type = "home"
+++
<!-- Nouveau chapitre
hugo new --kind chapter content/01-modelisation/_index.md -->

Le cours de soutien informatique a pour objectifs de former l’étudiante ou l’étudiant à diagnostiquer, résoudre et documenter des problèmes techniques tout en assurant une relation de service exemplaire. Au fil des ateliers, il ou elle apprendra à cerner le besoin réel de la personne utilisatrice, à poser les bonnes questions, à rechercher des sources fiables, puis à proposer une solution sécuritaire, compréhensible et soutenable.

La formation est résolument pratique : chaque séance se déroulera sous forme d’atelier (mises en situation, simulation de tickets, rédaction de courriels et de pas-à-pas, validation des correctifs). L’accent est mis autant sur la méthodologie de dépannage que sur la communication claire et la qualité du suivi.

<!-- Ce site regroupe toutes les ressources (notes, exemples de code, exercices) pour la session. -->

## Objectifs du cours
- Analyser le besoin et le niveau de connaissance de la personne utilisatrice, qualifier l’environnement et prioriser l’intervention.
- Effectuer une recherche pertinente en jugeant la fiabilité des sources et les risques, puis mettre en œuvre une solution ; traiter la cause profonde, tester et confirmer l’absence de nouveaux problèmes. 
- Accompagner la personne utilisatrice en démontrant les étapes de résolution avec un vocabulaire adapté et des attitudes professionnelles favorisant la confiance, puis assurer le suivi et formuler des recommandations de prévention.
- Rédiger un avis de soutien clair et conforme (présentation du logiciel, scénarios d’usage, captures, respect des normes de documentation).

## Notions à couvrir 

| BLOC | TITRE | DESCRIPTION |
|---|---|---|
| 1 | Analyse du besoin | Processus visant à comprendre précisément la demande en recueillant symptômes, contexte d’usage et contraintes afin d’en formuler une définition claire et actionnable. |
| 2 | Résolution du problème ou de la requête | Démarche structurée qui recherche, applique et valide la solution la plus appropriée en s’assurant qu’elle traite la cause et rétablit le fonctionnement attendu. |
| 3 | Communication de la solution et suivi du soutien | Transmission de la solution dans un langage accessible, avec étapes claires et vérification ultérieure pour confirmer la satisfaction et prévenir la récurrence. |

##### En détails (*cf. plan de cours, section « Contenus d’apprentissage »*) 
<style>
  .details-menu summary {
    list-style: none;              /* cache la flèche par défaut (Firefox) */
    cursor: pointer;
    padding: .25rem 0;
    font-weight: 700;
  }
  .details-menu summary::-webkit-details-marker { display: none; } /* Chrome/Safari */
  .details-menu summary::before {
    content: "▶";
    font-size: .9em;
    margin-right: .5rem;
    transition: transform .2s ease;
  }
  .details-menu[open] summary::before {
    content: "▼";
  }
  .details-menu ul { margin: .3rem 0 .8rem 1.4rem; }
</style>

<!-- Bloc 1 : menu déroulant avec flèche -->
<details class="details-menu">
  <summary>B1. Analyse du besoin de la personne utilisatrice</summary>
  <ul>
    <li><strong>Technique exploratoire avec la personne utilisatrice</strong>
      <ul>
        <li>Description du problème, du message d’erreur, captures d’écran</li>
        <li>Questions pertinentes sur l’environnement (système d’exploitation, état de mémoire, paramètre de pare-feu, validation des versions des logiciels, etc.)</li>
        <li>Formulation d’un courriel de soutien</li>
      </ul>
    </li>
    <li><strong>Reproduction du problème et identification de la cause</strong>
      <ul>
        <li>Consultation appropriée de la base de connaissances</li>
        <li>Fouille de la documentation officielle du logiciel impliqué (troubleshooting/dépannage, FAQ, etc.)</li>
        <li>Développer une théorie de la cause probable ou transmission de l’information à la personne ou au service concerné</li>
        <li>Techniques de résolution (élimination méthodique des sources d’erreurs possibles)</li>
        <li>Détermination judicieuse du niveau de priorité</li>
        <li>Utilisation d’une plateforme de ticket</li>
      </ul>
    </li>
  </ul>
</details>

<details class="details-menu">
  <summary>B2. Résolution du problème ou de la requête</summary>
  <ul>
    <li><strong>1 - Recherche de la solution</strong>
      <ul>
        <li>Recherche de différentes solutions disponibles sur les forums et les sites de support</li>
        <li>Problèmes fréquents et solutions fréquentes</li>
        <li>Déterminer les risques et les dérapages possibles avec la personne utilisatrice</li>
      </ul>
    </li>
    <li><strong>2. Vérification de la solution</strong>
      <ul>
        <li>S’assurer que la solution s’attaque à la cause profonde, et non seulement aux symptômes</li>
        <li>Jugement de la fiabilité des sources utilisé (cours sécurité informatique)</li>
        <li>Tester de manière approfondie pour s’assurer que le problème est résolu</li>
        <li>Vérifier si le système fonctionne comme prévu sans nouveaux problèmes</li>
      </ul>
    </li>
  </ul>
</details>

<details class="details-menu">
  <summary>B3. Communication de la solution à l’utilisateur et suivi du soutien</summary>
  <ul>
    <li>Niveau de langage approprié à utiliser durant un support à la personne utilisatrice (vulgarisation de l’informatique, limiter les termes techniques, utilisation de métaphore, etc)</li>
    <li>Décomposition de la solution en étapes simples pour la personne utilisatrice</li>
    <li>Technique de présentation des solutions (liste d’étape, capture d’écran, etc)</li>
    <li>Manifestation d’attitudes et de comportements favorisant l’établissement d’une relation de confiance, empreints de patience et respectueux des limites d’intervention professionnelle</li>
    <li>Pertinence et efficacité des démonstrations</li>
    <li>Formulation de documentation de soutien</li>
    <li>Enrichissement de la base de données open source ou ajouter la solution dans les forums.</li>
    <li>Vérification appropriée de la satisfaction de l’utilisatrice et de l’utilisateur</li>
    <li>Formulation claire de recommandations visant à prévenir la récurrence de pannes</li>
  </ul>
</details>


<!-- ## Horaire des séances  -->
<!-- Calendrier synthèse (sans colonne Commentaires)
<style>
  .cal-soutien { margin: 1rem 0; }
  .cal-soutien table { width:100%; border-collapse:collapse; font-size:0.95rem; }
  .cal-soutien th, .cal-soutien td { border:2px solid #555; padding:8px 10px; vertical-align:top; }
  .cal-soutien th { background:#eee; text-align:left; }
  .cal-soutien .sem { white-space:nowrap; font-weight:700; }
  .cal-soutien .points { text-align:center; font-weight:700; }
  .cal-soutien .pct { color:#d7263d; }      /* rouge pour les % */
  .cal-soutien .exam { background:#e9f7ef; }/* vert pâle pour examens */
  .cal-soutien em { color:#333; }
</style>

<div class="cal-soutien">
<table>
  <thead>
    <tr>
      <th>Semaine d’enseignement</th>
      <th>Nature et date de remise des évaluations</th>
      <th>Points alloués</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="sem">Semaine 1</td>
      <td><strong>Présentation du cours</strong>
        <ul>
          <li>Organisation d’une entreprise</li>
          <li>Fonctionnement général d’un centre de service TI</li>
          <li>État de l’art des ressources disponibles</li>
          <li>Explications sur le déroulement des activités du cours (et planification des horaires)</li>
        </ul>
      </td>
      <td class="points"></td>
    </tr>
    <tr>
      <td class="sem">Semaine 2</td>
      <td>Activité d’immersion dans un centre de service TI</td>
      <td class="points"><span class="pct">10&nbsp;%</span></td>
    </tr>
    <tr>
      <td class="sem">Semaine 3</td>
      <td><strong>B1. Analyse du besoin de l’utilisateur</strong></td>
      <td class="points"></td>
    </tr>
    <tr>
      <td class="sem">Semaine 4</td>
      <td><strong>B1. Analyse du besoin de l’utilisateur</strong><br><em>Atelier — reproduction du problème et identification de la cause</em></td>
      <td class="points"><span class="pct">5&nbsp;%</span></td>
    </tr>
    <tr>
      <td class="sem">Semaine 5</td>
      <td><strong>B2. Résolution du problème ou de la requête</strong></td>
      <td class="points"></td>
    </tr>
    <tr>
      <td class="sem">Semaine 6</td>
      <td><strong>B2. Résolution du problème ou de la requête</strong><br><em>Atelier — vérification d’une solution</em></td>
      <td class="points"><span class="pct">5&nbsp;%</span></td>
    </tr>
    <tr>
      <td class="sem">Semaine 7</td>
      <td><strong>B2. Résolution du problème ou de la requête</strong><br><em>Exercices de révision pour examen intra</em></td>
      <td class="points"></td>
    </tr>
    <tr class="exam">
      <td class="sem">Semaine 8</td>
      <td><strong>Examen intra</strong></td>
      <td class="points">25&nbsp;%</td>
    </tr>
    <tr>
      <td class="sem">Semaine 9</td>
      <td><strong>B3. Communication de la solution à l’utilisateur</strong></td>
      <td class="points"></td>
    </tr>
    <tr>
      <td class="sem">Semaine 10</td>
      <td>Formation Insertech</td>
      <td class="points"></td>
    </tr>
    <tr>
      <td class="sem">Semaine 11</td>
      <td>Activité réparation avec Insertech</td>
      <td class="points"><span class="pct">10&nbsp;%</span></td>
    </tr>
    <tr>
      <td class="sem">Semaine 12</td>
      <td><strong>B3. Communication de la solution à l’utilisateur</strong></td>
      <td class="points"></td>
    </tr>
    <tr>
      <td class="sem">Semaine 13</td>
      <td><strong>B3. Communication de la solution à l’utilisateur</strong><br><em>Atelier — documentation et suivi du soutien</em></td>
      <td class="points"><span class="pct">5&nbsp;%</span></td>
    </tr>
    <tr>
      <td class="sem">Semaine 14</td>
      <td>Exercices de révision pour épreuve finale</td>
      <td class="points"></td>
    </tr>
    <tr class="exam">
      <td class="sem">—</td>
      <td><strong>Épreuve finale (énoncé volet 1)</strong></td>
      <td class="points">20&nbsp;%</td>
    </tr>
    <tr class="exam">
      <td class="sem">Semaine 15</td>
      <td><strong>Épreuve finale (volet 2)</strong></td>
      <td class="points">20&nbsp;%</td>
    </tr>
  </tbody>
</table>
</div> -->

<!-- question exam 
basée sur atelier 1 
<div style="page-break-before: always; break-before: page;"></div>

la personne te donne tous les specs de l'ordi 
3 cas plus simple avc infos en trop 
vrai utilisateurs ils te melent, jms faire confiance 
**Le texte brouillon à nettoyer**


### exo 
télécharger un logiciel suite microsoft
un utilisateur nrml n'a pas les mm accès que vs, 

ds la rep 

qd il veut lancer le telechargement il n'a pas les autorisations necessaire, il vs dit que ca. marche ps et cmt faire 

- expliquer que les accès 
- une fois app téléchargé montrer à l'utilisateur elle est ou et la faire fonctionner  -->