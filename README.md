# Clustering d'articles de tickets de caisse

L'objectif de l'exercice est de proposer un clustering des articles trouvés dans les tickets de caisse reçus par KillBills. 

## Démarche

- Premièrement, il faut se connecter à la base de données postgreSQL pour récupérer les données à classifier dans la table "items". Cette table contient 14 colonnes au total mais plusieurs d'entre elles ont des valeurs *None*. Il a été choisi de garder seulement la colonne "itemName" pour effectuer le clustering.

- Ensuite, il faut nettoyer le texte contenu dans cette colonne pour supprimer les mots et les caractères qui n'apporteront pas d'informations utiles à notre modèle.

- Une fois nettoyé, il faut procéder à la vectorisation du texte pour pouvoir appliquer l'algorithme de clustering choisi.

- On va utiliser l'algorithme Mini-batch K-means pour effectuer le clustering. C'est une variante de l'algorithme K-means qui utilise un sous-ensemble des données d'entrée pour mettre à jour les clusters à chaque itération, ce qui permet de réduire le temps de calcul.

- Avec les résultats du clustering, on peut procéder à l'étiquetage de chaque cluster en utilisant les deux mots qui apparaissent le plus fréquemment dans chaque cluster. 

- Finalement, on peut prédire la catégorie à laquelle appartient un article donné d'après notre modèle.
