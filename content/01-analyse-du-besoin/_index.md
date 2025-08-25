+++
pre = '<b>1. </b>'
title = "Analyse du besoin"
weight = 2
+++
<!-- 1 - Technique exploratoire avec la personne utilisatrice
●	Description du problème, du message d’erreur, captures d’écran
●	Questions pertinentes sur l’environnement de l’utilisateur pour préciser la problématique (système d’exploitation, état de mémoire, paramètre de pare-feu, validation des versions des logiciels, etc.)
●	Formulation d’un courriel de soutien
2 - Reproduction du problème et identification de la cause
●	Consultation appropriée de la base de connaissances
●	Fouille de la documentation officielle du logiciel impliqué, de la section “troubleshooting” ou “dépannage/ résolution des problèmes”, FAQ, etc.
●	Développer une théorie de la cause probable ou transmission de l’information à la personne ou au service concerné
●	Techniques de résolution (c.-à-d.: élimination méthodique des sources d’erreurs possibles)
●	Détermination judicieuse du niveau de priorité -->

L’objectif de ce module est de **transformer une demande utilisateur en problématique clairement définie, reproductible et priorisée**, en recueillant les **symptômes** et le **contexte** (OS, mémoire, pare-feu, versions) puis en **reproduisant l’incident**. On y **formule une hypothèse de cause**, on **consigne** les informations clés dans un **courriel de soutien** et un **ticket** (avec captures), et l’on **prépare le plan d’intervention** à partir de la **documentation officielle** et de la **base de connaissances**.


<!-- ## Les différentes techniques de recherche de la cause du problème  
### Processus de dépannage (Troubleshooting)
* Notion d’organigramme de dépannage : un outil visuel utilisé pour guider une personne à travers les étapes nécessaires pour diagnostiquer et résoudre un problème technique, généralement lié à des machines, des systèmes informatiques ou des processus industriels. Il prend la forme d'un diagramme de flux (flowchart), où chaque étape du processus de dépannage est représentée par une case ou un symbole, avec des flèches indiquant la direction à suivre en fonction des réponses aux questions ou des résultats des tests effectués.
* Caractéristiques d'un organigramme de dépannage :
Début et fin clairs
Questions conditionnelles
Actions spécifiques
Décisions alternatives
Extensible (scalable)

{{< figure
    src="/420-510/images/troubleshooting.png"
    alt="troubleshooting"
    link="https://limblecmms.com/blog/what-is-troubleshooting/"
>}}

### Reproduction du problème :
- Demander les détails du problème et l’environnement exacte de l’utilisateur (OS, logiciels installés et leurs versions, spécification du matériel comme CPU, RAM.., conditions réseau…)

- Assurez-vous que votre environnement de test a la même version du système d'exploitation que l'ordinateur problématique. Installez les mêmes versions des logiciels, bibliothèques ou outils concernés. Reproduisez toutes les configurations système ou applicatives, telles que les variables d'environnement, les chemins de fichiers, ou les paramètres utilisateur.

- Exécutez soigneusement les étapes qui vous ont été partagées pour reproduire le problème. Soyez aussi précis que possible, en suivant la même séquence et en utilisant les mêmes entrées. Tenez un journal détaillé de ce qui se passe à chaque étape pour comparer avec le problème signalé.

- Considérez les Cas Limites : Testez avec des entrées extrêmes ou inhabituelles qui pourraient révéler le problème. Si le problème est lié au multithreading ou à la concurrence, testez avec différentes charges de travail ou nombres d'utilisateurs.

### Isolation du problème :
- Enlever la complexité et simplifier le problème : Essayez de retirer toutes les intégrations (comme les extensions de navigateur), les facteurs environnementaux, ou les personnalisations qui pourraient causer le problème. Essayez de revenir à un état de fonctionnement connu.
Par exemple :
Connectez-vous et déconnectez-vous
Effacez les cookies et le cache
Supprimez les extensions de navigateur
Essayez avec un autre navigateur
Essayez depuis une autre connexion Internet
Essayez sur un autre ordinateur

Si pas de solution, workaround (solution de contournement)
Exemples : - Écran bleu de la mort (BSOD) de Windows
          - Mise à jour d’un software échouée
                    
### Quand ne pas donner la solution :
Un agent de support technique devrait s'abstenir d'aider un utilisateur dans certaines situations pour garantir un support efficace et éthique. Voici des scénarios où il peut être approprié de ne pas fournir d'assistance :
1. Violations légales ou éthiques :
Accès non autorisé : Si un utilisateur demande de l'aide pour des activités impliquant un accès non autorisé aux systèmes ou aux données, comme le piratage ou le contournement des mesures de sécurité.
Activités illégales : Si l'utilisateur demande de l'aide pour des activités qui enfreignent les lois ou les réglementations, telles que le piratage ou la fraude.
2. Manque d'informations :
Détails insuffisants : Si un utilisateur fournit des informations inadéquates pour diagnostiquer le problème et refuse de fournir des détails supplémentaires ou un contexte.
3. Abus ou harcèlement :
Comportement hostile : Si l'utilisateur est abusif, menaçant ou harcelant envers l'agent de support, rendant l'assistance dangereuse ou improductive.
4. Mauvaise utilisation des ressources :
Demandes déraisonnables : Si l'utilisateur fait des demandes excessives ou déraisonnables qui dépassent le cadre des services de support standard ou sont impraticables.
5. Problèmes non pris en charge :
Appareils ou logiciels non pris en charge : Si le problème concerne un matériel ou un logiciel non pris en charge par la politique de support de l'entreprise, et qu'aucune alternative n'est disponible.
6. Violations de la politique de l'entreprise :
Conflits avec la politique : Si aider l'utilisateur entraînerait une violation des politiques ou des conditions de service de l'entreprise.

6. 	Problèmes de paiement non résolus :
Paiements en attente : Si l'utilisateur a des paiements en attente ou des problèmes de facturation non résolus qui doivent être réglés avant de pouvoir continuer le support.
7.	Risques de sécurité :
Menaces potentielles pour la sécurité : Si la demande de support présente un risque potentiel pour la sécurité, comme fournir un accès à distance à des systèmes sensibles sans autorisation appropriée.
Dans ces cas, il est crucial que les agents de support technique communiquent clairement les raisons pour lesquelles ils ne fournissent pas d'assistance et guident les utilisateurs vers les canaux ou ressources appropriés où leurs problèmes peuvent être traités correctement et légalement. -->
