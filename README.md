# Hybrid-exponential scheme for stochastic Volterra equations
This project implements the hybrid-exponential scheme of (Rømer, ?) for simulating stochastic Volterra equations (SVE's). A SVE X(t) is here defined as

![eqn1](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/sve_def.png)

![eqn1](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/temp1.png)

The scheme works by approximating K as 

![eqn2](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/K_approx.png)

![eqn2](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/temp2.png)

In case K behaves like a rough fractional having \kappa > 0 is needed to 
efficiently capture the singularity. To approximate K(t) on [kappa*\Delta,T] for some T > 0 one can the choose the
coefficients (c_j,\gamma_j)_{j=1}^m using e.g. the ideas of (Beylkin and Monzón, 2005). As an example we can 
consider the kernel K(t) = t^{H-\frac{1}{2}}, t \geq 0, H \in (0,1/2) on the interval [1/1000,1]. Below we then run
show the true kernel K(t) and a m = 5 sum of exponentials approximation.

![eqn2](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/K_plot.jpg)

The approximation of X(t) then comes out to

![eqn4](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/X_approx.png)

where U^j(t), j=1,...,m, are defined by

![eqn3](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/dU.png)

The hybrid-exponential scheme is then essentially defined by discretising the above expressions.

With an efficient exponential approximation, i.e. low m, the scheme is the efficient as the running time is
O(n*m) whereas a scheme computing the full convolution in general would require O(n^2) operations. 
Talk kappa > 0 important to capture singularity efficiently?
 
Remark: The code is limited to one-dimensional SVE's where the kernel functions are the same for both the stochastic and non-stochastic integral as defined above. The scheme can be considered more generally, see the paper.
 
# Example
As an example we simulate the rough Bergomi model used in Finance defined by

![eqn3](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/rbergomi.png)

![eqn3](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/rbergomi_params.png).

Using the hybrid-exponential scheme with kappa = 1 to simulate the process V(t) we get ... showing sqrt(V(t)) in the first plot (the volatility process) and the U^j(t), j=1,...,m, factors in the plot below that.
![pic1](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/volatility.jpg)
![pic2](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/u_factors.jpg)

See the paper for pricing examples and a comparison with existing methods in terms of running times.

# Getting started
See the folder '.../get_started'.

# Reference:
- Rømer, S.E., Hybrid-exponential scheme for stochastic Volterra equations, ?
