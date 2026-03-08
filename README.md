# Offshore Leaks Analysis : Data Science & Théorie des Graphes

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-150458)
![NetworkX](https://img.shields.io/badge/NetworkX-Graph%20Theory-lightgrey)
![Scikit-Learn](https://img.shields.io/badge/Scikit_Learn-Machine%20Learning-F7931E)
![ESIEA](https://img.shields.io/badge/Projet-ESIEA-red)

## À propos du projet
Ce projet a été réalisé dans le cadre d'un Travail Pratique (TP) à l'**ESIEA**. Il vise à explorer, analyser et modéliser la base de données massive des fuites financières de l'**ICIJ** (Panama Papers, Paradise Papers, Offshore Leaks, etc.). 

L'objectif principal est d'utiliser la **Data Science**, l'**Analyse de Réseaux (Graph Theory)** et le **Machine Learning** pour démasquer les schémas complexes de création de sociétés écrans, identifier les acteurs centraux (hubs, cabinets d'avocats) et détecter les anomalies financières (ex: utilisation massive de prête-noms).

---

## Fonctionnalités et Notions abordées

Le notebook est divisé en 4 grandes parties analytiques :

1. ** Nettoyage et Cartographie Temporelle (Data Wrangling)**
   - Traitement des valeurs temporelles aberrantes et gestion des valeurs manquantes.
   - Analyse de l'évolution historique de la création de sociétés offshore.
   - Détection d'anomalies textuelles (Noms génériques, utilisation d'homoglyphes cyrilliques via Regex).

2. ** Analyse de Réseau (Théorie des Graphes avec NetworkX)**
   - Construction d'un graphe modélisant les relations entre Entités, Officiers et Intermédiaires.
   - Calcul de la centralité de degré pour identifier les "Super-Hubs".
   - Détection de communautés (Algorithme de Louvain) et optimisation Big Data via l'extraction du *K-Core*.
   - Identification des prête-noms (*nominees*) par l'analyse de la densité des sous-graphes (structures en "étoile pure").

3. ** Analyse Géographique**
   - Création de matrices de flux (Origine-Destination) liant la nationalité des clients aux juridictions offshore.
   - Visualisation via Heatmaps interactives.
   - Comparaison des stratégies géographiques selon les différents scandales (Panama Papers vs Offshore Leaks).

4. ** Machine Learning (Scikit-Learn)**
   - **Apprentissage Non Supervisé :** Clustering (*K-Means*) pour segmenter le profil économique des paradis fiscaux.
   - **Détection d'Anomalies :** Utilisation d'*Isolation Forest* pour flagger les juridictions aux comportements statistiquement suspects.
   - **Apprentissage Supervisé :** Entraînement d'un *Arbre de Décision* (et Random Forest) pour prédire le statut actif/inactif d'une entité selon ses caractéristiques (Features).

---

##  Installation et Démarrage rapide

Pour reproduire cette analyse ou explorer le notebook sur votre machine locale, suivez ces étapes :

### 1. Cloner le dépôt
bash
git clone [https://github.com/votre-nom-utilisateur/nom-du-repo.git](https://github.com/votre-nom-utilisateur/nom-du-repo.git)
cd nom-du-repo

### 2. Créer un environnement virtuel (Recommandé)
python -m venv env
# Sur Windows :
env\Scripts\activate
# Sur macOS/Linux :
source env/bin/activate

###  3. Installer les dépendances
Assurez-vous d'avoir installé les librairies nécessaires via le fichier requirements.txt (ou installez-les manuellement).

Bash
pip install pandas numpy matplotlib seaborn networkx python-louvain scikit-learn tqdm
(Note : La librairie python-louvain est requise pour l'algorithme de détection de communautés).

### 4. Téléchargement des données (Dataset ICIJ)
En raison de leur taille massive, les fichiers CSV bruts de l'ICIJ ne sont pas inclus dans ce dépôt.

Téléchargez les données depuis le site officiel de l'ICIJ ou via votre source de TP.

Placez les fichiers CSV (entities.csv, officers.csv, intermediaries.csv, relationships.csv, addresses.csv) à la racine du projet ou dans un dossier data/.

Vérifiez les chemins d'accès dans la première cellule d'importation du notebook.

### 5. Lancer le Jupyter Notebook
Bash
jupyter notebook
Ouvrez le fichier principal .ipynb et exécutez les cellules de haut en bas.
