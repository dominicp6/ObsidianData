https://pubs.acs.org/doi/full/10.1021/acs.jctc.8b00187

Observable-driven Design of Effective Molecular models (ODEM) is a method for designing coarse-grained molecular models that accurately reproduce experimental observables. The method works by iteratively optimizing the parameters of the coarse-grained model to maximize the agreement between the model's predictions and the experimental data.

An optimal set of parameters can then be found by the following iterative approach:

1. The initial parameter values ϵ(0), defines a model Hamiltonian _H_(0)(**x**), where **x** indicates a configuration of the system (e.g., the Cartesian coordinates of the effective atoms of the protein system). We run MD simulations with _H_(0)(**x**).
2. We estimate the equilibrium distribution π(0)(**x**) for the model for the choice of parameters, ϵ(0), from the MD data. Computationally, the equilibrium distribution is usually evaluated on discrete states, such that π(0)(**x**) is not a function but a vector **π**(0). One practical approach is to discretize the state space into _N_ clusters, _S__i_, _i_ = 1,···,_N_, to estimate a maximum-likelihood Markov State model (MSM) (33) on it and to compute its equilibrium distribution **π**(0). (34,35) The use of an MSM allows us to obtain an equilibrium distribution from ensembles of short, nonequilibrium simulations. (36)
3. For each experimental measurement available, _f__k_, we use the distribution **π**(0) to estimate the value, _e__k_[**π**(0)], of the corresponding observable _g__k_(**x**), e.g., the probability of a FRET distance. 
4. If we treat the measurements as statistically independent and normally distributed, we can compute the likelihood of the simulation prediction in light of the experimental measurements, _Q_(0) = _Q_(ϵ(0)). [More sophisticated error models can be used that might better suit a particular observable. (37)] 
5. The equilibrium distribution **π**(1) associated with a new parameter set ϵ(1) = ϵ(0) + _δϵ_, for a small change _δϵ_, can be estimated in each discrete set, _S__i_, by reweighing.
6. [Equation 4](https://pubs.acs.org/doi/full/10.1021/acs.jctc.8b00187#eq4) provides an explicit expression of the likelihood as a function of the model parameters. We can then make a step in the parameter space in the direction that maximizes _Q_(1), using a bounded gradient descent method (see [Supporting Information](https://pubs.acs.org/doi/suppl/10.1021/acs.jctc.8b00187/suppl_file/ct8b00187_si_001.pdf)). New simulations are run with the new parameters ϵ(1), and a new maximum likelihood equilibrium distribution π(1)(**x**) is obtained. The steps above are repeated until convergence to a final _Q__opt_.


