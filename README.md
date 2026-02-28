# projet-final
Projet final- Formation Data Analyst

🏨 Revenue Management – Optimisation des Réservations Hôtelières

📌 Présentation du projet

Ce projet a pour objectif d’analyser les réservations hôtelières afin d’optimiser la stratégie de Revenue Management et de réduire le risque d’annulation.

Il combine :

Analyse SQL des KPI

Analyse exploratoire en Python

Feature engineering

Modélisation Machine Learning

Visualisation Power BI

Recommandations stratégiques

L’approche vise à transformer les données en décisions commerciales concrètes.

🎯 Problématique métier

Le secteur hôtelier est fortement impacté par les annulations, qui génèrent :

Perte de revenu

Instabilité financière

Difficulté d’anticipation du taux d’occupation

Question centrale :

Comment optimiser le revenu tout en maîtrisant le risque d’annulation ?

L’objectif n’est pas uniquement de maximiser le volume de réservations, mais de sécuriser un revenu stable et prévisible.

🗄 Source des données

Dataset : Hotel Booking Demand (Kaggle)
Environ 118 000 réservations (2015–2017)

🧮 Partie 1 – Analyse SQL des KPI

Extraction et calcul des indicateurs clés :

Chiffre d’affaires total

ADR (Average Daily Rate – tarif journalier moyen)

Taux d’annulation

Revenu par segment de marché

Revenu par canal de distribution

Objectif : identifier les principaux moteurs de performance.

📊 Partie 2 – Analyse et préparation des données (Python)

Travaux réalisés :

Nettoyage des données

Traitement des valeurs manquantes

Filtrage des outliers (ADR extrêmes)

Reconstruction des saisons

Segmentation du délai de réservation

Création de nouvelles variables (feature engineering)

Insight majeur

Le délai de réservation (lead_time) apparaît comme le principal facteur de risque d’annulation.

🤖 Partie 3 – Machine Learning : Prédiction du risque d’annulation
🎯 Type de problème

Classification binaire
Variable cible : is_canceled

0 = Réservation maintenue
1 = Réservation annulée

Un split temporel est utilisé :

Train : 2015–2016

Test : 2017

Les variables générant une fuite d’information (data leakage) sont exclues.

📈 Modèles comparés
Modèle	ROC-AUC	PR-AUC
Régression Logistique	0.861	0.818
Random Forest	0.872	0.826

Le Random Forest est retenu comme modèle final.

🎯 Performance du modèle retenu

Le modèle permet :

D’identifier environ 53% des annulations réelles

Avec une précision de 83%

Cela signifie que lorsqu’une réservation est classée “à risque”, le modèle a raison dans 83% des cas.

Le compromis précision / rappel peut être ajusté selon la stratégie commerciale.

🧠 Interprétation des variables importantes

Variables les plus influentes :

lead_time

deposit_type

total_of_special_requests

adr

previous_cancellations

Ces résultats confirment l’analyse exploratoire :

Les réservations effectuées longtemps à l’avance présentent un risque plus élevé.

L’absence de dépôt augmente le risque.

Le comportement client varie selon le niveau de service demandé.

💼 Traduction Business

La probabilité prédite est transformée en score de risque :

🟢 Faible → Conditions flexibles

🟠 Moyen → Conditions standards

🔴 Élevé → Dépôt obligatoire / non remboursable

Le modèle devient ainsi un outil d’aide à la décision en Revenue Management.

📊 Dashboard Power BI

Le projet inclut un tableau de bord interactif présentant :

Évolution du chiffre d’affaires

Performance par saison

Performance par canal

Taux d’annulation selon le délai de réservation

Objectif : faciliter la prise de décision stratégique.

⚠ Limites du projet

Données historiques uniquement

Absence d’informations concurrentielles

Pas de modélisation d’élasticité prix

Pas d’intégration temps réel

Axes d’amélioration possibles :

Optimisation du seuil de décision

Tuning des hyperparamètres

Intégration d’un modèle de forecasting

Couplage avec une stratégie tarifaire dynamique

🛠 Technologies utilisées

Python (pandas, scikit-learn)

SQL (MySQL)

Power BI

Jupyter Notebook

👩‍💻 Auteure

Solenn Le Bivic
Data Analyst – Revenue Strategy
