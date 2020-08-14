# Hybrid-exponential scheme for stochastic Volterra equations
This project implements the hybrid-exponential scheme of (Rømer, ?) for simulating stochastic Volterra equations (SVE's).

[EQUATION OF SVE]

Explain SVE.

Explain basics of scheme and U-factors?

The project also contains code for approximating a given kernel function K(t) by a sum of exponential functions as in (x). 

See the folder '.../get_started' for scripts to help you get started.
 
# Example
As an example we simulate the rough Bergomi model defined by
...
where ...

Using the hybrid-exponential scheme with kappa = 1 to simulate the process V(t) we get ... showing sqrt(V(t)) in the first plot (the volatility process) and the U^j(t), j=1,...,m, factors in the plot below that.
![pic1](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/volatility.jpg)
![pic2](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/u_factors.jpg)

# Main reference:
- Rømer, S.E., Hybrid-exponential scheme for stochastic Volterra equations, ?
