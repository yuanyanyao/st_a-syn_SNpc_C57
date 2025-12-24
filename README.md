# Stereo-seq CellBin PD analysis

This repo is the working record of my analysis on Stereo-seq **CellBin** spatial transcriptomics data from a unilateral α-syn PD mouse model. The goal is to keep the workflow runnable end-to-end and easy to audit (what was done, with which parameters, and where the figures/tables came from).

A note on terminology: CellBin units are not true single cells. When I write “DA neuron”, “microglia”, etc., I mean **CellBin units enriched for the corresponding marker signals and consistent spatial context**, not a definitive single-cell identity.

---

## What’s here

- `notebooks/Cellbin_analysis_clean.ipynb`  
  The main notebook. It’s cleaned for sharing:
  - English-only comments/section headers
  - no hard-coded personal file paths
  - outputs cleared (so it stays small on GitHub)

- `env/environment.yml` and `requirements.txt`  
  Environment specs used to run the notebook.

- `src/stereo_pd_cellbin/`  
  A small helper module (mostly stats helpers such as Fisher/MWU wrappers and p-value → stars).

- `scripts/run_pipeline.py`  
  A minimal command-line entrypoint to sanity-check loading and run lightweight steps without opening Jupyter.

---

