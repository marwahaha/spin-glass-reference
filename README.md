Notes about spin glasses, the Parisi variational formula, and CSPs

# What is a spin glass?

"Spin glass" refers to a model exhibiting a weirdo "glassy" state of matter. There is no universal mathematical definition of a spin glass. Typically, the phrase refers to the physical phenomena of ground states of magnetic alloys that are "frozen" in their configuration at low temperatures.

This is typically modeled by a probability distribution on the overall state of the particles $$\sigma \in\{-1,+1\}^N$$. Each of the particles $$\sigma_i$$ are also called **sites**.

The Hamiltonian is
$$
H(\sigma) = \sum_{k=1}^\infty c_k \langle J^{(k)}, \sigma^{\otimes k} \rangle
$$
where we have fixed parameters $$c_k \in \mathbb{R}$$, and a random **disorder matrix** or **interaction matrix** $$J^{(k)}$$. This is a random symmetric Gaussian tensor of order $$k$$. (If $$J^{(k)}$$ is a random matrix of Booleans instead of Gaussians, we say this is "boolean disorder". The behavior is qualitatively the same as for "Gaussian disorder")

Physical states can be thought of as samples from the Gibbs distribution, which weighs the likelihood you are likely to see different spin configurations based on relative energies and a temperature parameter. Given a inverse temperature $$\beta$$, the probability  of a given configuration $$\sigma$$ is
$$
\Pr[\sigma] \propto e^{\beta H(\sigma)}.
$$

## Why spin glasses?

Historically: study free energy of magnetic alloys (an Ising model, where each particle has "positive" or "negative" spin i.e. a Boolean) on a lattice (because physics, $$\mathbb{Z}^2$$ or $$\mathbb{Z}^3$$). The lattice is too hard, so relax to a "mean-field model".


In the mean-field model, we can finally get a mathematical handle on the behavior of the model. And we see a lot of beautiful math describing the behavior of the system!


## What kinds of spin glasses are there?


We usually consider a spin glass with the following characteristics:
* ``mixed-spin`` or ``pure``
* ``spherical`` or ``Ising`` domain

### Mixed vs Pure
A **pure** spin glass (of level $$p$$) only has $$p$$-body interactions. By contrast, a **mixed-spin** spin glass could have interactions of any number of terms.

We sometimes think about it with the mixture polynomial $$\xi(s)$$:
$$
\xi(s) = \sum_{k=1}^\infty c_k s^k
$$

With a pure spin spin glass, $$c_k = 0$$ except when $$k = p$$.

### Spherical vs Ising

An **Ising** spin glass has the spin configurations $$\sigma \in \{+1,-1\}^N$$. Sometimes, this is too challenging, so we consider **spherical** spin glasses, where the domain of spin configurations $$\{-1,+1\}^N$$ is relaxed to the sphere of radius $$\sqrt{N}$$ in $$\mathbb{R}^N$$.

Think of the sphere as a relaxation of the hypercube. The minimizer for the Ising model is an upper bound to the minimizer for the spherical model. However, because the sphere is a connected set (whereas the hypercube is discrete), properties of spherical spin glasses may be easier to determine using (e.g.) calculus.



# Spin glass energy, PVP, RSB

SK [] used the replica method to calculate SK free energy. But it didn't work at low temperature! Parisi extended it using a process called replica symmetry breaking.

What is replica symmetry breaking? It's the precise structure of overlap matrix .... @Juspreet

In general, we can calculate the minimum ground state energy density to a spin glass using the Parisi variational principle. We call $$P(f)$$ the *Parisi functional*:
$$
GSDE = min_{f} P(f)
$$

If there are jumps in the minimizing function, we call it **replica symmetry breaking**.

If there are *exactly* $$k$$ jumps, then we call it $$k$$-RSB. (For example, 1-RSB, 2-RSB, ...)

* If there are an infinite number of jumps, we call it $$\infty$$-RSB. This could be countable (in $$\mathbb{N}$$) or uncountable (in $$\mathbb{R}$$).
* If it's uncountably infinite, we call it Full-RSB or fRSB.

## How does this relate to OGP (overlap gap property)?

What is an OGP? (see here for a reference [])

This means that there is a continuous, compact subinterval of the Parisi measure that is not supported. We typically think about OGP at low temperature.

**The key takeaway:** If the Parisi minimizer is $$0$$-RSB or fRSB, then there is no overlap gap property. Otherwise, there is overlap gap property!

## TAP equations
@Juspreet

# Dense vs Sparse: escaping the mean field

Recall that the physicists' dream is to study Ising models on sparse, "physical" graphs, such as the lattice $$\mathbb{Z}^3$$. Sometimes, we can "pull back" properties of "dense" spin glasses to "sparse" models.

Mean-field models are **dense**, where all things are connected to all things. **Sparse** models have $$o(N)$$ average degree. Usually we study just degree $$O(1)$$, because this captures lattices in $$\mathbb{R}^3$$. And it's easier to study than intermediate regimes between $$O(1)$$ and $$\Omega(n)$$.

An intermediate setting between dense models and $$\mathbb{Z}^3$$ uses a random, sparse interaction matrix, known as a **diluted mean-field model**.

 * The interactions may be along a random $$d$$-regular graph
 * or random Erdos-Renyi graph with average degree $$d$$.

Still, the interactions are "not physical". For example, it's well known that **sparse random graphs are expanders**, and almost all small neighborhoods are trees. $$\mathbb{Z}^3$$, on the other hand, is not that similar to random graphs.


## Random CSPs are connected to spin glasses!

Random CSPs are "sparse" models. However, some of the properties of "dense" spin glasses do actually appear if you look closely and in the right places.

* [dembo2017extremal](https://arxiv.org/abs/1503.03923) (max cut)
* [sen2017optimization](https://arxiv.org/abs/1606.02365) Extending extremal cut paper to max-$$k-$$xor, max $$q$$-cut, etc
* [Chen_2019](https://arxiv.org/abs/1707.05386) (local algorithms are suboptimal on MAX-$$k$$-CUT, optimal value is related to parisi constant) [Chris asks: what is this paper?]
* [panchenko2017ksat](https://arxiv.org/abs/1608.06256) KSAT satisfying fraction relates to a spin glass problem too.
* [alaoui2020algorithmic](https://arxiv.org/abs/2009.11481) numerics for 2 XORSAT (SK) and 3 XORSAT (3-spin glass) using [auffinger2016parisi](https://arxiv.org/abs/1606.05335) method.
* [claes2021instance](https://arxiv.org/abs/2102.12043) qaoa on mixed spin glass models...
* [on phase transitions in xorsat](https://link.springer.com/article/10.1023/A:1022886412117)
* gives upper bounds, assuming random sparse CSP, if it was any kRSB [HERE IT IS](https://arxiv.org/abs/math/0405357)

# What we know about spherical models

* Pure Spherical $$p$$-spin glass is 2-RSB at $$\beta = \infty$$ [[AZ18]](https://arxiv.org/pdf/1802.02991.pdf).
* The analytic behavior of the mixture polynomial determines when the mixed spherical $$p$$-spin glass is fRSB [[Proposition-1, Sub21]](https://arxiv.org/abs/1812.04588).
* The TAP equations for mixed spherical $$p$$-spin glasses are to be solved on the _ball_ $$\mathcal{B}^n$$ (and not the sphere) [[Sub21a]](https://arxiv.org/abs/2111.07132),[[Sub21b]](https://arxiv.org/abs/2111.07134).
* The Free-Energy "landscape" of Spherical $$p$$-spin glasses (mixed and pure) is well understood by studying the first two moments of the number of critical points of the Hessian using the Kaz-Rice formula as a dictionary between the geometry of the problem at hand and the random matrix (the Hessian) [[Sub16]](https://arxiv.org/abs/1804.10576).
* An explicit and analytic expression for the free energy is given using a nice simplification of the _Crisanti-Sommers_ representation known as the Chen-Sen representation [[CS17]](https://arxiv.org/abs/1512.08492). In the event of fRSB, this formula simply becomes an integral over (roughly) the mixture polynomial [[Proposition-2, Sub21]](https://arxiv.org/pdf/1812.04588.pdf).


# What we know about Ising models


### Example: The SK Model
This is the canonical spin glass people study; i.e. the pure model at $$p=2$$.

At high temperature (when $$\beta < \beta_c$$), we know the SK Model is $$RS$$ (or 0-RSB) [[Bol18]](https://arxiv.org/abs/1809.07972). There exists an efficient algorithm to output solutions to the free energy. this is done by solving the TAP equations iteratively by Bolthausen [[Bol12]](https://arxiv.org/pdf/1201.2891.pdf).

At low temperature (when $$\beta > \beta_c$$), the SK Model is $$\infty$$-RSB [[ACZ20]](https://arxiv.org/abs/1703.06872). There exists an efficient algorithm to output solutions to the free energy. Assuming fRSB, this is done by an AMP algorithm that discretizes the dynamics of the Auffinger-Chen Principle rewrite of the Parisi-Variational Principle. This algorithm is due to Montanari [[Mon19]](https://arxiv.org/abs/1812.10897).

Some other cool papers:
* [Crisanti 2002](https://arxiv.org/abs/cond-mat/0111037) shows the actual original plots getting 0.7632 for SK.
* [Here is the original Parisi paper](https://iopscience.iop.org/article/10.1088/0305-4470/13/4/009) approximating the SK model; it's a good visual of symmetry breaking.

### Mixed even-spin models
Some results for SK generalize to mixed-spin models, especially if they are *even* (i.e. $$c_k = 0$$ when $$k$$ is odd.

* For pure models when $$k \ge 4$$ even, there is a coupled-OGP: [[CGPR19]](https://arxiv.org/abs/1707.05386)
* For mixed-spin models of even spin, the number of configurations at each energy level is known: [[CHL17]](https://arxiv.org/abs/1609.04368)


### In general

We also know several things about the Parisi functional for Ising spin glasses:

* It is strictly convex, so it has a unique minimum: [Auffinger_2014](https://arxiv.org/abs/1402.5132)
* It is differentiable, see [this link](https://projecteuclid.org/journals/electronic-communications-in-probability/volume-13/issue-none/On-differentiability-of-the-Parisi-formula/10.1214/ECP.v13-1365.full)
* [auffinger2013properties](https://arxiv.org/abs/1303.3573) this intro is the most clear on explaining order parameters and replica symmetry breaking
* the proof the parisi functional for mixed spin models [paper here](https://arxiv.org/pdf/1112.4409.pdf)
* properties of the parisi functional [paper here](https://arxiv.org/abs/1501.06635)
* [Jagannath_2015](https://arxiv.org/abs/1502.04398) alternate approach to calculating parisi formula at zero temp with dynamic programming, see [talk here](https://cims.nyu.edu/~aukosh/slides/cornelltalk.pdf)



A rewrite of the Parisi-Variational Principle in terms of a _functional_ min-max principle is provided by the Auffinger-Chen Principle [[AC17]](https://arxiv.org/pdf/1402.5132.pdf). The AC Principle gives a rewrite of the PVP in terms of an auxiliary stochastic process (a drifted Brownian motion) that does a random walk in the cavity field component of the initial free-entropy term ($$\Phi(1, x)$$).


# Algorithms


## Lower bounds from Overlap Gap Property (OGP)

## Algorithms exploiting fRSB

* [elalaoui2020optimization](https://arxiv.org/abs/2001.00904) message passing algorithm to solve p spin glass hamiltonian (generalization of SK) -- optimal without overlap gap

## Perceptron model

Not a spin glass.

More to add? Email me at [kmarw@uchicago.edu](mailto:kmarw@uchicago.edu).
