   - The main issue raised by the authors regarding the comparable analysis performed by Ma et al. 2015 is their lack of consideration regarding the connectivity of the HiC or ChIA-PET interaction network. In particular the authors assert that this previous method would be biased toward detecting co-localization for TFs that exhibit high connectivity. 
   This assertion may seem reasonable, since Ma et al. don't explicitly consider connectivity in their method to produce their control/null set. Nevertheless when examining the degree distribution provided by the authors in their reply to the third comment, it becomes clear that filtering HiC interactions based on the presence of TFBS dramatically transforms the HiC distribution from a normal-like distribution (as expected from an "even" genome coverage) to a power-law like distribution (illustrated in the authors reply to the third comment). This power-law like degree distribution is the principal empirical justification for accounting for connectivity, as this property indicates vast disparity in the connectivity among the considered TFBS contained within the corresponding HiC/ChIA-PET bins.
   Nevertheless it is unclear why the Ma et al. method wouldn't also reproduce such power-law like degree distribution in their control/null set. The reason being that they also filter interactions to contain the considered TFBS following their random shuffling step. It is therefore reasonable to assume that the disparity in connectivity would also be present in their control/null set. Supporting this assumption is the recapitulation of the results from Ma et al. in the present manuscript. To validate the assertion from the authors that the main originality of their method is the consideration for connectivity, the authors would need to demonstrate the absence of this property in the Ma et al. method, beyond the observation that it is not explicitly mentioned in the original paper.


            - Unclear ~ Ma shuffles binding sites keeping the same interaction profile of bins and anchor TFBS positions
                - Sparsifying interaction network by constraining to only consider interactions with considered TFs
                    - Transform degree distribution from Gaussian to Power law
                    - Shuffled sites would produce a new interaction network fullfilling the condition of co-binding
                    - Observed deviate from Random because interaction strength scrambled, hence the sum of interaction strengths should not be as high if there was an observed association.
                - Contention = Inherently some bins have a hub-like property in terms of TF-cobinding
                    - Such bins not reproduced by Ma shuffling (Assumption/Postulate -> unclear, need to be shown)
                        - Not obvious that the condition for a bin to contain considered TFBS would not spontaneously reproduce similar power-law like degree distribution in the shuffled interaction network produced by Ma.
                            - Thus considered paper provides a very incremental improvement by being more explicit wrt one of the many factors determining the interaction network  
                    - Alternative shuffle TF:bin mapping contrained by bin connectivity
                        - Shuffling connected components at best
                        - If not accounted for:
                            - most TF-TF interactions seem highly significant
                - Current state of comparison:
                    - We had also attempted to use the approach by Ma et al, who don't provide a software tool. We found that their randomization method was computationally expensive, in addition to being, we argue, less rigorous than ours in terms of maintaining the essential properties of the network.
                        - Comparison of method should be essential aspect of the results
                            - produced randomisation comparison, etc
                                - effect of connectivity on estimation for significance of co-binding
                    - Limited to small mention in discussion.

        - For ChIA-PET can be understood 
            - => Benefit of method relies on justifying the uniqueness of POL2 ChIA-PET for TF-cobinding investigation
                - heatmap viz for one or two chromosomes would make it obvious how the two forms of interaction network (HiC vs ChIA-PET) compare and maybe strengthed the benefit of ChIA-PET over Hi-C
    - Degree distribution indicate that the highly connected bins represent a tiny minority of nodes
        - influence on number of co-occurence marginal?
        - Compare with randomly shuffled bins?
