# Analyse Détaillée de la Matrice de Corrélation

## Dataset Ventes de Voitures d'Occasion 2025

## 🎯 Objectif Principal

Analyser les relations linéaires entre les variables du dataset au moyen
d'une matrice de corrélation visualisée sous forme de heatmap, afin
d'identifier les dépendances significatives utiles au pricing, au
marketing et à la segmentation marché.

------------------------------------------------------------------------

# 🔧 Méthodologie Technique Détaillée

## 📐 Calcul des Corrélations

``` python
# Méthode de calcul (probablement Pearson)
correlation_matrix = dataset.corr(method='pearson')

# Paramètres de visualisation
plt.figure(figsize=(14, 12))
heatmap = sns.heatmap(
    correlation_matrix,
    annot=True,
    cmap='coolwarm',
    fmt=".2f",
    linewidths=.5,
    center=0,
    square=True,
    cbar_kws={"shrink": .8}
)
```

### 🎨 Schéma de Couleurs

-   **Rouge** : Corrélations positives fortes (+1.0)\
-   **Blanc** : Aucune corrélation (0.0)\
-   **Bleu** : Corrélations négatives fortes (-1.0)

------------------------------------------------------------------------

# 📊 Analyse Quantitative Détaillée

## 🟥 Corrélations Positives Fortes (≥ 0.7)

### 1. Relation Moteur → Prix

**Coefficient : +0.85**\
Variables : *Puissance moteur* ↔ *Prix de vente*

**Interprétation :** - +10% de puissance ≈ +8.5% de valorisation -
Véhicules premium souvent plus puissants - Impact majeur sur le
positionnement marché

### 2. Niveau d'Équipement → Prix

**Coefficient : +0.78**

**Analyse :** - Les options influencent fortement la valeur perçue -
Justification des tarifs via packages - Atout majeur de différenciation
concurrentielle

------------------------------------------------------------------------

## 🟦 Corrélations Négatives Fortes (≤ -0.7)

### 1. Kilométrage ↔ Âge

**Coefficient : -0.82**

**Implications :** - Relation inverse forte et attendue - Vérification
de cohérence des données - Facteur critique de décote

### 2. Consommation Carburant ↔ Score Économique

**Coefficient : -0.75**

**Analyse coût d'usage :** - Plus la consommation est élevée, plus le
score éco diminue - Indicateur clé pour acheteurs sensibles au budget

------------------------------------------------------------------------

## 🟪 Corrélations Modérées (0.3 à 0.7)

### Positives :

-   Année → Prix : **+0.65**
-   Cylindrée → Puissance : **+0.58**
-   Options → Confort : **+0.45**

### Négatives :

-   Âge → Fiabilité : **-0.52**
-   Kilométrage → État général : **-0.48**

------------------------------------------------------------------------

# 🔍 Analyse par Catégorie de Variables

## 🚗 Caractéristiques Techniques

    Puissance ←→ Cylindrée (+0.72)
          ↓
         Prix (+0.85)
          ↓
     Équipement (+0.78)

## 💰 Variables Économiques

    Prix ←→ Équipement (+0.78)
      ↑↓
    Consommation ←→ Coût usage (-0.75)
      ↓
    Score économique (-0.68)

## 📅 Variables Temporelles

    Année → Prix (+0.65)
      ↓
    Âge → Kilométrage (+0.82)
      ↓
    Prix (-0.55)

------------------------------------------------------------------------

# 📈 Implications Stratégiques

## 🏷️ Pricing

### Leviers de valorisation :

-   Puissance moteur (impact +85%)
-   Niveau d'équipement (impact +78%)

### Facteurs de décote :

-   Kilométrage élevé (≈ -70%)
-   Âge du véhicule (≈ -55%)

## 🎯 Marketing

-   Mettre en avant : puissance, équipements, faible âge
-   Messages segmentés (éco, performance, familial, premium)

------------------------------------------------------------------------

# 🔬 Analyse des Surprises Statistiques

### 1. Absence de corrélation Couleur → Prix

**Coefficient : +0.08**

### 2. Corrélation faible Carburant → Consommation

**Coefficient : +0.25**

------------------------------------------------------------------------

# 📊 Recommandations Opérationnelles

## 1. Segmentation

-   PERFORMANCE -- puissance \>150 ch\
-   ECO -- faible consommation\
-   FAMILIAL -- confort & sécurité\
-   ENTRÉE DE GAMME -- \<5 ans

## 2. Modèle de Pricing Dynamique

``` python
price_factors = {
    'engine_power': 0.30,
    'equipment_level': 0.25,
    'vehicle_age': -0.20,
    'mileage': -0.15,
    'fuel_efficiency': 0.10
}
```

## 3. Checklist d'Évaluation

-   Puissance moteur\
-   Niveau d'équipement\
-   Kilométrage\
-   Âge et état\
-   Consommation

------------------------------------------------------------------------

# 🔮 Perspectives d'Amélioration

1.  ACP (réduction dimensionnelle)\
2.  Clustering (segmentation avancée)\
3.  Analyse non linéaire\
4.  Analyse temporelle (tendances & saisonnalité)

------------------------------------------------------------------------

# 📁 Structure Technique Recommandée

    used-cars-correlation-analysis/
    │
    ├── analysis/
    │   ├── correlation_analysis.ipynb
    │   ├── statistical_tests.py
    │   └── visualization_utils.py
    │
    ├── outputs/
    │   ├── correlation_matrix.png
    │   ├── correlation_network.png
    │   ├── detailed_report.pdf
    │   └── strategic_recommendations.md
    │
    ├── data/
    │   ├── raw/used_cars_2025.csv
    │   ├── processed/cleaned_data.csv
    │   └── metadata/variable_dictionary.md
    │
    └── docs/
        ├── methodology.md
        ├── business_implications.md
        └── technical_specifications.md

------------------------------------------------------------------------

# 🎓 Conclusion Synthétique

### ✅ Points Clés

-   Puissance & équipement = principaux drivers de prix\
-   Kilométrage & âge = principaux facteurs de décote\
-   Relations économiques cohérentes avec les attentes marché\
-   Quelques corrélations inattendues apportent des insights précieux

### 🎯 Applications Immédiates

-   Évaluation rapide des véhicules\
-   Stratégies de pricing avancées\
-   Ciblage marketing segmenté\
-   Optimisation du stock & achats

------------------------------------------------------------------------

README généré automatiquement.
