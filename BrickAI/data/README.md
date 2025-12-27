# 📊 Données du Projet

## 📥 Téléchargement

Les données sont sur **Google Drive** (trop volumineuses pour GitHub).

**[📥 Accéder aux données du projet principal](https://drive.google.com/drive/folders/1cB8scbYWxysJH98BO_TQlCaZEQQnjX8V?usp=drive_link)**

---

## 📁 Contenu

**Fichiers disponibles :**
- `loyers_clean_2024.csv` - Données loyers
- `insee_logement_2021_clean.csv` - Données INSEE logements
- `gares_clean.csv` - Données gares SNCF
- `enseignement_superieur_clean.csv` - Données universités
- `dvf_clean_2024.csv` - Valeurs foncières 2024
- `dvf_clean_2020_2024.csv` - Valeurs foncières 2020-2024

**Source :** data.gouv.fr (Open Data)

---

## 🚀 Utilisation

### Dans Google Colab
```python
from google.colab import drive
drive.mount('/content/drive')

# Tes données sont dans :
# /content/drive/MyDrive/BrickAI_Data/projet_principal/
```

### En local

1. Clique sur le lien ci-dessus
2. Télécharge les fichiers nécessaires
3. Place-les dans `BrickAI/data/`

---

## ⚠️ Note

Ces données sont utilisées par le notebook **`BrickAI.ipynb`** pour :
- Analyse des prix immobiliers
- Recommandations de villes
- Calculs de rentabilité

Sans ces données, les widgets d'analyse ne fonctionneront pas.
```