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

|Nom de la colonne           |Type de valeur |Exemple de valeur          |
| ville                      | texte         | Montigny-en-gohelle       |
| Code postal                | nombre        | 62640                     |
| Adresse                    | texte         | PONT DU TONKIN            |
| Prix Gazole                | nombre        |  2.20                     |
| Prix Gazole mis à jour le  |date           |  2026-09-18T08:50:21+00:00|

### Problèmes rencontrés à l'ouverture
__ Certaines colonnes sont difficiles à lire car elles contiennent des données affichées sous forme de texte structurés (ex:horaires,services,prix).
__ Les dates sont affichées dans un format difficile à lire (ex: 2026-09-18t08:50:21+00:00). 
__ Il y a des accents manquant  
__ Certainnes colonnes sont mal alignées les données des lignes ne sont pas en face .

### Remplissage de la grille 
|Dimension  |Méthode utilisée dans le tableur | Constat (chiffré ou exemple)|Gravité(faible/moyenne/forte)|
_____________________________________________________________________________________
|Complétude |Filtre sur les valeurs vides de la colonne Prix Gazole|14 Valeurs manquantes sur 231 lignes (environ 6.1%)|Faible|

|Exacitude  |Tri MIN/MAX de la colonne Prix SP98 | Prix MIN 1.99/Prix MAX 2.748|Aucune valeur implausible détectée |Faible |

|Cohérence  |Comparaison des colonnes Carburants disponibles et Prix SP98|Lorsque SP98 est indiqué disponible,le prix SP98 est renseigné;aucune incohérence détectée |Faible|

|Validité   |Filtre sur la colonne "Prix gazole mis a jour le " pour vérifier le format des valeurs |Les dates observées utilisent le même format|faible

|Unicité    |Mise en forme conditionnelle sur la colonne id avec NB.SI pour détecter les doublons |Aucun doublon détecté parmi les 231 identifiants |faible|

|Fraîcheur  |Tri de la colonne de Prix Gazole mis à jour le pour trouver la date la plus       récente|Date la plus récente :18/09/2026,identique à la date du jour |faible| 

## 4 Proposition des usages 

### Usage 1 "Dans quelles villes du Pas-De-Calais le carburant est il le moins cher?"
- Question métier : Dans quelle villes du Pas-De-Calais le E85 est-il le moins  cher?
- Colonnes utilisées : Ville,Prix E85 
- Défaut qualité pouvant fausser la réponse :134 valeurs de Prix E85 sont manquantes sur 231 lignes,ce qui peut rendre l'analyse incompléte et biaisée  


 
### Usage 2 "Suivre les prix actuels du Gazole dans le Pas-De-Calais "
- Question métier : Quels sont les prix actuels du Gazole dans les différentes villes de Pas-De-Calais?
- Colonnes utilisées : Ville,Prix Gazole mis a jour le.
- Défaut qualité pouvant fausser la réponse : 14 valeurs de Prix Gazole sont manquantes sur 231 lignes (6,1%).L'impact reste faible ,mais certaines stations ne pourront pas être prises en compte dans l'analyse.