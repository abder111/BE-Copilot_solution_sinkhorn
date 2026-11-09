# Classification de Sessions Utilisateurs (Solution Stacking & Sinkhorn)

Ce projet contient la solution complète sous forme de notebook Jupyter pour la prédiction et l'identification d'utilisateurs à partir de leurs sessions d'actions et de leur navigateur web.

---

##  Contenu du dossier

| Fichier / Dossier | Description |
| :--- | :--- |
| `YOLO_copilot_solution_sinkhorn.ipynb` | Notebook principal contenant tout le pipeline (prétraitement, modélisation TF-IDF + LinearSVC, méta-modèle Stacking, équilibrage par algorithme de Sinkhorn). |
| `train.csv` | Données d'entraînement (colonnes : utilisateur, navigateur, actions...). |
| `test.csv` | Données de test (colonnes : navigateur, actions...). |
| `requirements.txt` | Liste des dépendances Python nécessaires. |
| `README.md` | Guide d'installation et d'exécution (ce fichier). |
| `submission28_a1.csv` *(généré)* | Fichier de prédictions final généré lors de l'exécution. |
| `nb28_checkpoints/` *(généré)* | Dossier de checkpoints créé automatiquement pour sauvegarder les scores intermédiaires. |

---

## ⚙️ Prérequis

- **Python 3.9** ou supérieur (3.10 ou 3.11 recommandé).

---

## 🚀 Guide d'installation et de démarrage rapide

### 1. Décompresser l'archive
Décompressez le fichier `.zip` dans le dossier de votre choix et ouvrez un terminal dans ce dossier :
```bash
cd chemin/vers/dossier_dezippe
```

### 2. Créer un environnement virtuel (recommandé)
Il est fortement recommandé d'utiliser un environnement virtuel isolé :

- **Sur macOS / Linux :**
  ```bash
  python3 -m venv venv
  source venv/bin/activate
  ```

- **Sur Windows (Invite de commandes / PowerShell) :**
  ```cmd
  python -m venv venv
  venv\Scripts\activate
  ```

### 3. Installer les dépendances
Installez toutes les bibliothèques requises avec `pip` :
```bash
pip install --upgrade pip
pip install -r requirements.txt
```

---

## 💻 Exécution du Notebook

### Option A : Via l'interface Jupyter Notebook classique
Lancez Jupyter depuis le terminal (avec l'environnement virtuel activé) :
```bash
jupyter notebook
```
Votre navigateur web s'ouvrira automatiquement. Cliquez sur **`YOLO_copilot_solution_sinkhorn.ipynb`**, puis dans le menu supérieur :
> **Kernel** ➔ **Restart & Run All** (ou **Cell** ➔ **Run All**).

### Option B : Via VS Code ou Cursor
1. Ouvrez le dossier dans VS Code / Cursor.
2. Ouvrez le fichier `YOLO_copilot_solution_sinkhorn.ipynb`.
3. En haut à droite du notebook, sélectionnez le kernel Python correspondant à votre environnement virtuel (`venv`).
4. Cliquez sur **"Run All"** (Exécuter tout).

---

## Temps d'exécution & Sorties attendues

- **Temps d'exécution** : Entre **5 et 10 minutes** selon la puissance de votre processeur (le paramètre `RUN_ABLATION = True` réalise une validation croisée 5-folds complète avec plusieurs variantes de modèles).
- **Résultat généré** : À la fin de l'exécution, le fichier de prédictions **`submission28_a1.csv`** est automatiquement créé à la racine du dossier.
- Les checkpoints intermédiaires sont stockés dans le dossier `nb28_checkpoints/`.

