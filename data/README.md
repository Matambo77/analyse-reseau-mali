**Données du projet**

Le projet utilise le jeu de données suivant :

<2026-01-01\_performance\_mobile\_tiles.parquet>

Ce fichier contient des données de mesures de performance des réseaux mobiles issues d'Ookla.

Le jeu de données mondial contient 3 186 269 observations et 11 variables.

Pour cette analyse, les données ont été filtrées géographiquement afin d'extraire les observations correspondant au Mali, puis certaines analyses ont été approfondies au niveau de Bamako et de plusieurs villes maliennes.

Variables principales

Les principales variables utilisées dans l'analyse sont :

•	avg\_d\_kbps : débit descendant moyen en Kbps

•	avg\_u\_kbps : débit montant moyen en Kbps

•	avg\_lat\_ms : latence moyenne en millisecondes

•	tests : nombre de tests réalisés

•	devices : nombre de dispositifs utilisés

•	tile\_x et tile\_y : informations permettant la localisation des zones mesurées

Données utilisées dans l'analyse

Après filtrage géographique, 1 662 observations correspondant au Mali ont été utilisées.

Ces observations représentent :

•	4 304 tests

•	2 021 dispositifs

Le fichier original .parquet n'est pas inclus dans ce dépôt GitHub afin d'éviter d'alourdir inutilement le dépôt.

Les résultats présentés dans le projet sont obtenus à partir des données analysées dans le notebook.

Source

Les données utilisées proviennent d'Ookla.

Le présent projet est consacré à l'analyse des données disponibles et ne constitue pas une mesure exhaustive de la qualité du réseau mobile pour l'ensemble des utilisateurs ou du territoire malien.





