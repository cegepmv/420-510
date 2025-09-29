+++
pre = '<b>1.2 </b>'
title = "Gestion des problèmes"
weight = 2
+++

La **gestion des problèmes** vient compléter la gestion des incidents.  
Alors que les incidents visent à **rétablir rapidement le service**, la gestion des problèmes cherche à **éliminer les causes profondes**.

<!-- C’est un peu comme réparer une fuite d’eau : l’incident, c’est essuyer le sol ; le problème, c’est trouver et colmater le tuyau percé. 💧🔧 -->

**⚡ Exemple**

- Incident : « le serveur courriel est tombé » (on le redémarre pour rétablir le service).
- Problème : « pourquoi ce serveur tombe-t-il chaque semaine ? » (analyse et correctif durable).

L’**objectif principal** est donc la prévention et la durabilité :

- éviter la récurrence des incidents <br>
  → réduire ces irritants qui perturbent les services TI
- proposer des solutions définitives ou de contournement <br>
  → identifier rapidement réduire la durée et la gravité des pannes etminimiser l’impact des incidents
- documenter les erreurs connues et prévenir les problèmes/incidents <br>
  → grâce à l’analyse proactive des erreurs connues et des anomalies (design, équipements, etc.).

  <!-- Les erreurs connues ne sont pas obligatoirement des incidents que vous avez vécu dans votre environnement informatique.  Par exemple, une analyse de votre réseau vous fait détecter une anomalie dans le design, ou encore un fournisseur vous avise d’un problème potentiel avec son équipement.​ -->

<!-- ### Un peu de terminologie

| **Terme**                     | **Définition**                                                                                                                                                                 |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Problème**                  | Cause inconnue d’un ou plusieurs incidents de même catégorie. Important de valider la catégorie à la clôture de l’incident.                                                    |
| **Erreur connue**             | Problème dont la cause première est documentée et pour lequel une solution de contournement existe, mais la solution définitive n’est pas encore implantée (ou même inconnue). |
| **Solution de contournement** | Réduit ou élimine l’impact d’un incident ou problème en attendant une solution définitive.                                                                                     | --> |


### Aperçu du processus de gestion des problèmes

<style>
:root{
  --lane-bg:#fff7e6;      
  --box-bg:#e9f2fb;       
  --box-br:#93c5fd;
  --ink:#0b1220;
  --gdark:#1f4e23;        /* vert foncé */
  --gdark-br:#0f3311;
}

.prob-grid{
  display:grid;
  grid-template-columns:repeat(1,minmax(280px,1fr));
  gap:16px; margin:1rem auto;
  max-width: 760px;
  align-items:start;
}
.lane{border:2px solid #1e3a8a20;border-radius:12px;background:#fff}
.lane-inner{background:var(--lane-bg);border-radius:10px;padding:14px}
.lane-title{display:flex;justify-content:center;align-items:center;margin:.6rem 0 .4rem}
.badge{display:inline-block;padding:2px 10px;border-radius:999px;background:#111827;color:#fff;font-size:.75rem;font-weight:700}

.step{background:var(--box-bg);border:1.5px solid var(--box-br);border-radius:12px;
      padding:12px 14px;margin:10px 0;font-weight:700;color:var(--ink)}

.step.gdark {
  background: #1f4e23;
  color: #fff;
  border-color: #0f3311;
}
/* Forcer les notes à rester blanches sur fond vert */
.step.gdark .note {
  color: #fff;
}
details.step summary{cursor:pointer;list-style:none;display:inline}
details.step summary::-webkit-details-marker{display:none}
details.step[open]{filter:brightness(0.98)}
.note{font-weight:400;margin-top:8px;color:#374151;line-height:1.35}
.hint{font-size:.82rem;color:#6b7280;margin-left:.25rem;font-weight:400}

@media (prefers-color-scheme: dark){
  .lane{background:#0b1220;border-color:#334155}
  .lane-inner{background:#0f172a}
  .step{background:#0f2340;border-color:#3b82f6;color:#e5e7eb}
  .step.gdark{background:#0b2a16;border-color:#0b4d1f;color:#e8fcef}
  .note{color:#cbd5e1}
  .badge{background:#1f2937}
}
</style>

<div class="prob-grid">
  <div class="lane">
    <div class="lane-inner">
      <div class="lane-title"><span class="badge">NIVEAU 1–3</span></div>
      <details class="step">
        <summary>Détection et enregistrement <span class="hint">— afficher détails</span></summary>
        <div class="note">
            <p>La détection d’un problème peut résulter de plusieurs sources&nbsp;:</p>
            <ul>
                <li>
                    une <strong>suite d’incidents récurrents</strong> de même catégorie  
                    <br><em>Exemple&nbsp;: dix billets d’incidents en un mois concernant des lenteurs sur le même serveur applicatif.</em>
                </li>
                <li>
                    une <strong>analyse technique</strong> de l’infrastructure TI qui révèle une faille  
                    <br><em>Exemple&nbsp;: un audit de sécurité détecte un port réseau laissé ouvert sans justification.</em>
                </li>
                <li>
                    un <strong>événement majeur</strong> qui met en lumière un incident pointant vers une situation plus sérieuse  
                    <br><em>Exemple&nbsp;: une panne de courant dans un centre de données révèle que le système d’alimentation de secours est mal configuré.</em>
                </li>
                <li>
                    un <strong>avis ou bulletin</strong> d’un fournisseur de produits ou de services  
                    <br><em>Exemple&nbsp;: Microsoft publie un avis sur une vulnérabilité critique dans Windows Server, applicable à vos systèmes.</em>
                </li>
                <li>
                    une <strong>analyse approfondie des incidents passés</strong> qui révèle une faiblesse sous-jacente  
                    br><em>Exemple&nbsp;: en examinant les billets des 6 derniers mois, on observe que les redémarrages fréquents d’un routeur proviennent d’un bug connu du firmware.</em>
                </li>
            </ul>
            <p>Une fois identifié, le problème doit être <strong>enregistré</strong> par la création d’un 
            <strong>billet de problème</strong> dans le système de gestion des billets.  
            Tous les <strong>incidents associés</strong> sont alors <strong>liés</strong> à ce problème, 
            pour un suivi centralisé et une meilleure traçabilité.</p>
        </div>
      </details>
      <details class="step">
        <summary>Classification et priorisation <span class="hint">— afficher détails</span></summary>
        <div class="note">
            Comme pour les incidents, chaque problème doit être classé et priorisé.
            <p>La <strong>classification</strong> des problèmes utilise les <strong>mêmes catégories</strong> que celles définies pour les incidents 
            (ex. matériel, réseau, applications, sécurité). Cela permet de garder une cohérence entre les processus et de lier facilement les incidents aux problèmes.</p>
            <p>La <strong>priorisation</strong>, de son côté, repose sur une <strong>matrice d’impact × urgence</strong>, où deux approches sont possibles&nbsp;:</p>
            <ul>
                <li>utiliser une <strong>matrice dédiée aux problèmes</strong>, plus adaptée aux analyses de fond,</li>
                <li>ou réutiliser la <strong>même matrice que pour les incidents</strong> (par exemple dans GLPI, où une seule matrice existe).</li>
            </ul>
            <p>La différence est que la priorité se base souvent sur la <strong>gravité potentielle</strong>si le problème n’est pas résolu, et non seulement sur l’urgence immédiate.</p>
            <p>Les <strong>priorités</strong> servent tout de même à déterminer <em>quels problèmes doivent être investigués en premier</em>, mais comme la durée des analyses est souvent <strong>imprévisible</strong>, il n’existe généralement pas de 
            <a href="#" title="Service Level Agreement">SLA</a> (ententes de niveaux de service) spécifiques pour la gestion des problèmes.</p>
            <p>L’objectif principal de l’<strong>investigation</strong> est de déterminer la <strong>cause racine</strong> du problème 
            (<em>root cause analysis</em>). </p>
        </div>
      </details>
      <details class="step gdark">
        <summary>Erreur connue & solution de contournement <span class="hint">— afficher détails</span></summary>
        <div class="note">
            <p>Lorsque l’<strong>investigation</strong> risque de durer longtemps, il est recommandé d’identifier des 
            <strong>solutions de contournement</strong> (<em>workarounds</em>).  
            Ces solutions ne règlent pas la cause profonde, mais elles permettent de :</p>
            <ul>
                <li><strong>corriger temporairement les incidents</strong> liés au problème ;</li>
                <li><strong>rétablir rapidement le service</strong> pour les utilisateurs ;</li>
                <li>donner du temps pour continuer l’analyse vers une solution définitive.</li>
            </ul>
            <p>Exemple&nbsp;: un logiciel plante régulièrement à cause d’un bug non corrigé → en attendant le patch, 
            on planifie un <em>redémarrage automatique toutes les nuits</em> pour maintenir le service disponible.</p>
            <hr>
            <p>Durant l’analyse, on peut distinguer plusieurs étapes&nbsp;:</p>
            <ol>
                <li>Un<strong>problème</strong> : ni la cause, ni la raison ne sont connues.<br>
                    <em>Exemple&nbsp;: corruption de fichiers répétée, sans explication.</em></li>
                <li>L'<strong>erreur connue</strong> : la <u>source</u> du problème est identifiée, mais pas encore la <u>raison</u> précise derrière.<br>
                    <em>Exemple&nbsp;: on découvre que les fichiers corrompus proviennent d’un disque défectueux, 
                    mais on ne sait pas encore pourquoi ce disque tombe en panne.</em></li>
                <li>La <strong>résolution définitive</strong> : la <u>raison</u> est comprise (le pourquoi), ce qui mène habituellement à la solution finale pour résoudre le problème.<br>
                    <em>Exemple&nbsp;: le disque est défectueux à cause d’une alimentation instable → remplacement de l’alimentation et du disque.</em></li>
            </ol>
            <p>Ainsi, l’<strong>erreur connue</strong> est une étape intermédiaire clé : elle documente la source du problème et 
            permet souvent d’appliquer un contournement en attendant la solution permanente.</p>
        </div>
      </details>
      <details class="step">
        <summary>Résolution définitive <span class="hint">— afficher détails</span></summary>
        <div class="note">
          La résolution définitive vise à <strong>éliminer complètement le problème</strong> (correctif logiciel, remplacement matériel, configuration permanente).
          Cette étape peut nécessiter un <strong>changement</strong> (via le processus de gestion des changements). 
          Lorsque la solution permanente est implantée et qu’il est prouvé que le problème est entièrement résolu, le problème est fermé.  Les incidents reliés à ce problème qui sont encore ouverts sont aussi fermés.  
        </div>
      </details>
      <details class="step">
        <summary>Clôture <span class="hint">— afficher détails</span></summary>
        <div class="note">
          Comme pour les incidents, la clôture doit être faite par le <strong>centre de services</strong>.
          Elle inclut la <strong>documentation complète</strong> du problème, des solutions testées et de la résolution finale, afin de capitaliser sur l’expérience pour l’avenir. 
          <p>L’<strong>erreur connue</strong> est finalement retirée (ou marque comme résolue) du système (base de connaissances) et le centre de services est avisé. Le tout afin d'éviter que les agents continuent d’appliquer un contournement alors que le vrai problème est réglé.</p>
        </div>
      </details>
    </div>
  </div>
</div>

### Vue d’ensemble : lien entre incidents et problèmes

Un **problème** regroupe plusieurs **incidents** qui partagent la même cause sous-jacente.  
- Les incidents sont d’abord ouverts individuellement par les utilisateurs.  
- Une fois qu’on découvre qu’ils proviennent d’une **même cause**, on les **associe** à un billet de problème.  
- Le problème devient la **“racine”** (la cause à investiguer), et les incidents deviennent ses **“enfants”**.  

Lorsque le problème est **résolu de manière permanente** :  
- le billet de problème est **fermé**   
- tous les incidents liés sont également **fermés** (automatiquement ou par le centre de services)
Ils sont considérés comme résolus par la même action. 

**Gain de cette démarche**  
- Éviter de traiter chaque incident isolément.  
- Assurer un suivi **centralisé** et **cohérent**.  
- Garder une **traçabilité claire** entre incidents, problème et solution finale.  
- Alimenter la **base de connaissances** avec les erreurs connues et leurs contournements. 


#### Exemple concret
- 15 utilisateurs ouvrent chacun un billet d’incident : *« Impossible d’accéder au serveur de fichiers »*.  
- Après analyse, un billet de **problème** est créé : *« Carte réseau défectueuse sur le serveur de fichiers »*.  
- Le problème est lié à tous les incidents similaires.  
- Une fois la **carte réseau remplacée**, le **problème est fermé** → tous les incidents liés sont **clôturés automatiquement**, puisque la cause racine est éliminée.
