# Analyse des retards de livraison et optimisation de la satisfaction client

Projet de Data Analysis basé sur le dataset Olist (e-commerce brésilien), visant à identifier les maillons faibles du transport et leur impact sur la satisfaction client.

## Problématique

Une plateforme e-commerce subit une baisse de sa note de satisfaction client, causée principalement par des retards de livraison. Ce projet identifie précisément les régions, transporteurs et catégories de produits responsables, afin de proposer des recommandations concrètes.

## Données

- **Source** : [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/jayeshsalunke101/brazilian-ecommerce-publicdataset) (Kaggle)
- **Volume** : ~99 000 commandes, 9 fichiers CSV (orders, order_items, products, customers, geolocation, reviews, payments, sellers)
- **Variable cible** : délai de livraison réel (date de réception - date d'achat) vs délai estimé

Le dataset final nettoyé (`olist_final.zip`) est disponible à la racine du dépôt. Décompressez-le pour obtenir `olist_final.csv`.

## Méthodologie

1. Chargement des données via l'API Kaggle (`kagglehub`)
2. Analyse exploratoire (EDA) : valeurs manquantes, doublons, distributions
3. Pipeline ETL en Python (Pandas) : calcul des délais, jointures entre tables, export du dataset final
4. Construction d'un tableau de bord Power BI en schéma en étoile avec mesures DAX personnalisées
5. Interprétation des résultats et formulation de recommandations

## Langages et outils utilisés

- Python (Pandas, Matplotlib, Seaborn) — nettoyage et EDA
- Power BI Desktop — tableau de bord interactif et mesures DAX
- Google Colab — environnement d'exécution du notebook
- Git / GitHub — versioning et collaboration

## Résultats obtenus

| Indicateur | Valeur |
|---|---|
| Commandes totales | 97 007 |
| Délai moyen de livraison | 12,1 jours |
| Taux de retard | 6,8 % |
| Écart moyen à l'estimation | -11,9 jours (avance) |
| Note moyenne (livraison à l'heure) | 4,3 / 5 |
| Note moyenne (livraison en retard) | 2,3 / 5 |

**Insight principal** : les commandes livrées en retard obtiennent une note de satisfaction quasiment 2 points inférieure à celles livrées à temps. Les états du Nord et Nord-Est du Brésil (RR, AL, MA, CE) affichent les délais et taux de retard les plus élevés.

## Structure du dépôt
## Comment reproduire l'analyse

1. Ouvrir le notebook dans `Carnets/` via Google Colab
2. Exécuter les cellules dans l'ordre (le notebook télécharge automatiquement les données via `kagglehub`)
3. Le fichier `olist_final.csv` est généré en sortie
4. Ouvrir le fichier `.pbix` dans Power BI Desktop pour explorer le tableau de bord interactif

## Limites du projet

- Le dataset couvre uniquement la période 2016-2018
- Certaines catégories de produits ont des valeurs manquantes (poids, dimensions)
- Les données de géolocalisation sont approximatives (basées sur le code postal)
- Aucune donnée sur les transporteurs eux-mêmes (seulement sur les vendeurs)

## Perspectives d'amélioration

- Intégrer un modèle prédictif de risque de retard
- Affiner l'analyse par transporteur si la donnée devient disponible
- Déployer le dashboard sur Power BI Service ou Streamlit pour un accès public

## Auteur

Mansouratou ZAKARI — Projet réalisé dans le cadre du certificat Data Analysis
