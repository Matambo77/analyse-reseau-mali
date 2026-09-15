# Analyse des performances du réseau mobile au Mali

# Présentation

Ce projet porte sur l'analyse des performances du réseau mobile au Mali à partir de données de mesures issues d'Ookla.

L'objectif est d'étudier les performances du réseau à travers plusieurs indicateurs, notamment :

le débit descendant (Download) ;

le débit montant (Upload) ;

la latence ;

le nombre de tests réalisés ;

le nombre de dispositifs utilisés ;

la répartition géographique des mesures.

L'analyse est réalisée à l'échelle du Mali, puis approfondie au niveau de plusieurs villes afin d'identifier les différences de performances entre les zones étudiées.

# Données

Le jeu de données utilisé est :

2026-01-01_performance_mobile_tiles.parquet

Le jeu de données mondial contient 3 186 269 observations et 11 variables, dont :

* quadkey
* tile
* tile_x
* tile_y
* avg_d_kbps
* avg_u_kbps
* avg_lat_ms
* avg_lat_down_ms
* avg_lat_up_ms
* tests
* devices

Les données ont ensuite été filtrées géographiquement afin d'extraire les observations correspondant au Mali.

# Données du Mali

Après extraction géographique, l'analyse porte sur 1 662 observations, représentant :

* 4 304 tests
* 2 021 dispositifs
* un débit descendant moyen de 30,82 Mbps
* un débit montant moyen de 16,79 Mbps
* une latence moyenne de 56,52 ms

Ces valeurs correspondent aux mesures disponibles dans le jeu de données et ne doivent pas être interprétées comme une mesure exhaustive de la qualité du réseau sur l'ensemble du territoire malien.

# Zone d'étude

Deux niveaux d'analyse sont utilisés :

# Mali

Une extraction géographique est effectuée à partir des coordonnées de longitude et de latitude afin de sélectionner les observations situées au Mali.

# Bamako

Une extraction spécifique est également réalisée pour Bamako afin d'étudier plus précisément les performances observées dans la capitale.

# Méthodologie

L'analyse suit principalement les étapes suivantes :

1. Chargement des données au format Parquet.
2. Exploration et vérification du jeu de données.
3. Conversion des unités de débit en Mbps.
4. Filtrage géographique du Mali.
5. Analyse des performances de téléchargement.
6. Analyse de la latence.
7. Analyse de la répartition des mesures.
8. Agrégation des indicateurs par ville.
9. Sélection des villes disposant d'au moins 10 tests.
10. Comparaison des performances entre les villes.
11. Classification des villes selon des règles basées sur le débit moyen et la latence moyenne.
12. Visualisation des résultats sous forme de graphiques et de cartes.

# Analyse par ville

Pour comparer les villes, plusieurs indicateurs sont calculés :

* débit moyen en Mbps ;
* débit médian en Mbps ;
* latence moyenne en ms ;
* latence médiane en ms ;
* nombre de tests ;
* nombre de zones mesurées.

Une ville est retenue pour l'analyse comparative lorsqu'elle dispose d'au moins 10 tests.

Cette sélection permet de limiter l'interprétation des résultats pour les villes très faiblement représentées dans les données.

# Classification des performances

Une classification simple est appliquée aux villes suffisamment représentées.

Les règles utilisées sont :

| Condition                           | Catégorie         |
| ----------------------------------- | ----------------- |
| Débit ≥ 25 Mbps et latence < 50 ms  | Bonne performance |
| Débit ≥ 15 Mbps et latence < 100 ms | À surveiller      |
| Autres situations                   | Prioritaire       |

Cette classification est une classification basée sur des seuils définis dans l'analyse. Il ne s'agit pas d'un modèle de Machine Learning.

# Principaux résultats

Après sélection des villes disposant d'au moins 10 tests, les résultats obtenus sont :

| Ville      | Débit moyen | Latence moyenne | Tests | Catégorie         |
| ---------- | ----------: | --------------: | ----: | ----------------- |
| Sikasso    |  54,28 Mbps |        33,00 ms |    13 | Bonne performance |
| Kayes      |  46,10 Mbps |        26,10 ms |    40 | Bonne performance |
| Bamako     |  37,76 Mbps |        30,47 ms |   620 | Bonne performance |
| Koulikoro  |  30,45 Mbps |        20,23 ms |    65 | Bonne performance |
| Ségou      |  28,15 Mbps |        81,48 ms |    42 | À surveiller      |
| Mopti      |  27,38 Mbps |        35,42 ms |    12 | Bonne performance |
| Tombouctou |  16,22 Mbps |       269,11 ms |    47 | Prioritaire       |

Ces résultats montrent notamment que l'évaluation de la performance ne doit pas se limiter au débit. La latence peut également constituer un facteur important dans l'appréciation de la qualité observée.

Plusieurs limites doivent être prises en compte* :

les données correspondent aux mesures disponibles dans la source et ne couvrent pas nécessairement toutes les zones du Mali ;

certaines villes disposent d'un nombre de tests limité ;

l'analyse repose sur une période d'observation donnée ;

les seuils utilisés pour la classification sont des règles définies dans le cadre de cette analyse ;

les résultats ne constituent pas une mesure exhaustive de la qualité du réseau pour chaque utilisateur ou chaque localité du Mali.

# Structure du projet

analyse-reseau-mali/
│
├── README.md
├── requirements.txt
│
├── notebooks/
│   └── analyse_reseau_mali.ipynb
│
├── data/
│   └── README.md
│
└── app/
    ├── app.py
    └── tableau_final.csv

# Technologies utilisées

Le projet utilise principalement :

* Python
* Jupyter Notebook
* Pandas
* NumPy
* Matplotlib
* GeoPandas
* données au format Parquet

Objectif du projet

Ce projet vise à fournir une analyse exploratoire et géographique des performances du réseau mobile au Mali, afin de mettre en évidence les différences observées entre les zones étudiées et de faciliter l'identification des secteurs nécessitant une surveillance ou une analyse plus approfondie.

Auteur

Mamadou Matambo Sanogo , Data Scientiste 

Projet réalisé dans le cadre de la formation en Data Science.
