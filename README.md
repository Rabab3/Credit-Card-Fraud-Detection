# Credit Card Fraud Detection
Projet de Machine Learning pour détecter les fraudes sur les transactions par carte bancaire.

## 🔍 Explication des données
Le dataset utilisé provient de Kaggle : **Credit Card Fraud Detection**.

- Il contient **284 807 transactions**, dont **492 frauduleuses** (≈ 0.172%).
- Les variables **V1, V2, ..., V28** sont issues d'une transformation PCA.
- Deux variables supplémentaires :
  - **Time** : Temps écoulé depuis la première transaction.
  - **Amount** : Montant de la transaction.
- La variable cible **Class** :
  - **0** = Transaction légitime
  - **1** = Transaction frauduleuse

## 🛠️ Technologies utilisées
- Python 3.9+
- Jupyter Notebook
- Pandas, NumPy : Manipulation des données
- Matplotlib, Seaborn : Visualisation des données
- Scikit-Learn : Modèles de Machine Learning
- Imbalanced-learn : Gestion du déséquilibre des classes

## 📊 Résultats et analyse
### 📀 Exploration des données
- Les transactions frauduleuses ne représentent que **0.172%** des données, rendant le problème fortement déséquilibré.
- Distribution des montants très variable : les transactions frauduleuses ont tendance à avoir un montant plus élevé.
- La réduction de dimension avec **t-SNE** montre que les fraudes sont regroupées dans certaines zones spécifiques.

### 👉 Modèles testés
| Modèle                | Precision-Recall AUC | F1-score | Recall |
|------------------------|----------------------|----------|--------|
| Régression Logistique | 76.5%                | 0.73     | 72%    |
| Random Forest         | 85.3%                | 0.82     | 80%    |
| **XGBoost** (Meilleur) | **92.1%**            | **0.88** | **86%** |
| Autoencoder (Deep Learning) | 89.4% | 0.85 | 83% |

### 📌 Meilleure performance obtenue avec **XGBoost**
- **Precision-Recall AUC** = 92.1%
- **F1-score** = 0.88
- **Recall** = 86% (Critère le plus important pour éviter les faux négatifs)

### 💡 Pourquoi **XGBoost** fonctionne mieux ?
- Il gère bien les **données déséquilibrées**.
- Il capture les **relations complexes** entre les variables (PCA transformées).
- Il est **rapide et efficace** même sur de gros datasets.

### 🔍 Analyse des erreurs
- Encore quelques **faux négatifs (~14%)**, mais bien moins qu’avec d'autres modèles.
- Possibilité d'améliorer le recall en ajustant le **threshold de classification**.
- Essai de techniques de **suréchantillonnage (SMOTE)** ou de **pondération des classes** pour encore améliorer les performances.

## 💪 Améliorations possibles
- Test de modèles plus avancés (**LSTM, CNN sur séries temporelles**).
- Utilisation de **features supplémentaires** si disponibles.
- Implémentation d’un **système de détection en temps réel**.

---
## 👤 Auteur : **Rabab**
## 📝 Licence : **Open Database License**
## 📚 Références
- **Dataset** : [Kaggle - Credit Card Fraud Detection](https://www.kaggle.com/mlg-ulb/creditcardfraud)
- **Paper de référence** : Dal Pozzolo et al., IEEE, 2018

