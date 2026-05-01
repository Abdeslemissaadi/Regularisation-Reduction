#  Régularisation & Réduction de Dimensionnalité en Machine Learning

> Une étude comparative de la régression Ridge, Lasso et ElasticNet, combinée à une Analyse en Composantes Principales (PCA) appliquée à des données financières.

---

## 📌 Vue d'ensemble

Ce projet explore deux grandes familles de techniques en apprentissage statistique :

1. **Régression Régularisée** — Ridge, Lasso et ElasticNet pour contrôler la complexité du modèle et éviter le surapprentissage
2. **Réduction de Dimensionnalité** — PCA appliquée à un portefeuille boursier pour révéler la structure cachée des rendements financiers

---

## 🧠 Concepts Abordés

###  Régression Ridge (Régularisation L2)
- Pénalise la somme des coefficients au **carré**
- Réduit tous les coefficients vers zéro mais ne les **élimine jamais complètement**
- Testé avec les alphas : `[0.01, 0.1, 1, 10, 100]`

###  Régression Lasso (Régularisation L1)
- Pénalise la somme des **valeurs absolues** des coefficients
- Peut réduire certains coefficients à **exactement zéro** → sélection automatique de variables
- Testé sur la même plage d'alphas

###  Comparaison Ridge vs Lasso
- Visualise l'évolution des coefficients de chaque méthode à mesure que λ augmente
- Met en évidence la différence clé : Lasso produit des solutions **parcimonieuses**

###  ElasticNet
- Combine les pénalités L1 et L2 : `α * L1 + (1 - α) * L2`
- Recherche sur grille avec `alphas = [0.1, 1, 10]` et `l1_ratios = [0.1, 0.5, 0.9]`
- Visualisation en 9 sous-graphiques montrant l'effet de chaque combinaison d'hyperparamètres

###  PCA sur Portefeuille Boursier
- Appliquée à 9 actions tech et minières (2015–2016)
- Révèle un regroupement sectoriel dans l'espace des composantes principales

---

##  Actions Utilisées (Section PCA)

| Secteur | Tickers |
|---|---|
| Technologie | IBM, MSFT, META, T, INTC |
| Mines d'or | GOLD, NEM, AU, AEM, GFI |

---

## 🛠️ Technologies Utilisées

- Python 3.x
- `numpy` / `pandas` — génération et manipulation des données
- `scikit-learn` — Ridge, Lasso, ElasticNet, PCA, StandardScaler
- `matplotlib` — toutes les visualisations
- `yfinance` — téléchargement des données financières (section PCA)

---

## 📊 Résultats Clés

- **Ridge** réduit progressivement les coefficients à mesure que λ augmente — aucune variable n'est complètement éliminée
- **Lasso** annule agressivement les variables les moins importantes — `x_squared` est la première à disparaître
- **ElasticNet** offre un compromis ajustable entre les deux comportements
- **PCA** confirme que les actions tech et les mines d'or occupent des régions distinctes dans l'espace des composantes principales, validant leur rôle d'actifs décorrélés

---


##  Notes

- Les modèles de régression utilisent des **données synthétiques** (`y = 3x + bruit`) à des fins pédagogiques
- La section PCA utilise des **données de marché réelles** issues de Yahoo Finance
- Ce projet est réalisé à des fins éducatives uniquement et ne constitue pas un conseil financier

---
#Abdeslem
