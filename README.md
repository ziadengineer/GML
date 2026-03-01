# Projet Graph Machine Learning — Analyse comparative d’ego-réseaux Twitter

Ce dépôt contient notre projet de **Graph Machine Learning (GML)** : une analyse comparative de plusieurs **ego-réseaux Twitter** (format SNAP), combinant des méthodes de **science des réseaux** (métriques, centralités, communautés) et des approches **Graph ML** (embeddings, tâche aval, bonus deep learning).

## 👥 Auteurs
- DHARDEMARE
- VAUTERIN
- ALALI

## 📁 Contenu du dépôt
- `DHARDEMARE_VAUTERIN_ALALI.ipynb` : notebook principal (utilisable pour la présentation)
- `twitter_ego/twitter/` : dossier des données (fichiers `.edges`, `.feat`, `.egofeat`, `.circles`)
- `twitter_ego/twitter/summary_tables/` : **sorties générées** (CSV + figures)

> ⚠️ **Attention** : le dossier de données peut être volumineux. Selon les consignes, il peut être fourni séparément ou via un lien si nécessaire.

## 🎯 Objectifs
1. Charger plusieurs ego-réseaux Twitter
2. Construire les graphes (NetworkX)
3. Calculer des métriques de base et comparatives : taille, densité, degrés, clustering, connectivité
4. Identifier des réseaux “typiques” vs “atypiques” + sélectionner un réseau pour une analyse détaillée
5. Calculer les **centralités** : Degree, Eigenvector, Closeness, Betweenness, PageRank
6. Détecter les **communautés** : Louvain + Girvan–Newman et comparer via modularité / conductance
7. Apprendre des **embeddings** : Laplacian Eigenmaps (spectral) + Node2Vec (random walks / skip-gram)
8. Réaliser une **tâche aval** (Graph ML) : *link prediction* à partir des embeddings Node2Vec
9. (Bonus Deep Learning) entraîner un **GCN** sur des labels synthétiques et visualiser les embeddings

## 🧠 Données (SNAP Twitter ego networks)
Chaque ego-réseau est défini par des fichiers (par identifiant `ID`) :
- `ID.edges` : liste d’arêtes (source, cible)
- `ID.feat`, `ID.egofeat` : attributs de nœuds (optionnel dans notre analyse)
- `ID.circles` : cercles/communautés “ground truth” (optionnel / extension)

Dans notre pipeline, nous utilisons principalement les **arêtes** (`.edges`).  
Certaines analyses sont faites sur la version **non orientée** du graphe (ex. clustering, communautés, embeddings).

## ⚙️ Installation & dépendances
### Environnement recommandé
- Python ≥ 3.9

### Packages principaux
- `networkx`, `pandas`, `numpy`, `matplotlib`, `seaborn`
- `scikit-learn`
- `scipy`
- `node2vec`

### Bonus Deep Learning (GCN)
- `torch` (PyTorch)

Exemple d’installation :
```bash
pip install pandas numpy networkx matplotlib seaborn scikit-learn scipy node2vec
# Bonus GCN:
pip install torch torchvision torchaudio