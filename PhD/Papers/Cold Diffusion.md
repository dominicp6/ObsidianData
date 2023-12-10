#ML 

Useful diffusion models can be trained without having to resort to using Gaussian noise.

Diffusion models work by specifying a degradation operator D and a restoration operator R, that approximately inverts D.

R is parameterised by a neural network and is usually trained using a simple convex loss. Application of R for large t yields blurry result. Diffusion models perform generation by iteratively applying the denoising operator and then adding the noise back to the image, with the level of added noise decreasing over time.

The optimal sampling algorithm is slightly different for differentiable depredations. Each iteration still involves inverting back with R, however the one-iteration-less-powerful D is corrected by $x_s - D(x_0, s)$. For a class of linear degradation operations, this produces exact reconstructions even when the restoration operator R fails to perfectly invert D.

Various methods to evaluate how well a diffusion model is approximating real training data, and this paper considers several of them:
1) **[Inception Score](https://en.wikipedia.org/wiki/Inception_score)**
2) **[[Mode Score]]**
3) **[Frechet Inception Distance](https://en.wikipedia.org/wiki/Frechet_inception_distance)**
4) **[[Kernel Inception Distance]]**

A related idea in drug-discovery is the [Frechet ChemNet Distance (FCD)](https://pubs.acs.org/doi/10.1021/acs.jcim.8b00234).