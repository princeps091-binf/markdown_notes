# Journal club

## CanSig: Discovering de novo shared transcriptional programs in single cancer cells

- Human tumors are highly heterogeneous in their cell composition
    - heterogeneity in transcriptional states of malignant cells
        - variability in tumorigenic properties and resistance to anti-cancer treatment

- scRNA-seq data contain all necessary information -> wrt shared transcriptional states of malignant cells in tumors
    - challenge of patient lvl data:
        - batch correction
        - patient-specific genetic background

- CanSig: discover known and de novo shared signatures in cancer single cells
    - preprocesses, integrates and analyzes scRNA-seq data
    - provide new signatures of shared transcriptional states 
        - links these states to known pathways

- rediscovers ground truth pathways determining shared transcriptional states
    - two simulated and three experimental datasets

## Pipeline
- data pre-processing -> 
    - gene expression matrix of all cells
    - classify cells into malignant and non-malignant
    - adding any associated annotations
    - CNV inference to remove cells
        - annotated as malignant that do not present CNVs
        - non-malignant cells that present CNVs
- Integration
    - projection of the dataset into a meaningful latent space
        - scVI:
            - select most highly variable genes
    - coordinates of all the cells of the dataset in a meaningful latent space
        - UMAP for viz
- Postprocessing
    - clustering of cells in the latent space
    - differential gene expression (1 vs. All)
    - gene set enrichment
    - differential copy number variation
