# Hybrid-exponential scheme for stochastic Volterra equations
This project implements the hybrid-exponential scheme of (Rømer, ?) for simulating stochastic Volterra equations (SVE's). The code is limited to one-dimensional SVE's where the kernel functions are the same for both the stochastic and non-stochastic integral. Thus define an SVE as

...as

X(t) = X(0) + \int_0^t K(t-s) b(s,X(s))ds + \int_0^t K(t-s) \sigma(s,X(s)) dW(s)

where X(0) \in \mathbb{R}, K,b,\sigma are functions and W(t) is a Brownian motion. 
We assume K is completely monotone.

The scheme works by approximating K as 

K(t) \approx 1_{} K(t) + \sum_{j=1}^m c_j e^{-\gamma_j t}

where (c_j,\gamma_j)_{j=1}^m are coefficients, m \in \mathbb{N}, kappa \in \mathbb{N}_0 and \Delta > 0 a 
step size. In case K behaves like a rough fractional it is highly recommended to put \kappa = 1 to capture the 
singularity properly. To approximate K(t) on [kappa*\Delta,T] for some T > 0 one can the choose the
coefficients (c_j,\gamma_j)_{j=1}^m properly.

The scheme then comes out to

X(t) = ...

where U^j(t), j=1,...,m, are defined by

dU^j(t) = (b(t,X(t)) - \gamma_j)dt + \sigma(t,X(t))dW(t), U^j(0) = 0.

With an efficient exponential approximation, i.e. low m, the scheme is the efficient as it only
requires O(n*m) whereas a scheme computing the full convolution in general would require O(n^2) operations.

See the folder '.../get_started' for scripts to help you get started.
 
# Example
As an example we simulate the rough Bergomi model defined by
...
where ...

Using the hybrid-exponential scheme with kappa = 1 to simulate the process V(t) we get ... showing sqrt(V(t)) in the first plot (the volatility process) and the U^j(t), j=1,...,m, factors in the plot below that.
![pic1](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/volatility.jpg)
![pic2](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/u_factors.jpg)

See the paper for pricing examples and a comparison with existing methods in terms of running times.

# Main reference:
- Rømer, S.E., Hybrid-exponential scheme for stochastic Volterra equations, ?
