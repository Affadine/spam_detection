# spam_detection

Ce projet a pour but d'étudier d'analyser de données textuelles. En l'occurrence, on cherche à identifier des spams dans une base de SMS.

Les étapes pour la réalisation du projet :
 * __Count Vectorizer__ : Une première étape consiste à transformer les données textuelles en données numériques afin de pouvoir les exploiter par un algorithme de classification. Pour cela, on propose d'encoder chaque mot présent dans la base grâce à une variable binaire   (*True* si le mot est présent dans la ligne et *False* sinon). Cela produit une matrice dite *sparse* des données. 
 * __Comparaison de plusieurs algorithmes d’apprentissage sur une même validation croisée__ : Nous avons ensuite utiliser sur notre jeu de données les algorihtmes d'apprentissage supervisé suivants :
   * Tree
   * MLP
   * kNN
   * Bagging
   * AdaBoost
   * Random Forest
   
    Pour comparer les différents algorithmes, nous utilisons plusieurs métriques, : l'accuracy, l'aire sur la courbe AUC qui doit être proche de 1, le temps de calcul nécessaire et la précision. 
 
 * __TF-IDF term weighting__ : La dernière méthode est très gourmande en emplacement mémoire et en temps de calcul (notamment sur des bases de données plus conséquentes). Une solution serait d'utiliser TF-IDF : utiliser TF-IDF plutôt que le nombre d'occurrences de chaque mot dans un document permet de diminuer l'impact des mots à la fois très fréquents dans le texte et portant moins d'informations.
 * __TruncatedSVD__ : Afin de limiter l'utilisation de l'espace mémoire et du temps de calcul, on fait appel à un algorithme de réduction de dimension sur le même principe que PCA, mais sans centrer les features. (NB : en cas de crash, il faut relancer le programme bloc par bloc, à partir du chargement des données textuelles).
 * __Création d’un pipeline__ : On termine par la mise en place d'un Pipeline permettant de traiter des jeux de données textuelles. L'algorithme Random-Forest a été choisi pour ses bonnes performances et son temps d'entrainement réduit.

Data:

La première base contient des sms dont 13% des spams et la deuxième base contient 47 371 avis textuels accompagnés d'une note de 1 à 5.
