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
