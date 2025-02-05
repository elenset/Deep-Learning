# Rapport sur le Boston Housing Dataset

## 1. Introduction du Problème Choisi

Le **Boston Housing Dataset** est un ensemble de données classique utilisé pour prédire les prix des maisons à Boston. Il contient 506 échantillons et 13 caractéristiques, telles que la criminalité, la proximité des écoles, et l'âge des maisons. L'objectif principal de ce projet est de construire un modèle de régression capable de prédire le prix médian des maisons (MEDV) en fonction de ces caractéristiques.

## 2. Description des Étapes de Préparation des Données

### 2.1 Chargement des Données
Les données ont été chargées à partir d'un fichier texte contenant les informations sur les maisons à Boston.

### 2.2 Normalisation
Les caractéristiques ont été normalisées à l'aide de `StandardScaler` pour garantir que toutes les variables sont sur la même échelle, ce qui aide à améliorer la convergence lors de l'entraînement du modèle.

### 2.3 Division des Données
Les données ont été divisées en trois ensembles :
- **Ensemble d'entraînement** : 70 % des données.
- **Ensemble de validation** : 20 % des données.
- **Ensemble de test** : 10 % des données.

## 3. Justification des Choix d’Architecture et d’Hyperparamètres

### 3.1 Architecture du Modèle
Le modèle est composé de plusieurs couches `Dense` :
- **Couche d'entrée** : Adaptée au nombre de caractéristiques (13).
- **Couches cachées** : Deux couches avec un nombre décroissant de neurones (64 et 32), suivies par une couche supplémentaire (16) pour capturer des relations non linéaires.
- **Couche de sortie** : Une seule neurone sans activation pour prédire une valeur continue (prix médian).

### 3.2 Hyperparamètres
- **Fonction de perte** : `mean_squared_error` a été choisie car elle est couramment utilisée pour les problèmes de régression.
- **Optimiseur** : Adam a été utilisé pour sa capacité à s'adapter dynamiquement aux gradients.
- **Taux d'apprentissage** : Un taux initial de 0.001 a été utilisé, ce qui est standard pour Adam.

## 4. Analyse des Performances du Modèle Avant et Après Corrections

### 4.1 Performances Initiales
Après l'entraînement initial, le modèle a montré une perte relativement faible sur l'ensemble d'entraînement mais une perte plus élevée sur l'ensemble de test, indiquant un potentiel surapprentissage.

### 4.2 Corrections Apportées
Pour remédier à l'overfitting, plusieurs techniques ont été appliquées :
- **Régularisation L2** a été ajoutée aux couches.
- **Dropout** a été intégré pour réduire la dépendance entre les neurones.
- **Early Stopping** a été mis en place pour arrêter l'entraînement lorsque la perte de validation ne s'améliorait plus.

### 4.3 Performances Finales
Après avoir appliqué ces corrections, le modèle a montré une amélioration significative dans ses performances sur l'ensemble de test, avec une réduction notable du MAE et du RMSE.

## 5. Graphiques Montrant l’Évolution des Pertes et Métriques

### Graphique des Pertes
![Graphique des Pertes](https://raw.githubusercontent.com/elenset/Deep-Learning/master/Graphique%20des%20Pertes.JPG)

### Graphique du MAE
![Évolution du MAE]([URL_DU_GRAPHIQUE_DU_MAE](https://raw.githubusercontent.com/elenset/Deep-Learning/master/Graphique%20du%20MAE.JPG))

## Conclusion

Le projet a permis de construire un modèle performant pour prédire les prix des maisons à Boston en utilisant diverses techniques d'apprentissage automatique. Les ajustements apportés au modèle ont permis d'améliorer sa capacité à généraliser sur des données non vues, ce qui est essentiel dans tout projet d'apprentissage supervisé.
