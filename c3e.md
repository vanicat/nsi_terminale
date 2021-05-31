### exercice 3.1

Un ski-club utilise une base de données constituée de 2 tables :

- une table ADHERENTS
- une table STATIONS 

Dans la table ADHERENTS  on trouve un attribut “ref_station” qui permet de connaître les stations de ski préférées des adhérents.

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

### exercice 3.2

Exercice tiré du bac 2021

L’énoncé de cet exercice utilise les mots du langage SQL suivants :

SELECT FROM, WHERE, JOIN ON, INSERT INTO VALUES, UPDATE, SET, DELETE, COUNT, AND,OR.

Pour la gestion des réservations clients, on dispose d’une base de données nommée « gare » dont le schéma relationnel est le suivant :

```
Train (<u>numT</u>, provenance, destination, horaireArrivee, horaireDepart)

Reservation (<u>numR</u>, nomClient, prenomClient, prix, #numT)
```

Les attributs soulignés sont des clés primaires. L’attribut précédé de # est une clé étrangère.
La clé étrangère Reservation.numT fait référence à la clé primaire Train.numT.

Les attributs horaireDepart et horaireArrivee sont de type TIME et s’écrivent selon le format "hh:mm", où "hh" représente les heures et "mm" les minutes.

1) Quel nom générique donne-t-on aux logiciels qui assurent, entre autres, la persistance des données, l’efficacité de traitement des requêtes et la sécurisation des accès pour les bases de données ?

2)

a) On considère les requêtes SQL suivantes :

```
DELETE FROM Train WHERE numT = 1241 ;
DELETE FROM Reservation WHERE numT = 1241 ;
```

Sachant que le train n°1241 a été enregistré dans la table Train et que des réservations pour ce train ont été enregistrées dans la table Reservation, expliquer pourquoi cette suite d’instructions renvoie une erreur.

b) Citer un cas pour lequel l’insertion d’un enregistrement dans la table Reservation n’est pas possible.

3) crire des requêtes SQL correspondant à chacune des instructions suivantes :

a. Donner tous les numéros des trains dont la destination est « Lyon ».

b. Ajouter une réservation n°1307 de 33 € pour M. Alan Turing dans le train n°654.

c. Suite à un changement, l’horaire d’arrivée du train n°7869 est programmé à 08 h 11.
Mettre à jour la base de données en conséquence.

4) Que permet de déterminer la requête suivante ?

```
SELECT COUNT(*) FROM Reservation 
WHERE nomClient = "Hopper" AND prenomClient = "Grace";
```

5) Écrire la requête qui renvoie les destinations et les prix des réservations effectuées par Grace Hopper.