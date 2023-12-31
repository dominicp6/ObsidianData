The essence of bottom-up coarse graining is to determine suitable approximations to the [[potential of mean force]] that employs information from a more detailed model which are tractable to calculate, efficient to simulate, and sufficiently accurate for describing a given phenomena whilst also being (ideally) transferable to other systems.

At present, no single method completely addresses this challenge. 

A wide range of fitting strategies have been proposed, including:
1) Reproducing energetics
2) Matching structural properties
3) Integral equation theories

Regardless of the fitting strategy, the general framework is to parameterise the potential of generalised molecular mechanics form (each bond, angle, torsion, and pair non-bonded interaction is modelled by a single potential) i.e. a sum over types of bonding interactions over appropriate sets of particles (e.g. particle pairs for non-bonded pair interactions).

$$
U(\mathbf{R}) = \sum_{\zeta}\sum_{\lambda} U_\zeta (\psi_\zeta (\mathbf{R}_\lambda))
$$
This is a more complex functional approximation than is typically done with top-down approaches.

In practice, bottom-up models often represent these potentials as discretisations on a grid or parameterisations with flexible basis functions, such as splines. More technical details about this latter approach can be fond [here](https://pubs.aip.org/aip/jcp/article/135/21/214101/189927/Coarse-graining-entropy-forces-and-structures). 

The potentials $U_\zeta$ are often determined so that for the corresponding degree of freedom, $\psi_\zeta$, it reproduces the corresponding target distribution $p_\zeta(x)$ from the fully-atomistic model. For instance, each CG pair potential may be parameterised to reproduce the corresponding atomistic radial distribution function. Of course, *this condition does not imply that the CG and atomistic models will necessarily generate the same cross-correlations between the different degrees of freedom*. 

Although it has been proven for simple systems, it is not obvious *a priori* whether there exists a molecular mechanics potential that will reproduce a given set of target structural correlation functions generated by an atomistic model. Also, in practice, many structural features are quite insensitive to the CG potential. 

No direct (non-iterative) mechanism exists for determining potentials that are guaranteed to reproduce target correlation functions. State-of-the-art methods often employ iterative nonlinear optimization techniques to systematically refine the CG potential unit it accurately reproduces the target correlation functions of an atomistic model. 

Examples of specific methods include:
1) [[Direct Boltzmann inversion]]
2) [[Iterative Boltzmann inversion]]
3) [[Inverse Monte Carlo]]
4) Variational approaches



