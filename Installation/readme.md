# Installation d'outils

Nous vous proposons de suivre ces petits tutoriels pour l'installation de chaque outil. Si vous rencontrez des problèmes lors de l'installation, nous vous accompagnerons pour les résoudre.

### IDE Pycharm Community Edition

- Pour le développement en Python, nous vous proposons de télécharger l'IDE Pycharm sur https://www.jetbrains.com/es-es/pycharm/download/download-thanks.html?platform=linux&code=PCC.
- Une fois vous l'aurez installé, créez un nouveau projet Python (File -\> New Project -\> Pure Python).

### Talismane

- Installez Talismane en suivant les instructions : http://redac.univ-tlse2.fr/applications/talismane.html. Nous vous recommendons d'installer la version 6.0.0.

### Grew

- Pour l'installation de Grew, veuillez suivre : https://grew.fr/usage/install/

Après, il est nécessaire d'installer les dépendences suivantes dans un même dossier : 

- **POStoSSQ** : ```git clone https://gitlab.inria.fr/grew/POStoSSQ.git```
- [Sed Script](https://grew.fr/grs/parsing/tal2grew.sed)

### Spacy

Dans la ligne de commandes de votre système d'exploitation ou de Pycharm, exécutez :

```
pip install -U pip setuptools wheel
pip install -U spacy
python -m spacy download fr\_core\_news\_sm
```

### TermSuite

Pour l'installation de TermSuite, suivez le tutoriel http://termsuite.github.io/getting-started/#manual-installation.

Nous recommandons d'exécuter TermSuite avec Java 8. Vous pouvez vérifier la version de votre système avec la commande suivante : 

```
java -version
```

Pour l'installation de Java 8, vous pouvez exécuter sur Linux : 

```
sudo apt-get install openjdk-8-jdk
```

et choisir par défaut cette version avec la commande : 

```
sudo update-alternatives --config java
```

### COFR

Malgré nous n'arriverons pas à réaliser la résolution d'entités avec l'outil COFR, vous pourrez suivre les instructions d'installation sur https://github.com/boberle/cofr dans la section **"Getting Started"**.
