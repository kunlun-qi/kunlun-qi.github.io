---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---


My current research interests and expertise lie in _**developing multiscale, analytical, computational, and data-driven methods for the kinetic theory**_, mainly the Boltzmann equation and related kinetic models, arising from statistical physics, fluid dynamics, material science, biology, and so forth. Specifically,

- (I) _**Multiscale Modeling**_: Kinetic limit of many-particle dynamical complex systems, hydrodynamic limit of kinetic models, and semi-classical limit of quantum systems;
- (II) _**Theoretical Analysis for Kinetic PDE**_: Well-posedness and asymptotic behavior of Boltzmann equation and its related models via Fourier approach;
- (III) _**Numerical Simulation for Kinetic PDE**_: Fourier-Spectral method and the fast algorithm for kinetic equation with stability/convergence analysis;
- (IV) _**Data-driven and Machine-Learning-assisted Methods in Kinetic Theory**_: Data assimilation, Uncertainty Quantification (UQ) and machine-learning moments closure model.

![Big-pic](/files/Big-pic.png)

---

(I) From **multiscale modeling** perspective: 
In the classical hierarchy of fluid mechanics, the kinetic equation serves as the bridge that connects many-particle dynamical systems on the microscopic scale to the fluid system on the macroscopic level. 
![Big-pic](/files/multiscale1.png)
Recently, we mainly focus on the multiscale modeling derivation concerning: 
- Objective Molecular Dynamics (OMD), leveraging the symmetry and invariance of atomic forces and significantly reducing the computational cost compared to conventional Molecular Dynamics.
- Fluid-particle two-phase coupled system such as Vlasov-Fokker-Planck equation coupled with Navier-Stokes equations, and Boltzmann equation of (multi-species) gas mixture.
- Semi-classical limit for the Schrodinger equation and the effective dynamics of 2D material graphene. <br>
  
  > Corresponding Papers: <br>
  > [1] R. D. James, K. Qi and L. Wang, _On the kinetic description of the objective molecular dynamics_, **SIAM Multiscale Model. Simul.**, 2024. ([Link](https://arxiv.org/abs/2307.16814)). <br>
  > [2] K. Qi, L. Wang and A. B. Watson _Radiative transport in a periodic structure with band crossings_, **preprint**, 2024. ([Link](https://arxiv.org/abs/2402.06828)). <br>
  > [3] Z. Fang, K. Qi and H. Wen, _The small Deborah number limit for the fluid-particle flows I: incompressible case_, **Math. Models Methods Appl. Sci.(M3AS)**, 12(34), 2024. ([Link](https://doi.org/10.1142/S0218202524500489)). <br>
  > [4] Z. Fang, K. Qi and H. Wen, _The small Deborah number limit for the fluid-particle flows II: compressible case_, **preprint**, 2024. <br>
  > [5] Z. Fang and K. Qi, _From the Boltzmann equation for gas mixture to the two-fluid incompressible hydrodynamic system_, **preprint**, 2024. ([Link](https://arxiv.org/abs/2408.03570)).


(II) From **theoretical** perspective: 
I mainly focus on the _Measure-valued solutions_ to the Boltzmann equation and its variants (such as the inelastic collision model, homo-energetic model, etc.), including the existence, uniqueness, self-similar type asymptotic behavior and, so forth.
The heuristic motivations that push me to look for Measure-valued solutions include:
- Since the solution to the Boltzmann equation itself represents a probability distribution function in phase space, it is natural to find solutions in the probability measure space. 
- The Fourier Transform provides a powerful tool from which the Bobylev Identity ([A. Bobylev 1988](https://www.researchgate.net/publication/243771986_The_theory_of_the_nonlinear_spatially_uniform_Boltzmann_equation_for_Maxwell_molecules)) comes, and a new classification ([Y. Morimoto, S. Wang and T. Yang 2015](https://www.sciencedirect.com/science/article/pii/S0021782414001196)) on characteristic functions has been carefully constructed and studied. 
- In contrast with other perturbation frameworks, albeit with some limitations, the measure-valued solution theory  has the potential to be applied for more general initial conditions.
  
  > Corresponding Papers:<br>
  > [1] K. Qi, _On the Measure Valued Solution to the Inelastic Boltzmann Equation with Soft Potentials_, **J. Stat. Phys.**, 183, 27, 2021. ([Link](https://doi.org/10.1137/20M1351813)).<br>
  > [2] K. Qi, _Measure valued solution to the Spatially Homogeneous Boltzmann Equation with Inelastic Long-Range Interactions_, **J. Math. Phys.**, 63(2), 021503, 2022. ([Link](https://aip.scitation.org/doi/10.1063/5.0062859)).<br>
  > [3] J. W. Jang and K. Qi,  _Global existence and moment creation for the inelastic Boltzmann equation for hard potentials without angular cutoff_, **preprint**, 2023.  ([Link](https://arxiv.org/abs/2206.09636v2)).<br>
  > [4] J. W. Jang and K. Qi,  _Measure-valued solution to the inelastic Boltzmann equation for hard potentials without angular cutoff_, Proceedings of RGD32, **AIP Conf. Proc.**, 2996, 040008, 2024.  ([Link](https://pubs.aip.org/aip/acp/article-abstract/2996/1/040008/3262532/Measure-valued-solution-to-the-inelastic-Boltzmann?redirectedFrom=fulltext)).


(III) From **numerical** perspective, I mainly focus on developing an efficient and accurate numerical method for solving kinetic equations, i.e., the _Fast Fourier-Spectral Method_ ([I. Gamba, J. Haack, C. Hauck and J. Hu 2017](https://jingweihu-math.github.io/webpage/files/GHHH17.pdf)). Compared with other stochastic methods (e.g., DSMC) or deterministic methods (e.g., Discrete Velocity Models), it has the following advantages:
-Transform the high dimensional and nonlinear integral operator, the main trouble-maker in solving the Boltzmann equation, into a relatively simple weighted convolutional structure. 
- Provide significantly more accurate results with less numerical complexity O(N^6) and storage requirement O(MN^4, M<N), and utilize FFT to achieve further acceleration and reduce the computational cost to (MN^3logN, M<N). 
- Serve as a "black-box" solver to be combined with other time and spatial discretization methods to simulate the more practical complete Boltzmann equation.
![Time Evolution of Measure-valued Solution to Boltzmann equation with different collision kernels, which is simulated by our Fast Spectral Method](/files/four3.jpg)
Besides, I'm also working on rigorous proof of the _consistency and stability_ of the Fourier-Spectral Method for both cutoff and non-cutoff cases. Considering some intrinsic drawbacks of the Spectral method, which, e.g., only preserves mass conservation but fails in the momentum and energy conservation law (though still preserved up to spectral accuracy), some refined approaches are under investigation.

  > Corresponding Papers: <br>
  > [1] J. Hu and K. Qi, _A fast Fourier spectral method for the homogeneous Boltzmann equation with non-cutoff collision kernels_, **J. Comput. Phys.**, 423:109806, 2020. ([Link](https://doi.org/10.1016/j.jcp.2020.109806)). <br>
  > [2] J. Hu, K. Qi and T. Yang, _A new stability and convergence proof of the Fourier-Galerkin spectral method for the spatially homogeneous Boltzmann equation_, **SIAM J. Numer. Anal.**, 59(2), 613-633, 2021. ([Link](https://doi.org/10.1137/20M1351813)). <br>
  > [3] R. D. James, K. Qi and L. Wang, _An anisotropic rescaling velocity method for the homo-energetic Boltzmann equation_, **in preparation**, 2024.


(IV) From **data-driven** and **machine-learning-assisted** perspective: 
With the explosion of available data and the advancements of machine-learning techniques, we aim to leverage Data-driven methodologies to enhance our research in kinetic theory and related multiscale models. 
Rather than directly applying Machine-Learning tools to solve equations, we envision them providing heuristic and practical support in the modeling process, particularly in addressing the moments closure problem of kinetic-type equations.
- Generate benchmark/training data with Uncertainty Quantification (UQ). 
- Collect unmeasurable/sufficient data via Data Assimilation.
- Apply obtained data to derive the moments closure models by Machine-Learning-assisted techniques.
  
  > Corresponding Papers: <br>
  > [1] L. Liu and K. Qi, _Convergence of the Fourier-Galerkin spectral method for the Boltzmann equation with uncertainties_, **Commun. Math. Sci.**, 2024. ([Link](https://arxiv.org/abs/2212.04083)). <br>
  > [2] L. Liu and K. Qi, _Spectral convergence of a semi-discretized numerical system for the spatially homogeneous Boltzmann equation with uncertainties_, **SIAM/ASA J. Uncertain. Quantif.**, 12(3), 812-841 2024. ([Link](https://epubs.siam.org/doi/10.1137/24M1638483)). <br>
  > [3] J. Lu, K. Qi, L. Wang and J. Calder, _Recovering the data of unclosed hydrodynamics from partial observations_, **preprint**, 2024. ([Link](http://arxiv.org/abs/2409.03872)). <br>
  > [4] J. W. Jang, J. Y. Lee, L. Liu, K. Qi and Z. Zhu, _Machine-learning moments closure model for the multi-phase computations of the semiclassical limit of the Schrodinger equation_, **in preparation**, 2024. <br>
  > [5] J. Huang, L. Liu, K. Qi and J. Wan, _On the machine-learning moments closure for the linear semiconductor Boltzmann equation_, **in preparation**, 2024. 
