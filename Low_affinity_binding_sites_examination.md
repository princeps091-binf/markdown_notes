# Low-affinity binding sites examination

## Exploring binding space of TFs
- TF binding is often measured using ChIP-seq
    - Experimental technique makes this particular signal the outcome of the integration of a variety of processes
- TF binding behaviour is often represented as a PWM
    - Aggregate summary of binding events for considered TF
    - Matrix describing how different nucleotides at different positions have a probability to be found at binding events for considered TF
    - Given the aggregation of very different datasets, the produced PWM is expected to reflect the sequence-pattern affinity for the binding-domain of the considered TF
        - only invariant element across these datasets
- Gap between derived PWM and observed ChIP signal constitute an interesting "space" to examine
    - PWM score constitute an estimation of the affinity between a given sequence and binding domain of the considered TF
        - A high score can be interepreted as the indication of direct binding of the considered TF to the considered sequence
    - ChIP signal constitute a measure of the presence of the considered TF across the genome
        - A variety of mechanisms can produce the presence of TFs at a given position
            - high occupancy target regions
            - indirect binding
            - low-affinity binding
                - transitional
                - weak
            - direct binding (Unibind)

- trx-hubs constitute a priviledged space within which we expect regulation to be particularly active
    - Chart their available binding landscape -> Chromatin accessibility (DNase + ATAC)