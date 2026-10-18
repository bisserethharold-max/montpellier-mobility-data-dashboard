# Analyse des Mobilités & Bornes Électriques, Métropole de Montpellier

Ce projet présente un tableau de bord interactif sous Power BI permettant d'analyser le déploiement des bornes de recharge électrique au regard des flux de circulation routière dans la Métropole de Montpellier.

## Objectif du Projet

L'enjeu est de croiser les données de trafic avec les infrastructures de recharge pour identifier la couverture du réseau électrique et anticiper les besoins d'aménagement.

### Besoins utilisateurs (User Stories) :
- **Chargé de mission mobilité :** Visualiser la répartition des bornes par station pour repérer les secteurs à équiper.
- **Urbaniste / Métropole :** Consulter le volume moyen journalier de véhicules (MJA) pour évaluer la charge des grands axes.
- **Décideur public :** Disposer d'une vue synthétique combinant indicateurs de trafic et de recharge sur une seule page.

## Démarche & Choix Techniques

1. **Sources de données (Open Data Montpellier) :**
   - `MMM_MMM_BornesElecEtotem` : Réseau des bornes de recharge e-totem.
   - `MMM_MMM_Comptage` : Données de comptage du trafic routier.

2. **Nettoyage & Préparation (Power Query) :**
   - Typage des colonnes, suppression des doublons et validation des données.

3. **Indicateurs clés (DAX) :**
   - **Nb_Bornes** : COUNTROWS(MMM_MMM_BornesElecEtotem)
   - **Total_Vehicules** : SUM(MMM_MMM_Comptage[mja_jo])

4. **Restitution (Power BI) :**
   - Conception d'un tableau de bord épuré articulé autour de 2 KPI clés et de graphiques de répartition par station/axe.

## Principaux Chiffres (MVP)

- **Nombre de bornes de recharge :** 52 bornes
- **Trafic cumulé mesuré (MJA) :** 73 millions de véhicules

## Évolutions prévues

- Croisement géographique plus fin par commune/quartier.
- Ajout de filtres temporels sur les évolutions de trafic.
