+++
title = 'The area operator is not a unitary'
date = 2026-02-26T13:26:59-06:00
draft = false
description = "For some reason people try to represent the area operator as a unitary on the Hilbert space. This is just not correct. People also try to do say things about subregions without actually constructing well defined subregions."
slug = ""
authors = ['yasin']
tags = ['physics-t']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}

## The area operator

The area of a bifurcation surface is an important observable. Bifurcation surfaces are extremal surfaces so if we slightly deform the surface, to leading order, the area does not change. In holography, RT surfaces are extremal surfaces. Indeed, the area of a black hole is something all observers can agree on. I can point my telescope into the sky and just look at a black hole to figure out what the area is (or so I am told by my GR friends). 

In a quantum theory, the area should be an operator \\( \hat A\\). This operator is not the same as other operators in QFT or QM, it acts geometrically on the spacetime itself by kinking an initial data surface, i.e. the extrinsic curvature has a delta function. A simple example is given by Witten [here](https://groups.oist.jp/sites/default/files/imce/u139004/WittenLecture.pdf) [^1] where he just considers a simple black hole or even flat space. If we just look at flat space in null coordinates \\( (U,V,\theta,\phi)\\), there is a simple action of the area operator: 

$$U \to U' = \Theta(U) U + \Theta(-U) e^t U ~,\quad  V \to V' = \Theta(-V) V + \Theta(V) e^{-t} V,$$
where the bifurcation surface is at \\(U=V=0\\). 

In affine coordinates, it is easy to identify this as a half sided boost. If we look at the \\(V=0\\) hypersurface \\((U,\theta,\phi)\\), this boosts everything on one side of the bifurcation surface and leaves the other side alone.  One can use this canonical action to *define* an infinitesimal action of the area operator on the fields 

$$ \phi(U) \to [\hat A, \phi(U)]=\Theta(-U)\partial_U\phi(U).$$
It is important to check that this is consistent as an action on phase space which is well defined under quantization. One can generate the full half sided boosts by exponentiating 

$$ e^{-i t \hat A}. $$
## is not a good operator

However, this is not a good operator on the Hilbert space. This is not a surprising fact. It has been known that half sided boosts have poor behavior near the bifurcation surface, there is a huge UV divergence due to the action of the operator turning on suddenly at the bifurcation surface (also noted in Witten's talk above). In other words, 

$$ || \hat A |\phi \rangle||^2 \to \infty$$ and the area operator kicks you out of the Hilbert space. 

At this point, one may ask "so what?" Sometimes the momentum operator can blow up in regular quantum mechanics. This is indeed true, but there exists vectors in the Hilbert space on which the definition of the momentum is fine. **The main point here is that, there is *no* state on which the area operator acts well.** 

Because every state looks like the vacuum at short distances, this argument extends to not only every state, but also other geometries with bifurcation surfaces (AdS-Schwarzschild, Schwarzschild, Rindler, dS static patch, etc).

This popped up in my work with Gautam and Sarah several times. We actually calculated this in several ways but in momentum space, at large energies, the integrand of the inner product scales as a polynomial in \\(\omega\\), the energy, so at large energies it blows up. 

## Gaps in the literature

For some reason, despite the fact that the above should be well knows, in several places in the literature (particularly gravitational algebras) people still try to write down a half sided boost unitary 

$$ U =^? e^{-i t \hat A}.$$But as we saw before, this object makes no sense. I can't exponentiate infinity and magically hope to have it make sense. Notably this happens in in [Chandrasekaren's recent paper](https://arxiv.org/abs/2601.07915) where he tries to use a unitary that isn't actually a unitary [^2] very early on. 

Another place where this happens is on a paper by Bousso and friends where they claim the area operator is holographically dual to Connes cocycle. This statement also makes absolutely no sense. As we saw before, the area operator is not a good operator, but Connes cocycle has *by definition* a good action on the Hilbert space. There is no way these two things can be dual.

As Witten and some other have pointed out, a possible candidate is the operator 

$$ \hat A - h_R $$ where \\(h_R\\) is the formal half sided modular Hamiltonian. This thing has a chance to be well defined. In physical terms, the area boosts the geometric data (the coordinates/background) and the modular Hamiltonian compensates for the fields themselves. This is the operator that shows up in well defined gravitational algebras stories.

In my paper with Gautham and Sarah, we use a variation of this which is well defined to define algebras for well-defined subregions. Indeed, we check the operators we define are actually good operators on the Hilbert space. 

While I won't go into a rant on subregions here, there has been an open problem for defining algebras in subregions within the community and it seems like most people are saying things that are already known or are arguing things that are poorly defined. For example, in a paper with Antony Speranza and Tom Faulkner, they gauge boosts around an arbitrary point of a null hypersurface, but this doesn't even give me a well defined notion of a subregion. An arbitrary point is not an extremal surface so if I deform it, the area of such a cut will not generally remain invariant. This is also an issue in the original Jensen, Sorce, Speranza paper, while much of their construction is correct, many of the things they say about subregions do not hold and in fact, are sometimes not even well defined subregions.




[^1]: Also see Witten's OIST talk here: https://groups.oist.jp/exu-oist/recorded-talks

[^2]: Gautam pointed this out to him and after several exchanges was ghosted.
