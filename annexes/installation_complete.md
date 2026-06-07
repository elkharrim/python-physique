# A — Installation complète

Cette annexe détaille l'installation de l'environnement Python complet 
pour suivre la formation sur votre machine locale.

---

## Option 1 : Conda (recommandée)

Conda gère les dépendances C/Fortran sous-jacentes (BLAS, LAPACK, MPI) 
plus fiablement que pip seul.

### 1.1 Installer Miniforge

```bash
# Linux/macOS
curl -L -O "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh"
bash Miniforge3-$(uname)-$(uname -m).sh

# Windows : télécharger l'installateur depuis
# https://github.com/conda-forge/miniforge/releases
```

### 1.2 Créer l'environnement

```bash
# Cloner le dépôt
git clone https://github.com/VOTRE_USERNAME/python-physique.git
cd python-physique

# Créer l'environnement (5–10 min)
conda env create -f environment.yml

# Activer
conda activate python-physique

# Vérifier
python -c "import numpy, scipy, matplotlib, astropy; print('Installation OK')"
```

### 1.3 Lancer JupyterLab

```bash
jupyter lab
```

---

## Option 2 : pip + venv

```bash
python3.11 -m venv env-physique
source env-physique/bin/activate   # Linux/macOS
# env-physique\Scripts\activate    # Windows

pip install --upgrade pip
pip install -r requirements.txt
jupyter lab
```

---

## Option 3 : Sans installation (Binder)

Cliquer sur le badge Binder en haut de n'importe quelle page du livre.  
Démarrage : ~2 minutes. Aucune installation requise.

```{warning}
Les sessions Binder sont temporaires (durée max ~2h) et ne persistent pas.
Télécharger vos notebooks avant de fermer la session.
```

---

## Option 4 : Google Colab

Pour les notebooks individuels, utiliser le bouton "Ouvrir dans Colab".  
Installer les dépendances manquantes en début de notebook :

```python
# Cellule à exécuter en premier sur Colab
!pip install astropy iminuit uncertainties qutip pennylane --quiet
```

---

## Vérification de l'installation

```python
# Exécuter ce script pour vérifier toutes les dépendances
import importlib, sys

packages = {
    'numpy'      : '1.26',
    'scipy'      : '1.12',
    'sympy'      : '1.12',
    'matplotlib' : '3.8',
    'pandas'     : '2.1',
    'astropy'    : '6.0',
    'numba'      : '0.59',
    'qutip'      : '4.7',
}

print(f"Python : {sys.version.split()[0]}\n")
print(f"{'Paquet':<15} {'Requis':>8} {'Installé':>10} {'OK':>5}")
print("-" * 42)

for pkg, version_min in packages.items():
    try:
        mod = importlib.import_module(pkg)
        ver = getattr(mod, '__version__', '?')
        ok  = '✓' if ver >= version_min else '✗'
        print(f"{pkg:<15} {version_min:>8} {ver:>10} {ok:>5}")
    except ImportError:
        print(f"{pkg:<15} {version_min:>8} {'manquant':>10} {'✗':>5}")
```

---

## Problèmes fréquents

**`conda: command not found`**  
Rouvrir le terminal après l'installation de Miniforge, ou exécuter :
```bash
source ~/.bashrc   # Linux
source ~/.zshrc    # macOS avec zsh
```

**Conflit de dépendances conda**  
```bash
conda env remove -n python-physique
conda clean --all
conda env create -f environment.yml
```

**PySCF ne s'installe pas sur Windows**  
PySCF ne supporte pas Windows nativement. Utiliser WSL2 ou Google Colab 
pour les notebooks de la Rubrique 9.

**numba : erreur LLVM**  
```bash
conda install numba llvmlite --force-reinstall
```
