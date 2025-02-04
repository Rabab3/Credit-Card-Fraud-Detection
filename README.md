📌 Credit Card Fraud Detection
Projet de Machine Learning pour détecter les fraudes sur les transactions par carte bancaire.

🔍 Explication des données
Le dataset utilisé provient de Kaggle : Credit Card Fraud Detection.

- Il contient 284 807 transactions, dont 492 frauduleuses (≈ 0.172%).
- Les variables V1, V2, ..., V28 sont issues d'une transformation PCA.

- Deux variables supplémentaires :
  Time : Temps écoulé depuis la première transaction.
  Amount : Montant de la transaction.

- La variable cible Class :
  0 = Transaction légitime
  1 = Transaction frauduleuse

🛠️ Technologies utilisées
- Python 3.9+
- Jupyter Notebook
- Pandas, NumPy : Manipulation des données
- Matplotlib, Seaborn : Visualisation des données
- Scikit-Learn : Modèles de Machine Learning
- Imbalanced-learn : Gestion du déséquilibre des classes
