# Journal club : Transcription factor expression is the main determinant of variability in gene co-activity
## Context
- Gene expression is the integrated result of multiple gene regulatory processes
    - local TF-binding
    - permissive chromatin environment
- Disentangling the regulatory mechanisms acting upon each gene in its native context is crucial to understand gene regulation

- often co-regulated groups of genes
    - Modulated by the same regulatory processes
        - Common TFs exerting their influence on shared regulatory regions
        - Common permissive chromatin micro-environment
    - TADs = confine regulatory elements' interactions
        - segregate active from inactive genes (?)
        - formation of TADs only has a marginal contribution to gene expression 
    - Co-expression measured by :
        - Between cell types:
            - gene expression level correlation across cell types
            - concordant differential expression between cell types or conditions
            - degree to which they define cellular identity in single cell experiments
        - Within the same cell type 
            - More subtle regulatory patterns than between cell-types
            - Major determinant of co-expression is genomic proximity


    - Quantifying co-regulatory effect sizes is complicated 
        - regulatory processes may impact coordinated expression (co-activity) differently from expression of gene itself.
        - Accurately parse the two kinds of effect
            - decompose RNA expression data into 2 components:
                - genomic location-dependent 
                    - accurately captures domains of chromatin compartments (large-scale co-activity patterns)
                - genomic location-independent 

- Investigate variability in co-activity in a genotyped panel of lymphoblastoid cells profiled by RNA-seq
    - identify domains of co-active genes
        - gene co-activity on the domain level is largely invariable between individuals
        - sub-domains exhibiting high individual variation
            - variability in co-activity largely reflects histone PTM variation
            - genes contained within variable co-activity domains
                - higher sharing of eQTLs
                - higher number and variability of interactions with enhancers
                - enriched in specific TF binding sites
                    - bound by more variably expressed TFs
        - Combined effects of regulatory processes underlying co-activity
            - for explaining variation in co-activity 
                - at variable domains:
                    - trx levels of TFs > genetic variation or interactions 
## Model                    
Trx = PD + PI
- hierarchical model for every 10kb bin
    - PD = Random walk ([PD(i)-PD(i+1)]~Normal distribution)
    - PI = Generic iid Gaussian
- PD = co-activity score
    - strong inter-individual correspondence (correlation ~ 0.94)
    - proportion of expression attributed to co-activity
        - correlated better between individuals of the same cell type than between cell types
## Positional dependencies of expression reveal co-activity domains of shared regulation
- Gene pairs that had a higher and more similar co-activity score tended to have higher co-expression (mean PCC across LCLs)
    - than those with low or dissimilar co-activity scores 
- => co-activity domains = 
    - define domains of shared transcriptional regulation between genes influencing their co-activity
    - genomic regions (10kb bins) with
        - positive co-activity in at least 15% of individuals 
        - at least two expressed annotated genes
    - 1,489 co-activity domains
    - 88% of expressed genes in LCLs
    - 44% of the human genome
### Domains reflected chromatin states ?
- active chromatin compartments = 75% of the total genomic co-activity domains footprint 
    - 10% of background regions with negatively signed co-activity scores
- heterochromatin compartments made up 75% of background regions 
    - 15% of co-activity domains
- active domains associated with almost four times more open chromatin regions than background regions
- correlation between co-activity score and activating histone modifications > than in background regions of negative co-activity scores

- enrichment in physical contacts within TADs ~ positional dependency in transcription within co-activity domains
    - boundaries of co-activity domains enriched in TAD boundaries 

- correlation between neighboring active genes within co-activity domains compared to gene pairs outside of domains

- links to regulatory elements for genes in vs out of co-activity domains.
    - activity-by-contact (ABC) modeling => 
        - predict regulatory interaction maps for 79 of the 343 individuals with available chromatin accessibility and H3K27ac activity
    - general association between the number of associated enhancers and the expression of genes
        - multi-enhancer genes having a higher expression than those with few or no predicted enhancers
    - genes in co-activity domains less variable in their number of ABC-associated enhancers (higher gene expression levels)

- investigated the co-operative capacity of eQTL in domain
    - We focused on genes associated with at least one eQTL
    - 38% of neighboring eGene pairs contained within the same co-activity domain shared at least one eQTL
        - 7% of eGene pairs outside domains
        - not explained by differences in the distances between eGene pairs
### Transcriptional variation across individuals uncovers regulatory mechanisms underlying co-activity
- presence of sub-regions within co-activity domains displaying considerable variation between individuals
    - understanding regulation of co-activity 
        - -> differed in co-activity between individuals ~ differed in activity of underlying shared regulatory mechanisms
- co-activity domains >2 expressed genes + showing high variability (standard deviation > 0.6)
    - 212 genomic regions (?)
- neighboring gene pairs in variable co-activity domains were more co-expressed (wrt non-variable domains)

- which mechanisms are associated with individual variability
    - histone modifications, TF binding,enhancer-promoter interactions, and genetic variants.
    
    - average co-activity score in variable co-activity domains ~ chromatin state across individuals [compared to matched non-variable co-activity domains]
        - open chromatin regions did not differ significantly between the variable and matched non-variable co-activity domains
        - genes in variable co-activity domains had 20% more ABC-predicted interactions + 20% higher interaction variability 
        - variable co-activity domains ~ correlated strongly with H3K27ac, H3K4me1 and H3K4me3
            - Domains of co-varying histone modifications have previously been described as variable chromatin modules (VCMs) -> relatively smaller domains
                - enrichment in variable co-activity domains -> 85% coverage of variable co-activity domains
    - variable expression of TFs preferentially binding to regulatory elements in these domains
        - 83 tested TFs -> 9 significantly enriched in variable domains wrt co-activity domains (NFATC1, CEBPB, EP300, BMI1, ATF2,TBX21, NFIC, BCL11A, BATF)
            - BATF and NFIC also enriched in matched non-variable domains
        - within variable co-activity domains 
            - the more enriched the TFBSs for a given TF, the more variable the expression of that TF
                - association was weaker in matched non-varying domains
            - more variably expressed genes tend to be bound by more variably expressed TFs
            - absence of TFBSs within a domain for a given TF: weaker correlation between TF expression and domain co-activity scores
            - open chromatin regions in variable co-activity domains shared more predicted TFBSs than those in matched non-variable co-activity domains
    - association between variability in co-activity and genotypic effects
        - separation by ancestry of the individuals for the co-activity scores
            - genetic variation influences individual differences in the regulation of gene co-activities
        - neighboring gene pairs sharing an eQTL
            - contained in variable co-activity domains: 58%
            - matched co-activity domains: 42%
            - all co-activity domains: 38%
        - association between SNPs and the average co-activity score in a domain = co-activity QTL
            - variable co-activity domains: 68%
            - matched non-variable co-activity domains: 51%
            - Stronger explanatory capacity of genetic variation for co-activity variation in variable domains compared to matched non-variable domains
### Transcription factor expression is the dominant regulatory determinant of co-activity
- co-activity ~ different regulatory mechanisms (set of 29 individuals)
    - Multiple linear regression
        - Predictor Variables:
            - predicted enhancer-promoter interactions ~ ABC interactions
            - genetic variation ~ QSS
            - TF activities ~ log(expression level)
            - excluded histone modifications because reciprocal influence (?)
    - For each variable co-activity domain
        - TF activities
            - selected 10 TFs
                - random forest model predicting average co-activity top 10 most important TFs
        - genetic variation
            - summarize all QTLs inside domain ~ contribution to effect size
    - considerable variation in the total amount of explained variance
        - 
#------------------------------------------------------------------------------
Rennie 2018:
- We posited that a proportion of steady-state RNA expression is reflecting three-dimensional chromatin organisation. 
    - We reasoned that a transcription unit (TU) is likely to be more similar in terms of expression to its proximal TUs than to distal loci, which are likely to be associated with different domains of chromatin interactions. 
    - However, expression is also influenced by gene-specific transcriptional and post-transcriptional regulatory programmes independent of a TU’s chromosomal position. 
        - We need to be able to estimate the proportion of expression from a genomic region explained by its chromosomal position. 

- Our strategy is based on [approximate Bayesian modelling] (INLA) + replicate measurements -> hierarchical model for each chromosome across cell-lines
    - decompose normalised aggregated RNA expression read counts in genomic bins 
        - into two components (PD and PI) + some constant intercept (Methods)
            - PD: component difference between successive bins  
    - sum of the two transcriptional components (random effects model)
    - Hyperparameters :
        - for the PD
            - size (gamma-distributed) 
            - zero-probability parameters (Gaussian-distributed) of the negative binomial distribution
            - precision parameters τrw
        - for PI :
            - τiid (log-gamma-distributed priors)

The decomposition of this sum into its respective components (summands) can be interpreted as an optimisation problem over a chromosome to best separate the proportion of total expression that is similar between consecutive genomic bins (PD) from position-independent expression (PI).
