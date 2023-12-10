#chemistry #ML

AI QM Docking Net (AQDnet)
Uses 3D structure of protein-ligand complexes to predict binding affinity.

The NN learns the protein-ligand quantum energy landscape for the prediction of protein-ligand interactions.

Ranked first on CASF-2016 benchmark.

See also,
[[CASF-2016]]
[[PDBbind]]

Three essential requirements for AI to predict the potential energy:
1) Invariant predictions for system rotation and translation
2) Invariant predictions regardless of atom processing order
3) A unique representation of a 3D molecular structure

Various approaches have been developed to represent the molecular structure as graphs or as 3D images. These have limitations (lack of distance information and lack of invariance respectively). 

Importance is to be able to predict **both** the most stable ligand conformation in the protein complex **and** the binding affinity of P-L complexes. AQDnet achieves this through the help of atom-centred symmetry functions (ACSFs).

It is difficult to prepare a sufficient amount of training data using crystal structures alone. Furthermore, crystal structures are not adequate because virtual screening also needs to be able to evaluate the configurations of the transition process before reaching the most stable configuration.

This paper proposes a new data augmentation method that generates a large number of configurations based on a single crystal structure registered in a database. It dovetails with a method for estimating the charge and stability of each generated configuration compared to that of the most stable pose using a QM calculation, thereby expanding the training dataset 1000 fold. 

The method they use for labelling these structures is SMO-COSMO, a semi-empirical QM method.

They trained two different ADQnet models. *Docking AQDnet*, a model specialised for the evaluation of [[docking power]], was used for the evaluation of [[docking power]] and [[screening power]]. *Scoring AQDnet* was used to evaluate [[scoring power]]. The only difference is the training data.


**[[DeepBSP]]**
Uses a simple data augmentation method using configuration generation. 


