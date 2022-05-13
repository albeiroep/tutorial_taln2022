# Tutoriel TALN 2022 : Quelques étapes souvent omises dans la préparation de corpus

## Objectif

Face à un corpus dans un domaine de connaissances spécifique, certaines étapes de traitement sont souvent omises ou traitées superficiellement, nous vous proposons une première introduction à trois : l’extraction de termes liés au domaine, l’extraction d’entités nommées et la résolution d’anaphores. Ces trois étapes sont importantes pour toute tâche de traitement automatique de la langue, que ce soit de l’extraction d’information, de la compréhension de langage, du résumé automatique ou de la traduction automatique.

## Nom, prénom et affiliation du ou des organisateurs

- Tian **TIAN**, *IMT Atlantique, Brest, France.*
- Albeiro **ESPINAL**, *DSI Global Services, Le Plessis Robinson, France. IMT Atlantique, Brest, France.*

## Adresse mail de contact
 
Vous pouvez nous contacter sur [tian.tian@imt-atlantique.fr](mailto:admin@cloudhadoop.com) et [albeiro.espinal@imt-atlantique.fr](mailto:admin@cloudhadoop.com)

## Description du tutoriel (déroulement, organisation, etc.)

Parmi les méthodes d’extraction de termes, nous allons utiliser deux mesures : la mesure de «termitude» (C-Value de
[Frantzi et al., 1999]) et le «weirdness ratio» [Ahmad et al., 1999] pour évaluer dans quelle mesure un syntagme donné
constitue un terme lié au domaine étudié. 

Pour détecter les entités nommées, et en particulier les noms propres complexes (de plus d’un mot), nous allons
également nous baser sur des motifs de POS tags, combinés avec l’utilisation de ressources externes, comme Wikipédia.
Nous allons comparer notre méthode «artisanale» avec des outils clé-en-main de détection d’entités nommées comme
spaCy.

La même approche sera utilisée pour la résolution d’anaphores : dans quelle mesure peut-on, simplement en se basant
sur l’analyse morphosyntaxique et sur certains traits grammaticaux, résoudre des anaphores pronominales ?

Ce tutoriel sous forme d'un TP, a pour but de montrer sur un exemple concret (des articles de presse concernant l'ouragan Irma qui a frappé l'Atlantique Nord en septembre 2017) comment préparer un corpus dans un  domaine spécifique en prenant soin d'extraire les termes complexes, d'identifier les entités nommées et de résoudre les anaphores pronominales.
Dans les trois cas nous allons comparer notre méthode «maison» artisanale à des outils existants.

## Outils utilisés (matériel, logiciel, corpus, etc.)

### Corpus

- 60 articles du journal Le Monde

### Environnement de travail

Les outils utilisés pour ce chaîne de traitements seront :

- Environnement Linux, Mac OS ou Windows.
- Talismane [Urieli & Tanguy, 2013] et Grew [Guillaume & Perrier, 2015] pour les approches «maison» ;
- Termsuite [Cram, 2016] et spaCy (https://spacy.io/), pour comparer les résultats et évaluer les performances.
- Python 3.X
- Librairies Python : spacy / transformers

## Public cible (pré-requis scientifique, connaissance du domaine, etc.)

- Des personnes intéressées par le prétraitement de corpus dans des domaines spécifiques,
  - Ayant un minimum de connaissances en programmation Python

## Durée.

- 1/2 journée.

## References

- *URIELI A. (2013). Robust French syntax analysis : reconciling statistical methods and linguistic know-
ledge in the Talismane toolkit. Thèse de doctorat, Université de Toulouse II le Mirail.*
- *CRAM D. (2016). TermSuite : Terminology extraction with term variant detection. In Proceedings of the
54th Annual Meeting of the Association for Computational Linguistics—System Demonstrations, p. 13–18*.