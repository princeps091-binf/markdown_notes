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
            - constrained to reproduce sone network topology properties -> Why are these topological properties important ?
                - TF linked to region with comparable degree distribution (in region-region interaction network)
                - TF degree kept
        2. For every possible TF-pairs, compute an empirical p-value:
            - count of region-region edges with considered TFs across corresponding edge-ends?
                - random vs observed
        3. Comparison with sequential co-occurence (within bin)
            - unclear how this is done
                - indication that sampling restricted to narrow set of components fitting the topological constraint for edge shuffling
            - Instead sample window extended so as to match the span of spatial neighbours?