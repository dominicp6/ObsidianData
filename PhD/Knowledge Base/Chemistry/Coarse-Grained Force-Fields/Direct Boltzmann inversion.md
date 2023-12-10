The simplest and most straightforward approach for determining CG potentials from atomistic distribution functions. 

Each term in the CG potential is determined directly from the corresponding atomistic distribution function
$$
U_\zeta(x) = -k_BT \ln \left[p_\zeta(x)/J_\zeta(x)\right]
$$
where $J_\zeta(x)$ is the corresponding Jacobian factor. 

Q) But isn't the Jacobian matrix non-square?

In this case, the potential determined by DBI is equivalent to the atomistic pair potential of mean force (ppmf):

$$
w_\zeta (r) = - k_B T \ln{g_\zeta (r)}
$$
where $g_\zeta (r)$ is the corresponding radial distribution function (RDF) determined by the atomistic model and CG mapping.

DBI has been used successfully in polymeric systems, for short peptides, RNA and for improving bonded potentials in [[The MARTINI Force Field]]. 

DBI provides an accurate description for interactions that are effectively isolated. It is therefore useful for nonbonded pair potentials if the CG sites are "dilute" and for bonded potentials if the CG bonds are "stiff".

In the g-YBG theory, the CG pair mean force $-W^{'}_\zeta(r|U)$ can be decomposed as 
$$
F_\zeta(r) + \sum_{\zeta'} \int dx' \tilde{G}_{\zeta \zeta'}(r, x'|U)F_{\zeta'}(x')
$$
i.e. a "direct" contribution due to the force $F_\zeta(r)=dU_\zeta/dr$ and a correction through a structural correlation function describing the coupling of the interactions. 

This suggests a systematic framework for improving the agreement between the atomistic, $p_\zeta(r)$, and CG distributions, $P_\zeta(r |U)$ - [[Iterative Boltzmann Inversion]].