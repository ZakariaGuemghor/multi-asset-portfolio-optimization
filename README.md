![Image de couverture du projet](images/image_couverture.png)

# Optimisation Stratégique d'un Portefeuille Multi-Actifs 

## Introduction

La construction de portefeuille moderne exige des outils capables d'intégrer des contraintes d'investissement réalistes et de s'adapter dynamiquement aux conditions de marché. Les approches traditionnelles peinent souvent à concilier la recherche de performance absolue avec le respect d'une allocation stratégique et la gestion de l'écart par rapport à un benchmark.

Ce projet propose un cadre d'optimisation de portefeuille avancé qui dépasse ces limites. L'objectif est de développer une stratégie qui maximise le rendement ajusté du risque tout en respectant un cahier des charges d'investissement strict, incluant des contraintes d'allocation hiérarchiques et un contrôle de l'erreur de suivi (*Tracking Error*).

## Objectif du Projet

Ce projet vise à concevoir, optimiser et valider une stratégie d'allocation d'actifs multi-classe. L'idée centrale est de démontrer l'efficacité d'un processus de gestion de portefeuille dynamique, basé sur un rééquilibrage périodique et une évaluation rigoureuse de la performance historique.

L'objectif final est de construire un portefeuille robuste qui non seulement génère une performance attractive, mais reste également fidèle à une politique d'investissement prédéfinie, offrant ainsi un cadre de décision fiable et réaliste pour un gérant.

## Structure du Projet

La méthodologie est structurée en quatre étapes séquentielles, formant un pipeline complet depuis la donnée jusqu'à l'analyse de performance.

#### 1. Définition de l'Univers d'Investissement et Collecte des Données
La première étape consiste à définir l'univers d'actifs et à collecter leurs données historiques sur une période de 10 ans. Cet univers diversifié inclut :
-   **Actions :** Réparties en secteurs clés (Technologie, Finance, etc.), filtrées par capitalisation.
-   **Obligations et Matières Premières :** Sélection d'ETFs représentatifs, filtrés par volume.
-   **Benchmark :** Utilisation de l'ETF `AOR` (iShares Core Growth Allocation) comme référence.
Les données de prix sont ensuite nettoyées et converties en rendements logarithmiques.

#### 2. Modélisation et Optimisation du Portefeuille
Le cœur du projet réside dans un modèle d'optimisation mathématique conçu pour trouver l'allocation d'actifs optimale. Ce modèle intègre :
-   **Une Fonction Objectif Hybride :** Maximise le Ratio de Sharpe tout en pénalisant la *Tracking Error* par rapport au benchmark.
-   **Des Contraintes d'Allocation Complexes :** Incluant des poids fixes par classe d'actifs (60% Actions, 30% Obligations, 10% Matières Premières), des minimums par secteur, un plafond de volatilité, et une gestion contrôlée de la vente à découvert.

#### 3. Backtesting Stratégique sur 10 Ans
Cette étape simule la performance de la stratégie dans le temps. Un moteur de backtesting rééquilibre le portefeuille à une fréquence définie (ex: trimestrielle), en relançant le processus d'optimisation à chaque période sur la base des données historiques alors disponibles. La performance est ensuite agrégée pour reconstituer l'historique du portefeuille.

#### 4. Analyse de Performance et Comparaison
La dernière étape évalue les résultats du backtest pour mesurer l'efficacité de la stratégie :
-   **Calcul des Métriques de Performance :** Rendement cumulé, rendement annualisé et rendements annuels calendaires.
-   **Comparaison au Benchmark :** La performance du portefeuille est tracée face à celle du benchmark `AOR` pour visualiser la valeur ajoutée.
-   **Analyse des Allocations :** Une fonction interactive permet d'inspecter la composition exacte du portefeuille à n'importe quelle date historique, offrant une vision transparente des décisions prises par le modèle.