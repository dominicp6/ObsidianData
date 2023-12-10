#chemistry #ML  #physics

A diffusion generative model is trained on protein structure from molecular dynamics simulations, and it is shown that its score function approximates a force field that can be directly used to simulate CG molecular dynamics. 

A literature review on coarse graining:
https://pubs.aip.org/aip/jcp/article/139/9/090901/315544/Perspective-Coarse-grained-models-for-biomolecular

In bottom-up approaches to constructing coarse-grained force fields, the simulations following the CG model should have the same equilibrium distribution as obtained by projecting equilibrated all-atom simulations onto the CG resolution. This is also known as the *thermodynamics consistency principle*. These are often used in combination with machine learning methods. Common approaches include:

**Variational force matching**
Minimising the MSE between the model's CG forces and the atomistic force projected onto the CG space. However, the stochastic nature of the projected forces means that this noisy force-matching estimator has a large variance, leading to data-inefficient training. 

**Relative Entropy Minimisation**
Perform density estimation in the CG space without accessing atomistic forces. Equivalent to energy-based models. Training these models requires iteratively drawing samples from the model to estimate log-likelihood gradients, and so demand significantly higher computational cost. 

**Energy-based models**


**Flow-matching**
Is a hybrid approach that does not require atomistic forces for training (like relative entropy minimisation) while also retaining good sample-efficiency. First, a CG density is modelled with an augmented normalizing flow. A second learning stage with a force-matching-like objective is then required to extract a deterministic CG force field that can be used in CG molecular dynamics simulations. The learnt CG models are not yet accurate enough for reproducing the thermodynamics of the corresponding fine-grained models, and scaling to larger proteins leads to instabilities. 

**Coarse-graining maps**
$\Xi : \mathcal{R}^{3N} \xrightarrow{} \mathcal{R}^{3n}$, where $n < N$. In molecular systems, the coarse-graining map is usually linear (i.e. $\Xi$ can be represented as a matrix). By identifying the ensemble of atomic configurations $x$ that map to the same CG configuration $z$, we can explicitly express the probability density of the CG configurations, which in turn defines the thermodynamically consistent effective potential of mean force $V(z)$. In summary:

$$
q(z) = \frac{\int \exp{(-U(x)/kT)}\delta (\Xi(x) - z) dx}{\int \exp{(-U(x)/kT)dx}}
$$
and
$$
V(z) = - kT log(q(z)) + const
$$
In the above, $V(z)$ constitutes the [[potential of mean force]].

TODO: How does Langevin dynamics map under this coordinate transform?
TODO: Constructing data-efficient/optimal coarse grain mappings?


**Variational force matching**
Under certain constraints on the coarse-graining mapping, a more tractable consistency equation between the coarse-grained force field and the atomic force-field can be obtained. More specifically, if $\Xi$ is a linear map, and if each bead has at least one atom with a nonzero coefficient only for that specific bead, then the following relation holds:
$$
-\nabla_z V (z) = \mathbb{E}_{q(x|z)}[\Xi_f(-\nabla_x U(x)]
$$
Here $\Xi_f$ is a linear map whose coefficients are related to the linear coefficients of the CG map $\Xi$. The above relation can be used to approximate a thermodynamically consistent CG potential $V_{\theta}(z)$ with parameters $\theta$ by minimising the following variational loss:
$$
\mathbb{E}_{q(x,z)}[ \vert \nabla_z V_\theta (z) - \Xi_f (\nabla_x U(x) \vert_2^2)].
$$


**Relative entropy minimisation**
Basic idea: optimizing the density implicitly leads to optimized mean potential functions. We want to minimise the relative entropy (a.k.a. Kullback-Leibler divergence) 
$$
\mathbb{E}_{q(z)} [{\log{(q(z))}-\log{(p_\theta (z))}}]
$$
which is equivalent to optimizing the maximum likelihood when a finite number of samples is drawn from $q(z)$. The approximate CG forces can be extracted from the optmized model density $p_\theta (z)$ through $-\nabla_z V_\theta (z) \propto \nabla_z \log p_\theta (z)$. Traditionally, an unnormalised version of $p_\theta$ is modelled through $V_\theta$. 

To minimise entropy, one would either need to estimate the free energy (normalisation constant) or draw i.i.d. samples for gradient estimation, which is impractical for higher-dimensional problems.

**Augmented Normalising Flows**


Song et al (2020) showed that the DDPM loss is equivalent to a weighted sum of donoising score matching objectives. At sufficiently low noise levels, the marginal distribution will resemble the data distribution. So the score effectively approximates the score of the unknown data distribution. When the latter is equal to the CG Boltzmann distribution, the optimal score at level i=1 will approximately match the CG forces. 

Since the CG force field must be conservative, the $\epsilon_\theta$ is parameterised as the gradient of an energy neural network. Using a conservative score in diffusion is crucial for stable CG MD simulations with the extracted denoising force field. 

The researchers take account of rotational invariances empirically through data augmentation, showing that the errors introduces are only $<10^{-6}$. 

They use a graph transformer network.


**Graph Transformer**


They benchmarked their approach against several other models such as *Flow i.i.d*, *Flow-CGNet sim* and *CGNet Sim.*. 


They evaluated the model with *four-fold cross validation*, where three of the simulations are used for training and validation and one for testing. 

**Parallel Tempering**

**Elbow Method**
A systematic way of setting K in K-means clustering.

The relation between fine-grained and coarse-grained time is non-trivial (e.g. Jin et al 2022; Nuske et al 2019)

