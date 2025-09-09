
+++
pre = '<b>1.3 </b>'
title = "Identification de la source du problème "
weight = 3
+++
La présente leçon vise à vous entraîner à **distinguer** divers **types d’informations** : **faits**, **symptômes**, **présomptions**, **informations non pertinentes**, et **déductions**.​

Apprendre à les reconnaître rapidement est la base pour vous permettre d'**identifier la cause d’un problème** et démarrer une résolution efficace.

### Les faits 
<!-- La définition de faits n’est pas facile à établir.  Un fait se veut, par définition, une vérité.  À l’époque où nous vivons, les faits alternatifs (fake news) pullulent et la vérité est souvent une opinion personnelle face à une situation donnée.​
Sans oublier les situations où une information est vraie à une certaine époque, puis démentie plus tard.  Il suffit de regarder diverses études dans le domaine alimentaire pour découvrir des aliments bons pour la santé, ou mauvais, selon les études et les époques.  Bref, notre objectif n’est pas de lancer un débat sur ce sujet.  Pour nous, un fait est: ​-->
- Un **fait** est une information **vérifiée** (ou **directement observable**) et **traçable**.
- À défaut, on accepte temporairement une info **tenue pour vraie** si la **source est fiable**, mais on la **valide** dès que possible.
<!-- une information qui a été validée.  Ex: je constate que l’ordinateur est éteint.​
une affirmation que nous tenons pour vraie jusqu’à preuve du contraire, en autant que la source de cette information soit fiable.  Ex: l’enseignant(e) affirme que l’examen sera facile. -->

<!-- **Comment tester qu’une info est un fait ?**
- [ ] Observée **par vous** ou confirmée par **deux sources indépendantes**  
- [ ] **Mesurable** (horodatage, capture, log, métrique)  
- [ ] **Reproductible** (mêmes conditions → même résultat)  
- [ ] **Ne dépend pas** d’une opinion ou d’une interprétation -->

**Les pièges fréquents**
- Contexte qui **évolue** (un fait vrai hier ne l’est plus aujourd’hui).  
- **Biais de confirmation** : on sélectionne seulement les faits qui confirment notre intuition.

##### Exercices

**Les 3 maisons**

À partir des informations suivantes, situez chacune des maisons (noire, rouge, bleue) sur la rue:
<img src="/420-510/images/exo-maison.png" alt="Exo maisons" width="420" style="height:auto; display:block; margin:0 auto;">

- La maison **noire** est **au centre**.  
- La maison **rouge** n’est **pas** au centre : elle est **près de la borne**.  
- La maison **bleue** est **la plus éloignée** de la borne.
<!-- La maison noire est au centre: donc en B.​
La maison rouge n’est pas au centre donc pas en B: elle est près de la borne fontaine donc en A.​
La maison bleue est la plus éloignée de la borne fontaine donc en C. -->

**Le passage**

**3 technicien·ne·s** doivent traverser un tunnel étroit de nuit.
Il n’y a qu’**une seule lampe** et **au plus deux personnes** peuvent être **dans le tunnel en même temps**.
Quand deux personnes traversent ensemble, **la durée est celle de la plus lente**.
La lampe doit toujours être ramenée de l’autre côté par une personne.

Le temps individuels de traversée :
- A : 2 min
- B : 5 min
- C : 9 min

Objectif : tout le monde de l’autre côté en **≤ 17 minutes**.
<!-- Idée clé (3 personnes) : faire traverser le plus lent avec le plus rapide, puis le plus rapide revient, puis le plus rapide accompagne le 2ᵉ plus lent.
Formule : C + A + B.

Séquence optimale
A + C traversent → 9 min (la plus lente = C)
A revient → +2 min ⇒ 11 min
A + B traversent → +5 min ⇒ 16 min
Total = 16 min → Objectif atteint (≤ 17 min). -->

**Variante bonus (4 personnes)**

En appliquant les mêmes règles. 

Le temps individuels de traversée :
- A : 1 min
- B : 2 min
- C : 6 min
- D : 10 min

Objectif : tout le monde traverse en **≤ 17 minutes**. 
<!-- Deux stratégies “classiques” :

Stratégie A (navette du plus rapide)
1+10 → 10
1 ← → +1 = 11
1+7 → +7 = 18
1 ← → +1 = 19 (trop long)

Stratégie B (deux rapides se passent la lampe)
1+2 → 2
1 ← → +1 = 3
7+10 → +10 = 13
2 ← → +2 = 15
1+2 → +2 = 17 ✅

Conclusion : Oui, en 17 min avec la stratégie B. -->
---
### Les déductions
- Une **déduction** est une information **nouvelle** obtenue par **raisonnement logique** à partir de **faits** (elle **n’apparaît pas** telle quelle dans la liste des faits).

**Une méthode rapide**
1. Lister les **faits sûrs**.  
2. Écarter ce qui est **impossible** (contradictions, extrémités, etc.).  
3. Conclure ce qui **reste nécessairement vrai**.  
4. Finalement, **marquer** la déduction (ex. « donc en B »)pour l'exercice des maisons.

##### Exercices

**Les 4 maisons**

À partir des informations suivantes, situez chacune des maisons (noire, rouge, bleue, verte) sur la rue:
<img src="/420-510/images/exo-4-maisons.png" alt="Exo maisons" width="420" style="height:auto; display:block; margin:0 auto;">

- La **noire** est la **plus éloignée** de la borne.  
- La **bleue** est **près** de la borne et **pas** à une **extrémité**.  
- La **verte** est elle aussi **près** de la borne.  
<!-- La maison noire est la plus éloignée de la borne fontaine donc en D.​
La maison bleue est près de la borne fontaine, et n’est pas à une des extrémités de la rue donc pas en A ni en D (extrémités); il ne reste que B près de la borne fontaine.  Ceci est une déduction !​
La maison verte est elle aussi près de la borne fontaine donc près de la borne fontaine il ne reste que A de libre.​
La maison rouge n’est pas mentionnée dans les faits.  Par déduction, vous voyez qu’il ne reste que C de libre.​ -->

--- 
### Les informations non pertinentes
<!-- Une des plus grande difficulté dans la résolution de problèmes est de distinguer les informations pertinentes de celle qui le sont moins, ou ne le sont pas.  Certaines informations non pertinentes peuvent nous diriger dans des pistes de solutions erronées et ainsi nous ralentir dans la résolution du problème. -->
<!-- Par exemple, votre ordinateur est très lent et votre collègue vous avise qu’un problème est connu avec la dernière mise à jour de Windows.  En effet, à la suite de cette mise à jour, plusieurs personnes ont un souci de lenteur d’ordinateur.  Votre collègue vous avise que vous devez attendre le correctif de Microsoft qui sera disponible demain.​
Le lendemain, le correctif est installé sur votre ordinateur qui demeure tout aussi lent.  Vous découvrez alors que votre ordinateur n’était pas affecté par le mise à jour problématique et que la lenteur est causée par une défectuosité du disque dur.​ -->
**Idée clé**
- Elles **parasitent** le diagnostic, créent des **fausses pistes** et font perdre du **temps**.

**Exemple typique**
- « beaucoup ont eu un problème après la **mise à jour Windows** » → on attend un correctif…  
  **Le lendemain** : votre poste est **toujours lent** → c’était en fait un **disque défectueux**.  
  👉 L’info « mise à jour problématique » était **non pertinente** pour *votre* cas.

---

### Les présomptions
<!-- Les présomptions sont des informations qu’on présume vraies.  Elles sont souvent basées sur une opinion, ou sont de nature instinctive (gut feeling).​ -->
- Une **présomption** est une **hypothèse** tenue pour vraie **sans validation** ; souvent basée sur une opinion, ou sont de nature instinctive (intuition, rumeur, *gut feeling*).

**Les dangers**
- Est décidé comme si c’était un **fait**.  
- Effet de **groupe** (*group thinking*) : une voix influente entraîne tout le monde.
<!-- Le danger est de décider, sans aucune vérification, qu’une présomption est un fait.  Ce danger se produit souvent en réunion, où les participants adoptent, par effet de groupe (group thinking), une information en la faisant vérité.  En effet, il suffit généralement qu’un participant, ayant la confiance des autres, lance une information en la faisant passer pour un fait, pour que les participants adoptent cette nouvelle vérité, sans aucune forme de vérification.  La désinformation se propage beaucoup à travers de tels groupes où un membre influent propage des informations erronées dans lesquelles il croit.​
Les autres membres du groupe adoptent cette vérité sans aucune vérification puisqu’elle provient d’un membre influent du groupe, souvent le leader.​ -->

<!-- Exemple ne pas parler entre témoins apres un crime, attendre de faire déposition à la police  -->

**Comment neutraliser ?**
- [ ] Essayer de reformuler en **hypothèse testable** : « Nous **pensons que**… si c’est vrai, on **observera**… ».  
- [ ] **Exiger la source** et un **élément de preuve**.  
- [ ] Chercher un **test de réfutation** (que devrait-on voir si c’était **faux** ?).  
- [ ] Tracer l’état : **présumé** → **en test** → **confirmé/invalidé**.

---
### Les symptômes
<!-- Les symptômes sont des effets observables et souvent mesurables du problème.  Trois des symptômes les plus communs en médecine: la douleur, les maux de tête et la fatigue.  Ils sont un effet d’un ennui de santé et rarement l’ennui de santé lui-même.  Le médecin doit donc identifier la source du problème pour le résoudre, ce qui éliminera les effets.​ -->
- Effets **observables** (souvent **mesurables**) d’un problème : lenteur, gel, erreur, crash, redémarrages, etc.  
  (Ex. trois des symptômes les plus communs en médecine: la douleur, les maux de tête et la fatigue)
- Un **symptôme n’est pas la cause** : la prudence s’impose pour ne pas apporter une solution qui élimine les symptômes sans résoudre la situation.  
  (Ex. redémarrer un serveur d’application deux fois par jour car l’application gèle : le gel de l’application est un symptôme)
<!-- Pourquoi l’application gèle?  Le serveur manque-t-il me mémoire vive?  La configuration du serveur ou de l’application limite-t-elle la taille de la mémoire utilisable par l’application?  Y a –t-il trop de transactions et l’application n’arrive pas à répondre?​
Bien entendu, le redémarrage peut aider à rendre le système fonctionnel, pendant qu’on cherche la cause et résoudre le problème une fois pour tout.  Comme les analgésiques calment la douleur pendant que le médecin investigue.​ -->

**Attention aux “pansements”**
- Le redémarrage d'un serveur qui gèle **ne résout pas** la cause ; c’est un **contournement**.  
- Analogie médicale : un **analgésique** calme la douleur pendant que le médecin **cherche la cause**.

**Que faire avec les symptômes ?**
- [ ] Les **décrire précisément** (quoi, quand, fréquence, durée).  
- [ ] Tenter de les **reproduire** (étapes).  
- [ ] **Mesurer** (CPU, RAM, I/O, latence, logs corrélés).  
- [ ] Documenter les **conditions** (charge, pics, version, changement récent).  
- [ ] Mettre éventuellement un **workaround** (accepté par le métier) le temps d’investiguer.

---

### ​Exercice recapitulatif
**5 personnes** habitent **cinq maisons** d’alignement différent sur la rue Georges :
**Javier**, **Antoine**, **Hakim**, **Clémence**, et **Aïsha**.
Chaque maison a une couleur différente (**rouge**, **bleue**, **verte**, **jaune**, **orange**) et chaque personne possède un **animal de compagnie** différent (**chat**, **chien**, **oiseau**, **tortue**, **iguane**).

À partir des informations suivantes, résolvez l’énigme, soit de déterminer **dans quelle maison chacun habite, et avec quel animal**.​

- Le chat habite la maison jaune.​
- La personne qui réside dans la maison orange travaille en TI.​
- Antoine n’aime pas les chats à cause de sévères allergies.​
- Hakim habite la maison bleue.​
- L’animal de Clémence a des ailes avec des tâche de la même couleur que sa maison, et ce ne sont pas des tâches rouges.​
- Javier habite la maison au bout de la rue.​
- L’animal de Javier n’a ni plumes ni poils.​
- La personne qui travaille en TI a un chien.​
- La grand-mère de Naomie habite la maison brune, à côté du pompier qui a un poisson rouge.​
- Derrière la maison bleue il y a un jardin où la tortue aime se promener et manger des laitues.​
- Notes safa Les diff façons de recherche cause d’un prob 

--- 
### Le processus de dépannage (*troubleshooting*)
Le but est de remonter à partir de l’**effet observé** (symptômes) jusqu'à la **cause racine**, puis appliquer une **solution vérifiable**.

**Organigramme de dépannage (flowchart)**

Outil visuel utilisé pour guider pas à pas le diagnostic : chaque **étape** (test ou action) mène à une **décision** (oui/non) qui oriente vers la **prochaine étape** jusqu’à la résolution. Il prend la forme d'un diagramme de flux (*flowchart*) généralement lié à la résolution de problèmes techniques, des machines, des systèmes informatiques ou des processus industriels.

{{< figure
    src="/420-510/images/troubleshooting.png"
    alt="troubleshooting"
    link="https://limblecmms.com/blog/what-is-troubleshooting/"
>}}

##### Les caractéristiques d’un bon organigramme
- **Début / fin clairs** (conditions d’entrée, critères de sortie).
- **Questions conditionnelles** simples (oui/non) et non ambiguës.
- **Actions spécifiques** (commande exacte, emplacement du log, valeur attendue).
- **Décisions alternatives** prévues (branche A/B selon résultat).
- **Extensible (scalable)**: facile à enrichir avec de nouveaux cas sans tout refaire.

