
# Compte Rendu Détaillé – Analyse du Dataset « Default of Credit Card Clients »

## 📌 1. Introduction
Ce compte rendu présente une analyse complète du dataset **Default of Credit Card Clients in Taiwan**, largement utilisé pour des projets de classification binaire en finance. Il contient des informations financières, démographiques et comportementales de 30 000 clients de cartes de crédit, permettant de prédire le **risque de défaut de paiement le mois suivant**.

Ce travail inclut :
- Préparation et nettoyage des données  
- Encodage et normalisation  
- Feature engineering  
- Visualisation et analyse exploratoire  
- Entraînement de modèles de machine learning  
- Comparaison des performances  
- Validation croisée (Cross-validation)  
- Optimisation des hyperparamètres  

---

## 📌 2. Description du Dataset
Le dataset comprend **25 variables**, regroupées comme suit :

### ✔ Informations démographiques
- Sexe, âge, niveau d’éducation, statut marital.

### ✔ Informations financières
- LIMIT_BAL : limite de crédit accordée.

### ✔ Historique de paiement (PAY_0 → PAY_6)
Statut de paiement mensuel (−1 = paiement normal, 1 à 9 = retard de 1 à 9 mois ou plus).

### ✔ Montants de factures (BILL_AMT1 → BILL_AMT6)
Montants des factures des 6 derniers mois.

### ✔ Montants payés (PAY_AMT1 → PAY_AMT6)
Sommes payées au cours des 6 derniers mois.

### ✔ Variable cible
`default.payment.next.month` :  
- **1** = défaut  
- **0** = pas de défaut  

---

## 📌 3. Préparation des Données

### ✔ Nettoyage
- Suppression des doublons  
- Vérification de la complétude : **aucune valeur manquante**

### ✔ Encodage
- One-Hot Encoding pour EDUCATION, MARRIAGE, PAY_0 à PAY_6  
- SEX conservé comme variable binaire  

### ✔ Normalisation
Utilisation de **StandardScaler** pour :
- LIMIT_BAL  
- AGE  
- BILL_AMT1 → BILL_AMT6  
- PAY_AMT1 → PAY_AMT6  

---

## 📌 4. Feature Engineering
Création de nouvelles variables pertinentes :

- `AVG_BILL_AMT` : moyenne des factures  
- `AVG_PAY_AMT` : moyenne des paiements  
- `UTIL_RATIO` : ratio d’utilisation du crédit  
  - (moyenne des factures / limite de crédit)

Ces variables améliorent la compréhension du comportement financier.

---

## 📌 5. Analyse Exploratoire
### ✔ Histogrammes
- LIMIT_BAL : distribution asymétrique → peu de clients très fortunés  
- BILL_AMT : corrélation temporelle forte  
- PAY_AMT : grande dispersion et outliers  

### ✔ Boxplots
- Présence d’outliers sur BILL_AMT et PAY_AMT  
- Age : distribution relativement stable

### ✔ Heatmap de corrélation
- Corrélation élevée entre les BILL_AMT  
- Corrélation forte entre LIMIT_BAL et BILL_AMT  
- PAY_AMT faiblement corrélé au défaut  

---

## 📌 6. Modèles de Machine Learning

### Modèles entraînés :
- **Régression Logistique**  
- **Decision Tree**  
- **Random Forest**  

### Résultats (test set) :
| Modèle | Accuracy | Precision | Recall | F1 |
|--------|----------|-----------|--------|-----|
| Logistic Regression | 0.8188 | 0.6667 | 0.3442 | 0.4540 |
| Decision Tree | 0.7170 | 0.3681 | 0.4090 | 0.3874 |
| Random Forest | **0.8197** | 0.6571 | 0.3679 | **0.4717** |

➡ **Random Forest gagne** avec le meilleur F1-score.

---

## 📌 7. Cross-Validation (5-fold)

### Résultats moyens :
| Modèle | Accuracy | Precision | Recall | F1 |
|--------|----------|-----------|--------|-----|
| Logistic Reg. | **0.8201** | **0.6791** | 0.3546 | 0.4659 |
| Decision Tree | 0.7272 | 0.3908 | **0.4174** | 0.4036 |
| Random Forest | 0.8162 | 0.6506 | 0.3657 | **0.4682** |

➡ **Logistic Regression → meilleure précision**  
➡ **Random Forest → meilleur F1-score global**

---

## 📌 8. Hyperparameter Tuning (GridSearchCV)

### Meilleurs paramètres trouvés :
- **Logistic Regression :** C=1, penalty='l2'  
- **Decision Tree :** max_depth=10, criterion='gini'  
- **Random Forest :** n_estimators=200, max_depth=20, leaf=1  

➡ Les modèles tunés améliorent légèrement les scores, comme attendu.

---

## 📌 9. Conclusion Générale

L’analyse complète du dataset de défaut de paiement montre que :

- Les comportements de paiement passés sont les meilleurs indicateurs du risque.  
- Les montants des factures sont fortement corrélés entre eux.  
- Le taux d’utilisation du crédit est un puissant indicateur du risque.  

### 🔥 Meilleur modèle global :
👉 **Random Forest** (meilleur F1-score, robuste et performant)

### ✔ Applications possibles :
- Systèmes de scoring de crédit  
- Modèles de décision automatisés  
- Détection de comportements à risque  

---

## 📌 10. Recommandations
- Utiliser un modèle d’ensemble (Random Forest ou XGBoost)  
- Optimiser les seuils de décision selon le coût des erreurs  
- Explorer le SMOTE pour équilibrer les classes  
- Tester des modèles avancés : XGBoost, LightGBM, CatBoost  

---

**Auteur :** Analyse générée automatiquement  
**Format :** Markdown (.md)  
