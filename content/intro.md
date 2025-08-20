+++
pre = '<b>0. </b>'
title = "Introduction au support TI"
weight = 1
+++

Le soutien informatique est l’activité qui consiste à **assister les utilisatrices et utilisateurs** en diagnostiquant leurs incidents ou requêtes, puis en **appliquant et communiquant une solution vérifiée** pour rétablir un usage fiable et sécuritaire des ressources numériques.

{{< figure
    src="/420-310/images/soutien-canada.png"
    alt="Technicien·ne de soutien technique au Canada — Guichet-Emplois"
    caption="[Guichet-Emplois du Canada](https://www.guichetemplois.gc.ca/rapportmarche/profession/27302/ca;jsessionid=91C0F026FDEB73404DEB74C25F3BCFBB.jobsearch74)"
    link="https://www.guichetemplois.gc.ca/rapportmarche/profession/27302/ca;jsessionid=91C0F026FDEB73404DEB74C25F3BCFBB.jobsearch74"
>}}

{{< figure
    src="/420-310/images/agent-soutien-tech.png"
    alt="Agent de soutien technique — portrait de la profession"
    caption="Source : [Fiche métier — Agent de soutien technique](https://www.macarrieretechno.com/fr/carrières/professions/agent-de-soutien-technique)"
    link="[https://exemple/agent-soutien-tech.pdf](https://www.macarrieretechno.com/fr/carrières/professions/agent-de-soutien-technique)"
>}}

### Nuance service clients vs support technique
- **Service aux clients** = point de contact **relationnel** : accueillir la demande, clarifier le besoin et en faire le triage, rassurer, suivre l’avancement (relation + ticket).  
- **Support technique** = point de contact **technique** : diagnostiquer, corriger, valider la solution.

Les deux sont complémentaires : le service aux clients **prend en charge la relation** et **oriente** la demande, alors que le support technique **résout** (ou escalade) et **confirme** le rétablissement. 

> Les **titres de postes** varient, mais suivent souvent les **niveaux L1 → L2 → L3** (de l’accueil à l’expertise).

<!-- | Aspect | Service aux clients | Support technique |
|---|---|---|
| Rôle principal | Accueil, triage, suivi, communication | Diagnostic, correction, validation |
| Mesure clé | Satisfaction, délai de réponse | Qualité de résolution, non-régression |
| Compétences | Écoute, vulgarisation, priorisation | Méthodologie de dépannage, outils, sécurité | -->

### Qui fait quoi ? (vue d’ensemble)

| Terme (FR) | Anglais courant | Rôle principal | Niveau typique |
|---|---|---|---|
| **Agent·e de soutien aux utilisateurs** | Service desk / Help desk analyst | **Première ligne (L1)** : accueille, qualifie, crée le ticket, résout les cas simples, escalade si besoin. | L1 |
| **Technicien·ne en soutien informatique** *(poste de travail/terrain)* | Desktop/Workplace Support, Field Tech | Interventions **pratiques** sur les postes/perifs : préparation du matériel, installations, dépannages sur site. | L1–L2 |
| **Analyste support applicatif** | Application Support Analyst | Spécialiste d’une **application** : repro des bugs, paramètres, correctifs, lien avec l’équipe produit. | L2 |
| **Support technique** *(au sens large)* | Technical Support | Ensemble des **interventions techniques** au-delà de l’accueil (diagnostic poussé, corrections). | L2–L3 |
| **Admin. systèmes / réseaux / cloud** | Sysadmin / Network / Cloud Engineer | Gère **serveurs, réseau, sécurité** ; intervient en **escalade** et pour la stabilité de la plateforme. | L3 |
| **Centre de services TI** | IT Service Desk / Service Center | **Équipe/processus** qui opère l’accueil, le triage, le suivi, les niveaux et les SLAs. | Organisation |

> À retenir : *« Le service aux clients gère la **relation** et la **promesse** alors que le support technique gère la **cause** et la **preuve** que ça fonctionne. »*

<!-- ### Exemples rapides à donner
- **Service aux clients** : “Bonjour, je comprends le souci d’impression. Je crée le ticket, on priorise, je vous tiens informé(e) du prochain jalon.”  
- **Support technique (employés)** : “Préparation d’un nouvel ordinateur : image standard, chiffrement, MDM, création du compte, tests de connexion, remise avec check-list.”  
- **Support technique (serveurs)** : “Lenteurs applicatives : analyse logs/CPU, corrélation monitoring, correctif de config, test, validation et fenêtre de mise en prod.” -->
---
## Vocabulaire clé
- **Incident** = panne à rétablir · **Requête** = demande de service (accès, installation, matériel).  
- **Sévérité** (impact/urgence) ≠ **Priorité** (ordre de traitement fixé par la DTI).  
- **Workaround** (contournement) ≠ **Fix** (correction de la cause).

### Niveaux de sévérité / gravité 
<style>
  .sev-table { width:100%; border-collapse:collapse; font-size:0.95rem; margin:10px 0 }
  .sev-table th, .sev-table td { border:2px solid #555; padding:10px; vertical-align:top }
  .sev-table th { background:#eee; text-align:left }
  .sev-table tr.s1 td:first-child { background:#dc2626; color:#fff; font-weight:800 }
  .sev-table tr.s2 td:first-child { background:#f97316; color:#fff; font-weight:800 }
  .sev-table tr.s3 td:first-child { background:#f59e0b; color:#111; font-weight:800 }
  .sev-table tr.s4 td:first-child { background:#64748b; color:#fff; font-weight:800 }
  .sev-table tr.s5 td:first-child { background:#475569; color:#fff; font-weight:800 }
  .sev-table ul{ margin:.3rem 0 .2rem 1.1rem }
</style>

<table class="sev-table">
  <colgroup>
    <col style="width:16%">
    <col style="width:28%">  <!-- Description (plus étroite) -->
    <col style="width:32%">
    <col style="width:24%">
  </colgroup>
  <thead>
    <tr>
      <th>Sévérité</th>
      <th>Description</th>
      <th>Exemples</th>
      <th>Temps de réponse</th>
    </tr>
  </thead>
  <tbody>
    <tr class="s1">
      <td>S1 — critique</td>
      <td>Niveau de sévérité le plus élevé, souvent indiquant une panne complète du système ou une perturbation majeure affectant un grand nombre d'utilisateurs ou des opérations critiques.</td>
      <td>
        <ul>
          <li>Panne du serveur de messagerie d’entreprise</li>
          <li>Application critique hors service</li>
          <li>Violation de sécurité</li>
        </ul>
      </td>
      <td><strong>Immédiat</strong> : escalade au plus haut niveau et à la direction ; résolution priorité absolue.</td>
    </tr>
    <tr class="s2">
      <td>S2 — élevée</td>
      <td>Impact significatif sur les opérations commerciales ou un grand groupe d'utilisateurs, sans être une panne totale.</td>
      <td>
        <ul>
          <li>Service clé hors service pour un département</li>
          <li>Dégradation marquée d’un système critique</li>
          <li>Fonction importante indisponible</li>
        </ul>
      </td>
      <td>Une réponse <strong>rapide</strong> est nécessaire, le problème est traité dès que possible, mais il peut ne pas nécessiter une escalade immédiate.</td>
    </tr>
    <tr class="s3">
      <td>S3 — moyenne</td>
      <td>Gêne modérée affectant un petit groupe ; l’entreprise peut poursuivre ses activités. L'entreprise peut continuer à fonctionner, mais le problème doit être résolu en temps opportun.
      </td>
      <td>
        <ul>
          <li>Dysfonctionnement d’une application non critique</li>
          <li>Problème touchant un utilisateur ou un petit groupe</li>
          <li>Problème de performance mineur</li>
        </ul>
      </td>
      <td>La réponse et la résolution sont importantes mais peuvent être programmées <strong>pendant les heures de travail normales</strong>.</td>
    </tr>
    <tr class="s4">
      <td>S4 — faible</td>
      <td>Problèmes mineurs ayant peu ou pas d'impact sur les opérations commerciales. Il s'agit souvent de demandes non urgentes ou de problèmes qui n'empêchent pas les utilisateurs de travailler.
      </td>
      <td>
        <ul>
          <li>Problèmes cosmétiques / bugs mineurs</li>
          <li>Demandes d’information générale</li>
          <li>Demandes de fonctionnalité</li>
        </ul>
      </td>
      <td><strong>File standard</strong> : temps de réponse et de résolution basé sur la disponibilité des équipes.</td>
    </tr>
    <tr class="s5">
      <td>S5 — très faible / informatif</td>
      <td>Aucun impact opérationnel ; ticket consigné pour suivi ou référence.</td>
      <td>
        <ul>
          <li>Demande d’informations</li>
          <li>Documentation / mise à jour sans impact</li>
        </ul>
      </td>
      <td><strong>Priorité la plus basse</strong> : traité à la disponibilité.</td>
    </tr>
  </tbody>
</table>


### En bref
- **Niveaux (L1, L2, L3, L4)** = **qui** traite le ticket (compétence / profondeur technique).
- **Sévérité (S1…S5)** = **à quel point c’est grave** pour l’organisation (impact + urgence).
- On peut donc avoir un **ticket S1 traité par L3**, ou un **ticket S4 traité par L1** : ce sont **deux axes distincts**.

<!-- Exercice à faire 
### Comment ça se combine ? (exemples)
| Cas | Sévérité | Niveau initial | Remarques |
|---|---|---|---|
| Messagerie entreprise en panne | **S1** | **L1 → L2/L3** immédiat | L1 enregistre & alerte; L2/L3 prennent en charge (incident majeur). |
| Application d’un département ralentie | **S2** | **L1 → L2** | L1 vérifie le basique, L2 analyse performance; escalade L3 si bug. |
| Imprimante d’un usager ne répond plus | **S3** | **L1** | L1 suit la procédure, escalade L2 si échec. |
| Icône décalée dans une appli | **S4** | **L1** | À planifier; peut rester L1. |
| Demande d’information | **S5** | **L1** | Réponse informative, pas d’urgence. | -->
