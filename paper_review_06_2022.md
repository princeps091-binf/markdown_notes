# Paper review

- Build bi-partite graph linking TF to regions observed to interact significantly
    - Region-to-Region network -> RNAP2 ChIA-pet
        - Filtered network: merging "error" or cell average
            - regions with < 20 interacting neighnours
            - regions < 30kb
        - Summary statistic of this network genome-wide
            - number of components
            - size of components
            - degree distribution per component
            - At this level can we already observe relation between TF-coincidence and component properties
                - given ensuing shuffling procedure constrained by interaction network degree property
    - Mapping TF-to-regions -> ChIP-seq signal

- assess TF-pairs that co-occur through the "region" interaction network
    - significance obtained through bootstrapping procedure
        1. Shuffle TF-to-region network
            - constrained to reproduce some network topology properties -> Why are these topological properties important ?
                - TF linked to region with comparable degree distribution (in region-region interaction network)
                - TF degree kept
        2. For every possible TF-pairs, compute an empirical p-value:
            - count of region-region edges with considered TFs across corresponding edge-ends?
                - random vs observed
        3. Comparison with sequential co-occurence (within bin)
            - unclear how this is done
                - suffle then examine co-occurence within each connected bin?
                - indication that sampling restricted to narrow set of components fitting the topological constraint for edge shuffling
            - Instead sample window extended so as to match the span of spatial neighbours?
        - 2 groups emerging
- Motif analysis
    - spatial co-occurence coinciding with Motif strength ?
        - aggregate motifs into non-redundant clusters/archetype
    - Recover 2-group segmentation
        - Sequential procdure using motifs produces larger groups

- Aggregate and delineate consensus TF-pairing pattern across Motif/ChIP-Spatial/Sequential clustering

- difference in protein/DNA/gene interaction unclear?
    - PPI
        - internal PPI TF-node? 
            - found on the path between pairs of TFs
    - Gene enrichment
        - examine neighbouring genes of considered TFBS
        - Gene assignmnt to either group based on 5 in one group and at most 2 in other group
        - Group 1 = housekeeping gene enrichment (robust to group assingment criteria)
        - Group 2 = cell-line specfic enrichment ~ robust to threshold?

- Motif strength vs. spatial neighbourhood -> 42 tested but 62/61 TFs evaluated
    - categorise TF-peaks as strong if top 10% motif match
    - Proportion of strong vs other in spatially clustered vs "isolated" peaks

- Original contribution of restricted ChIA-pet