# Tutoriel TALN 2022 : Quelques étapes souvent omises dans la préparation de corpus

## Objectif

Face à un corpus dans un domaine de connaissances spécifique, certaines étapes de traitement sont souvent omises ou traitées superficiellement, nous vous proposons une première introduction à trois : l’extraction de termes liés au domaine, l’extraction d’entités nommées et la résolution d’anaphores. Ces trois étapes sont importantes pour toute tâche de traitement automatique de la langue, que ce soit de l’extraction d’information, de la compréhension de langage, du résumé automatique ou de la traduction automatique.

## Organisateurs


- Tian **TIAN**, *IMT Atlantique, Brest, France. DECIDE, UMR 6285 Lab-STICC, Brest, France,*
- Albeiro **ESPINAL**, *DSI Global Services, Le Plessis Robinson, France. IMT Atlantique, Brest, France.  DECIDE, UMR 6285 Lab-STICC, Brest France.*
- Yannis **HARALAMBOUS**, *IMT Atlantique, Brest, France. DECIDE, UMR 6285 Lab-STICC, Brest, France,*

## Adresse mail de contact
 
Vous pouvez nous contacter sur [tian.tian@imt-atlantique.fr](mailto:tian.tian@imt-atlantique.fr) et [albeiro.espinal@imt-atlantique.fr](mailto:albeiro.espinal@imt-atlantique.fr) 

## Description du tutoriel

Parmi les méthodes d’extraction de termes, nous allons utiliser deux mesures : la mesure de «termitude» (C-Value de
*[Frantzi et al., 1999]*) et le «weirdness ratio» *[Ahmad et al., 1999]* pour évaluer dans quelle mesure un syntagme donné
constitue un terme lié au domaine étudié. 

Pour détecter les entités nommées, et en particulier les noms propres complexes (de plus d’un mot), nous allons
également nous baser sur des motifs de POS tags, combinés avec l’utilisation de ressources externes, comme Wikipédia.
Nous allons comparer notre méthode «artisanale» avec des outils clé-en-main de détection d’entités nommées comme
spaCy.

La même approche sera utilisée pour la résolution d’anaphores : dans quelle mesure peut-on, simplement en se basant
sur l’analyse morphosyntaxique et sur certains traits grammaticaux, résoudre des anaphores pronominales ?

Ce tutoriel sous forme d'un TP, a pour but de montrer sur un exemple concret (des articles de presse concernant l'ouragan Irma qui a frappé l'Atlantique Nord en septembre 2017) comment préparer un corpus dans un  domaine spécifique en prenant soin d'extraire les termes complexes, d'identifier les entités nommées et de résoudre les anaphores pronominales.
Dans les trois cas nous allons comparer notre méthode «maison» artisanale à des outils existants.



## Corpus

- 60 articles de presse du journal Le Monde concernant l'ouragan Irma qui a frappé l'Atlantique Nord en septembre 2017.

## Environnement de travail

Les outils utilisés pour ce chaîne de traitements seront :

- Environnement Linux, Mac OS ou Windows, 
- Talismane *[Urieli & Tanguy, 2013]* et Grew *[Guillaume & Perrier, 2015]* pour les approches «maison»,  
- Termsuite *[Cram, 2016]* et spaCy (https://spacy.io/), pour comparer les résultats et évaluer les performances, 
- Python 3.X, 
- Librairies Python : spacy / transformers.

## Public cible

- Des personnes intéressées par le prétraitement de corpus dans des domaines spécifiques,
- Avoir un minimum de connaissances en programmation Python

## Date et durée

- lundi 27 juin 9h-12h30 

## IMPORTANT 

Pour participer à ce tutoriel, merci de compléter la formulaire ici (https://forms.gle/W49a1iFVCZjSiYbR8). 
Cela nous permet de mieux connaître notre public et de mieux vous aider. 

## References

- *AHMAD K., GILLAM L. & TOSTEVIN L. (1999). University of Surrey Participation in TREC8 :
Weirdness Indexing for Logical Document Extrapolation and Retrieval (WILDER). In TREC, volume 500-246 de
NIST Special Publication : National Institute of Standards and Technology (NIST)*
- *CRAM D. (2016). TermSuite : Terminology extraction with term variant detection. In Proceedings of the
54th Annual Meeting of the Association for Computational Linguistics—System Demonstrations, p. 13–18*.
- *FRANTZI K. T., ANANIADOU S. & TSUJII J. (1999). The C-value/NC-value Method of Automatic
Recognition for Multi-word Terms. In Proceedings of ECDL’98, volume 1513 de Springer LNCS, p. 585–604*
- *URIELI A. (2013). Robust French syntax analysis : reconciling statistical methods and linguistic know-
ledge in the Talismane toolkit. Thèse de doctorat, Université de Toulouse II le Mirail.*
- *URIELI A. & TANGUY L. (2013). L’apport du faisceau dans l’analyse syntaxique en dépen-
dances par transitions : études de cas avec l’analyseur Talismane. In Actes de la 20e conférence sur le Traitement
Automatique des Langues Naturelles (TALN’2013), p. 188–201.*


