# Poster text

## Abstract (100 words)
Abstract: The genome is a complex and dynamic object coordinating a multitude of processes enabling the appropriate activation of cell function from DNA information. Among this collection of processes, transcription plays a fundamental role as the necessary transition from the seemingly static and “universal” DNA information shared across a whole organism to the dynamic and particular transcription determining tissue function. The regulatory mechanisms enabling this transcriptional agility relies on a precise coordination of both structure and function of the genome. In this study we integrate multiple omics data to chart this coordination. This effort highlights transcriptional hubs that dynamically concentrate relevant biological features across cell-lines

## 
 
Introduction: The regulatory mechanisms enabling the genome’s transcriptional agility producing the variety of tissue functions observed in eukaryotes remains an active field of study. In particular, reconciling this complex behaviour with the conventional 1 dimensional representation of the genome highlights the limits of this narrow description of the genome. 

The 3D spatial configuration of the genome within the nucleus offers a more concrete context in which to characterise these mechanisms. The regulatory importance of genome architecture manifests itself in the extensive spatial re-configuration the genome goes through to produce adequate transcription or upon disease onset.  

In this study we integrate HiC data and CAGE sequencing to detect candidate transcription hubs, we believe constitute a decisive locus of gene regulation. 
##  (100 words)
Methods: To highlight candidate transcription hubs, we detect chromosome clusters enriched in both self-interaction and transcriptional events using spectral clustering of HiC data followed by the detection of CAGE-peak enriched clusters. 

Critically, our original spectral clustering approach enables the integration of multiple resolutions of HiC data, thus allowing a systematic and comprehensive characterisation of genome architecture at every scale (Figure 1). 

With this collection of preferentially self-interacting clusters we then identify instances where we also observe an enrichment in transcriptional events, measured through CAGE-peaks, using a bootstrapping approach. Briefly, we compute an empirical p-value to estimate this enrichment for the considered cluster by comparing its observed peak content against a null distribution obtained by shuffling peaks along the genome, accounting for their positional bias.(Figure 2).  

We illustrate the biological relevance of these clusters jointly enriched in HiC and CAGE-peaks by examining various genomic and epi-genomic properties.
## Results and Discussion (150 words)
The gene content of these transcriptional hubs concentrates biologically relevant genes for the cell-lines considered. Notably, for HMEC we observed an enrichment in epithelial gene-sets, while we observed immune gene-set enrichment for GM12878. In contrast, H1 proved more cryptic with chromatin architecture and immune response gene sets getting enriched.(Fig.3) 

The relevance of the hub’s gene content was consolidated by their concentration of down-regulated genes when comparing HMEC with a breast cancer cell lines (Fig.4). This indicates the possible importance of these hubs in coordinating the genes required for healthy cell function as these get preferentially shut down in a cancer context.

Finally we also observed a distinct enrichment in more active enhancers inside hubs compared to enhancers outside hubs. When examining the H3K27ac histone mark, RNAP2 occupation or CAGE-peaks intensity we systematically observed significantly higher levels for enhancers within hubs (Fig.5). This observation holds true across multiple cell-lines and indicates the dynamic and rich regulatory context these hubs create.
## Conclusion (50 words)
In conclusion our multi-omics and multi-resolution approach is able to highlight candidate transcription hubs that concentrate biologically relevant gene content across cell-lines in a rich regulatory context animated by significantly more active enhancers. We envision to further characterise this regulatory landscape and better understand the principles that shape the regulatory behaviours of these transcriptional hubs.
## Figure legend (30-50 words)
BHiCect 2.0: Our multi-resolution spectral clustering of HiC data mobilises the adequate resolution to use for the scale of the considered clusters by dynamically adjusting the HiC resolution to maximize granularity and minimize sparsity. The main output is a hierarchical tree charting the nested configuration of clusters across all scales

Cluster CAGE-enrichment: We produce an empirical p-value for every cluster to estimate their respective CAGE-enrichment level, accounting for their positional bias. We further ensure an adequate FDR for candidate transcription hubs accounting for cluster nestedness using DAGGER 

Transcription hub gene set enrichment: For every cell-line we extract the active gene content of detected transcription hubs and perform a hypergeometric test across all GO-BP gene-sets. The background used is the total gene content associated with active CAGE-peaks in the corresponding cell-line.

Differentially expressed peak enrichment: After detecting differentiall expressed CAGE peaks between HMEC and MCF7 using DESeq2, we found an enrichment in downregulated peaks inside HMEC transcriptional hubs. Down-regulated peaks within hubs tend to have smaller p-values and larger log-fold-change. Furthermore a GSEA analsysis of thes peak-associated genes highlights breast cancer hallmark gene sets.


More active hub enhancers: We observe an enrichment in more active enhancers within hubs compared to outside for both H3K27ac, RNAP2 ChIP-seq data and CAGE-peak expression in GM12878. Furhtermore this higher activity within hubs isn't seen for TSS.


#--------------------------------------------------------------------------------------

Hi-C derived proximity data provides a way of studying how the distribution of binding sites along the chromosomes is organized in 3D space