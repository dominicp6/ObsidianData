Consider 
$$
W_\zeta(r|U) = U_\zeta(r) + \sum_{\zeta'} W_{\zeta;\zeta'}(r|U)
$$
An iterative Boltzmann Inversion (IBI) algorithm would be
$$
\delta U_\zeta(r) \propto w_\zeta(r) - W_\zeta(r|U) \propto k_BT ln{[P_\zeta(r|U)/p_\zeta(r)]}
$$
The modified potentials $U_\zeta(r) + \delta U_\zeta(r)$ are then employed in CG simulations, the distributions obtained from these simulations are compared with the atomistic distributions, and the potentials are modified again, repeating until convergence.

Correlations between different interactions and between different distances are treated implicitly through iteration. In some cases, though, this can lead to convergence difficulties that may be exacerbated by complex coupling between interactions or by the relative insensitivity of structural correlation functions to many aspects of the CG potential.

