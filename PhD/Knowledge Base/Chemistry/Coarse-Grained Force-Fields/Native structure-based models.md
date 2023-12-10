Popular implicit solvent CG models that are explicitly constructed on the basis of known PDB structures. 

We shall treat these “native structure-based” approaches as providing various approximations to the many-body PMF. As the quantity and quality of high resolution structures continues to rapidly increase, one may expect that native structure-based approaches should only become increasingly important in the future.

Given the CG representation of a folded structure, $R_0$, a pair of amino acid residues (or, more generally, a pair of CG sites) form a “native contact” if the distance between the residues is less than a predefined threshold distance. On this basis, the interaction between the pair is classified as either “native” or “non-native,” irrespective of the physicochemical character of the residues.

As a consequence of this feature, as well as their remarkable simplicity and tremendous computational efficiency, these models are perhaps the most popular and successful models for studying the folding, fluctuations, and interactions of proteins, protein complexes, and, to a lesser extent, also nucleic acids with known equilibrium structures.

Examples include:
1) Network models
2) Native-centric models
3) Knowledge-based models

**Network Models**
In network models, the folded-structure is the minimum of the potential which is a sum of weighted quadratic displacements of all CG site pairs from their reference locations in the folded structure. Often each amino acid is represented with a single cite corresponding to an alpha carbon.

**Native-centric models**
Also referred to as Go, native-based or structure-based models. In contrast to the harmonic potential employed by network models, native-centric models approximate the many-body PMF with an anharmonic molecular mechanics potential.

These models are motivated by the observation that the folded structure achieves mutual consistency among all relevant interactions, where the structure is "minimally-frustrated". 

As a consequence of their simplicity and capability to guide proteins from an unfolded conformation to the correct folded conformation, native-centric models have enjoyed remarkable popularity.

**Knowledge-based models**
Knowledge-based approaches employ known PDB structures for multiple nonhomologous proteins (i.e., proteins with sufficiently distinct sequences) to determine a set of transferable, i.e., protein-independent, potentials that are intended for modeling multiple proteins, including proteins that were not in the training set and proteins that may have unknown structure.

1) Statistical potentials: Estimate the effective interaction between a pair of amino acid residues based upon the statistical frequency of finding contacts between the pair in PDB structures.
2) Potential optimization: employs PDB structures for multiple proteins (with distinct sequences) to optimize a set of transferable (i.e., protein-independent) parameters for CG potentials that stabilize these structures.
3) Fragment and homology based approaches: For instance, models have been tailored for specific proteins of unknown structure by supplementing transferable statistical potentials with Gō-like potentials that stabilize _predicted_ native contacts. This strategy may prove increasingly powerful due to very recent improvements in the prediction of native contacts from multiple sequence alignments.
