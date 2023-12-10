Consider a coarse-graining:
$$
\Xi : \mathbb{R}^N \rightarrow \mathbb{R}^n, \text{where } n\ll N
$$
Then the corresponding potential of mean force (PMF) is given by
$$
V(z) = - kT log(q(z)) + const
$$
where
$$
q(z) = \frac{\int \exp{(-U(x)/kT)}\delta (\Xi(x) - z) dx}{\int \exp{(-U(x)/kT)dx}}
$$
The PMF is completely specified by the underlying atomistic model and the CG (or CV) mapping.

V weights each configuration according to the total Boltzmann weight for the atomistic configurations that map to z.

If V(z) is known to within an additive constant, then it can be used to sample a canonical distribution of CG configurations, that is equivalent to the one implied by the atomistic model and the CG mapping.

It should be stressed, that this, however, does not imply that the CG model will necessarily reproduce the dynamical properties, such as the time correlation functions, of any atomistic model.

Importantly, the many-body PMF is also **not** a conventional potential energy function, but should be considered a configuration-dependent free energy function that reflects **both** energetic and entropic contributions. 

The CG forces determined from gradients of the PMF equal conditioned averages of atomic forces (i.e. it truly is a potential energy for generating mean forces!)

**Important**: The PMF is a function of thermodynamic state. It depends on volume through the limits of integration and temperature through the Boltzmann weight factor.

PMF is impossible to calculate exactly for most systems. Not only is the integration often infeasible, but it is also generally a many-body function with new couplings between the remaining CG coordinates that cannot be represented by a simple molecular mechanics form.  

Instead one often seeks to approximate the PMF in a data-driven approach. When this is done using global native structure information or other macroscopic thermodynamic constraints, this is called top-down coarse-graining. When this is done using simulations from a higher-resolution fully-atomistic model, this is called bottom-up coarse-graining. 
