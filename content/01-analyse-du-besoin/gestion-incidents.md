+++
pre = '<b>1.1 </b>'
title = "Gestion d’incidents"
weight = 1
+++


<style>
/* Conteneur & déclencheur */
.gloss {
  position: relative;
  display: inline-block;   
  margin: 0 2px;
}
.gloss-trigger {
  list-style: none;          
  cursor: pointer;
  display: inline;           
  color: #134a13ff;            /* couleur du mot cliquable */
  font-weight: 600;
  text-decoration: underline dashed;
}
.gloss-trigger::-webkit-details-marker { display: none; } 
.gloss-popup {
  position: absolute;
  top: 1.8em;              
  left: 0;
  z-index: 100;
  min-width: 260px;
  max-width: 340px;
  padding: 12px 14px;
  background: #ffffff;
  color: #0b1220;
  border: 1px solid #e5e7eb;
  border-radius: 10px;
  box-shadow: 0 8px 24px rgba(0,0,0,0.12);
  line-height: 1.35;
  font-size: 0.95rem;
}
/* Ouverture/fermeture : la popup n’apparaît que si <details> est open */
.gloss:not([open]) .gloss-popup { display: none; }

/* Petit indicateur lorsqu’ouvert */
.gloss[open] .gloss-trigger { color: #0a58ca; }

/* Astuce ferme-yeux */
.gloss-tip {
  margin-top: 8px;
  font-size: 0.82rem;
  opacity: 0.7;
}
/* Mode sombre si ton thème Hugo l’utilise */
@media (prefers-color-scheme: dark) {
  .gloss-popup {
    background: #0b1220;
    color: #e5e7eb;
    border-color: #334155;
    box-shadow: 0 8px 24px rgba(0,0,0,0.5);
  }
  .gloss-trigger { color: #61a8ff; }
  .gloss[open] .gloss-trigger { color: #9cccff; }
}
</style>

Un incident est une **interruption non planifiée** ou la **dégradation de la qualité d’un service** informatique.​
​
L’objectif principal de la gestion des incidents est de **restaurer les conditions normales** de service aussi **rapidement** que possible.​
​

Les incidents sont signalés au centre de service par les utilisateurs, via divers <a href="420-510/content/01-analyse-du-besoin/_index.md" target="_blank" rel="noopener">canaux de communication</a>.

<p>Les incidents peuvent aussi être détectés par :</p>
<ul>
  <li>le personnel technique : par exemple, un administrateur de systèmes constate des lenteurs sur un serveur applicatif et crée lui-même le billet d’incident.</li>
  <li>un système de surveillance : par exemple, l’application de surveillance
      <details class="gloss">
        <summary class="gloss-trigger">Nagios</summary>
        <div class="gloss-popup">
          <strong>Nagios</strong> — outil de supervision (monitoring) open-source qui surveille l’état des hôtes et
          des services (serveurs, applications, bases de données, sites web, imprimantes, routeurs, etc.) et
          alerte en cas de panne ou de dépassement de seuil.
          <div class="gloss-tip">Appuyez à nouveau pour fermer.</div>
        </div>
      </details>
      détecte qu’une connexion réseau a cessé de fonctionner et crée automatiquement le billet d’incident dans le système de billets.
  </li>
</ul>

## Aperçu du processus de gestion des incidents 
<!-- Voir notes process-gest-incidents.png -->

<style>
:root{
  --lane-bg:#fff7e6;        /* fond beige pâle du panneau */
  --box-bg:#e9f2fb;         /* fond bleu pâle des étapes */
  --box-br:#93c5fd;         /* bordure des étapes */
  --text:#0b1220;
  --badge:#111827;
}
.inc-grid{
    display:grid;
    grid-template-columns:repeat(3,minmax(220px,1fr));
    gap:16px;margin:1rem 0;
    align-items: start; 
}
.lane{
    border:2px solid #1e3a8a20;
    border-radius:12px;
    background:#fff;
}
.lane-inner{background:var(--lane-bg);border-radius:10px;padding:14px;}
.lane-title{display:flex;justify-content:center;gap:.5rem;align-items:center;margin:.6rem 0 .4rem;}
.badge{display:inline-block;padding:2px 10px;border-radius:999px;background:var(--badge);color:#fff;font-size:.75rem;font-weight:700;letter-spacing:.02em;}
.step, details.step{background:var(--box-bg);border:1.5px solid var(--box-br);border-radius:12px;padding:12px 14px;margin:10px 0;font-weight:600;color:var(--text);}
details.step summary{cursor:pointer;list-style:none;display:inline;}
details.step summary::-webkit-details-marker{display:none;}
details.step[open]{background:#dbeafe;}
.note{font-weight:400;margin-top:8px;color:#374151;line-height:1.35;}
.hint{font-size:.82rem;color:#6b7280;margin-left:.25rem;font-weight:400;}
@media (prefers-color-scheme: dark){
  .lane{background:#0b1220;border-color:#334155;}
  .lane-inner{background:#0f172a;}
  .step, details.step{background:#0f2340;border-color:#3b82f6;color:#e5e7eb;}
  details.step[open]{background:#0b356d;}
  .note{color:#cbd5e1;}
  .badge{background:#1f2937;}
}
</style>

<div class="inc-grid">

  <!-- NIVEAU 1 -->
  <div class="lane">
    <div class="lane-inner">
      <div class="lane-title"><span class="badge">NIVEAU 1</span></div>
      <details class="step">
        <summary>Détection et enregistrement <span class="hint">— afficher détails</span></summary>
        <div class="note">
        <p><strong>Qui ouvre un incident&nbsp;?</strong></p>
        <ol>
          <li><strong>Alarmes de systèmes</strong> et <strong>outils de surveillance</strong> : incidents ouverts <strong>automatiquement</strong>.</li>
          <li><strong>Administrateurs</strong> : ouvrent un incident lorsqu’une situation anormale est détectée sur les <strong>systèmes informatiques</strong>.</li>
          <li><strong>Agents du centre de services</strong> : à la suite d'une <strong>prise de contact des utilisateurs</strong> (constituent la <strong>grande majorité</strong> des incidents).</li>
        </ol>
        <p>L’enregistrement d'un incident permet d'assurer le <strong>suivi</strong> et d'éviter d’<strong>oublier</strong> de travailler sur un incident.</p>
        <p><strong>Informations à enregistrer</strong> (dans le billet)&nbsp;:</p>
        <ol>
          <li><strong>Nom</strong> de la <strong>personne</strong> qui ouvre le billet.</li>
          <li><strong>Environnement</strong> et <strong>systèmes affectés (CI)</strong>.</li>
          <li>Noter si le billet est ouvert  <strong>pour soi</strong>, <strong>au nom d’une autre personne</strong> ou d’une <strong>équipe</strong>.</li>
          <li><strong>Une description de l’incident et toute information pertinente</strong> : 
            <ul>
              <li>les <strong>message(s) d’erreur</strong> exact(s).</li>
              <li><le strong>contexte</strong> : ce que la personne faisait <strong>avant</strong> l’incident.</li>
              <li><strong>actions déjà tentées</strong> pour résoudre le problème.</li>
            </ul>
          </li>
        </ol>
        <p>En somme, vous voulez éviter de devoir  <strong>recontacter</strong> l’utilisateur pour demander des précisions.</p>
        </div>
      </details>
      <details class="step">
        <summary>Classification et priorisation <span class="hint">— afficher détails</span></summary>
        <div class="note">
                <p>L'<strong>objectif</strong>, ici, est de classer l’incident dans une <strong>catégorie principale</strong> puis une/plusieurs <strong>sous-catégories</strong>, afin de <strong>router</strong> vers la bonne équipe et de <strong>prioriser</strong> le traitement.</p>
                  <ul>
                    <li><strong>Validation</strong> : à la <em>résolution</em>, vérifier que la classification initiale était correcte et la <strong>corriger</strong> au besoin.</li>
                    <li><strong>Association et routage automatique</strong> : les catégories sont souvent liées à des <strong>équipes de support</strong> (ex.&nbsp;: classification d'un incident en <em>réseaux &gt; téléphonie IP</em> → équipe téléphonie IP reçoit l'incident).</li>
                    <li><strong>Priorité</strong> : une priorité est <strong>assignée dès l’ouverture</strong> (ajustable après diagnostic) pour permettre à chaque équipe de traiter d’abord les cas <strong>critiques</strong>.</li>
                </ul>
                <p><strong>Exemple de méthodes de classification</strong>:</p>
                    <ul>
                        <li>catégorie → sous-catégorie → type de produit → type de problème</li> <br>
                        Exemples :   <br>
                            1. <em>matériel &gt; PC &gt; écran &gt; dysfonctionnement</em>  <br>
                            2. <em>système d’exploitation &gt; PC &gt; Windows 11 &gt; lenteurs</em>  <br>
                            3. <em>réseaux &gt; PC &gt; accès &gt; dysfonctionnement</em>  <br>  <br>
                        <li>catégorie → type → item</li>  <br>
                        Exemples :   <br>
                            1. <em>PC &gt; écran &gt; dysfonctionnement</em>  <br>
                            2. <em>PC &gt; Windows 11 &gt; lenteurs</em>  <br>
                            3. <em>PC &gt; accès réseau &gt; dysfonctionnement</em> <br>  <br>
                    </ul>                 
                    <p><strong>À considerer</strong></p>
                    <ul>
                        <li>
                            <details class="gloss">
                                <summary class="gloss-trigger">ITIL</summary>
                                <div class="gloss-popup">
                                <strong>ITIL  (Information Technology Infrastructure Library)</strong> — est un cadre de bonnes pratiques pour la gestion des services informatiques (ITSM) visant à aligner les services informatiques sur les objectifs de l'entreprise. Il fournit des directives et des processus éprouvés pour améliorer l'efficacité, l'efficience et la valeur des services IT, en se concentrant sur la création de valeur, l'amélioration continue et la collaboration.
                                <div class="gloss-tip">Appuyez à nouveau pour fermer.</div>
                                </div>
                            </details>
                            n’est pas prescriptif</strong> : retenez la méthode qui <strong>répond à vos besoins</strong> (certains outils imposent un schéma). L’important est d’avoir en place une méthode de classification.</li>
                        <li><strong>Limiter</strong> le nombre de <strong>catégories</strong> au 1<sup>er</sup> niveau et la profondeur à <strong>2–3 niveaux</strong> (réduit erreurs et temps d’ouverture).</li>
                        <li>Essayer de maintenir un <strong>catalogue</strong> de catégories <strong>vivant</strong> : revue périodique, renommages/merge si doublons.</li>
                    </ul>
            </div>
      </details>
      <details class="step">
        <summary>Diagnostic <span class="hint">— afficher détails</span></summary>
        <div class="note">
            <p>Cette étape sert à <strong>confirmer la classification</strong> et la <strong>sévérité/priorité</strong> de l’incident.</p>
        <p><strong>Issues possibles</strong> :</p>
        <ol>
            <li>Une solution a été trouvé → on passe alors à l’<strong>étape de résolution</strong>.​</li> <br>
            <li>Aucune solution / droits manquants</strong> → on consigne les infos pertinentes puis on passe alors à l’<strong>étape d’affectation</strong> vers un autre niveau.​</li>  <br>
        </ol> 
        <p class="tip">Notez que cette logique s’applique aussi aux <strong>N2</strong> et <strong>N3</strong> (réaffectation possible vers un autre niveau ou groupe).</p>
        </div>
      </details>
      <details class="step">
        <summary>Affectation et escalade (+ suivis) <span class="hint">— afficher détails</span></summary>
        <div class="note">
        <p>L'<strong>affectation</strong> est le transfert de l’incident vers l’<strong>équipe de support appropriée</strong> pour réaliser la résolution.</p>
        <p>Notez que selon la configuration de l’outil, les transferts entre équipes sont parfois <strong>bloqués</strong>. Il faut, dans ces cas, <strong>réaffecter</strong> l’incident au <strong>centre de services</strong> pour qu’il soit <strong>réaffecté</strong> à l’équipe appropriée.</p>
        <p>Une <strong>escalade</strong> est utilisée dans les incidents <strong>majeurs</strong> (typiquement <strong>S1/P1</strong>).​</p>
        <ul>
            <li>Notification de la <strong>direction TI</strong> (et parties prenantes) via le canal de crise défini.</li>
            <li>Objectif : <strong>accélérer</strong> l’engagement des ressources, la prise de décision et la communication.</li>
        </ul>
        <p><strong>La responsabilité centre de services (mention + suivis)</strong> : il demeure <strong>propriétaire</strong> du dossier.</p>
    <ul>
      <li>Vérifie régulièrement la <strong>progression</strong> auprès de l’équipe assignée.</li>
      <li>Met à jour le <strong>ticket</strong> (notes, ETA/ETR, changements de sévérité) et <strong>informe l’utilisateur</strong>.</li>
      <li>Fréquence des suivis <strong>proportionnelle à la sévérité</strong> (ex. S1 très fréquents, S3 quotidiens).</li>
    </ul>
    </div>
      </details>
      <details class="step">
        <summary>Résolution <span class="hint">— afficher détails</span></summary>
        <div class="note">
        <p>Lorsqu’une solution est identifiée, elle est <strong>implantée</strong> pour rétablir le service.</p>
    <p><strong>À faire pendant la résolution</strong></p>
    <ul>
      <li><strong>Appliquer</strong> le correctif ou un <strong>contournement</strong> et vérifier l’absence d’effets secondaires.</li>
      <li><strong>Valider avec l’utilisateur</strong> (tests de non-régression). Idéalement, obtenir une <strong>confirmation</strong> que le service fonctionne.</li>
      <li><strong>Documenter</strong> la résolution : cause (si connue), étapes réalisées, paramètres/scripts changés, CI impactés, temps passé.</li>
      <li><strong>Mettre à jour le ticket</strong> : notes, <strong>sévérité</strong> finale, et <strong>ajuster la classification</strong> si nécessaire.</li>
    </ul>
    <p><strong>À la clôture</strong></p>
    <ul>
      <li>Le <strong>centre de services</strong> est le <strong>seul</strong> autorisé à <strong>fermer</strong> définitivement l’incident.</li>
      <li>Un <strong>message de clôture</strong> est envoyé à l’utilisateur, avec un <strong>sondage de satisfaction</strong>.</li>
      <li>Si l’utilisateur constate que le problème persiste, le centre de services peut <strong>rouvrir</strong> l’incident à sa demande.</li>
    </ul>
   </div>
      </details>
      <div class="step">Clôture</div>
    </div>
  </div>

  <!-- NIVEAU 2 -->
  <div class="lane">
    <div class="lane-inner">
      <div class="lane-title"><span class="badge">NIVEAU 2</span></div>
      <div class="step">Diagnostic</div>
      <div class="step">Affectation et escalade</div>
      <div class="step">Résolution</div>
    </div>
  </div>

  <!-- NIVEAU 3 -->
  <div class="lane">
    <div class="lane-inner">
      <div class="lane-title"><span class="badge">NIVEAU 3</span></div>
      <div class="step">Diagnostic</div>
      <div class="step">Affectation et escalade</div>
      <div class="step">Résolution</div>
    </div>
  </div>
</div>

### Exemple d'une matrice pour la gestion d'incidents 
<div class="note">
  <p>En principe, la <strong>priorité</strong> d’un incident se détermine en croisant <strong>l’impact</strong> et <strong>l’urgence</strong>.</p>

  <ul>
    <li><strong>Impact</strong> — ampleur des <em>dégâts</em> ou de la perturbation&nbsp;: nombre d’utilisateurs touchés, service critique ou non, risques (sécurité, légaux), pertes d’exploitation.</li>
    <li><strong>Urgence</strong> — <em>vitesse de réaction</em> requise pour rétablir le service ou livrer un nouveau service (délais tolérables, échéance imminente, cours/réunion en cours, etc.).</li>
  </ul>

* “priorité” ≠ “sévérité” par défaut :
    - la sévérité décrit l’ampleur des effets (souvent technique/business)
    - la priorité décide dans quel ordre traiter (souvent calculée = impact × urgence).
</div>

<div> Le tableau ci-dessous est un <strong>exemple</strong>&nbsp;: ajuster libellés et
<details class="gloss">
        <summary class="gloss-trigger">SLA</summary>
        <div class="gloss-popup">
          <strong>SLA (Service Level Agreement) </strong> — (entente de niveau de service) engagement mesurable entre un fournisseur de service (ex. centre de services TI) et ses clients sur ce qui sera livré et dans quels délais/qualité. À quoi ça sert : fixer des attentes claires, prioriser, et mesurer la performance.
          <div class="gloss-tip">Appuyez à nouveau pour fermer.</div>
        </div>
      </details>
 à votre réalité.
 </div>

<style>
/* ===== Matrice Sévérité / Priorité (pastel) ===== */
.sev-matrix table{width:100%;border-collapse:separate;border-spacing:0;font-size:.98rem}
.sev-matrix th,.sev-matrix td{padding:10px 12px;border:1px solid #76777aff;vertical-align:middle;text-align:center}

/* En-têtes : gris uni */
.sev-matrix thead th{
  background:#f3f4f6;   /* gris clair */
  color:#111827;
  font-weight:700;
}

/* Colonne "Impact \ Urgence" (1re colonne) */
.sev-matrix tbody td:first-child{
  background:#f3f4f6;   /* gris pour l'étiquette d'impact */
  color:#111827;
  font-weight:700;
  text-align:left;
}

/* === Cellules internes (Impact × Urgence) — pastels sans bleu === */
/* Ligne 1 : Impact HAUT */
.sev-matrix tbody tr:nth-child(1) td:nth-child(2){background:#fee2e2;color:#111827} /* P1 rouge pastel */
.sev-matrix tbody tr:nth-child(1) td:nth-child(3){background:#ffedd5;color:#111827} /* P2 orange pastel */
.sev-matrix tbody tr:nth-child(1) td:nth-child(4){background:#fef9c3;color:#111827} /* P3 jaune pastel  */

/* Ligne 2 : Impact MOYEN */
.sev-matrix tbody tr:nth-child(2) td:nth-child(2){background:#ffedd5;color:#111827} /* P2 orange pastel */
.sev-matrix tbody tr:nth-child(2) td:nth-child(3){background:#fef9c3;color:#111827} /* P3 jaune pastel  */
.sev-matrix tbody tr:nth-child(2) td:nth-child(4){background:#dcfce7;color:#065f46} /* P4 vert pastel   */

/* Ligne 3 : Impact BAS */
.sev-matrix tbody tr:nth-child(3) td:nth-child(2){background:#fef9c3;color:#111827} /* P3 jaune pastel  */
.sev-matrix tbody tr:nth-child(3) td:nth-child(3){background:#dcfce7;color:#065f46} /* P4 vert pastel   */
.sev-matrix tbody tr:nth-child(3) td:nth-child(4){background:#ecfdf5;color:#065f46} /* P5 vert très clair*/

/* Arrondis visuels */
.sev-matrix thead th:first-child{border-top-left-radius:10px}
.sev-matrix thead th:last-child{border-top-right-radius:10px}
.sev-matrix tbody tr:last-child td:first-child{border-bottom-left-radius:10px}
.sev-matrix tbody tr:last-child td:last-child{border-bottom-right-radius:10px}

/* Survol (léger) */
.sev-matrix td:not(:first-child):hover{
  outline:2px solid rgba(0,0,0,.12);
  outline-offset:-2px;
}

/* Mode sombre (optionnel) */
@media (prefers-color-scheme: dark){
  .sev-matrix th,.sev-matrix td{border-color:#374151}
  .sev-matrix thead th,.sev-matrix tbody td:first-child{background:#111827;color:#e5e7eb}
  .sev-matrix tbody tr:nth-child(1) td:nth-child(2){background:#4c1d1d;color:#f8fafc}
  .sev-matrix tbody tr:nth-child(1) td:nth-child(3){background:#451a03;color:#f8fafc}
  .sev-matrix tbody tr:nth-child(1) td:nth-child(4){background:#3f3b07;color:#f8fafc}
  .sev-matrix tbody tr:nth-child(2) td:nth-child(4),
  .sev-matrix tbody tr:nth-child(3) td:nth-child(3),
  .sev-matrix tbody tr:nth-child(3) td:nth-child(4){background:#064e3b;color:#e7f9f1}
}

</style>

<div class="sev-matrix">

| **Impact \ Urgence** | **Haute** <br>*(action immédiate)* | **Moyenne** <br>*(prochaines heures)* | **Basse** <br>*(prochains jours)* |
|---|---|---|---|
| **Haut** <br>*affecte tous les utilisateurs ou services critiques* | **P1 – Très haute** | **P2 – Haute** | **P3 – Moyenne** |
| **Moyen** <br>*affecte plusieurs utilisateurs / opération importante* | **P2 – Haute** | **P3 – Moyenne** | **P4 – Basse** |
| **Bas** <br>*affecte quelques utilisateurs / opération non-critiques* | **P3 – Moyenne** | **P4 – Basse** | **P5 – Très basse** |

</div>

**Légende (exemple de cibles SLA)**  
- **P1 – Très haute** : prise en charge **immédiate**, communication de crise, résolution/contournement < 4h.  
- **P2 – Haute** : début < 2h, résolution/contournement < 1 jour ouvrable.  
- **P3 – Moyenne** : début < 1 jour ouvrable, résolution < 3 jours ouvrables.  
- **P4 – Basse** : planifiable dans la semaine.  
- **P5 – Très basse** : planifiable sans urgence (lot, maintenance).

> **Note** : revoir la **priorité** si l’**impact** ou l’**urgence** évoluent (ex. incident isolé devenu généralisé).

##### Exercice - appliquer la matrice 
Quelle priorité donneriez-vous à :​
- Un problème d’accès, pour le président, à une application non-essentielle pour son travail?​
- Un employé qui rapporte une possible infection de son poste de travail par un virus?

<!-- Quelle priorité donneriez-vous à :​
1. Un problème d’accès, pour le président, à une application non-essentielle pour son travail?​
Que dit la matrice de priorité?  L’impact est pour un seul utilisateur, et l’urgence pourrait être d’agir en 72 heures et moins.  Donc la priorité serait P4, donc basse.​
2. Un employé qui rapporte une possible infection de son poste de travail par un virus?​
Que dit la matrice de priorité?  L’impact est pour un seul utilisateur, et l’urgence pourrait être d’agir immédiatement.  Donc la priorité serait P3, donc moyenne.​
​
SELON UNE UTILISATION PURE DE LA MATRICE DE PRIORITÉS !!!​
EST-CE QUE ÇA FAIT DU SENS ?​ -->


<!-- Si c’est le président, c’est toujours une très haute priorité (P1)?  Ça dépend !​
Dans certains entreprises, un service VIP est en place pour les exécutifs et cette équipe prend en charge rapidement les besoins des exécutifs.  Donc cette équipe décide du niveau de priorités.​
Dans les entreprises où une telle équipe n’existe pas, ça peut dépendre de votre gestionnaire (il veut bien paraitre) ou du président lui-même (certains présidents veulent être traités comme les autres employés et d’autres se jugent plus importants que les employés).​
Les problème impliquant la sécurité doivent être pris au sérieux et traités en urgence.  Même s’il s’agit d’un seul poste de travail, un virus peut se propager rapidement dans le réseau.​
​
DONC, LA MATRICE NOUS GUIDE POUR LE CHOIX DE LA PRIORITÉ​
MAIS LE JUGEMENT DOIT S’APPLIQUER !!!​ -->

**Est-ce que ça fait du sens ? — règle d’or**

La matrice **nous guide**, mais le **jugement** s’applique :
- Certaines orgs ont des **règles VIP** (exécutifs) → traitement plus rapide que la matrice brute.
- Les **incidents de sécurité** se **priorisent** plus haut (prévention de propagation/impact légal).
- Contexte métier > matrice : échéance critique, examen en cours, salle d’opération, etc.

Exemples:​
- Une imprimante en panne pour un seul utilisateur a une priorité P4 (basse).  Cependant l’utilisateur vous informe que si l’imprimante n’est pas réparée d’ici 3 jours la production des produits sera affectée.  Vous augmentez la priorité à P2 (haute) pour une prise en charge plus rapide.​
- Un équipement de lecture de radiographie a une priorité P3 (moyenne) à l’hôpital, lorsqu’il est en panne.  Cependant, le même équipement en panne, en salle d’opération avec une chirurgie en cours, devient une priorité P1 (très haute).​
- Une panne du système hydraulique d’un avion a une priorité P3 (moyenne) lorsque l’avion est au sol, mais une priorité P1 (très haute) si la panne survient en vol.​
​

En premier temps, on établit la priorité selon la matrice, et ensuite on évalue le contexte pour déterminer si la priorité doit être augmentée.​

### La documentation d'incidents 
Lors de vos cours de français les enseignant(e )s exigent souvent un nombre de mots et de pages pour vos travaux.  Ici en informatique nous sommes à l’inverse.  Il faut avoir le **maximum d’informations**, en **peu de mots**.​

Alors, documenter un incident, ce n’est pas écrire un roman avec tous les détails inimaginables.  
Allez-y en phrases courtes, point par point.  

**Exemple**:​
- J’ai modifié la clé de registre HKEY… et ça n’a pas fonctionné. J’ai remis à la valeur initiale.​
- J’ai modifié le paramètre de résolution d’écran dans Windows, sans succès.​
- J’ai modifié le paramètre « screen size » dans le fichier config.txt pour la valeur 1248x728 et j’ai redémarré le programme. Ça a fonctionné.​

<p><strong>Guider votre rédaction</strong></p>
<ul>
    <li>En <strong>phrases courtes</strong>, <strong>point par point</strong>.</li>
    <li>Un item = <strong>une action</strong> + <strong>le résultat</strong> (succès/échec).</li>
    <li>Inclure les <strong>détails concrets</strong> utiles&nbsp;: message d’erreur exact, paramètre modifié, valeur, fichier/chemin.</li>
</ul>

L’objectif est de laisser des traces qui permettront à un autre technicien, ou à vous-mêmes quelques mois plus tard:​
de **comprendre l’incident​**, d’avoir les **informations recueillies**​ ainsi les grandes **étapes réalisées** pour la résolution.

<!-- ##### Exercice — transformer un « roman » en documentation claire

À partir du **texte brouillon** ci-dessous (volontairement pénible à lire), **sortez l’information utile** et **rédigez des notes d’incident courtes** (une action + un résultat par item).  
Objectif : laisser des traces exploitables par un·e autre technicien·ne.

**Le texte brouillon (à nettoyer)**

Vendredi, vers 8 h 42 (juste après la pause café du scrum meeting), Naomie (celle au 3e étage près de l’imprimante qui mange souvent des muffins aux bleuets, pas l’autre Naomie de la compta) m’a écrit sur Teams pour dire que GéoCarto Pro ne se lance pas. Elle dit qu’hier ça marchait « pas pire » mais aujourd’hui écran noir puis un popup avec quelque chose comme “Render init failed – code 0xC004 / invalid size” (ou 0xC0044 ? elle n’était pas sûre). Elle est sur Windows 11, portable HP EliteBook, branché parfois au dock USB-C (de mémoire, celui avec deux ports HDMI; je crois que le câble rouge est sur le port de gauche parce que l’autre est loose). Elle a redémarré, puis débranché/rebranché le deuxième écran, puis elle a fait une mise à jour de « je sais plus quoi » proposée par Windows (peut-être carte graphique ?) et ensuite c’était pire : le logiciel splash puis disparaît. Elle m’a envoyé une capture, mais par mail (je ne l’ai pas retrouvée parce que mon Outlook était en mode hors connexion après que le Wi-Fi du 3e a clignoté). On a essayé en désactivant l’antivirus 5 minutes (oui je sais), aucun changement. J’ai regardé dans `C:\Program Files\Geocarto\logs\client.log` et j’ai vu `DesiredScreen 1920x1080 not supported, fallback failed`. Il y a aussi un fichier `config.txt` dans `C:\Users\naomie\AppData\Roaming\Geocarto\`, avec une ligne `ScreenSize=` qui était vide (je crois). Quelqu’un a dit sur le forum que 1248x728 marche « souvent ». Ah et le DisplayLink du dock date de l’an dernier. J’ai testé vite fait en débranchant le dock** : miraculeusement, le logiciel s’ouvre, mais Naomie veut garder ses deux écrans pour travailler.

**À faire**

1. **Faits & symptômes (5–10 puces)** : extrayez uniquement les infos **vérifiables/utiles** (message exact si possible, contexte, chemins/logs).  
2. **Actions tentées & résultats (3–8 puces)** : une **action** + un **résultat** (*succès/échec*).  
3. **Prochaine étape** : proposez un **plan court** et testable (1–3 puces), incluant **rollback** si besoin.  
4. **Notes d’incident (80–120 mots)** : rédigez vos notes **courtes**, prêtes à coller dans le ticket. -->

<!-- 
### Corrigé possible (à dévoiler après votre tentative)
<details>
  <summary>Afficher un exemple de réponse structurée</summary>

**1) Faits & symptômes**
- Appli **GéoCarto Pro** ne se lance pas (Windows 11, HP EliteBook).  
- Popup au lancement : **“Render init failed – code 0xC004 / invalid size”**.  
- Log `C:\Program Files\Geocarto\logs\client.log` : **`DesiredScreen 1920x1080 not supported, fallback failed`**.  
- Fichier `C:\Users\naomie\AppData\Roaming\Geocarto\config.txt` : clé **`ScreenSize=` vide**.  
- **Dock USB-C DisplayLink** présent ; **appli démarre sans le dock**.

**2) Actions & résultats**
- Redémarrage système → **échec** (symptôme identique).  
- Débrancher/rebrancher 2e écran → **échec**.  
- MAJ Windows non précisée → **pire** (appli splash puis quitte).  
- **Désactivation antivirus 5 min** → **sans effet**.  
- **Test sans dock** → **succès** (appli s’ouvre).  
- Lecture du log client → **erreur de taille d’écran non supportée** confirmée.

**3) Prochaine étape (plan)**
- **Mettre à jour DisplayLink** vers dernière version **puis tester**.  
- Dans `config.txt`, définir **`ScreenSize=1248x728`** (valeur tolérante) → **tester** lancement avec le dock.  
- Si OK, **remettre** résolution souhaitée progressivement ; sinon **revenir** à 1248x728 (rollback).

**4) Notes d’incident (≈100 mots)**
GéoCarto Pro ne démarre pas (Win11, HP). Popup **“Render init failed – 0xC004 / invalid size”**.  
Log : `DesiredScreen 1920x1080 not supported, fallback failed`. `config.txt` → `ScreenSize=` vide.  
Sans dock USB-C (DisplayLink old), **l’appli démarre**. Antivirus off = sans effet.  
Plan : **MAJ DisplayLink**, puis fixer `ScreenSize=1248x728` dans `…\Roaming\Geocarto\config.txt`.  
Tester lancement avec dock + 2 écrans ; si OK, remonter résolution pas à pas ; sinon rollback 1248x728.  
Pièces jointes à récupérer : capture d’erreur et `client.log`. **Sévérité S3** (impact 1 utilisateur, urgence moyenne).

</details> -->