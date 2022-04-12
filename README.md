
Notes about spin glasses, the Parisi variational formula, and CSPs

## The optimal value of a CSP is the ground state energy of a spin glass

* [dembo2017extremal](https://arxiv.org/abs/1503.03923) (extremal cuts)
* [sen2017optimization](https://arxiv.org/abs/1606.02365) Extending extremal cut paper to max $$k$$ xor, max $$q$$-cut, etc
* [Chen_2019](https://arxiv.org/abs/1707.05386) (local algorithms are suboptimal on MAX $$k$$ CUT, optimal value is related to parisi constant)
* [alaoui2020optimization](https://arxiv.org/abs/2001.00904) message passing algorithm to solve p spin glass hamiltonian (generalization of SK) -- optimal without overlap gap
* [panchenko2017ksat](https://arxiv.org/abs/1608.06256) KSAT satisfying fraction relates to a spin glass problem too.
* [alaoui2020algorithmic](https://arxiv.org/abs/2009.11481) numerics for 2 XORSAT (SK) and 3 XORSAT (3-spin glass) using [auffinger2016parisi](https://arxiv.org/abs/1606.05335) method.
* [claes2021instance](https://arxiv.org/abs/2102.12043) qaoa on mixed spin glass models...
* [on phase transitions in xorsat](https://link.springer.com/article/10.1023/A:1022886412117)

## The SK model is canonical

* [the SK model is infinite RSB](https://arxiv.org/pdf/1703.06872.pdf)
* the actual original plots getting 0.7632 for SK [Crisanti_2002](https://arxiv.org/abs/cond-mat/0111037)
* [auffinger2021sk](https://arxiv.org/abs/1703.06872) the Sk model is full symmetry breaking, so the minimizing function has infinite number of ``jumps''. Can prove it by always adding a jump near 1.
* original parisi paper on approximating SK model, good visual of symmetry breaking [link here](https://iopscience.iop.org/article/10.1088/0305-4470/13/4/009)

## We know a lot about the Parisi functional

* [Auffinger_2014](https://arxiv.org/abs/1402.5132) the parisi functional is convex so it has a unique minimum
* [Jagannath_2015](https://arxiv.org/abs/1502.04398) alternate approach to calculating parisi formula at zero temp with dynamic programming, see [talk here](https://cims.nyu.edu/~aukosh/slides/cornelltalk.pdf)
* the parisi formula is differentiable, see [this link](https://projecteuclid.org/journals/electronic-communications-in-probability/volume-13/issue-none/On-differentiability-of-the-Parisi-formula/10.1214/ECP.v13-1365.full)
* [auffinger2013properties](https://arxiv.org/abs/1303.3573) this intro is the most clear on explaining order parameters and replica symmetry breaking
* properties of the parisi functional [paper here](https://arxiv.org/abs/1501.06635)
* the proof the parisi functional for mixed spin models [paper here](https://arxiv.org/pdf/1112.4409.pdf)


## Notes on Replica symmetry breaking

If there are jumps in the function provided to the Parisi functional, we call it replica symmetry breaking at each jump point.

### What is $$k$$-RSB?

* If the minimizer to the Parisi functional is some function $$f$$ with **exactly** $$k$$ jumps, then we call it $$k$$-RSB. (For example, 1-RSB, 2-RSB, ...)
* If there are an infinite number of jumps, we call it $$\infty$$-RSB. This could be countable (in $$\mathbb{N}$$) or uncountable (in $$\mathbb{R}$$).
* If it's uncountably infinite, we call it Full-RSB.

### How does this relate to overlap gap property?

If the Parisi minimizer is $$0$$-RSB or Full-RSB, then there is no overlap gap property. Otherwise, there is overlap gap property!



More to add? Email me at kmarw@uchicago.edu.