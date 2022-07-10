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

## Faire les cours

- [Découvrez le cloud avec Amazon Web Services](https://openclassrooms.com/fr/courses/4810836-decouvrez-le-cloud-avec-amazon-web-services)
- [Concevez des architectures Big Data](https://openclassrooms.com/fr/courses/4467491-concevez-des-architectures-big-data)
- [Réalisez des calculs distribués sur des données massives](https://openclassrooms.com/fr/courses/4297166-realisez-des-calculs-distribues-sur-des-donnees-massives)

## Stockage

Buckets sur le cloud

- Amazon S3 (Simple Storage Service)
- Microsoft Azure Blob Storage (BLOB = Binary Large OBject)
- Google Storage Buckets

## Validation de la chaine de traitement

Dans un premier temps, on développe une prémière chaine de traitement sur un machine gratuit :

- [Développer avec PySpark en locale](https://sparkbyexamples.com/pyspark/how-to-install-and-run-pyspark-on-windows/)
- [Devélopper en Pyspark sur Colaboratory](https://www.analyticsvidhya.com/blog/2020/11/a-must-read-guide-on-how-to-work-with-pyspark-on-google-colab-for-data-scientists/)
- <https://www.pauldesalvo.com/how-to-install-spark-on-google-colab/>
- [Développer avec Pyspark sur Kaggle](https://www.kaggle.com/questions-and-answers/95448)
- [Sagemaker Lab](https://eu-west-3.console.aws.amazon.com/sagemaker/home?region=eu-west-3#/getting-started)
- [DataBricks Community](https://databricks.com/product/faq/community-edition)

Note:

- installation sur Windows - il faut installer Java SDK et copier Spark dans racine de C
- sur Colab et Kaggle, commandes sont similaires (pip install)
- sagemaker - il faut configurer les IAM Users, S3 buckets, ...`
- Databricks Community - il faut un simple login - l'environnement est prête - plein d'exemples. Creer un cluster hadoop en un clique (nom du cluster)

Une fois validé, on mont à l'échelle de Big Data, ou les couts peuvent monter rapidement

## Traitement en PySpark

- [Image classifier Transfer Learning avec Pyspark](https://docs.databricks.com/applications/machine-learning/preprocess-data/transfer-learning-tensorflow.html)


## Options BigData

- Amazon AWS
  - EC2 = base machine à configurer
  - EMR = cluster de nodes EC2 à configurer
  - Sagemaker Studio = Environnement DataScience Preconfiguré
- Microsoft Azure
  - via Databricks (qui peuvent être installé / transféré vers AWS/GCP)
- Google GCP
  - dev en Google Colab
  - Kubernetes Cluster

## Configurer Amazon Web Services

- Sign Up (root)
- Create IAM admin group and user

## Initialiser Sagemaker Studio (premier 2 mois gratuits - fonctions limités)

- Create Sagemaker policy
- Create Sagemaker user (or apply policy to user)
- Apprendre à monter/connecter/démonter un cluster EMR composé de EC2

## Amazon EMR

- il faut créer un script terraform, ou documenter le setup du cluster
- Tutorial : <https://ec2spotworkshops.com/running_spark_apps_with_emr_on_spot_instances.html> 

## Devéloppement local

- échantillon de données en local
- Créer un notebook en local pour faire le traitement de quelques images
- permet de comprendre quel sont les parties qui change quand on met à l'échelle

## Dataset - copie un échantillon de données à un bucket S3

## PySpark

copie notebook à Sagemaker Studio
