# Used Cars Sales Listings Dataset 2025

## Analyse complète et Modélisation

### 🎯 Objectif du projet

Ce projet vise à analyser le dataset **Used Cars Sales Listings 2025**,
comprenant des données sur les véhicules d'occasion.\
L'objectif est de : - explorer les relations entre variables, -
visualiser la corrélation, - comparer plusieurs modèles de régression, -
analyser un modèle de classification, - interpréter la performance
prédictive.

------------------------------------------------------------------------

## 🚘 1. Contexte du thème

Le dataset regroupe diverses caractéristiques des véhicules d'occasion
: - Prix - Kilométrage - Modèle / Marque - Année - Puissance -
Carburant, etc.

L'analyse aide à : - comprendre les facteurs influençant les prix, -
prédire les valeurs futures, - fournir des insights au marché de
l'automobile.

------------------------------------------------------------------------

## 🔍 2. Analyse de la matrice de corrélation

Une matrice de corrélation a été calculée et visualisée via un heatmap
Seaborn.

### 🔹 Observations :

-   Plusieurs variables présentent une corrélation positive
    significative avec le prix.
-   Certaines variables montrent une corrélation négative (ex :
    kilométrage).
-   Présence de multicolinéarité entre certaines caractéristiques.

------------------------------------------------------------------------

## 📈 3. Comparaison des modèles de régression

Plusieurs modèles ont été évalués via : - **RMSE** (Root Mean Squared
Error) - **R² Score**

### 🔹 Enseignements :

-   Les modèles flexibles capturent mieux les variations des prix.
-   Les meilleurs modèles présentent un faible RMSE et un bon suivi
    visuel.
-   Les modèles linéaires simples montrent des performances limitées.

------------------------------------------------------------------------

## 📊 4. Visualisation des prédictions

Des graphiques montrent la différence entre valeurs réelles et
prédictions.

Cela permet : - de valider visuellement les performances, - de détecter
le sur/sous-ajustement, - d'identifier les limites de certains modèles.

------------------------------------------------------------------------

## 🧪 5. Modèle de classification

Une régression logistique a également été testée.

### 🔹 Résultats :

-   Bonne précision sur certaines classes,
-   Difficultés sur classes déséquilibrées,
-   Le rapport de classification met en lumière les faiblesses de
    rappel.

------------------------------------------------------------------------

## 🧠 6. Conclusion générale

L'analyse montre que : - Certaines variables sont de très bons
prédicteurs, - Les modèles non linéaires s'en sortent le mieux, - La
classification nécessite un meilleur équilibrage.

### 🔹 Améliorations possibles :

-   Feature engineering avancé,
-   Comparaison de modèles (XGBoost, CatBoost),
-   Optimisation hyperparamétrique,
-   Normalisation/standardisation,
-   Gestion du déséquilibre des classes.

------------------------------------------------------------------------

## 📂 Structure recommandée du repository

    📁 used-cars-analysis
    │── 📄 README.md
    │── 📁 data/
    │── 📁 notebooks/
    │── 📁 models/
    │── 📁 visuals/

------------------------------------------------------------------------

## 👤 Auteur

README généré automatiquement à partir du notebook fourni.
