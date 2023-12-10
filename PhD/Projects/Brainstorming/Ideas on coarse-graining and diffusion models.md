
The lofty aim:
- To use ML to learn a coarse-grained dynamics such that both original dynamics and structure information can be recovered

The key scientific innovation:
A) Learning a (coarse-graining mapping, diffusive dynamics model) pair that aims to not only preserve equilibrium dynamics, but also non-equilibrium dynamics such as time correlation functions.
B) Efficient simulations of coarse-grained dynamics simulations through coordinate transforms.
C) Fully-atomistic in-painting based on a coarse-grained model

Theoretical components:
- How to specify the coordinate mapping?
	- Fixed linear map from $\mathbb{R}^N$ to $\mathbb{R}^n$ with tunable params
	- A linear map that itself implicitly depends on the atomistic configuration (in some convenient, efficient parameterisation). Why would this be useful? Because the salient structural components in a system depend on where the protein is in its phase space
- How to train/learn the mapping?
	- Begin with a bottom-up approach first, since this is the most physics-based and, perhaps, theoretically straightforward.
	- In the most simple case, we could even hard-code the mapping based on chemical insights. 
	- However, a key idea that I would like to explore is how, even in the mapping itself is prescribed, I would like to set up a learning problem that would allow learning of the best-fitting diffusion tensor based on bottom-up data.
	- The objective would be to match key dynamical properties such as the autocorrelation functions of the collective variables. 
	- A fun strategy to try would be to restrict the learning problem to the form of diffusion tensors that can be transformed to constant diffusion through the methods that I have developed. I would like to see whether this is sufficient to recover accurate dynamics, or whether a more general D would be required. I could also restrict investigation to a general diagonal diffusion tensor, as this is still of the form accessible to some efficient trapezoidal integrator methods. 
- The generative diffusion component:
	- I would like to incorporate generative diffusion ML models in a central role in the learning task. My hope is to use this diffusion model to learn the "inpainting" mapping from the coarse-grained configuration to the fully-atomistic configuration. 
	- Perhaps this diffusion model can also play a role in the D-tensor learning task, although I cannot yet see a clear connection. Of course, ideally the two learning tasks ought to "talk to each other" for the best results.

Some unresolved questions from this so far:
- In principle, I would not want to restrict myself to Brownian dynamics processes. I would  also like to look more generally at Langevin dynamics processes. But then the question arises - what becomes the equivalent of the diffusion tensor D in this context? What configuration-dependent dynamical properties of Langevin dynamics should I try learn?


Next steps:
- Research to what extent in painting from coarse-grained to atomistic models / learning a dynamical model of a coarse-grained structure has been studied in the literature
