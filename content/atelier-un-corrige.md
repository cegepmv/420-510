<!-- ### Exercice 1 : une documentation claire

CORRIGÉ (proposition)
1) Faits & symptômes (vérifiables)
- OS/Matériel : HP EliteBook, Windows 11 23H2, Intel Iris Xe.
- Appli/Version : GéoCarto Pro v5.14.2.
- Affichage : Dock USB-C DisplayLink; écrans : 2560×1440 en portrait + LCD portable 1920×1200; échelle 125 %.
- Erreur au lancement avec dock : Render init failed — code 0xC004 / invalid size; splash puis fermeture.
- Journal client.log : DesiredScreen 1920x1080 not supported, fallback failed + GL init failed.
- Config : config.txt → ScreenSize= vide.
- Comportement : Sans dock → l’appli démarre; Avec dock → échec.
- Action testée : ScreenSize=1280x800 → OK même avec dock.
- Mises à jour : KB5034xxx la veille; pilote graphique installé (imprécis).
- DisplayLink local 5.6.x; 5.8.0 dispo.

2) Actions tentées & résultats (court, action → résultat)
- Redémarrage Windows → échec.
- Débrancher/rebrancher écran → échec.
- Windows Update / pilote GPU → empire (splash → fermeture).
- Désactiver antivirus 5 min → aucun effet.
- Démarrer sans dock → succès (appli OK).
- Éditer config.txt → ScreenSize=1280x800 → succès avec dock.
- (Optionnel) MAJ DisplayLink 5.8.0 → à planifier/tester (non encore fait).

3) Présomptions (non vérifiées / opinions)
- Le câble rouge sur le port gauche explique le bug.
- Le thème sombre ou la couleur du câble influence le rendu.
- La mise à jour Windows est forcément la cause.
- Le Wi-Fi qui clignote a cassé Outlook et GéoCarto.

4) Déductions (raisonnement à partir des faits)
- L’échec uniquement avec le dock + log DesiredScreen … not supported ⇒ problème lié à la configuration d’affichage/résolution.
- Le champ ScreenSize= vide empêche le fallback → init GL échoue.
- Fix fonctionnel en forçant une résolution supportée (1280×800) ⇒ la cause probable est un ScreenSize invalide (interaction multi-écrans/portrait + DisplayLink).
- Antivirus et réseau/Outlook non impliqués (tests négatifs).

5) Infos non pertinentes (à ignorer dans la doc)
- Scrum, muffins, imprimante du 3e, câble “rouge”, thème sombre, café sur le bureau (pas sur le PC), Wi-Fi qui clignote (sans lien), l’autre Naomie de la compta.

6) Note d’incident — version « propre » (exemple)
- Symptôme : GéoCarto Pro ne démarre pas avec dock DisplayLink (2 écrans : 2560×1440 portrait + 1920×1200). OK sans dock.
- Logs : DesiredScreen 1920x1080 not supported, fallback failed / GL init failed.
- Constat : config.txt → ScreenSize= vide.
- Action : Défini ScreenSize=1280x800 → l’appli démarre (avec dock).
- Hypothèse : ScreenSize invalide + multi-écrans/portrait (DisplayLink).
- Suivi : Planifier MAJ DisplayLink 5.8.0, vérifier liste résolutions supportées; si récurrence → ouvrir bug chez l’éditeur (fallback quand ScreenSize vide).
- Impact : Utilisatrice opérationnelle (2 écrans conservés).


Grille de correction (rapide)
- Faits/Symptômes clairs (≥8 items) — 4 pts
- Actions & résultats au format action → résultat — 4 pts
- Présomptions vs Déductions bien séparées — 4 pts
- Non pertinentes élaguées — 2 pts
- Note finale courte, exploitable — 6 pts
 -->


# ATELIER BLOC 1 — Exercice 1 · Documentation adéquate (corrigé)

Vous trouverez ci-dessous, pour **chaque cas**, une réponse structurée et directement exploitable dans un ticket :  
**Faits & symptômes**, **Actions & résultats**, **Déductions**, **Présomptions**, **Infos non pertinentes**, **Classification**, **Prochaines étapes** et une **Note d’incident** concise.

---

## CAS A — Ordinateur en panne (Martine)

### Fiche synthèse
| Élément | Détail |
|---|---|
| **Utilisateur** | Martine |
| **CI/Service** | Poste **Dell (tour)** — modèle à confirmer |
| **Catégorie** | **Matériel** → **PC** → **Démarrage/POST** |
| **Impact** | 1 personne (poste inutilisable) |
| **Urgence** | Haute (rapports à envoyer) |
| **Sévérité / Priorité** | **S2 / P2** *(impact bas × urgence haute)* |
| **Niveau & Équipe** | **N2 — Matériel/terrain** (diagnostic matériel / beep codes) |

### Faits & symptômes (observables/vérifiables)
- À l’allumage : **court bruit**, puis **écran noir**.
- **Témoin** en façade **clignote 3 fois**, pause, **répète** (pattern).
- Parfois un **bip** avant arrêt.
- **Changement d’écran** (écran de Damien) → **même problème** (donc **pas l’écran**).
- **Redémarrages multiples** → **aucun effet**.
- **PC fixe Dell**, modèle non relevé (étiquette à l’arrière).

### Actions tentées & résultats (1 action → 1 résultat)
- **Redémarrer** via le bouton → **échec** (symptôme identique).
- **Tester avec un autre écran** → **échec** (pas d’affichage).
- **Débrancher/rebrancher l’alimentation** → **échec** (symptôme identique).

### Déductions (basées sur les faits)
- **Affichage absent** + **beep/pattern LED** au POST ⇒ probable **erreur matérielle** (RAM / GPU / Alim / CM).
- Le test **avec autre écran** isole **le PC** comme source du problème (pas l’écran).
- **Pattern LED “3 clignotements”** sur Dell correspond souvent à **RAM non détectée** ou **défaillante** *(à confirmer sur le guide de codes Dell du modèle exact)*.

### Présomptions (à écarter / non vérifiées)
- ~~Le café au 4ᵉ étage influence le démarrage~~  
- ~~Le “vroum” signifie que le disque est bon/mauvais~~ (interprétation sans test)

### Infos non pertinentes (bruit)
- ~~Qualité de la machine à café~~  
- ~~“Vroum” décrit de façon subjective~~  
- ~~Rapports “ultra importants”~~ *(sert à l’urgence métier, mais pas au diagnostic technique)*

### Classification & décision
- **Catégorie** : Matériel → PC → Démarrage/POST  
- **Sévérité / Priorité** : **S2 / P2** (1 utilisateur bloqué, urgence haute)  
- **Niveau assigné** : **N2 Matériel** (intervention terrain / ouverture châssis)

### Prochaines étapes (plan testable / N2)
- **Identifier le modèle Dell** (service tag) + consulter la **table LED/bip** du fabricant.  
- **Power drain** (débrancher, maintenir power 30 s).  
- **Tester RAM** : retirer/resserrer barrettes, boot **avec 1 barrette** en slot recommandé, **swap** si plusieurs.  
- **CMOS reset** si nécessaire.  
- Si échec → **diagnostic PSU/GPU/CM** (carte graphique dédiée si présente).  
- Documenter **code LED/bip** confirmé + résultat de chaque essai.

### Note d’incident (prête à coller)
- **Symptôme** : PC Dell — **écran noir** au démarrage, **LED façade : 3 clignotements** en boucle, **bip** occasionnel.  
- **Tests** : autre écran → **KO** (donc pas l’écran) ; redémarrages/AC off → **KO**.  
- **Contexte** : modèle Dell non relevé (étiquette arrière).  
- **Déduction** : échec **POST** probable (**RAM**/GPU/PSU/CM).  
- **Décision** : **N2 Matériel**. Plan : relever **service tag**, vérifier **codes Dell**, **power drain**, tests **RAM** (1 barrette / slots), **CMOS reset**, puis diag **PSU/GPU/CM**.  
- **Sévérité/Priorité** : **S2 / P2** (utilisateur bloqué — urgence haute).

---

## CAS B — Impression difficile (poste SMOREAU-LP)

### Fiche synthèse
| Élément | Détail |
|---|---|
| **Utilisateur** | Service RH (poste **SMOREAU-LP**) |
| **CI/Service** | **Impression** — file locale **Kyocera_TA-M5526cdw_1A12** |
| **Catégorie** | **Périphériques** → **Impression** → **Qualité/Erreur format** |
| **Impact** | 1 poste (documents RH urgents) |
| **Urgence** | Haute (production jour même) |
| **Sévérité / Priorité** | **S2 / P2** *(impact bas × urgence haute)* |
| **Niveau & Équipe** | **N1 Impression** (pilotage/queue), escalade **N2 Systèmes** si file serveur/driver |

### Faits & symptômes (observables/vérifiables)
- **Lenteur** / **aucune sortie** ; parfois **format incorrect** ou **décalage**.
- Un job PDF (**BULLETIN_Paie_Sep25.pdf**) a **“terminé avec erreur”**.
- **Imprimante par défaut** (système) : **Kyocera_TA-M5526cdw_1A12**.
- **Pilote** installé : **KX Universal v8.2 (10/09/2025)**.
- **Statut** : **Connectée – Pas de bourrage – En attente**.
- **Autres files** présentes : **HP_OpenSpace2**, **PDF Creator**, **Fax_Machine**.
- Utilisateur dit avoir **sélectionné “l’imprimante HP”** (habitude).

### Actions tentées & résultats (1 action → 1 résultat)
- **Redémarrage** du poste → **aléatoire** (problème persistant).  
- **Tester autres documents** (Excel/PowerPoint) → **symptômes variables** (toujours non fiable).

### Déductions (basées sur les faits)
- Le système **envoie** vers **Kyocera** (par défaut), tandis que l’utilisateur **pense** imprimer sur **HP** → **risque d’imprimante cible incorrecte**.  
- Sortie **illisible / caractères** → **mauvais langage d’impression** (PCL/PS) ou **pilote inadéquat** pour la file utilisée.  
- **Job en erreur** + **aléatoire** → possible **mélange de drivers** / mauvais **profil papier** / file **non alignée** avec le périphérique réel.

### Présomptions (à écarter / non vérifiées)
- ~~“Réinstaller le pilote” résout tout~~ (à vérifier après tests ciblés)  
- ~~“Parce qu’on a toujours utilisé l’HP, ça doit être l’HP”~~ (fait contredit par la **file par défaut Kyocera**)

### Infos non pertinentes (bruit)
- ~~Localisation physique (“près du panneau Ne pas laisser de documents…”)~~  
- ~~Historique “d’habitude ça marche même les gros PDF”~~ (non probant pour ce cas)

### Classification & décision
- **Catégorie** : Périphériques → Impression → Qualité/Erreur format  
- **Sévérité / Priorité** : **S2 / P2** (urgence du jour, 1 poste)  
- **Niveau assigné** : **N1 Impression** (pilotage, file, driver). Escalade **N2** si file réseau/serveur en cause.

### Prochaines étapes (plan testable / N1)
1. **Vérifier imprimante cible** dans l’app au moment de l’impression (**Kyocera vs HP**). **Forcer la bonne file**.  
2. **Imprimer une page de test** Windows depuis **Paramètres > Imprimantes** sur **Kyocera_TA-M5526cdw_1A12**.  
3. **Effacer la file** (jobs en attente), puis retester le **PDF problématique**.  
4. **Changer le pilote** si sortie illisible : **KX PCL6** ↔ **KX PS** (selon modèle), puis retester.  
5. **Vérifier format papier** (A4/Lettre), **orientation**, options **Recto/Verso**, **Échelle 100 %** dans le driver.  
6. Si KO : **tester l’autre imprimante (HP_OpenSpace2)** pour isoler **CI** ; si OK sur HP ⇒ **problème file Kyocera** → **N2** (partage/serveur/driver).

### Note d’incident (prête à coller)
- **Symptôme** : impressions **lentes/absentes** ou **illisibles/décalées** sur **Kyocera_TA-M5526cdw_1A12** (SMOREAU-LP).  
- **Contexte** : **KX Universal v8.2**, job PDF “**BULLETIN_Paie_Sep25.pdf**” **en erreur**.  
- **Déduction** : cible **Kyocera** alors que l’utilisateur pense à **HP** ; **driver/langage** potentiellement inadéquat (**PCL vs PS**).  
- **Plan N1** : vérifier **file sélectionnée**, **vider file**, **page de test**, **alterner driver KX PCL6/PS**, **vérifier format/échelle** ; si échec → **test HP_OpenSpace2** pour isoler, puis **N2** si file Kyocera en cause.  
- **Sévérité/Priorité** : **S2 / P2** (documents RH urgents).

---







## Exercice 2 — Rédiger une procédure (courriel de support)

Un·e utilisateur·rice **débutant·e** sous **Excel** vous demande comment reproduire la **grille** ci-dessous (tableau avec totaux + graphique en colonnes).

![Grille à reproduire](atelier-un-exo-excel.png)

### Objectif
Rédiger un **courriel de support** clair et concis qui guide l’utilisateur **pas à pas** jusqu’au même résultat, **avec 1–3 liens** vers la **documentation officielle** :  
👉 https://support.microsoft.com/fr-fr/excel

### Ce qu’on attend (consignes)
- Le courriel doit couvrir :
  1) **Saisie des données** (en-têtes, valeurs)  
  2) **Formules des totaux** (lignes et colonnes)  
  3) **Mise en forme** (fusion/centrage du titre, gras, bordures, format monétaire, alignements)  
  4) **Graphique en colonnes groupées** (catégories = produits, séries = mois)  
  5) **Contrôles finaux** (vérifier les résultats)
- Style : phrases **courtes**, étapes **numérotées**, vocabulaire simple.
- Joindre **au moins un lien** de la doc pour : *Créer un graphique*, *Fonction SOMME*, *Fusionner et centrer*, *Appliquer des bordures* ou *Format monétaire*.
- Remettre **uniquement le courriel** (pas de roman technique séparé).

---

### Données à saisir (dans votre procédure)
| Produit                 | Janvier | Février | Mars |
|---|---:|---:|---:|
| Bagel tout garni        | 300 | 240 | 287 |
| Bagel au sésame         | 250 | 180 | 260 |
| Beigne original         | 450 | 490 | 435 |
| Beigne au chocolat      | 270 | 275 | 130 |
| Beigne à la crème       | 308 | 345 | 281 |

➡️ Le tableau final doit ajouter une **colonne “Total”** (SOMME par ligne) et une **ligne “Total”** (SOMME par colonne).  
*(Vous pouvez indiquer dans le courriel comment recopier les formules.)*

---

### Gabarit de courriel (à compléter)

**Objet :** Étapes pour reproduire la grille et le graphique dans Excel

Bonjour,

Voici les étapes pour créer le **tableau** et le **graphique** :

1) **Saisir les données**  
… (plage, en-têtes, valeurs)

2) **Calculer les totaux**  
… `=SOMME(...)` (ligne), puis recopier ; `=SOMME(...)` (colonne)

3) **Mettre en forme**  
… (Fusionner et centrer le titre, gras en-têtes + ligne Total, bordures, format monétaire)

4) **Insérer le graphique en colonnes**  
… (plage à sélectionner, type de graphique, titre, légende)

5) **Contrôles finaux**  
… (vérifier que les totaux s’affichent et que le graphique correspond)

**Ressources utiles**  
- Créer un graphique : *(lien support.microsoft.com)*  
- Fonction SOMME : *(lien support.microsoft.com)*  
- Fusionner et centrer / Bordures / Format monétaire : *(lien support.microsoft.com)*

Cordialement,  
(Votre signature)

---

### Barème (suggestion)
- Étapes complètes et ordonnées (1→5) — **6 pts**  
- Clarté et concision du courriel — **4 pts**  
- Formules correctes (SOMME) — **4 pts**  
- Références vers la doc officielle — **2 pts**

> Rappel atelier : pas d’outils d’IA, respect des consignes de remise.  

<!-- ### Ce qu’on attend (consignes)
- Le courriel doit couvrir :
  1) **Saisie des données** (en-têtes, valeurs)  
  2) **Formules des totaux** (lignes et colonnes)  
  3) **Mise en forme** (fusion/centrage du titre, gras, bordures, format monétaire, alignements)  
  4) **Graphique en colonnes groupées** (catégories = produits, séries = mois)  
  5) **Contrôles finaux** (vérifier les résultats)
- Style : phrases **courtes**, étapes **numérotées**, vocabulaire simple.
- Joindre **au moins un lien** de la doc pour : *Créer un graphique*, *Fonction SOMME*,  -->