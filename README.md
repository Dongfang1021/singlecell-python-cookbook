# Single-cell Python Cookbook

A **Python-first, package-oriented** learning repository for single-cell data analysis.
This repo is organized so that **each Python package has its own folder**, with clear examples
showing *what the package does*, *when to use it*, and *how it fits into real workflows*.

---

## How to use this repository

1. **Start with setup**
   - Go to `00_setup/`
   - Create the environment and run a sanity check

2. **Learn tools by package**
   - Browse `02_packages/`
   - Each folder introduces *one Python package* (Scanpy, AnnData, scvi-tools, CellTypist, etc.)

3. **Follow end-to-end workflows**
   - Go to `03_workflows/`
   - See how multiple packages are combined into real analyses

This repo is designed as a **cookbook**, not a black-box pipeline.

---

## Repository structure

```
singlecell-python-cookbook/
├── README.md
├── 00_setup/
│   ├── README.md
│   ├── env/
│   │   ├── environment.yml
│   │   └── requirements.txt
│   └── sanity_check.py
├── 01_basic/
│   ├── README.md
│   ├── notebooks/
│   └── scripts/
├── 02_packages/
│   ├── README.md
│   ├── anndata/
│   ├── scanpy/
│   ├── scvi_tools/
│   ├── pertpy/
│   ├── celltypist/
│   ├── scrublet/
│   ├── bbknn/
│   └── muon/
├── 03_workflows/
│   ├── README.md
│   ├── read_singlecell_data/
│   ├── qc_and_filter/
│   ├── merge_multiple_datasets/
│   ├── integrate_batch/
│   ├── clustering_and_markers/
│   ├── cell_annotation/
│   └── crispr_feature_barcodes/
├── _shared/
│   ├── README.md
│   ├── utils.py
│   └── toy_data/
└── .gitignore
```

---

## Design philosophy

- **One folder = one concept or one package**
- Minimal hidden magic
- Intermediate `.h5ad` files are saved explicitly
- Emphasis on *understanding*, not just running

---

## Core data structure

All analyses are built around **AnnData (`.h5ad`)** objects:

- `adata.X` — expression matrix (cells × genes)
- `adata.obs` — cell-level metadata
- `adata.var` — gene-level metadata
- `adata.obsm` — embeddings (PCA, UMAP, latent spaces)

This structure is shared across Scanpy, scVI, Pertpy, CellTypist, and related tools.

---

## Typical workflow covered

1. Read data (10x, MTX, H5AD)
2. Quality control & filtering
3. Normalization & log transform
4. Feature selection (HVGs)
5. Dimensionality reduction (PCA)
6. Batch correction / integration (optional)
7. Clustering
8. Marker gene analysis
9. Cell type annotation
10. Save results as `.h5ad` + tables/figures

---

## Expected outputs

Most examples write outputs to local folders that are **not tracked by git**:

- `.h5ad` files (intermediate and final)
- QC figures
- UMAP plots
- Marker gene tables

---

## Who this repo is for

- People learning **single-cell analysis in Python**
- Users transitioning from Seurat (R) to Scanpy/scverse
- Scientists who want to understand *what each tool does*
- Anyone building their own single-cell pipelines

---

## License

This repository is released under the MIT License.

