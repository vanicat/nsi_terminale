### exercice 3.1

Un ski-club utilise une base de données constituée de 2 tables :

- une table ADHERENTS
- une table STATIONS 

Dans la table ADHERENTS  on trouve un attribut “ref_station” qui permet de connaître les stations de ski préférées des adhérents.

Table ADHERENTS

| num_licence | nom    | prenom  | annee_naissance | ref_station |
| ----------- | ------ | ------- | --------------- | ----------- |
| 12558       | Doe    | John    | 1988            | 5           |
| 13668       | Vect   | Alice   | 1974            | 6           |
| 1777        | Dect   | Bob     | 1967            | 3           |
| 13447       | Beau   | Tristan | 1999            | 4           |
| 1141        | Pabeau | John    | 1975            | 3           |

table STATIONS

| ref | nom              | altitude_max |
| --- | ---------------- | ------------ |
| 3   | Le grand Bornand | 2050         |
| 4   | La clusaz        | 2616         |
| 5   | Flaine           | 2510         |
| 6   | Avoriaz          | 2466         |

1. Comment appelle-t-on l’attribut ref_station de la table ADHERENTS ?
2. Écrire la requête SQL permettant d’obtenir le nom des stations ayant une altitude maxi strictement supérieure à 2500 m.
3. Écrire une requête SQL permettant d’obtenir le numéro de licence des adhérents nés après 1980 et ayant pour prénom John.
4. Donnez le résultat de la requête SQL suivante :
```
SELECT nom 
FROM ADHERENTS 
WHERE num_licence > 2000 OR  ref_station = 3
```
5. Donnez le résultat de la requête SQL suivante :
```
SELECT STATIONS.nom
FROM STATIONS
INNER JOIN ADHERENTS ON ADHERENTS.ref_station = STATIONS.ref
WHERE annee_naissance > 1975
```
![](img/cc.png)

Auteur : David Roche
