# Exemple d'utilisation d'outils TAL

## Introduction

Ce document a pour objectif d'illustrer comment utiliser les outils de traitement automatique de la langue tout au long de la chaîne de traitement proposée dans ce tutoriel.

Dans le dossier "Exemple" de ce dépôt Github, nous vous fournissons les liens nécessaires pour l'installation de chaque outil.

## Mise en forme du corpus

Nous commençons par regrouper tous les documents du corpus dans un fichier .txt. Pour la réalisation de ce tutoriel, nous vous fournirons le fichier *irma.txt* qui contient les textes regroupés de 60 articles du journal Le Monde.

## Extraction des parties du discours

Nous réalisons l’identification des parties du discours à l’aide de l’outil Talismane. Après avoir installé cet outil, exécutez la commande suivante : 

```
java -Xmx1G -Dconfig.file=talismane-fr-X.X.X.conf -jar talismane-core-X.X.X.jar \
  --analyse \
  --endModule=posTagger \
  --sessionId=fr \
  --encoding=UTF8 \
  --inFile=data.txt \
  --outFile=data.tal
```

Ci-dessous un exemple du résultat attendu : 

```
5	l'	le	DET	DET	n=s	6	det	6	det
6	ouragan	ouragan	NC	NC	n=s|g=m	9	suj	9	suj
7	Harvey	Harvey	NPP	NPP	n=s|g=m	6	mod	6	mod
8	a	avoir	V	V	n=s|t=P|p=3	9	aux_tps	9	aux_tps
9	frappé	frapper	VPP	VPP	n=s|g=m|t=K	0	root	0	root
10	le	le	DET	DET	n=s|g=m	11	det	11	det
11	Texas	Texas	NPP	NPP	n=s|g=m	9	obj	9	obj
```


## Analyse de dépendances syntaxiques

L’outil Grew permet une identification plus optimale de l'ensemble de dépendances syntaxiques d’un texte. Veuillez exécuter la commande suivante pour réaliser cette analyse :

```
sed -f tal2grw.sed irma.tal > irma.pos.conll
grew transform -grs POStoSSQ/grs/surf_synt_main.grs -i irma.pos.conll -o irma.surf.conll
```

Ci-dessous, une illustration du résultat attendu : 

```
5	l'	le	D	DET	n=s	6	det	_	_
6	ouragan	ouragan	N	NC	g=m|n=s|s=c	9	suj	_	_
7	Harvey	Harvey	N	NPP	g=m|n=s|s=p	6	mod	_	_
8	a	avoir	V	V	m=ind|n=s|p=3|t=pst	9	aux.tps	_	_
9	frappé	frapper	V	VPP	g=m|m=part|n=s|p=3|t=past	_	_	_	_
10	le	le	D	DET	g=m|n=s	11	det	_	_
11	Texas	Texas	N	NPP	g=m|n=s|s=p	9	obj	_	_
```

## Extraction de termes candidats et calcul de la termitude

Réalisez l’extraction de candidats à partir de votre implémentation de la C-Valeur. Définissez votre propre format de sortie (une liste, un fichier .cls ou .xls, etc).

### Comparaison de votre implémentation avec les termes extraits par l’outil TermSuite

Placez dans un dossier le fichier *irma.txt*. Ce dossier ne doit que contenir les fichiers .txt du corpus étudié. Après, exécutez la commande :

```
java -cp termsuite-core-3.0.10.jar fr.univnantes.termsuite.tools.TerminologyExtractorCLI \
  -t /treetaggerpath/ \
  -c /corpus_folder/ \
  -l fr \
  --post-filter-property spec \
  --post-filter-top-n 50 \
  --tsv /output_path/terminology.tsv
```

Le paramètre "spec" indique que la métrique *weirdness ratio* doit être utilisée par TermSuite.


## Extraction d'entités nommées

Extrayez les entités nommées à partir de votre implémentation. Vous devez définir votre propre format de sortie.

### Comparaison avec Spacy

Comparez les entités nommées identifiés avec celles détectées par Spacy. L’extraction d’entités nommées à partir de Spacy peut se réaliser à l’aide du code suivant :

```
import spacy

// Stocker le string du fichier irma.txt dans la variable irma_document
nlp = spacy.load("fr_core_news_sm")
doc = nlp(irma_document)

for ent in doc.ents:
    print(ent.text, ent.start_char, ent.end_char, ent.label_)
```

Pour chaque entité, vous obtiendrez son texte, la position de départ, de fin et le type d'entité nommée : 

```
TEXT	    START   END	   LABEL	
Irma	    10	    15	    ORG	    
CNRS	    27	    31	    GPE
U.K.	    35	    45	    GPE
```

## Résolution d'anaphores

Finalement, réalisez la résolution d'anaphores à partir de votre propre solution. Vous devrez définir le  format de sortie. 

Nous vous proposons de comparer votre résultat avec l'outil *COFR* https://github.com/boberle/cofr (Nous n'arriverons pas à réaliser la comparaison dans ce tutoriel).

## Observations et conclusions

Décrivez progressivement les différences entre votre approche artisanale et les outils existants. Nous vous inviterons à apporter une de vos observations ou conclusions à la fin du cours. 
