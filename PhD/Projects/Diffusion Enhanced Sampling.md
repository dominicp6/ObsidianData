We consider a double-well potential 
$$
V(x) = 2 x^4 - 4 x^2
$$
which has minima at $x = \pm 1$ and a local maximum at $x=0$.

We consider overdamped Langevin dynamics with a configuration dependent diffusion given by:
$$
D(x; \alpha) = \begin{cases}
\exp((V(x) - V_{max})(1-\alpha)) \quad \text{if } |x|<1\\
\exp((V_{min} - V_{max})(1-\alpha)), \quad \text{otherwise}.
\end{cases}
$$
This is a scaling function which equals 1 when at the well local maximum and reaches a minimum when at the local minima. The difference $D_{max} - D_{min}$ is controlled by the $\alpha$ parameter. As $\alpha \rightarrow 1$ , $D(x) \rightarrow 1$ for all $x$. $D(x)$ becomes maximally configuration dependent as $\alpha \rightarrow 0$. 

Note that this functional form of $D$ has the property 
$$
D(x; \alpha') \leq D(x; \alpha), \forall x \text{ where } \alpha'\leq\alpha
$$
Reducing $\alpha$ therefore reduces the RMS diffusion, but increases its configuration dependence. 

The amplitude of the noise is then
$$
\sigma(x) = \sqrt{2kT D(x)}.
$$
We plot $V(x)$ and $\sigma(x)^2$ for the cases:

## Preliminaries 
(iii) $kT =1$ and $\alpha = 1$:
![[Pasted image 20231016164302.png]]

(ii) $kT=1$ and $\alpha = 0.5$:
![[Pasted image 20231016164124.png]]
$kT = 1$, $\alpha = 0$:
![[Pasted image 20231016164210.png]] 

We investigate how modifying $\tau = kT$ and $\alpha$ effects the rate of hopping between the basins of the double-well potential.

$T = 1000, dt = 0.01$ using the Hummer-Leimkuhler-Matthews integrator:
![[Pasted image 20231016164700.png]]
The colour scale is the log of the number of transitions between the basins. Red "x"s denote the value of alpha that gave the maximum number of transitions for a fixed $\tau$. This result is robust to changes in $T$. Here's the same plot with $T = 100$:
![[Pasted image 20231016170851.png]]

Note that low values of $\alpha$ favour increased hopping, even though these have lower mean square noise when averaged over all configurations. The effect is small (below this is back to the $T=1000$ case):
![[Pasted image 20231016165110.png]]
The above plot shows transition counts vs alpha for values of $\tau \in \{0, 1, 2, 3, \dots, 30\}$. Notice the slight peak at lower alpha, which becomes more pronounced as $\tau$ increases. These values are averaged over 100 independent repeats.

As expected, the more consequential effect is increasing noise amplitude, rather than increasing noise localisation. This is a plot of the mean number of transitions as $\tau = kT$ increases:

![[Pasted image 20231016165056.png]]
Surprisingly, when we investigate how the L1 convergence error (w.r.t. the invariant measure) varies as a function of $\tau$ and $\alpha$ for fixed $T=1000$, we see that actually values of $\alpha$ close to $1$ are preferred, even though these lead to fewer hops between the basins. Presumably, this is because the larger noise values away from the basin improve the sampling in those regions. 
![[Pasted image 20231017132608.png]]
Above: Average L1 error over 100 independent trials. L1 error is with respect to 30 discrete histogram bins in the range (-3, 3). 
![[Pasted image 20231017122741.png]]
![[Pasted image 20231017122753.png]]
![[Pasted image 20231017122804.png]]
This is robust to the value of $T$. Here's the same plot with $T=10$:
![[Pasted image 20231016170800.png]]
For $T=10$ we also see the dependence on alpha clearly:
![[Pasted image 20231016171051.png]]
And here is the same plot with $T = 10,000$: 
![[Pasted image 20231016172319.png]]
In this case, it is clear that there is an intermediate value of $\tau$ for which the L1 error is minimal:
![[Pasted image 20231016172730.png]]

As one might expect, we are also able to verify that the longer your simulation, the smaller the noise that you want to use in order to get minimum sampling error.

I wanted to check that this was not just a curious feature of the HLM integrator, so here is the same plot for $T=100$ for several more integrators:

*Stochastic-Heun* ($T=1000$)

![[Pasted image 20231017130419.png]]
![[Pasted image 20231017122157.png]]
![[Pasted image 20231017122234.png]]
![[Pasted image 20231017122248.png]]
*Euler-Maruyama* ($T=1000$, stability issues means we stop at $\tau=20$)
![[Pasted image 20231017125557.png]]
![[Pasted image 20231017121015.png]]
![[Pasted image 20231017121047.png]]
![[Pasted image 20231017121106.png]]
*Milstein Method* ($T=1000$, stability issues means we stop at $\tau=20$)

![[Pasted image 20231017132132.png]]]]
![[Pasted image 20231017121603.png]]
![[Pasted image 20231017121620.png]]
![[Pasted image 20231017121635.png]]
*Limit Method with Variable Diffusion*

![[Pasted image 20231017114603.png]]



Change of notation:
It is more convenient to make $\alpha=0$ denote the scenario where we have constant diffusion, therefore:

**Diffusion Model 1**
![[Pasted image 20231129143136.png]]
$$
D(x; \alpha) = \begin{cases}
\exp((V(x) - V_{max})\alpha) \quad \text{if } |x|<1\\
\exp((V_{min} - V_{max})\alpha), \quad \text{otherwise}.
\end{cases}
$$

This model is particularly convenient, as the time-transformed potential has a particular interpretation (note how the location of the minima are unchanged?):
![[Pasted image 20231129143303.png]]


We also examine two more diffusion models.

**Diffusion Model 2**
$$
D(x; \alpha) = \begin{cases}
1 - \alpha \quad \text{if } V''(x) > 0 \\
1 - \alpha (|\text{min}_x V''(x)| + V''(x)) / |\text{min}_x V''(x)|, \quad \text{otherwise}.
\end{cases}
$$
![[Pasted image 20231129143346.png]]
In this model, the diffusion only starts to deviate from the background level at the inflection points of the potential. However, the time-rescaled potentials are less easy to interpret:
![[Pasted image 20231129143439.png]]

**Diffusion Model 3**
$$
D(x; \alpha) = \begin{cases}
1 - \alpha \quad \text{if } V''(x) > V''(x_{min}) \\
1 - \alpha (|\text{min}_x V''(x)| + V''(x)) / (|\text{min}_x V''(x)| + V''(x_{min})), \quad \text{otherwise}.
\end{cases}
$$
![[Pasted image 20231129143504.png]]
In this model, the diffusion goes to zero at the minima of the potentials.
![[Pasted image 20231129143536.png]]


## Euler-Maruyama - Changing the stepsize and final simulation time

