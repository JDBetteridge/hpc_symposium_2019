## [Efficient solvers for semi-implicit hybridised DG methods in fluid dynamics](https://jdbetteridge.github.io/hpc_symposium_2019)
#### Presented by: Jack Betteridge, Dept of Mathematical Sciences
#### Co-authors: Thomas Gibson, Ivan Graham, Lawrence Mitchell, Eike Müller

For problems in Numerical Weather Prediction (NWP), time to solution is a critical factor.
Semi-implicit time-stepping methods can speed up geophysical fluid dynamics simulations by taking larger time-steps than explicit methods.
This is possible because they treat the fast (but physically less important) waves implicitly, and the time-step size is not restricted by the CFL condition for these waves.
One disadvantage of this method is that an expensive linear solve must be performed at every time step, however, using an effective preconditioner for an iterative method significantly reduces the computational cost of this solve, making a semi-implicit scheme faster overall.

Higher-order Discontinuous Galerkin (DG) methods are known for having high arithmetic intensity making them well suited for modern HPC hardware, but are difficult to precondition due to the large number of coupled degrees of freedom.
By using a hybridised DG method we can eliminate the original coupling and instead couple the equations to a smaller global system on the trace space, which is easier to precondition.
This is achieved by considering the numerical flux variables which only lie on the facets of the mesh. We build on recent work[1] in this area by solving the resultant system using a non-nested geometric multigrid technique instead[2].

We discretise and solve the non-linear shallow water equations, an important model system in geophysical fluid dynamics, and demonstrate the effectiveness of the multigrid preconditioner for a semi-implicit IMEX time-stepper.
The method is implemented in the SLATE language, which is part of the Firedrake project.
Firedrake is a Python framework for solving finite element problems via code generation.

[1] Kang, Shinhoo and Giraldo, Francis X andBui-Thanh, Tan. IMEX HDG-DG: a coupled implicit hybridized discontinuous Galerkin (HDG) and explicit discontinuous Galerkin (DG) approach for shallow water systems arXiv preprint arXiv:1711.02751, 2017

[2] Cockburn, Bernardo and Dubois, Olivier and Gopalakrishnan, Jay and Tan, Shuguang. Multigrid for an HDG method IMA Journal of Numerical Analysis 34(4):1386–1425, 2014

**Keywords**: Numerical Weather Prediction, Efficient solvers, Hybridised DG, Firedrake, Shallow Water Equations, Code Generation
