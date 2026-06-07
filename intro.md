# Python pour physiciens

## Formation intensive — Doctorat et recherche

```{admonition} À propos de cette formation
:class: tip

Cette formation couvre l'utilisation de Python dans 11 domaines de la physique, 
du calcul numérique à la reproductibilité computationnelle. 
Chaque rubrique combine une présentation théorique, des applications physiques 
commentées, et des exercices de difficulté croissante.

**Public cible :** Doctorants et chercheurs en physique.  
**Prérequis :** Bases de Python (variables, boucles, fonctions). Aucune maîtrise avancée requise.  
**Durée estimée :** 3 jours intensifs ou 6 semaines à raison de 4h/semaine.
```

---

## Structure de la formation

La formation est organisée en 11 rubriques thématiques couvrant l'ensemble 
de l'écosystème Python pour la physique :

| # | Rubrique | Bibliothèques clés |
|---|---|---|
| 1 | Calcul numérique et simulation | NumPy, SciPy |
| 2 | Calcul symbolique | SymPy |
| 3 | Traitement de données expérimentales | Pandas, SciPy, iminuit |
| 4 | Visualisation scientifique | Matplotlib, Seaborn |
| 5 | Apprentissage automatique | PyTorch, JAX, scikit-learn |
| 6 | Calcul haute performance | Numba, mpi4py, CuPy |
| 7 | Physique quantique et information quantique | QuTiP, Qiskit, PennyLane |
| 8 | Astronomie et astrophysique | Astropy, photutils |
| 9 | Physique computationnelle spécialisée | MDAnalysis, PySCF, PlasmaPy |
| 10 | Interfaces legacy et formats | f2py, ctypes, h5py, uproot |
| 11 | Reproductibilité et workflow | Snakemake, pytest, Git |

---

## Comment utiliser ce livre

### Exécution interactive

Chaque notebook peut être exécuté directement dans votre navigateur 
sans installation locale via les boutons en haut de chaque page :

- **Binder** : environnement complet, démarrage ~2 min
- **Google Colab** : rapide, nécessite un compte Google
- **Thebe** : exécution inline dans la page (beta)

### Installation locale (recommandée pour la production)

```bash
# Cloner le dépôt
git clone https://github.com/VOTRE_USERNAME/python-physique.git
cd python-physique

# Créer l'environnement conda
conda env create -f environment.yml
conda activate python-physique

# Lancer JupyterLab
jupyter lab
```

### Structure des notebooks

Chaque rubrique suit la même structure :

1. **Positionnement épistémique** — Pourquoi cette rubrique, quelles limites
2. **Sommaire des techniques** — Table des méthodes Python utilisées
3. **Comparaison Python/MATLAB** — Pour les utilisateurs venant de MATLAB
4. **Applications** — 3 à 5 applications physiques détaillées avec code complet
5. **Limites quantifiées** — Tableau des contraintes et seuils critiques
6. **Références** — Citations Tier 1 et Tier 2

---

## Conventions du livre

```{note}
Les blocs **Note** signalent des informations importantes sur l'implémentation.
```

```{warning}
Les blocs **Warning** signalent des pièges fréquents ou des erreurs courantes.
```

```{tip}
Les blocs **Tip** contiennent des bonnes pratiques et raccourcis.
```

```{admonition} Définition physique
:class: dropdown
Les blocs **Définition** (dépliables) rappellent les fondements physiques 
d'un problème avant son implémentation.
```

---

## Pourquoi Python en physique ?

Python n'est pas intrinsèquement plus rapide ni plus précis que MATLAB ou Fortran.
Il est **le premier environnement généraliste qui unifie** :

- Le calcul numérique haute performance (via NumPy/SciPy sur C/Fortran)
- L'analyse de données et la visualisation
- L'apprentissage automatique
- La physique quantique computationnelle
- L'astronomie observationnelle
- La reproductibilité et le workflow scientifique

**sans sacrifier la performance sur aucun d'eux**, tout en étant gratuit, 
pérenne, et universellement adopté par la communauté scientifique.

Pour l'argument complet, voir {doc}`avant-propos/pourquoi-python`.

---

## Licence et citation

Ce matériel est distribué sous licence **CC BY 4.0**.  
Vous pouvez librement l'utiliser, le modifier, et le redistribuer 
avec attribution.

Pour citer cette formation :

```bibtex
@misc{python_physique_2024,
  title     = {Python pour physiciens — Formation intensive},
  year      = {2024},
  url       = {https://github.com/VOTRE_USERNAME/python-physique},
  note      = {Formation doctorale, 11 rubriques}
}
```
