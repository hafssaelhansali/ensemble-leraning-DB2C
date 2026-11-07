# Ensemble Learning sur DB2C

TP de Machine Learning : comparaison de méthodes d'ensemble pour classer des images de **voitures** et de **bateaux**.

## Dataset
DB2C : 490 images couleur (120×80 px) en 2 classes.
- `obj_car` : 400 images
- `obj_ship` : 90 images

Les classes sont déséquilibrées, donc on utilise le F1 et le recall en plus de l'accuracy.

## Modèles de base
SVM RBF, SVM linéaire, SVM sigmoïde, KNN (k=3), KNN (k=5) et arbre de décision.

## Méthodes d'ensemble
- **Vote** : majoritaire, moyenne (soft) et pondéré
- **Bagging** (Bootstrap Aggregation)
- **Boosting** : AdaBoost et Gradient Boosting
- **Stacking** (méta-modèle : régression logistique)

## Méthode
1. Chargement des images (redimensionnées en 60×40) et transformation en vecteurs
2. Prétraitement : StandardScaler puis PCA (95 % de variance)
3. Séparation 80 % train / 20 % test, validation croisée en 5 plis
4. Entraînement et évaluation : accuracy, precision, recall, F1, matrices de confusion

## Résultats
Le vote et le stacking ont la meilleure validation croisée (≈ 0.977). AdaBoost (souches) a le meilleur F1 sur le test (0.923). Les méthodes d'ensemble apportent surtout de la stabilité, notamment pour l'arbre de décision.

Le jeu de test est petit (98 images), donc les écarts entre les meilleures méthodes sont faibles.


## Technologies
Python, scikit-learn, NumPy, pandas, Matplotlib, Pillow

## Auteure
Hafssa El Hansali – Master Machine Learning et Intelligence Multimédia, FSDM Fès
