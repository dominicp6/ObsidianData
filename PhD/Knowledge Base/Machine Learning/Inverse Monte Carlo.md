The IMC algorithm considers a susceptibility matrix
$$
K_{\zeta\zeta'}(x, x' |U) = \frac{\delta P_\zeta(x|U)}{\delta U_{\zeta'}(x')}
$$
that describes the sensitivity of each simulated CG distribution to small variations in the CG potential functions.

The corrections to the CG potentials, $\delta U_\zeta(x)$, are determined by solving the system of coupled linear equations
$$
p_\zeta(x) - P_\zeta(x|U) = \sum_{\zeta'} \int dx' K_{\zeta \zeta'}(x, x' | U) \delta U_{\zeta'}(x')
$$
This and subsequent integral equations are typically solved either by discretization or by employing a linear basis for the potentials. 

