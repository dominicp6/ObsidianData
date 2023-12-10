The forward diffusion SDE is:
$$
d\mathbf{X}_t = - \frac{1}{2}\beta(t)\mathbf{X}_t dt + \sqrt{\beta(t)}d\mathbf{W}_t
$$
The reverse diffusion SDE is:
$$
d\mathbf{X}_t = [-\frac{1}{2}\beta(t)\mathbf{X}_t - \beta(t)\nabla_{\mathbf{X}} \log q(\mathbf{X}_t)]dt + \sqrt{\beta(t)}d\mathbf{W}_t
$$
Typically the reverse diffusion process is solved by EM integration:
$$
d\mathbf{X}_{t-1} = [-\frac{1}{2}\beta(t)\mathbf{X}_t - \beta(t)\nabla_{\mathbf{X}} \log q(\mathbf{X}_t)]\Delta t + \sqrt{\beta(t)\Delta t}\mathcal{N}(0, I) 
$$
We can consider the reverse SDE as an augmented system:
$$

d\begin{bmatrix}
           \mathbf{X} \\
           t \\
\end{bmatrix} = \begin{bmatrix}
           (-\frac{1}{2}\beta(t)\mathbf{X} - \beta(t)\nabla \log q(\mathbf{X}))dt + \sqrt{\beta(t)}d\mathbf{W}_t \\
           dt \\
\end{bmatrix}
$$
Defining 
$$
\hat{X} = \begin{bmatrix}
           \mathbf{X} \\
           t \\
\end{bmatrix}
$$
we can also write this as
$$
d\hat{X} = \mathbf{f}(\hat{X})dt + \sigma(\hat{X})d\mathbf{W}_t
$$
where 
$$
\mathbf{f}(\hat{X}) = \begin{bmatrix}
           -\frac{1}{2}\beta(t)\mathbf{X} - \beta(t)\nabla_X \log q(X) \\
           t \\
\end{bmatrix}
$$
and 
$$
\sigma(\hat{X}) = \begin{bmatrix}
           \sqrt{\beta(t)} & 0 \\
           0 & 1 \\
\end{bmatrix}
$$
so this is an instance of noise with configuration-dependent diffusion.

It is possible to map this to constant diffusion by a combination of a time-rescaling and a Lamperti transform