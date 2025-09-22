+++
pre = '<b>1.1 </b>'
title = "Gestion d’un ticket d’incident"
weight = 1
+++

<!-- # pratiquer la gestion d'incidents  -->
# système de billetterie


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

<p>Lors de cet atelier, vous allez vous exercer à la gestion d’un incident à l’aide de <details class="gloss">
        <summary class="gloss-trigger">GLPI</summary>
        <div class="gloss-popup">
          <strong>GLPI</strong> est un outil open source de gestion des services informatiques. 
          Il permet de gérer :  
          <ul>
            <li> les <strong>incidents et demandes</strong> utilisateurs</li>
            <li> les <strong>actifs informatiques</strong> (ordinateurs, logiciels, périphériques, réseaux)</li>  
            <li> ainsi que les processus de <strong>maintenance et support</strong></li> 
          </ul>
          Lien vers le site officiel : <a href="https://glpi-project.org" target="_blank" rel="noopener">glpi-project.org</a>  alerte en cas de panne ou de dépassement de seuil.
          <div class="gloss-tip">Appuyez à nouveau pour fermer.</div>
        </div>
      </details>
      , et ce à travers un <strong>cas pratique</strong> inspiré d’une situation réelle en support technique.  
Vous apprendrez à enregistrer un billet, à le classifier, à en définir la priorité, à poser un diagnostic et à appliquer une résolution
</p>

### Le cas à l’étude
<div style="background-color:#f9f9f9; border:2px solid #ccc; border-radius:8px; padding:15px; margin:15px 0;">

Vous recevez un appel téléphonique de **Julie Tremblay**, employée du département administratif, qui rencontre des difficultés pour accéder à son application de gestion des horaires.  

Elle précise que tout fonctionnait correctement la veille (lundi), mais qu’aujourd’hui, lorsqu’elle tente de se connecter, elle reçoit le message suivant :  

<div style="background-color:#ffecec; border:1px solid #ff5c5c; border-radius:6px; padding:10px; margin:10px 0; color:#b30000; font-weight:bold; text-align:center;">
⚠️ Erreur : Accès refusé. Contactez l’administrateur.
</div>

Julie indique qu’elle doit obligatoirement soumettre ses horaires **avant mercredi 17h**, sinon elle risque un retard de paie.  
</div>

---

### Étape 1 : détection et enregistrement
Ici, **détection** est faite par l’utilisatrice (Julie) qui signale le problème. 
Lorsque vous répondez au téléphone, appliquez les pratiques de l’entreprises. Vous répondez à l’appel de façon professionnelle, par exemple : *« Bonjour, services informatiques, ici Sara, comment puis-je vous aider ? »* 

À des fins de suivi, vous allez **créer un billet dans GLPI**. 
1. Ouvrez GLPI et sélectionnez **créer un ticket**.  
2. ​Ensuite, renseignez les informations essentielles :  
   - demandeur : Julie Tremblay  
   - lieu : Bureau administratif (à confirmer avec elle)  
   - description :  
     *« Un problème d’accès à l’application HorairePro. Message : Accès refusé. Contactez l’administrateur. »*  
   - titre : *Problème d’accès – HorairePro*  

Une bonne pratique est de **mentionner à l’utilisateur ce que vous faites**, afin qu’il ne soit pas laissé dans l’incertitude.  
Vous voulez qu’il se sente pris en charge et accompagné. Vous n’avez pas besoin d’expliquer chaque détail technique, mais simplement les grandes étapes.  

<strong>Exemple de formulation :</strong>
<div style="background-color:#fff8e6; border-left:5px solid #ff9900; padding:10px; margin:10px 0; border-radius:6px;">
<em>👩‍💻 :</em> « Je vais ouvrir un incident et l’assigner à votre nom, donnez-moi quelques instants… merci de votre patience. »<br><br>
<em>👩‍💻 :</em> « Alors, maintenant, j’aimerais confirmer avec vous que votre poste de travail est toujours situé au bureau administratif. Est-ce exact ? »
</div>

Lorsque vous ouvrez le billet, si vous avez pris rapidement des notes, validez-les avec l’utilisatrice.  

<strong>Exemple de validation :</strong>
<div style="background-color:#fff8e6; border-left:5px solid #ff9900; padding:10px; margin:10px 0; border-radius:6px;">
<em>👩‍💻 :</em> « Donc, si j’ai bien compris, vous avez tenté de vous connecter à l’application HorairePro pour compléter vos horaires et vous avez eu le message d’erreur <span style="color:#b30000; font-weight:bold;">Accès refusé. Contactez l’administrateur.</span> Exact ? »<br><br>
<em>👩‍💻 :</em> « Pour m’assurer de transférer l’incident à la bonne équipe, est-ce bien le logiciel HorairePro que vous utilisez pour vos feuilles de temps ? »
</div>

---

### Étape 2 : classification et priorisation
Vous devez sélectionner, dans le champ **catégorie**, la catégorie appropriée pour classifier l’incident. Il est donc essentiel de se familiariser avec le système de classification de l'entreprise (catégories ITIL).​

**Exemple** :  
  - Accès → *Accès à une application* → *Application HorairePro*  

Cela permet de classer correctement l’incident pour le suivi. Associez ensuite l’item concerné :  
  - Logiciel : HorairePro (s’il a été ajouté à l’inventaire des assets).

Vous devez, ensuite, déterminer le niveau de **priorité** de l’incident.  
Pour ce faire, référez-vous à la **matrice d’impact et d’urgence** afin d’évaluer correctement la situation.  

**Exemple d’évaluation** :  
- Impact : seul Julie est affectée par le problème → Impact = *Bas*.  
- Urgence : elle doit soumettre ses horaires avant jeudi 16h → Urgence = *Moyenne*.  
- Priorité : en combinant impact et urgence, on obtient une priorité = *P3 – Moyenne*.

<strong>À considérer</strong>  
<div style="background-color:#fdfdfd; border-left:4px solid #6c8ebf; padding:12px 16px; margin:16px 0; border-radius:6px; font-size:0.95em; line-height:1.6;">
Dans ce cas, une <strong>urgence moyenne</strong> correspond à un temps de résolution de <strong>72 heures ou moins</strong>, ce qui nous amènerait à <em>vendredi</em>.  

Cependant, en tenant compte de l’importance de la tâche (soumission des horaires avant mercredi 17h), vous jugez que ce délai est trop serré et décidez d’opter pour une <strong>urgence élevée</strong>.  

La priorité qui en résulte est établie à <strong>moyenne (P3)</strong>.  
</div>

---

### Étape 3 : diagnostic
L’organigramme de dépannage (flowchart) sert de **guide visuel** pour analyser et résoudre un incident.  
Ouvrez le diagramme et démarrez votre résolution à partir du **déclencheur (le problème signalé)**.  

**1. définir le problème**
Vous disposez déjà d’assez d’informations pour commencer :  
- un message d’erreur s’affiche (*Accès refusé. Contactez l’administrateur.*),  
- vous savez quelle application est touchée (HorairePro),  
- vous savez quel utilisateur rencontre la difficulté (Julie Tremblay),  
- vous savez dans quel contexte l’erreur survient (tentative de connexion).  

**2. collecter les informations pertinentes**  
Confirmez ces informations auprès de l’utilisatrice, puis demandez plus de détails si néecessaire :  
- « Pouvez-vous me préciser depuis quand ce problème est apparu exactement ? »  
- « Avez-vous essayé de vous connecter à partir d’un autre poste ou navigateur ? »  
Ces détails vous permettront de confirmer que le problème n’est pas lié à un mauvais usage ou à un poste de travail spécifique.  

**3. analyser les informations**  
Votre objectif est clair : résoudre le problème de connexion à l’application HorairePro.  
- Vérifiez si d’autres utilisateurs sont touchés.  
- Vérifiez si le problème est temporaire (ex. : maintenance, coupure réseau).  

**4. vérifier si le problème est connu**  
Avant de proposer une solution, demandez-vous :  
- Est-ce un problème **déjà documenté** dans la base de connaissances GLPI ?  
- Existe-t-il une **solution de contournement** déjà utilisée dans le passé ?  

---

### Étape 4 : affectation et résolution
- Vous appliquez la solution : demandez à Julie de fermer et redémarrer l’application.  
- Elle confirme que l’accès fonctionne à nouveau.  
- Notez la résolution dans GLPI :  
  *« Redémarrage de l’application HorairePro → accès rétabli »*.  
- Changez le statut du ticket en **Résolu**.

​### Étape 5 : Affectation ou escalade

À ce stade, plusieurs scénarios peuvent se présenter :  
- Vous avez trouvé une **solution** ou un **contournement** et vous êtes en mesure de l’appliquer directement.  
- Vous avez trouvé une solution ou un contournement, mais vous ne disposez pas des **droits d’accès** ou des **autorisations nécessaires** pour l’exécuter.  
- Vous n’avez identifié **aucune solution** et vous manquez de temps pour pousser l’investigation.  
- Le problème dépasse vos **compétences techniques** et doit être pris en charge par une équipe spécialisée.  

Enfin, si vous êtes dans la première situation, vous pouvez passer directement à l’étape suivante : la **résolution**  
sinon, dans les autres cas, l’incident doit être **transféré au groupe approprié**.  
  
L’**escalade**, dans GLPI, se fait simplement en sélectionnant le bon **groupe** dans le champ *Attribué à*.  
Vous aurez l’occasion de mettre cela en pratique dans un autre atelier.  

---
### Étape 5 : résolution de l’incident
Afin de résoudre l’incident, vous proposez à **Julie Tremblay** de fermer complètement l’application **HorairePro**, puis de vider la session active (fermer l’onglet du navigateur et effacer les cookies si nécessaire).  
Ensuite, vous lui demandez de relancer l’application et de tenter une nouvelle connexion.  
- Après ce test, Julie confirme qu’elle peut maintenant accéder à son compte sans message d’erreur.  

Vous en profitez pour **expliquer** que ce type d’erreur se produit parfois lorsque la connexion entre le poste de travail et le serveur de l’application est interrompue : dans ce cas, fermer puis rouvrir l’application permet souvent de rétablir la communication.  

Vous donnez également un **conseil préventif** à l’utilisatrice :  
si elle rencontre à nouveau le même problème, elle peut essayer cette méthode de base avant de contacter le service informatique.  

<!-- Notez qu’ici nous n’avons pas publié l’entrée de la base de connaissances à tous les utilisateurs.  Nous aurions pu la publier en mode FAQ.  Dans ce mode, l’utilisateur peut faire ses propres recherches de solutions.​
Cependant, même si une entrée existe dans la FAQ, soyez indulgents envers les utilisateurs qui préfèrent contacter le centre de services aux utilisateurs.  Certaines personnes ne sont pas à l’aise avec les technologies ou se sentent insécures de tenter des résolutions par eux-mêmes.​ -->

### Étape 6 : clôture
Une fois la résolution effectuée, la première action consiste à **vérifier la classification** du billet.  
En effet, il arrive que la véritable cause du problème ne corresponde pas à la catégorie initialement choisie.  
C’est donc à ce moment qu’il faut corriger la classification si nécessaire, afin de garder des statistiques fiables et cohérentes.  

Ensuite, descendez au bas du billet et utilisez le **bouton réponse** :  
- Cliquez sur la flèche (▾) du bouton **réponse**.  
- Choisissez l’option **ajouter une solution**.  
- Rédigez votre solution de manière claire et concise.  
- Cliquez sur **ajouter** pour l’enregistrer.  
- Notez que l’incident est passé à l’**état clos**, le billet est maintenantfermé.​

--- 

Vous avez suivi toutes les étapes d’un traitement d’incident dans GLPI :  
1. Création du ticket (enregistrement du problème).  
2. Classification (catégorie).  
3. Priorisation (impact et urgence).  
4. Diagnostic (base de connaissances).  
5. Résolution (solution appliquée).  

Ce cas pratique vous permet de vous mettre dans la peau d’un agent du support technique et de vous familiariser avec les bonnes pratiques ITIL dans GLPI.

-----

## Exercice – Gestion complète d’un ticket 

À travers cet exercice, vous allez mettre en pratique la création, l’assignation et la résolution d’un ticket à l’aide de GLPI.

- À partir des cas analysés lors du dernier cours, dans le cadre de l'atelier du bloc 1, vous allez créez un ticket dans GLPI sur l'un des deux scénario. Assurez-vous de remplir les informations essentielles, et assignez le ticket à l’un de vos collègues.

- Vous recevrez par conséquent, un ticket qui vous aura été assigné également. Votre tâche sera de le résoudre dans GLPI en suivant les bonnes pratiques vues en classe.

Notez que la validation finale des tickets sera effectuée uniquement par l’administrateur (votre enseignante). Vous ne pouvez donc pas fermer définitivement un ticket par vous-même.