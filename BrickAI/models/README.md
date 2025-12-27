# 🤖 Modèle IA - Classificateur SDB

## 📥 Téléchargement des Données d'Entraînement

Les images d'entraînement sont sur **Google Drive**.

**[📥 Accéder aux données du modèle SDB](https://drive.google.com/drive/folders/1O7nmSWhpmq2tYR_LmgBYvHIjPkDDSgkY?usp=drive_link)**

---

## 🖼️ Contenu

**3 dossiers d'images :**
- `sdb_bas/` - 50 images salles de bain à rénover
- `sdb_moyen/` - 50 images état correct
- `sdb_haut/` - 50 images excellent état

**Total :** 150 images labellisées manuellement

---

## 🚀 Utilisation

### Entraîner le modèle

1. Ouvre le notebook **`ModelSDB.ipynb`**
2. Clique sur le lien Google Drive ci-dessus
3. Télécharge les 3 dossiers
4. Zip chaque dossier :
   - `sdb_bas.zip`
   - `sdb_moyen.zip`
   - `sdb_haut.zip`
5. Upload les 3 ZIP dans Colab (Cell 2)
6. Lance l'entraînement

### Utiliser le modèle entraîné

⏳ **Modèle en cours de finalisation**

Le fichier `.pt` du modèle entraîné sera disponible après validation finale.

---

## 📊 Informations Techniques

- **Architecture :** YOLOv8n-cls (nano)
- **Dataset :** 150 images SeLoger
- **Classes :** bas / moyen / haut
- **Objectif :** Évaluer l'état des salles de bain pour ajuster les estimations immobilières

---

## ⚠️ Note

Ce modèle est utilisé dans le cadre du projet **BrickAI** pour analyser automatiquement l'état des biens immobiliers à partir de photos.

**Statut :** 🚧 En développement (Phase 2)
```