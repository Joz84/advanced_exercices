## GRP-C. LAG
La fonction LAG permet de récupérer la valeur de la ligne précédente d'une colonne donnée.
Elle est utile pour calculer les variations entre deux lignes.


### Titre de l'exercice : Calcul des variations avec la fonction LAG

#### Objectif : Comprendre l'utilisation de la fonction LAG pour calculer les variations entre deux lignes dans une table de données.

### Instructions :

#### Enoncé : 
Ci-joint une table de données qui enregistre les ventes mensuelles d'un produit dans une entreprise ("create_db_lag.sql" et "insert_monthly_sales.sql").
Créer une requête SQL qui utilise la fonction LAG pour calculer la variation mensuelle des ventes par rapport au mois précédent.

#### Question 1 :
Écrire une requête SQL pour extraire les données de ventes mensuelles, en incluant une colonne supplémentaire 
qui utilise la fonction LAG pour récupérer les ventes du mois précédent.

#### Question 2 :
Ajouter une autre colonne à la requête qui calcule la variation en pourcentage entre les ventes du mois actuel et du mois précédent.

#### Question 3 :
Afficher le résultat de la requête, en mettant en évidence les mois où la variation est la plus importante.

```
CREATE DATABASE IF NOT EXISTS db_lag;

USE db_lag;

CREATE TABLE IF NOT EXISTS ventes_mensuelles (
    mois DATE,
    ventes DECIMAL(10, 2)
);
```

```
INSERT INTO ventes_mensuelles (mois, ventes)
VALUES
    ('2022-01-01', 22500.00),
    ('2022-02-01', 24630.00),
    ('2022-03-01', 26550.00),
    ('2022-04-01', 28450.00),
    ('2022-05-01', 30890.00),
    ('2022-06-01', 32200.00),
    ('2022-07-01', 34600.00),
    ('2022-08-01', 36400.00),
    ('2022-09-01', 38000.00),
    ('2022-10-01', 40000.00),
    ('2022-11-01', 42000.00),
    ('2022-12-01', 44210.00),
    ('2023-01-01', 46350.00),
    ('2023-02-01', 48840.00),
    ('2023-03-01', 50100.00),
    ('2023-04-01', 52000.00),
    ('2023-05-01', 54000.00),
    ('2023-06-01', 56000.00),
    ('2023-07-01', 58210.00),
    ('2023-08-01', 60230.00),
    ('2023-09-01', 62990.00),
    ('2023-10-01', 64000.00),
    ('2023-11-01', 66000.00),
    ('2023-12-01', 68000.00);
```

## GRP-B Window Function
Une fonction de fenêtre calcule une valeur en fonction d'un ensemble de lignes dans une table. Elle peut être utilisée pour effectuer des calculs sur des données agrégées ou pour calculer des totaux cumulatifs.

### Ennoncé
Avec la db olist  Tache:  Écrivez une requête SQL qui renvoie : 
- les ventes totales et le revenu total pour chaque produit et chaque state. 
- les ventes totales et le revenu total par produits.  
- les ventes et state par région.  
on peut résoudre cet exercice en utilisant des fonctions window telles que SUM() avec l'option OVER pour calculer les totaux.

## GRP-A. VIEW
Une vue est une requête stockée dans la base de données sous forme de table virtuelle. 

Elle permet de simplifier les requêtes en combinant plusieurs tables et en pré-filtrant les données.

### Ennoncé

1) FROM ONE TABLE
Créer une View table à partir de la table client de la base de données 'commandes' qui contiendra:
		- nom, prenom, et les villes commençant par 'L'.
		- Afficher la table

2) FROM MULTIPLE TABLES
Créer une View table à partir des tables client et commande qui contiendra:
		- nom, prenom et la somme des achats par clients. 
		- Afficher la table

3) Afficher une table des View tables créées avec :
Ex: show full tables where table_type like "%VIEW";

4) Supprimer une View avec 'DROP WIEW view_name':
Ex: DROP VIEW 'nom de la view table';

5) Enfin, avec la clause WITH CHECK OPTION suivant une condition WHERE,
il est possible d'empêcher l'ajout de rows ne respectant pas la condition WHERE.

Une UPDATE ou INSERT ne respectant pas la condition WHERE retournera une erreur.

En utilisant la View table de la question 1). Ajouter la clause 'WITH CHECK OPTION' la ligne suivant la clause WHERE.
Ajouter un client habitant à 'Lyon' puis un client habitant à 'Bordeaux'.
Vous devriez avoir un message d'erreur en ajoutant le second client.


#### Commentaires/Tips

On peut créer ou remplacer pour ajouter ou supprimer les fields d'une View.

Ex:
```
CREATE OR REPLACE VIEW view_name AS
SELECT column1,column2,..
FROM table_name
WHERE condition;
```

Il est aussi possible d'ajouter et supprimer des rows dans une View table.
Ex:
```
INSERT INTO view_name(column1, column2 , column3,..) 
VALUES(value1, value2, value3..);
```
```
DELETE FROM view_name
WHERE condition;
```

## GRP-D. BUCKET
La création de "buckets" Les buckets sont des intervalles de valeurs créés à partir d'une colonne donnée. Ils sont utiles pour agréger les données en groupes.

### Analyse des salaires des joueurs de la NBA en utilisant des buckets


### Ennoncé

Dans cet exercice, vous devrez utiliser des "buckets" pour classer les salaires des joueurs de la NBA pour la saison 2017-2018.

Vous devrez créer des intervalles de salaires (buckets) :

Classer le salaire des joueurs en 4 catégories afin de regrouper les joueurs en fonction de la tranche des salaires pendant cette période. 
Indice : vous pouvez vous servir des quantiles pour créer les 4 groupes.

Cet exercice mettra en pratique les compétences de SQL liées à l'agrégation, au filtrage et à la manipulation des données.

#### Source des données
Pour cet exercice vous devrez utiliser ce [dataset](https://www.kaggle.com/datasets/koki25ando/salary?select=NBA_season1718_salary.csv) 

### A vos marques, prêt, dunkez !!!

![michael](https://www.basketusa.com/wp-content/uploads/2020/02/jordan-sdk-1988.jpg)



