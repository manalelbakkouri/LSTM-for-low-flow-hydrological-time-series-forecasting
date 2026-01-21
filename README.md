# LSTM-for-low-flow-hydrological-time-series-forecasting
## for Low-Flow Hydrological Time Series Forecasting
**Reproduction et adaptation de l’étude :**  
*Sahoo et al. (2019), Acta Geophysica*

**Plateforme :** Google Colab (GPU NVIDIA T4)  
**Langage :** Python (TensorFlow / Keras) 

## Contexte

La prévision des séries temporelles hydrologiques, en particulier des **débits faibles (low-flow)**,
constitue un enjeu majeur pour la gestion durable des ressources en eau, la planification
hydraulique et la préservation des écosystèmes aquatiques.

Les méthodes statistiques classiques présentent des limites face à la **non-linéarité** et aux
**dépendances temporelles longues** caractéristiques des processus hydrologiques.
Les réseaux de neurones récurrents, et en particulier les **Long Short-Term Memory (LSTM)**,
offrent une alternative prometteuse grâce à leurs mécanismes de mémoire interne.

## Objectifs

Les objectifs principaux de ce travail sont :

- Implémenter un modèle **LSTM many-to-one** pour la prévision du low-flow mensuel.
- Reproduire la méthodologie proposée par **Sahoo et al. (2019)** sur un dataset hydrologique réel.
- Comparer les performances du LSTM avec :
  - un **RNN classique**
  - une **méthode naïve saisonnière** (benchmark).
- Évaluer les modèles à l’aide des métriques :
  **RMSE, MAE, coefficient de corrélation (R) et Nash–Sutcliffe Efficiency (ENS)**.

  ## Description du dataset

Le dataset utilisé contient des **données de débit journalier** mesurées à une station hydrologique.
Les données brutes sont pré-traitées selon les étapes suivantes :

- Sélection de la variable **Discharge** (débit journalier).
- Agrégation mensuelle et calcul du **low-flow Q75**.
- Transformation logarithmique pour stabiliser la variance.
- Normalisation des données.
- Construction de séquences temporelles avec un **lag de 12 mois**.

Ce pré-traitement est conforme à la méthodologie décrite dans l’article de référence.

## Méthodologie

La méthodologie suivie dans ce notebook est structurée comme suit :

1. Importation et nettoyage des données hydrologiques.
2. Calcul de l’indicateur de low-flow (Q75 mensuel).
3. Préparation des séquences temporelles.
4. Implémentation et entraînement des modèles :
   - LSTM
   - RNN
   - Méthode naïve
5. Évaluation et comparaison des performances.
6. Analyse et interprétation des résultats.

## Configuration expérimentale

- **Environnement** : Google Colab
- **Accélérateur matériel** : GPU NVIDIA T4
- **Framework** : TensorFlow / Keras
- **Optimiseur** : Adam
- **Fonction de perte** : Mean Squared Error (MSE)
- **Découpage des données** :
  - 70 % entraînement
  - 15 % validation
  - 15 % test

## Référence

Sahoo, B. B., Jha, R., Singh, A., & Kumar, D. (2019).  
**Long short-term memory (LSTM) recurrent neural network for low-flow hydrological time series forecasting**.  
*Acta Geophysica*. https://doi.org/10.1007/s11600-019-00330-1


