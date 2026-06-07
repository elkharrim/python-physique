# Python pour physiciens — Formation intensive

[![Statut déploiement](https://github.com/VOTRE_USERNAME/python-physique/actions/workflows/deploy.yml/badge.svg)](https://github.com/VOTRE_USERNAME/python-physique/actions/workflows/deploy.yml)
[![Ouvrir dans Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/VOTRE_USERNAME/python-physique/main)
[![Ouvrir dans Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/VOTRE_USERNAME/python-physique/blob/main/notebooks/r01/01_introduction.ipynb)
[![Licence: CC BY 4.0](https://img.shields.io/badge/Licence-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

Formation intensive Python pour physiciens (doctorat/recherche).  
11 rubriques, du calcul numérique à la reproductibilité computationnelle.

---

## 🚀 Déploiement en 5 étapes

### Étape 1 — Créer le dépôt GitHub

```bash
# Créer un nouveau dépôt GitHub nommé "python-physique"
# (via l'interface GitHub ou GitHub CLI)
gh repo create python-physique --public --description "Formation Python pour physiciens"
```

### Étape 2 — Cloner et pousser le contenu

```bash
git clone https://github.com/VOTRE_USERNAME/python-physique.git
cd python-physique

# Copier les fichiers de cette formation
# (remplacer par le chemin réel des fichiers)
cp -r /chemin/vers/python-physique/* .

git add .
git commit -m "Initial commit — Structure JupyterBook complète"
git push origin main
```

### Étape 3 — Activer GitHub Pages

1. Aller dans **Settings** → **Pages** du dépôt GitHub
2. Source : **GitHub Actions**
3. Sauvegarder

### Étape 4 — Déclencher le premier déploiement

```bash
# Le push sur main déclenche automatiquement le workflow
# Vérifier l'avancement : Actions → deploy.yml
```

### Étape 5 — Accéder au site

```
https://VOTRE_USERNAME.github.io/python-physique
```

Le déploiement prend environ **3–5 minutes** lors du premier build.

---

## 📁 Structure du projet

```
python-physique/
│
├── _config.yml              ← Configuration JupyterBook
├── _toc.yml                 ← Table des matières
├── intro.md                 ← Page d'accueil
├── environment.yml          ← Environnement conda complet
├── requirements.txt         ← Dépendances pip (CI)
│
├── avant-propos/
│   ├── pourquoi-python.md
│   ├── installation.md
│   └── guide-lecture.md
│
├── notebooks/
│   ├── r01/                 ← Rubrique 1 : Calcul numérique
│   │   ├── 01_introduction.ipynb
│   │   ├── 02_numpy_fondements.ipynb
│   │   ├── 02a_ndarray.ipynb
│   │   ├── 02b_vectorisation.ipynb
│   │   ├── 02c_linalg.ipynb
│   │   ├── 03_scipy_solveurs.ipynb
│   │   ├── 03a_ode.ipynb
│   │   ├── 03b_integration.ipynb
│   │   ├── 03c_sparse.ipynb
│   │   ├── 04_monte_carlo.ipynb
│   │   └── 05_limites.ipynb
│   ├── r02/ ... r11/        ← Rubriques 2 à 11
│
├── exercices/
│   ├── r01/exercices.ipynb  ← 3 niveaux par rubrique
│   └── r02/ ... r11/
│
├── projets/
│   ├── projet_1_ising_complet.ipynb
│   ├── projet_2_exoplanete.ipynb
│   ├── projet_3_ml_phases.ipynb
│   └── projet_4_pipeline_complet.ipynb
│
├── annexes/
│   ├── installation_complete.md
│   ├── comparaison_matlab.md
│   ├── ressources.md
│   └── glossaire.md
│
├── _static/
│   ├── logo.png
│   ├── favicon.ico
│   └── custom.css
│
├── references.bib           ← Bibliographie BibTeX
│
└── .github/
    └── workflows/
        └── deploy.yml       ← CI/CD GitHub Actions
```

---

## 💻 Installation locale

```bash
# 1. Cloner le dépôt
git clone https://github.com/VOTRE_USERNAME/python-physique.git
cd python-physique

# 2. Créer l'environnement conda
conda env create -f environment.yml
conda activate python-physique

# 3. Lancer JupyterLab
jupyter lab

# 4. (Optionnel) Construire le livre localement
jupyter-book build .
# Ouvrir _build/html/index.html dans un navigateur
```

---

## 🔄 Workflow de contribution

```bash
# Modifier un notebook
jupyter lab notebooks/r01/01_introduction.ipynb

# Vérifier le build localement
jupyter-book build . --all

# Pousser les modifications
git add notebooks/r01/01_introduction.ipynb
git commit -m "R01: amélioration section broadcasting"
git push origin main
# → Déploiement automatique en ~3 min
```

---

## 📊 Couverture des rubriques

| Rubrique | Notebooks | Exercices | Status |
|---|---|---|---|
| 1 — Calcul numérique | 10 | 3 | ✅ Complet |
| 2 — Calcul symbolique | 6 | 3 | 🔄 En cours |
| 3 — Données expérimentales | 6 | 3 | 🔄 En cours |
| 4 — Visualisation | 6 | 3 | 🔄 En cours |
| 5 — ML | 5 | 3 | 🔄 En cours |
| 6 — HPC | 5 | 3 | 🔄 En cours |
| 7 — Physique quantique | 5 | 3 | 🔄 En cours |
| 8 — Astronomie | 5 | 3 | 🔄 En cours |
| 9 — Physique spécialisée | 5 | 3 | 🔄 En cours |
| 10 — Legacy/Formats | 5 | 3 | 🔄 En cours |
| 11 — Reproductibilité | 5 | 3 | 🔄 En cours |

---

## 📖 Licence

Ce matériel est distribué sous licence **CC BY 4.0**.  
Vous pouvez librement l'utiliser, le modifier, et le redistribuer avec attribution.
