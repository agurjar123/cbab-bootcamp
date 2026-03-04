# Computational Biology at Berkeley (CBAB) — Bootcamp

Hands-on homework assignments teaching foundational computational biology skills using real biological datasets.

---

## 📁 Repository Structure

```
cbab-bootcamp/
└── homework/
    ├── HW1_scRNAseq_student.ipynb    ← Student version (fill in the blanks)
    └── HW1_scRNAseq_completed.ipynb  ← Answer key
```

---

## 💻 Running the Notebooks

### Google Colab — no installation needed

1. Go to [colab.research.google.com](https://colab.research.google.com)
2. **File → Upload notebook** → select `HW1_scRNAseq_student.ipynb`
3. **Runtime → Change runtime type → R**
4. Run all cells top to bottom

### Locally (VS Code or JupyterLab)

See **[LOCAL_SETUP.md](LOCAL_SETUP.md)** for step-by-step instructions for Mac and Windows.

The short version:
1. Install [R](https://cran.r-project.org)
2. `pip install jupyterlab`
3. In an R console: `install.packages("IRkernel"); IRkernel::installspec()`
4. `jupyter lab` and open the notebook — or open it directly in VS Code with the Jupyter extension

> The dataset (~85 MB) downloads automatically on first run and is excluded from this repo via `.gitignore`.

---

## 📓 Homework 1 — Single-Cell RNA-Seq Analysis with Seurat

**Language:** R  |  **Kernel:** `ir` (IRkernel)  |  **Dataset:** PBMC 3k (10x Genomics)

### What You'll Learn

- Load raw 10x Genomics count matrices with `Read10X` / `CreateSeuratObject`
- Apply QC filters to remove empty droplets, doublets, and dying cells
- Normalize and scale expression data for cross-cell comparability
- Identify highly variable genes and run PCA
- Choose dataset dimensionality with an elbow plot
- Cluster cells with graph-based community detection (Louvain)
- Visualize clusters in 2D with t-SNE and UMAP
- Find cluster-specific marker genes with Wilcoxon rank-sum tests
- Annotate clusters with known immune cell type labels

### Homework Questions (12 coding + 5 reflection)

| # | Topic | What to fill in |
|---|-------|-----------------|
| Q1 | Load data | `min.cells`, `min.features` in `CreateSeuratObject` |
| Q2 | QC metrics | `"^MT-"` pattern for `PercentageFeatureSet` |
| Q3 | QC filtering | Thresholds in `subset()` |
| Q4 | Normalization | Call `NormalizeData()` |
| Q5 | Variable features | `selection.method`, `nfeatures` in `FindVariableFeatures` |
| Q6 | Scaling | `features` argument in `ScaleData` |
| Q7 | PCA | `features` argument in `RunPCA` |
| Q8 | Dimensionality | Write `ElbowPlot()` + justify number of PCs |
| Q9 | Clustering | `dims` and `resolution` parameters |
| Q10 | Visualization | `dims` for `RunTSNE` and `RunUMAP` |
| Q11 | Marker finding | `FindMarkers` for cluster 3 |
| Q12 | Annotation | Fill in 9 cell type names |
| Q13–17 | Reflection | Written conceptual questions |

---

## 📚 References

- Hao et al. (2021). *Integrated analysis of multimodal single-cell data.* Cell. [DOI: 10.1016/j.cell.2021.04.048](https://doi.org/10.1016/j.cell.2021.04.048)
- [Seurat PBMC3k Tutorial](https://satijalab.org/seurat/articles/pbmc3k_tutorial)
- [10x Genomics PBMC 3k dataset](https://cf.10xgenomics.com/samples/cell/pbmc3k/pbmc3k_filtered_gene_bc_matrices.tar.gz)

---

*Tutorial originally adapted by Lila Wijaya · Homework version by CBAB Bootcamp*
