# Audit d'un jeu de données Open Data 
## 1.Identification du jeu de données 


Élément          	Votre réponse
___________________________________________________
Titre du jeu	| Prix des carburants en france
Producteur	    | Ministére économiques et Financiers
URL	            | https://www.data.gouv.fr/datasets/prix-des-carburants-en-france-flux-instantane-v2-amelioree/community-resources

Licence   	     | Ouverte /open licence version 2.0
Date de dernière mise à jour| 18/09/2026
Fréquence de mise à jour	| Temps Reel 
Couverture géographique et temporelle | France Depuis le 07 Mars 2023

Format téléchargé	| CSV
Dictionnaire des variables disponible ? (oui/non)|oui 

## 2. Ouverture et Description d'un jeu de données
### Dimensions du jeu de données 
Nombre de lignes(aprés filtrage 62)   : 231
Nombre de colonnes(avant tri) : 47

### Descritption de 5 colonnes

|Nom de la colonne           |Type de valeur |Exemple de valeur                 |
| ville                      | commune(texte)       | Montigny-en-gohelle       |
| Code postal                | code_postal (nombre) | 62640                     |
| Adresse                    |     adresse (texte)  | PONT DU TONKIN            |
| Prix Gazole                |    float  (nombre)   |  2.20                     |
| Prix Gazole mis à jour le  |datetime_aware (date) |  2026-09-18T08:50:21+00:00|

### Problèmes rencontrés à l'ouverture
__ Certaines colonnes sont difficiles à lire car elles contiennent des données affichées sous forme de texte structurés (ex:horaires,services,prix).
__ Les dates sont affichées dans un format difficile à lire (ex: 2026-09-18t08:50:21+00:00). 
__ Il y a des accents manquant  
__ Certainnes colonnes sont mal alignées les données des lignes ne sont pas en face .

### Remplissage de la grille 
