+++
pre = '<b>1.2 </b>'
title = "Gestion des reqêtes"
weight = 2
+++

Un incident est une **interruption non planifiée** ou la **dégradation de la qualité d’un service** informatique. J’ai donc quelque chose qui fonctionnait et qui ne fonctionne plus. 
Une demande, quant à elle, est un **nouveau besoin**. Je n’ai pas quelque et il me le faut. 
​
<!-- Par exemple, mon accès VPN fonctionnait hier et il ne fonctionne plus aujourd’hui 
VS
Par exemple, j’ai besoin d’avoir un accès VPN et je n’ai jamais eu un tel accès.​ -->

L’objectif principal de la gestion des demandes est d’**offrir aux utilisateurs un canal** au travers duquel sont **demandés des services**.​

Les demandes sont signalées au centre de service par les utilisateurs, via divers <a href="420-510/content/01-analyse-du-besoin/_index.md" target="_blank" rel="noopener">canaux de communication</a>. Les administrateurs et les systèmes de surveillance ne peuvent, cela dit, pas deviner les besoins des utilisateurs.​
​
### Aperçu du processus de gestion des requêtes 

<style>
:root{
  --lane-bg:#fff7e6;      /* fond panneau */
  --box-bg:#e9f2fb;       /* fond bleu pâle (étapes communes) */
  --box-br:#93c5fd;
  --ink:#0b1220;
  --green:#d9f0d3;        /* vert pâle (étapes spécifiques aux demandes) */
  --green-br:#6ab06e;
  --green-dark:#1f4e23;   /* vert foncé (Validation/approbation) */
}

/* Grille des 3 niveaux */
.inc-grid{
  display:grid;
  grid-template-columns:repeat(3,minmax(220px,1fr));
  gap:16px; margin:1rem 0;
  align-items:start;
}
.lane{border:2px solid #1e3a8a20;border-radius:12px;background:#fff}
.lane-inner{background:var(--lane-bg);border-radius:10px;padding:14px}
.lane-title{display:flex;justify-content:center;align-items:center;margin:.6rem 0 .4rem}
.badge{display:inline-block;padding:2px 10px;border-radius:999px;background:#111827;color:#fff;font-size:.75rem;font-weight:700}

/* Étapes */
.step{background:var(--box-bg);border:1.5px solid var(--box-br);border-radius:12px;
      padding:12px 14px;margin:10px 0;font-weight:700;color:var(--ink)}
.step.green{background:var(--green);border-color:var(--green-br)}
.step.gdark{background:var(--green-dark);color:#fff;border-color:#0f3311}

details.step summary{cursor:pointer;list-style:none;display:inline}
details.step summary::-webkit-details-marker{display:none}
details.step[open]{filter:brightness(0.98)}
.note{font-weight:400;margin-top:8px;color:#374151;line-height:1.35}
.hint{font-size:.82rem;color:#6b7280;margin-left:.25rem;font-weight:400}

/* Notice */
.notice{
  margin:18px 0 8px; padding:14px 16px;
  background:#e7f5e9; color:#114b22; border:2px solid #7bc17f; border-radius:12px;
  font-weight:600;
  box-shadow:0 1px 0 rgba(0,0,0,.03) inset;
}

@media (prefers-color-scheme: dark){
  .lane{background:#0b1220;border-color:#334155}
  .lane-inner{background:#0f172a}
  .step{background:#0f2340;border-color:#3b82f6;color:#e5e7eb}
  .step.green{background:#0d3220;border-color:#2e7d32;color:#d1fae5}
  .step.gdark{background:#0b2a16;border-color:#0b4d1f;color:#e8fcef}
  .note{color:#cbd5e1}
  .badge{background:#1f2937}
  .notice{background:#0e2414;color:#c7f9d4;border-color:#2e7d32}
}
</style>

<div class="inc-grid">

  <!-- NIVEAU 1 -->
  <div class="lane">
    <div class="lane-inner">
      <div class="lane-title"><span class="badge">NIVEAU 1</span></div>
      <div class="step">Détection et enregistrement</div>
      <div class="step green">Classification et priorisation</div>
      <div class="step gdark">Validation et approbation</div>
      <div class="step">Affectation et escalade (+ suivis)</div>
      <div class="step green">Résolution</div>
      <div class="step">Clôture</div>
    </div>
  </div>

  <!-- NIVEAU 2 -->
  <div class="lane">
    <div class="lane-inner">
      <div class="lane-title"><span class="badge">NIVEAU 2</span></div>
      <div class="step gdark">Validation</div>
      <div class="step">Affectation et escalade</div>
      <div class="step green">Résolution</div>
    </div>
  </div>

  <!-- NIVEAU 3 -->
  <div class="lane">
    <div class="lane-inner">
      <div class="lane-title"><span class="badge">NIVEAU 3</span></div>
      <div class="step gdark">Validation</div>
      <div class="step">Affectation et escalade</div>
      <div class="step green">Résolution</div>
    </div>
  </div>

</div>

<div class="notice">
  Notez les <strong>bulles vertes</strong> : ce sont les éléments qui <strong>diffèrent</strong> du processus de <a href="420-510/content/01-analyse-du-besoin/gestion-incidents.md" target="_blank" rel="noopener"><em>gestion des incidents</em></a>. Les autres étapes sont identiques.
</div>

<style>
.diff-note{
  margin: 12px 0;
  padding: 12px 14px;
  background: #f8fafc;
  border: 1px solid #e5e7eb;
  border-left: 4px solid #7bc17f;  /* liseré vert */
  border-radius: 10px;
  line-height: 1.45;
}
@media (prefers-color-scheme: dark){
  .diff-note{ background:#0f172a; color:#e5e7eb; border-color:#334155; border-left-color:#2e7d32; }
}
</style>

<div class="diff-note">
  <strong>Gestion de demandes vs incidents</strong>
  <ul>
    <li><strong>Niveau 1 : diagnostic → validation &amp; autorisation</strong>. <br> Une demande n’exige pas de diagnostic de panne ; elle doit d’abord être <strong>validée</strong>, puis <strong>autorisée</strong>.</li>
    <li><strong>Niveaux 2 &amp; 3 : diagnostic → validation</strong>. <br> Les N2 et N3 <strong>valident</strong> la demande (technique/capacité), l’<strong>autorisation</strong> ayant normalement été obtenue par le <strong>N1</strong> au préalable.</li>
  </ul>
</div>

### Les principales différences

#### 1) La priorisation
- L’étape préserve la **même logique de base** : on croise **impact × urgence** ⇒ niveau
- Le choix de la **matrice dédiée** : l’organisation peut utiliser **une matrice par contexte**  
  *(incidents / demandes / changements)* ou **une seule** commune.
- La **classification** peut être adaptée selon le contexte: incident ou demande (Ex.: la classification PC > écran > défectueux ne peut exister pour une demande). La classification pour une demande serait par exemple PC > écran > 2e écran requis.​

Au moment de prioriser il faut distinguer les types de demandes **standard vs non-standard**:
  - **standard** : figurent au **catalogue de services**, **fréquentes**, déjà **modélisées**  
    → priorités et **SLA** souvent **prédéfinis** (ex. installation de logiciels comme *Acrobat Reader*, créer un accès dossier).
  - **Non-standard** : **hors catalogue**, spécifiques peu habituelles, parfois **projetisées**  
    → la priorité dépend de l’**impact métier**, des **dépendances** (achats, licences, approbations) et des **risques** (ex. installation d’un logiciel de gestion d’imports-exports). 
<!-- nouveau logiciel métier pour un labo → dépend de l’**achat**, du **packaging** et des **tests sécurité** → priorité ajustée selon l’échéance. -->

#### 2) La validation
Au lieu d’exécuter un **diagnostic**, vous devez **valider la demande​**. 
- **Niveau 1 (N1)** : **conformité & complétude**  
  - [ ] Identité du demandeur & **droit de demander** (rôle, unité).  
  - [ ] **Formulaire complet** (justification, échéance, environnement).  
  - [ ] **Pièces jointes** requises (ex. approbation, modèle signé).
- **Niveaux 2 & 3 (N2/N3)** : validations **techniques & capacitaires**  
  - [ ] **Licences disponibles** / coûts récurrents.  
  - [ ] **Compatibilité** (OS, versions, sécurité).  
  - [ ] **Impact capacité / performance** (serveur, réseau, stockage).  
  - [ ] **Conformité** (sécurité, données, réglementation).

<!-- Habituellement le niveau 1 vérifie que la demande est conforme et complète.​
Les niveaux 2 et 3 peuvent aussi vérifier la conformité de la demande, mais s’attarderont à d’autres éléments comme le nombre de licences disponibles pour la demande d’un logiciel ou d’un accès.  La vérification de l’impact sur la capacité ou la performance d’un système peut aussi faire partie des vérifications. -->

<!-- Demande d’accès à une appli RH :  
N1 vérifie que le **formulaire est complet** et la **justification**.  
N2 vérifie **licences restantes** et **droits** nécessaires ; peut demander l’aval du **propriétaire des données**. -->

#### 3) Les autorisations
La demande doit habituellement être approuvée car elle implique **des coûts** tels que l’achat d’un logiciel ou d’une licence, l’achat de matériel, l’octroi d’accès et de permissions dans des systèmes.​

- **Qui approuve ?** selon le cas : **gestionnaire**, **propriétaire des données** (*data owner*), **sécurité**, **RH**, **achats/finances**.
- **Traçabilité obligatoire** :
  - [ ] Conserver la **preuve** d’autorisation **dans la demande** (workflow, PDF du courriel, ticket lié).  
  - [ ] Mentionner la **date**, le **nom/fonction** de l’approbateur et, si utile, une **date d’expiration**.
- **Achats** : peuvent **retarder** la réalisation de la demande (délais fournisseur, réception, préparation).

Exemple, Yassine demande le remplacement de son ordinateur portable par un modèle plus puissant. L’autorisation de remplacement a été accordée.  Vous devez procéder à l’achat du nouvel ordinateur que le fournisseur livrera seulement dans deux semaines.  En plus, vous avez besoin d’une semaine pour préparer le nouvel ordinateur (installation et configuration de Windows et des logiciels).​
<!-- - Accès à un partage **contenant des salaires** → **approbation RH** (propriétaire des données) **requise**, preuve jointe.  
- Logiciel payant sans licence disponible → **achat** nécessaire, donc **délais** (commande + packaging + déploiement). -->

<!-- Les demandes d’accès exigent beaucoup de vigilance et ne doivent jamais être prises à la légère. Les approbations sont donc un élément essentiel.​
Par exemple, vous recevez une demande pour un accès au partage réseau RH contenant les salaires de tous les employés.  Il faut l’approbation du Directeur RH.​
Pour chaque partage réseau et pour chaque application, il doit y avoir un responsable (propriétaire des données) pour autoriser les accès et faire une révision annuelle des accès.​​
Il est primordial de conserver les autorisations avec la demande.  Certains logiciels permettent de demander l’autorisation directement dans la demande; d’autres logiciels permettent de joindre un fichier (par exemple, un pdf du courriel qui démontre l’autorisation).​​
L’important est de pouvoir prouver que vous avez bien reçu l’autorisation du propriétaire des données.​ -->

#### 4) La résolution
La **règle d’or** est de livrer **exactement ce qui a été demandé et autorisé**, **ni plus ni moins**.
- **Check de conformité avant livraison** :
  - [ ] Concordance **demande ↔ autorisation** (portée, durée, niveau d’accès).  
  - [ ] Journaliser : **étapes**, **paramètres** appliqués, **CI** affectés.
- **Communication & clôture** :
  - [ ] Informer l’utilisateur, joindre la **preuve** (ex. accès créé, logiciel installé).  
  - [ ] Si la preuve d’autorisation **diffère** de la demande initiale, **aligner** la livraison sur **l’autorisation**.
- **Si l’utilisateur conteste** : revoir l’**autorisation** (écart de périmètre) avant toute modification.

Exemples concrets :
- **Francis** demande **lecture** sur un dossier ; tu envisages lecture+écriture “pour gagner du temps” → **à éviter**.  
  → Livrer **lecture uniquement** (autorisation reçue).  
<!-- Sara demande un accès lecture à un dossier réseau.  Le propriétaire du dossier réseau a approuvé la demande.  Vous décidez de donner un accès lecture et écriture car les demandes précédentes pour d’autres utilisateurs étaient toujours pour un accès lecture, puis finalement une deuxième demande était effectuée pour un accès écriture.  Vous vous dites que vous sauverez du temps en accordant tout de suite l’accès en écriture.  Ce n’est pas à vous de juger.  Vous êtes là pour exécuter.  Peut-être que Francis est stagiaire et que l’accès en écriture peut compromettre des données importantes.​ -->
- **Henri** demande un accès lecture+écrituresur un dossier réseau; **autorisation** accordée = **lecture** uniquement → livrer **lecture** et demander mise à jour d’autorisation pour l’écriture.
<!-- Questions exam : quelle type est standard vs non standard : demande de cellulaire (stand) -->