+++
pre = '<b>3.1 </b>'
title = "Aide à distance"
weight = 1
+++

La communication avec le client est une partie essentielle du rôle de technicien en soutien informatique.  
Il ne suffit pas de résoudre un problème : il faut aussi **savoir expliquer clairement la solution**, que ce soit **en personne, au téléphone ou à distance**.  

Il existe plusieurs contextes, dans lesquels le technicien **ne peut se déplacer**. Il doit donc être capable de **prendre le contrôle d’un poste à distance** pour diagnostiquer et corriger un problème, tout en **gardant une attitude professionnelle, calme et claire**


**En quoi est-il pertinent d’utiliser l’aide à distance dans un contexte de soutien informatique ?**
L’assistance à distance est devenue une **pratique incontournable** dans le domaine du soutien technique.  
Elle permet de résoudre rapidement des problèmes tout en optimisant le temps et les ressources.

| **Avantage** | **Explication** |
|:--------------|:----------------|
| **Gain de temps** | Nul besoin de se déplacer : le technicien peut intervenir instantanément sur le poste du client. |
| **Efficacité accrue** | Permet d’observer le problème directement et d’agir plus rapidement qu’en guidant verbalement. |
| **Accessibilité** | Utile pour les clients situés dans d’autres locaux, villes ou même pays. |
| **Formation et accompagnement** | Le technicien peut montrer les étapes à suivre tout en expliquant la démarche à l’utilisateur. |
| **Documentation simplifiée** | Certains outils permettent d’enregistrer la session pour conserver une trace de l’intervention. |

**Avant toute intervention à distance**, le technicien doit :
- Obtenir l’**autorisation explicite** de l’utilisateur  
- **Indiquer / prévenir** des actions prévues (ex. redémarrage, fermeture d’applications) 
- **Informer** l’utilisateur tout au long de la manipulation  
- **Clôturer proprement** la session à la fin de l’intervention

> Assurez-vous de **mentionner clairement le rôle attendu du client** : par exemple, préciser s’il doit **observer pour apprendre** / **suivre la démarche**, **exécuter certaines étapes**, ou simplement **laisser le technicien intervenir seul** (ex. accès administrateur temporaire).   

---

### 🧰 Outils d’aide à distance sous Windows
Il existe plusieurs outils d’aide à distance, chacun avec ses **avantages et limites**.  
Certains ne donnent accès qu’à **la session de l’utilisateur actuellement connectée**, ce qui signifie qu’en cas de redémarrage ou de changement d’utilisateur, la connexion est rompue. Alors que d’autres permettent un **accès complet à l’ordinateur**, même sans qu’un utilisateur soit connecté, ce qui est pratique pour la maintenance continue.  

Certains logiciels sont aussi **multiplateformes** (compatibles avec Windows, macOS ou même Android), tandis que d’autres sont conçus spécifiquement pour l’écosystème Windows.

Voici **trois outils couramment utilisés** pour offrir de l’assistance à distance sur un poste Windows :
| **Logiciel** | **Description** | **Utilisation typique** |
|:--------------|:----------------|:-------------------------|
| **Quick Assist (Assistance rapide)** | Application intégrée à Windows 10 et 11. Permet de donner ou de recevoir de l’aide à distance via un code temporaire. | Idéal pour les interventions ponctuelles entre collègues d’une même organisation. |
| **TeamViewer** | Logiciel populaire offrant des connexions rapides, un transfert de fichiers et un support multiplateforme (Windows, macOS, Linux, Android, iOS). | Parfait pour le soutien à des utilisateurs externes ou pour aider à domicile. |
| **AnyDesk** | Léger, rapide et performant même sur des connexions Internet limitées. Permet aussi des connexions permanentes à des postes configurés. | Souvent utilisé dans les PME pour le soutien régulier ou les postes d’administration à distance. |

> Ces outils nécessitent toujours une **autorisation de l’utilisateur** avant toute prise de contrôle, et certaines organisations bloquent les connexions externes pour des raisons de sécurité.

---
### Atelier formatif : assistance à distance avec Quick Assist (binôme)
À travers cet atelier, vous travaillerez en binôme pour pratiquer la **communication et le dépannage à distance** à l’aide de l’outil **Quick Assist**.  
L’objectif est d’apprendre à diagnostiquer un problème **techniquement**, tout en gardant une **communication claire, professionnelle et rassurante** avec l’utilisateur.

**Objectifs de l’activité**
- Appliquer les bonnes pratiques de **communication à distance** (explications, autorisations, ton professionnel).  
- Utiliser **Quick Assist** pour diagnostiquer et résoudre un problème réel.  
- Identifier les **causes probables** et **proposer une solution claire**.  

**Fonctionnement de l’activité**  
Chaque scénario comporte **deux rôles** :  
- **Étudiant A : le technicien** (celui qui se connecte à distance)  
- **Étudiant B : l’utilisateur** (celui qui a un problème sur son poste)

> **Important :** ne regardez pas l’onglet du rôle de votre collègue, chaque rôle doit rester secret pour rendre la simulation réaliste.  
> Une fois le premier scénario terminé, **inversez les rôles** : celui qui était technicien devient alors utilisateur, et vice versa.

<style>
.tab-container {
  margin-top: 20px;
}
.tab-buttons {
  display: flex;
  gap: 8px;
  margin-bottom: 10px;
}
.tab-buttons button {
  background-color: #f0f0f0;
  border: none;
  padding: 8px 14px;
  border-radius: 6px;
  cursor: pointer;
  font-weight: bold;
  transition: background-color 0.3s;
}
.tab-buttons button.active {
  background-color: #2a4d69;
  color: #fff;
}
.tab-content {
  display: none;
  background-color: #fafafa;
  border: 1px solid #ddd;
  padding: 15px 20px;
  border-radius: 6px;
}
code {
  white-space: pre-wrap;   /* autorise le retour à la ligne */
  word-wrap: break-word;   /* casse les mots trop longs */
}
</style>

<script>
function openTab(evt, tabId) {
  const contents = document.getElementsByClassName("tab-content");
  for (let c of contents) c.style.display = "none";
  const buttons = document.getElementsByClassName("tab-btn");
  for (let b of buttons) b.classList.remove("active");
  document.getElementById(tabId).style.display = "block";
  evt.currentTarget.classList.add("active");
}
</script>

##### scénario 1 – problème de connexion Internet
<div class="tab-container">
  <div class="tab-buttons">
    <button class="tab-btn active" onclick="openTab(event, 's1a')">Étudiant A – Technicien</button>
    <button class="tab-btn" onclick="openTab(event, 's1b')">Étudiant B – Utilisateur</button>
  </div>

  <div id="s1a" class="tab-content" style="display: block;">
    <h4>🎧 Rôle : Technicien (Étudiant A)</h4>
    <p>Vous travaillez au <strong>centre de soutien informatique</strong> d’une entreprise. Vous recevez un appel du <strong>département des ressources humaines</strong>.</p>
    <p>La responsable du service vous explique :</p>
    <blockquote>« Je suis connecté au Wi-Fi, mais je n’ai plus accès à Internet. Aucune page Web ne se charge, même après plusieurs essais »</blockquote>
    <p>Connectez-vous à son ordinateur via <strong>Quick Assist</strong> et :</p>
    <ul>
      <li>Communiquez clairement à chaque étape (ex. : « Je vais vérifier vos paramètres réseau »).</li>
      <li>Identifiez la cause du problème et proposez la solution.</li>
      <li>Expliquez à l’utilisateur ce que vous faites et pourquoi.</li>
      <li>Enfin, clôturez la session proprement et validez que la connexion est rétablie.</li>
    </ul>
  </div>

  <div id="s1b" class="tab-content">
    <h4>💻 Rôle : Utilisateur (Étudiant B)</h4>
    <p>Vous devez créer un petit problème réseau à résoudre avant que votre collègue se connecte.</p>
    <p>Voici les étapes :</p>
    <ol>
      <li>Ouvrez : <code>Panneau de configuration → Réseau et Internet → Options Internet → Connexions → Paramètres réseau local</code></li>
      <li>Cochez <strong>« Utiliser un serveur proxy pour votre réseau local »</strong>.</li>
      <li>Entrez une adresse IP arbitraire (ex. <code>123.45.67.89</code>) et validez.</li>
    </ol>
    <p><strong>Effet attendu :</strong> les sites Web ne se chargent plus.</p>
    <p><strong>Solution attendue :</strong> le technicien devra décocher l’option du proxy ou rétablir les paramètres automatiques.</p>
  </div>
</div>

---

##### scénario 2 – message d’erreur au démarrage

<div class="tab-container">
  <div class="tab-buttons">
    <button class="tab-btn active" onclick="openTab(event, 's2a')">Étudiant A – Technicien</button>
    <button class="tab-btn" onclick="openTab(event, 's2b')">Étudiant B – Utilisateur</button>
  </div>

  <div id="s2a" class="tab-content" style="display: block;">
    <h4>🎧 Rôle : Technicien (Étudiant A)</h4>
    <p>Vous travaillez au <strong>centre de soutien informatique</strong> du collège. Un employé du département d’informatique vous contacte à propos d’un message d’erreur inquiétant s’affiche à chaque fois qu’il démarre son ordinateur.</p>
    <blockquote>« Dès que j’ouvre ma session, j’ai un message qui dit que le système est compromis ! Je crois que c’est depuis un exercice qu’on a fait en classe… »</blockquote>
    <p>Connectez-vous à distance via <strong>Quick Assist</strong> pour :</p>
    <ul>
      <li>Observer le message et rassurer l’utilisateur.</li>
      <li>Effectuer les vérifications nécessaires pour comprendre d’où vient le message. </li>
      <li>Proposer une explication plausible solution et une action pour le corriger. </li> 
      <li>Fournir des conseils de prévention pour éviter que la situation se reproduise (ne pas exécuter de fichiers inconnus, etc.).</li>
      <li>Enfin, clôturer la session en validant que tout est revenu à la normale.</li>
    </ul>
  </div>

  <div id="s2b" class="tab-content">
    <h4>💻 Rôle : Utilisateur (Étudiant B)</h4>
    <p>Vous devez créer un faux message d’erreur avant que votre collègue ne se connecte.</p>
    <p>Voici comment faire :</p>
    <ol>
      <li>Ouvrez le <strong>Bloc-notes</strong> et copiez le code suivant :</li>
    </ol>
    <pre><code>msg * "Erreur : Le système est compromis"</code></pre>
    <ol start="2">
      <li>Enregistrez le fichier sous le nom <code>alert.bat</code>.</li>
      <li>Placez-le dans le dossier <strong>Démarrage</strong> :
        <code>Windows + R → shell:startup</code>.</li>
    </ol>
    <p><strong>Effet attendu :</strong> le message apparaît au démarrage (ou exécutez-le directement pour le voir sans redémarrage).</p>
    <p><strong>Solution attendue :</strong> supprimer le fichier batch du dossier de démarrage.</p>
  </div>
</div>

---

<!-- Faire un retour réflexif
À la fin de l’activité, discutez ensemble :
- Le technicien a-t-il expliqué clairement ses actions ?
- L’utilisateur a-t-il compris la source du problème ?
- Comment améliorer la communication et la confiance dans une intervention à distance ?
 -->

<!-- 1. Explication rapide
Quand tu actives un serveur proxy dans Windows (dans Options Internet → Connexions → Paramètres réseau local), toutes les requêtes web (HTTP/HTTPS) passent par ce proxy avant d’atteindre Internet.
Alors, si tu entres une adresse IP inexistante (par ex. 123.45.67.89) ou un port invalide, ton navigateur tente de passer par ce serveur…
mais comme il n’existe pas, la connexion échoue. -->

<!-- 2. Explication rapide
Le message d’erreur affiché au démarrage est causé par un fichier batch (.bat) placé dans le dossier de démarrage automatique de Windows.
Ce type de fichier peut contenir une commande comme “msg * 'Erreur : Le système est compromis'”, qui affiche une boîte de dialogue à chaque ouverture de session.
Comme le script est exécuté automatiquement au démarrage, le message réapparaît tant que le fichier n’est pas supprimé du dossier “Démarrage”.

Le dossier Démarrage automatique de Windows (Startup folder) permet d’exécuter automatiquement un programme, un script ou un raccourci à chaque ouverture de session utilisateur.
C’est une fonctionnalité utile et légitime quand elle est bien utilisée.
Exemples légitimes :
Scripts d’administration : un service TI peut y placer un script pour
monter automatiquement un lecteur réseau,
lancer un outil interne (ex. : synchronisation, antivirus, etc.),
afficher un message d’accueil ou de maintenance à chaque connexion.
Applications utiles : certains logiciels (OneDrive, Teams, Discord, etc.) y placent leur raccourci pour démarrer automatiquement.
-->

