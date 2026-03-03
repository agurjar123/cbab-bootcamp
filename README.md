# Computational Biology at Berkeley (CBAB) — Bootcamp

Welcome to the **CBAB Bootcamp** repository! This repo contains hands-on homework assignments designed to teach foundational computational biology skills using real biological datasets.

---

## 📁 Repository Structure

```
cbab-bootcamp/
└── homework/
    ├── HW1_scRNAseq_student.ipynb    ← Student version (fill in the blanks)
    └── HW1_scRNAseq_completed.ipynb  ← Answer key (instructors / self-check)
```

---

## 📓 Homework 1 — Single-Cell RNA-Seq Analysis with Seurat

**Topic:** End-to-end scRNA-seq analysis pipeline using the Seurat R package
**Dataset:** PBMC 3k — 2,700 Peripheral Blood Mononuclear Cells (10x Genomics)
**Language:** R (Jupyter kernel: `ir`)

### What You'll Learn
- Load raw 10x Genomics count matrices with `Read10X` and `CreateSeuratObject`
- Apply quality-control filters to remove empty droplets, doublets, and dying cells
- Normalize and scale expression data for cross-cell comparability
- Identify highly variable genes and perform PCA
- Determine dataset dimensionality with an elbow plot
- Cluster cells with graph-based community detection (Louvain)
- Visualize clusters in 2D with t-SNE and UMAP
- Find cluster-specific marker genes with Wilcoxon rank-sum tests
- Annotate clusters with known immune cell type labels

### How to Use

| File | Who should use it |
|------|------------------|
| `HW1_scRNAseq_student.ipynb` | **Students** — fill in `...` placeholders at each step |
| `HW1_scRNAseq_completed.ipynb` | **Instructors / answer key** — all blanks filled with explanations |

### Getting Started

1. **Open in Google Colab** (recommended — no local R install needed):
   - Go to [colab.research.google.com](https://colab.research.google.com)
   - File → Upload notebook → select `HW1_scRNAseq_student.ipynb`
   - Make sure the runtime is set to **R** (Runtime → Change runtime type → R)

2. **Run locally** (requires R ≥ 4.1 and the `ir` Jupyter kernel):
   ```bash
   pip install jupyter
   R -e "install.packages('IRkernel'); IRkernel::installspec()"
   jupyter notebook homework/HW1_scRNAseq_student.ipynb
   ```

3. Run cells **top to bottom** — later cells depend on earlier ones.
   The dataset (~85 MB) will download automatically on first run.

---

## 🧬 About CBAB

[Computational Biology at Berkeley (CBAB)](https://callink.berkeley.edu) is a student-run organization at UC Berkeley that teaches computational approaches to biological research through workshops, bootcamps, and research projects.

---

## 📚 References

- Hao et al. (2021). *Integrated analysis of multimodal single-cell data.* Cell. [DOI: 10.1016/j.cell.2021.04.048](https://doi.org/10.1016/j.cell.2021.04.048)
- [Seurat PBMC3k Tutorial](https://satijalab.org/seurat/articles/pbmc3k_tutorial)
- 10x Genomics PBMC 3k dataset: [link](https://cf.10xgenomics.com/samples/cell/pbmc3k/pbmc3k_filtered_gene_bc_matrices.tar.gz)

---

*Tutorial originally adapted by Lila Wijaya · Homework version by CBAB Bootcamp team*
