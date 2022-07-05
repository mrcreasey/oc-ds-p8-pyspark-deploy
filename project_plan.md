# Plan de projet - Déployez un modèle dans le cloud

## Problèmatique:

Le start-up de l'AgriTech nommé 'Fruits!'

- propose des solutions innovantes pour robotiser traitement / récolte des fruits.
- veul mettant en place une application mobile
  - permettre de prendre en photo un fruit et d'obtenir des informations sur ce fruit
  - utilisant une première version du moteur de classification des images de fruits.

Le développement de l’application mobile permettra de construire une première version de l'architecture Big Data nécessaire.

## Les données

Il y a un [jeu de données](https://www.kaggle.com/moltean/fruits) constitué des images de fruits et des labels associés, qui pourra servir de point de départ pour construire une partie de la chaîne de traitement des données.

## Mission - Une première chaine de traitement de données

Développer (dans un environnement Big Data) et mettre en place les premières briques de traitement qui serviront lorsqu’il faudra passer à l’échelle en termes de volume de données :

- le preprocessing des images; et
- une étape de réduction de dimension.

Il n’est pas nécessaire d’entraîner un modèle pour le moment.

## Actions

- Faire les cours
- Stockage : Créer une sous échantillon de données
  - en local (5 classes, 5 images)
  - sur un serveur à distance (object/blob storage)
- Definir et valider la chaine de traitement
- Developper sur pyspark
- Mettre à l'echelle sur un cluster Hadoop
