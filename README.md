# Stereo-seq CellBin PD Analysis (GitHub-ready)

This repository contains a cleaned and reproducible analysis workflow for **Stereo-seq CellBin** spatial transcriptomics data in a unilateral Parkinson’s disease mouse model.

> **Important**: CellBin units are **not true single cells**. Any "cell type" labels in this project should be interpreted as **cell-type–associated CellBin units inferred from marker expression and spatial context**.

---

## Repository contents

- `notebooks/Cellbin_analysis_clean.ipynb`  
  Cleaned notebook:
  - no Chinese comments
  - no hard-coded personal paths
  - richer English headers + purpose notes per step

- `env/environment.yml` / `requirements.txt`  
  Reproducible environment specs.

- `src/stereo_pd_cellbin/stats.py`  
  Small helper functions (p-value stars, Fisher/Chi2/MWU wrappers).

- `scripts/run_pipeline.py`  
  Minimal headless entrypoint (sanity load + write). The full analysis remains in the notebook.

---

## Quick start

### 1) Prepare data (do **not** commit raw data)

Put your input `.h5ad` here:

```
data/raw/Y01504E1.cellbin_1.0.adjusted.h5ad
```

Raw data is ignored by `.gitignore` by default.

### 2) Create environment

Conda (recommended):

```bash
conda env create -f env/environment.yml
conda activate stereo_pd
```

Or pip:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### 3) Run the notebook

Open JupyterLab and run `notebooks/Cellbin_analysis_clean.ipynb` top-to-bottom:

```bash
jupyter lab
```

Edit the `INPUT_H5AD` variable at the top of the notebook.

---

## What should be committed to GitHub?

✅ Commit:
- `README.md`
- `notebooks/Cellbin_analysis_clean.ipynb` (preferably **without outputs**)
- `env/environment.yml` and/or `requirements.txt`
- `scripts/` and `src/`
- `LICENSE`, `CITATION.cff`, `.gitignore`

❌ Do NOT commit:
- Raw data: `data/raw/`
- Large intermediate objects or results (unless small and necessary)

---

## Recommended Git workflow (first-time setup)

```bash
git init
git add README.md notebooks env scripts src LICENSE CITATION.cff .gitignore requirements.txt
git commit -m "Initial commit: cleaned CellBin analysis notebook"
```

Create a GitHub repository (web UI), then:

```bash
git branch -M main
git remote add origin https://github.com/<YOUR_GITHUB>/<REPO>.git
git push -u origin main
```

---

## Tips for clean notebooks on GitHub

To automatically strip notebook outputs before committing:

```bash
pip install nbstripout
nbstripout --install
```

Then future commits will not include heavy outputs.

---

## Citation

Update `CITATION.cff` (author + repo link). If you use this code in a manuscript, cite the repository and the underlying dataset accession (GEO/OMIX/etc.) when available.
