# 🚗 Prédiction des Causes d'Accidents à Chicago_projet_phase3
## 📘 Description du projet

Ce projet a pour objectif de prédire la cause principale des accidents de la route survenus à Chicago, en se basant sur les jeux de données publiques de la Chicago Police Department (CPD) .
L'approche repose sur un modèle de classification multi-classes entraîné à partir de caractéristiques météorologiques, temporelles, routières et géographiques.

L'ensemble du pipeline est conçu pour fonctionner sans dépendances externes (pas de librairies comme déséquilibred-learn, seaborn, etc.), afin de rester compatible avec un environnement standard Jupyter/Anaconda.

# 📂 Structure du projet
## 📁 projet_chicago_accidents/
│
   ├── CPD_traffic_crashes-crashes-20240501.csv     # Données principales des accidents
   
   ├── CPD_traffic_crashes-vehicles-20240501.csv    # Données sur les véhicules impliqués
   
   ├── CPD_traffic_crashes-people-20240501.csv      # Données sur les personnes impliquées
   
   ├── chicago_accidents_prediction.py              # Script principal (ce fichier)
   
   ├── README.md                                    # Documentation du projet
   
   └── modele_random_forest.pkl                     # Modèle sauvegardé (optionnel)

# ⚙️ Fonctionnalités principales

✅ Chargement et vérification des jeux de données spécifiques à Chicago

✅ Fusion intelligente des tables crashes, vehicleset people

✅ Analyse et nettoyage de la variable cible PRIM_CONTRIBUTORY_CAUSE

✅ Regroupement automatique des classes rares sous « AUTRES_CAUSES »

✅ Sélection et encodage des caractéristiques pertinentes :

## Conditions routières et météorologiques

Données temporelles (heure, jour, mois)

Type et manœuvre des véhicules

Informations géographiques (latitude, longitude, rue)

✅ Entraînement d'un modèle Random Forest multi-classes équilibré

✅ Évaluation complète : matrice de confusion, rapport de classification

✅ Analyse de l'importance des caractéristiques

# 🧠 Modèle de Machine Learning

Type de modèle : Random Forest Classifier

Approche : Classification multi-classes (plusieurs causes possibles)

Gestion du déséquilibre :class_weight='balanced'

Séparation des données : 80% entraînement / 20% test

Métriques utilisées :

Précision globale

Rapport de classification (précision, rappel, score f1)

Matrice de confusion (visualisée via Matplotlib)

Évaluation typique :

Performance acceptable entre 0.4 et 0.6 pour un jeu de données multi-classes

# 📊 Visualisations intégrées

Le script génère automatiquement les graphiques suivants :

Histogramme des 15 principales causes d'accidents

Matrice de confusion multi-classes normalisée

Top 15 caractéristiques les plus importantes du modèle

# 🚀 Exécution du projet
### 🔧 Prérequis

Assurez-vous d'avoir installé les bibliothèques suivantes (toutes incluses dans Anaconda) :

pip install pandas numpy matplotlib scikit-learn joblib

# ▶️ Exécution

Lancez simplement le script dans votre terminal ou votre notebook :

python chicago_accidents_prediction.py


ou dans un notebook Jupyter :

%run chicago_accidents_prediction.py


**Le script :**

Charger les fichiers CSV.

Prétraite et fusionne les données.

Entraînez le modèle Random Forest.

Évaluez et affichez les résultats.

Montrez les visualisations des causes et de l'importance des variables.

## 📦 Sauvegarde du modèle

Le modèle appliqué peut être sauvegardé pour une utilisation ultérieure :

joblib.dump(model, "modele_random_forest.pkl")


Et chargé plus tard pour des prédictions :

model = joblib.load("modele_random_forest.pkl")

## 🧩 Extensions possibles

Intégration d'un tableau de bord Power BI ou Streamlit pour visualiser les prédictions.

Utilisation de SMOTE ou d'autres techniques de rééquilibrage (si bibliothèques externes disponibles).

Déploiement du modèle sous forme d'API Flask.

Ajout d'un système de géolocalisation (carte des zones les plus accidentogènes).

# 👩‍💻 Auteurs

Projet réalisé par :
👤 LUBE 123

📚 Dans le cadre du cours de Science des Données — Phase 3

🏛️ Akademi_DS_P3 — 2025

📜 Licence

Ce projet est publié sous licence MIT.
Vous pouvez librement l'utiliser, le modifier et le distribuer, à condition de définir l'auteur original.
