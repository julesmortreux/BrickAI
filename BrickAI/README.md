# 🧱 BrickAI - Plateforme Intelligente d'Investissement Immobilier Étudiant

> Analyseur de faisabilité d'investissement immobilier avec IA de vision pour étudiants et jeunes investisseurs

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![YOLOv8](https://img.shields.io/badge/YOLOv8-Computer_Vision-green.svg)](https://docs.ultralytics.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-En_développement-orange)](docs/ROADMAP.md)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/TON-USERNAME/BrickAI/blob/main/notebooks/BrickAI.ipynb)

---

## 🎯 Vision du Projet

**BrickAI** est une plateforme d'aide à la décision pour l'investissement immobilier locatif, conçue spécifiquement pour les **étudiants et jeunes actifs**. 

Le projet combine :
- 📊 **Analyse de profil financier** personnalisée
- 💰 **Simulation de financement** adaptée aux étudiants
- 🏙️ **Recommandations de villes** par rentabilité
- 🔍 **Scraping intelligent** d'annonces SeLoger
- 🤖 **Intelligence Artificielle** pour évaluation automatique des biens *(en développement)*

---

## 🚀 Fonctionnalités Actuelles

### ✅ Module 1 : Analyse de Faisabilité (100% Fonctionnel)

**14 Widgets Interactifs** permettant de :

#### 📊 Évaluation de Profil
- Calcul d'un **score de faisabilité** (0-100) personnalisé
- Basé sur : revenus, statut étudiant, apport, garant, années restantes
- Recommandations de financement adaptées (prêt différé/immédiat)

#### 💰 Simulation Financière
- **Budget d'achat réaliste** selon votre profil
- **Capacité d'emprunt** estimée
- **Mensualités supportables** (règle 33%)
- Comparaison avec/sans apport

#### 🏙️ Recommandations Géographiques
- **30+ villes** classées par rentabilité locative
- 3 catégories : Très Rentable (10%+) / Rentable (8%+) / Modérée (6%+)
- Prix au m², demande locative, potentiel étudiant

#### 🔍 Analyse d'Annonces SeLoger
- **Scraping automatique** via ScraperAPI
- Extraction : prix, surface, pièces, description
- **Score d'opportunité** (0-100) calculé sur :
  - Prix/m² vs marché
  - Rentabilité locative estimée
  - Adéquation budget
  - Potentiel plus-value
- **Recherche automatique** selon votre profil

---

### 🤖 Module 2 : IA de Vision (En Développement - 60%)

**Modèle YOLOv8 Classification** pour analyse automatique des biens :

#### 🚿 Classificateur Salle de Bain (Version Alpha)

**Objectif :** Évaluer l'état d'une salle de bain à partir de photos

**Architecture :**
- Modèle : YOLOv8n-cls (nano)
- Dataset : 150 images SeLoger labellisées manuellement
- Classes : BAS (travaux) / MOYEN (correct) / HAUT (excellent)
- Accuracy actuelle : **73.33%**

**Utilisation prévue :**
```python
# Vision future (intégration prévue)
modele_sdb = YOLO('models/sdb_classifier.pt')
resultat = modele_sdb.predict(photo_sdb)
# → Impact sur score final de l'annonce
```

#### 🔮 Évolutions Prévues

**Phase 1 (Q1 2025) - Intégration SDB**
- Connexion modèle IA ↔ analyse d'annonce
- Ajustement automatique du score selon état SDB
- Impact sur estimation travaux

**Phase 2 (Q2 2025) - Extension Cuisines**
- Modèle YOLOv8 pour cuisines
- Dataset 300+ images
- Classification 3 niveaux

**Phase 3 (Q3 2025) - Multi-critères**
- Façade extérieure
- État général intérieur
- Scoring composite global
---

## 📊 Architecture Technique

### Projet Principal (`BrickAI.ipynb`)

**14 Widgets Jupyter interactifs :**

| Widget | Nom | Fonctionnalité |
|--------|-----|----------------|
| **1** | Configuration Profil | Saisie paramètres utilisateur |
| **2** | Score Faisabilité | Calcul score + recommandations |
| **3** | Villes Recommandées | Top villes par rentabilité |
| **4** | Estimateur Budget | Simulation financière |
| **5** | Résumé Financement | Synthèse recommandations |
| **6** | Critères Recherche | Paramètres scraping |
| **7** | Analyse Annonce | Scraping + notation 1 URL |
| **8** | Calcul Score | Détail scoring |
| **9** | Conseils Personnalisés | Recommandations sur le bien |
| **10** | Comparateur | Analyse 5 annonces |
| **11** | Tableau Comparatif | Visualisation multi-biens |
| **12** | Meilleure Opportunité | Affichage top 1 |
| **13** | Classes Scraping | Code scraping SeLoger |
| **14** | Recherche Auto | Scraping 5-10 annonces auto |

**Technologies :**
```python
requests          # HTTP pour scraping
BeautifulSoup4    # Parsing HTML
ipywidgets        # Interface interactive
ScraperAPI        # Contournement anti-bot
```

### Modèle IA (`ModelSDB.ipynb`)

**Pipeline d'entraînement YOLOv8 :**
```
1. Upload Dataset (3 ZIP : bas/moyen/haut)
2. Organisation (70% train / 20% valid / 10% test)
3. Entraînement (100 epochs, early stopping)
4. Évaluation 
5. Interface test Gradio
```

**Cellules :**
- Cell 1 : Installation (ultralytics, gradio)
- Cell 2 : Upload & organisation données
- Cell 3 : Split train/valid/test
- Cell 4 : Entraînement YOLOv8
- Cell 5 : Évaluation & résultats
- Cell 6 : Interface graphique test

Voir [docs/MODELE_IA.md](docs/MODELE_IA.md) pour détails techniques.

---

## 🚀 Installation & Utilisation

### Prérequis
- Python 3.10+
- Compte Google (pour Colab)
- Compte ScraperAPI (gratuit, 1000 crédits/mois)

### Option 1 : Google Colab (Recommandé)

**Projet Principal :**
1. [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/TON-USERNAME/BrickAI/blob/main/notebooks/BrickAI.ipynb)
2. Exécute les cellules dans l'ordre
3. Configure ton profil (Widget 1)
4. Explore les widgets !

**Modèle IA (optionnel) :**
1. [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/TON-USERNAME/BrickAI/blob/main/notebooks/ModelSDB.ipynb)
2. Active GPU : `Exécution > Modifier type d'exécution > T4 GPU`
3. Suis les instructions du notebook

### Option 2 : Installation Locale
```bash
# Cloner le repo
git clone https://github.com/TON-USERNAME/BrickAI.git
cd BrickAI

# Environnement virtuel
python -m venv venv
source venv/bin/activate  # Mac/Linux
# ou venv\Scripts\activate  # Windows

# Installer dépendances
pip install -r requirements.txt

# Lancer Jupyter
jupyter notebook
```

### Configuration ScraperAPI

1. Créer compte gratuit : https://www.scraperapi.com
2. Copier ta clé API
3. Dans `BrickAI.ipynb`, Widget 13, remplacer :
```python
SCRAPER_API_KEY = "TA_CLE_API_ICI"
```

Voir [docs/GUIDE_UTILISATION.md](docs/GUIDE_UTILISATION.md) pour guide détaillé.

---

## 📁 Structure du Projet
```
BrickAI/
├── notebooks/
│   ├── BrickAI.ipynb          # 🏆 Projet principal (widgets)
│   └── ModelSDB.ipynb         # 🤖 Modèle IA SDB
├── models/
│   └── README.md              # Instructions modèle
├── data/
│   ├── sample_images/         # Exemples images SDB
│   └── README.md              # Infos données
├── docs/
│   ├── GUIDE_UTILISATION.md   # Guide complet
│   ├── ARCHITECTURE.md        # Détails techniques
│   ├── ROADMAP.md             # Planning
│   └── MODELE_IA.md           # Doc modèle IA
├── .gitignore
├── README.md                  # Ce fichier
├── requirements.txt
├── LICENSE
└── config.example.json
```

---

## 🛠️ Technologies

**Backend :**
- Python 3.10+
- Jupyter Notebook / Google Colab
- YOLOv8 (Ultralytics)
- PyTorch

**Scraping :**
- Requests + BeautifulSoup4
- ScraperAPI

**Interface :**
- ipywidgets
- Gradio (modèle IA)

**ML/IA :**
- YOLOv8 Classification
- Transfer Learning (ImageNet)

---

### Priorités actuelles :
- 🎯 Dataset cuisines (300+ images)
- 🎯 Intégration modèle IA → pipeline
- 🎯 Tests unitaires
- 🎯 Documentation API

---

## ⚠️ Avertissements

- **Estimations** : Basées sur moyennes de marché (non contractuelles)
- **ScraperAPI** : 1000 crédits gratuits/mois (~200 annonces)
- **Données SeLoger** : Usage conforme aux CGU (données publiques uniquement)

---

## 👤 Auteur

**[MORTREUX Jules]**
- 🎓 Projet Intelligence Lab
- 📧 jules.mortreux@edu.ece.fr
- 🐙 GitHub : @julesmortreux
