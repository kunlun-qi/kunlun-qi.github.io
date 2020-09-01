---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

### My research interest lies in _Kinetic Partial Differential Equations_, mainly the _Boltzmann equation and its related models_, in the theoretical and numerical fields. Specifically speaking:
---

(i). In the _**theoretical**_ sense, I mainly focus on the _Measure-valued Solutions_ to the Boltzmann equation and its variants (such as the inelastic collision model, uniform shear flow, etc.), including the existence, uniqueness, self-similar type asymptotic behavior and so forth.
The heuristic motivations that push me to find out the Measure-valued Solution consist of the following points:
> - Since the solution to Boltzmann equation itself represents a density function describing the velocity and position distribution of rarefied gas of particles, it is then pretty natural to find solutions from the probability measure space. <br>
> - The Fourier Transform provides a powerful tool from which the Bobylev Identity ([A. Bobylev 1988](https://www.researchgate.net/publication/243771986_The_theory_of_the_nonlinear_spatially_uniform_Boltzmann_equation_for_Maxwell_molecules)) comes, and a new classification ([Y. Morimoto, S. Wang and T. Yang 2015](https://www.sciencedirect.com/science/article/pii/S0021782414001196)) on characteristic functions has been carefully constructed and studied, which also brings lots of conveniences. <br>
> - In contrast with other Perturbation framework or Theories in the small, albeit some limitations, the Measure-valued Solution theory seems to be applied for more general initial datum as long as a probability measure. <br>
> - The possibly intrinsic relationship with the following numerical spectral method also attracts my attention...

(ii). In the _**numerical**_ sense, I mainly focus on developing an efficient and accurate numerical method in simulating the kinetic equation, which I mean the _Fast Spectral Method_ ([I. Gamba, J. Haack, C. Hauck and J. Hu 2017](https://jingweihu-math.github.io/webpage/files/GHHH17.pdf)) for Boltzmann equation and its related variants. Comparing with other stochastic methods (like DSMC) or deterministic methods (like Discrete Velocity Models), the Fast Spectral Method has the followings advantages:
> - It is able to transform the high dimensional and nonlinear integral operator, which is regarded as the main trouble-maker of the numerical simulation in Boltzmann equation, into a relatively simple weighted convolutional structure. <br>
> - It provides significantly more accurate results with less numerical complexity O(N^6) and storage requirement O(MN^4, M<N), and the fast acceleration can further reduce the computational cost to (MN^3logN, M<N) with the help of FFT. <br>
> - Its spatially homogeneous form can serve as a "black-box" solver in the velocity domain to be combined with other time and spatial discretization method to simulate the more practical complete Boltzmann equation, even with more complex geometric property. 

The following figure describes "Time Evolution of a Measure-valued Solution to Boltzmann equation with different collision kernels", which is simulated by our Fast Spectral Method:
![Time Evolution of Measure-valued Solution to Boltzmann equation with different collision kernels, which is simulated by our Fast Spectral Method](/files/four3.jpg )

Besides I'm also working in the study of the _consistency and stability property_ of Fast Spectral Method including the cutoff case and non-cutoff case. As there are some drawbacks in the Spectral method, which, for instance, merely preserves mass conservation but fails in the momentum and energy conservation law (though still preserve up to spectral accuracy), I would also expect to further improve the method and make it more practically applicable.
