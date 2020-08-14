# Hybrid-exponential scheme for stochastic Volterra equations
This project implements the hybrid-exponential scheme of (Rømer, ?) for simulating a stochastic Volterra equation (SVE) X(t) of the form

![eqn1](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/sve_def.png)

![eqn1](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/temp1.png)

The scheme works by approximating K as 

![eqn2](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/K_approx.png)

![eqn2](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/temp2.png)

![eqn3](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/temp4.png)

![eqn2](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/K_plot.jpg)

With the above, the approximation of X(t) then comes out to

![eqn4](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/X_approx.png)

![eqn4](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/temp5.png)

![eqn3](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/dU.png)

The hybrid-exponential scheme is then essentially defined by discretising the above expressions.

With the sum of exponentials approximation one obtains a running time scaling linearly in the number of time steps, instead of quadraticly as one should in general expect for the computation of a convolution. Keeping m low, as one can do using e.g. the method of (Beylkin and Monzon, 2005), the scheme will also be very efficient for practical values.
 
# Example
As an illustration we simulate the rough Bergomi model used in Finance defined by

![eqn3](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/rbergomi.png)

![eqn3](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/rbergomi_params.png).

![eqn1](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/temp3.png)

![pic1](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/volatility.jpg)
![pic2](https://github.com/sigurdroemer/hybrid_exponential_scheme/blob/readme_images/u_factors.jpg)

# Getting started
See the folder '.../get_started'.

# Reference:
- Rømer, S.E., Hybrid-exponential scheme for stochastic Volterra equations, ?
- Belykin
- Lifting heston
- Multi-factor
- BSS...
