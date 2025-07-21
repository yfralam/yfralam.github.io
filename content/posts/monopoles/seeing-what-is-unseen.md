+++
title = 'Seeing What Is Unseen'
date = 2025-05-23T21:28:43-05:00
draft = true
description = "Some comments on seeing things beyond the Lagrangian."
slug = ""
authors = ['yasin']
tags = ['physics-t']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}
## What is Seen
One of the things I have had to get used to is finding objects in a theory that one didn't write down in initially. Such things are usually non-perturbative or topological in nature. What I mean by this is the following: 
- We write a Lagrangian,
- We study the symmetries, properties, and consistencies of the theory we wrote down,
- We see that, maybe unknowingly, there is a "new" object in our theory that we didn't directly write down.

There are several examples of this but we will just consider two. 

## Magnetic Monopoles 

Lets say we want to study quantum electrodynamics (QED) on a sphere (\\(S^2\\)). We can write the Lagrangian as $$\mathcal{L} = -\frac{1}{4e^2} F_{\mu\nu}F^{\mu\nu} + \sum_{i=1}^{N_f} \bar \psi_i (i \gamma^\mu D_\mu - m)\psi_i$$ where  we see that the field content is a photon (\\(A_\mu\\)) and \\(N_f\\) fermions. For instance, if \\(N_f=1\\), one can reasonably think of this as electrodynamics with an electron (and positron). Note that the only objects we explicitly wrote down that carry charge here are the electrons/positron. There is a manifest \\(U(1)\\) symmetry which gives rise to a current 
$$j^\mu = \bar \psi \gamma^\mu \psi \implies Q_e=\int_{S^2} j^0 .$$Indeed, this is what we **mean** by *electric charge*. It is just counting the fermion number of our system (One can see this explicitly by going to the mode expansion of the fields and writing the operator in terms of creation/annihilation operators). 

But there is *something else* that is permitted in this theory. To see this, we note because the 2nd de Rham cohomology of the 2-sphere \\(H^2(S^2) \\) is non-trivial, there are closed 2 forms which are not exact:
$$dF = 0 , \quad \text{but } F \neq dA \textit{ globally}.$$
This is not the case in \\(\mathbb R^3\\) where the 2nd cohomology is trivial.

The easy way to see that we can't write a non-trivial flux globally is Stokes theorem:
$$\int_{S^2} F = \int_{\partial S^2} A = 0$$
as the 2-sphere has no boundary. Instead we can break the one form into two pieces:
- \\(F = d A_+\\) on the northern hemisphere \\(H^+\\)
- \\(F = d A_-\\) on the southern hemisphere \\(H^-\\)
- \\(A_+ - A_- = d\chi\\) at the equator \\( \Sigma = \partial H^+ = -\partial H^-\\) so we can glue the two fields together via a simple gauge transformation. Single-valuedness of the wave function requires $$\int_{S^1} d\chi = 2\pi \mathbb Z.$$ In more mathematical terms, the transition function on the equator defines a map from \\(S^1\\) to \\(U(1)\\)  (classified by \\(\pi_1(U(1)) = \mathbb Z\\) as $$e^{i\chi(\varphi)}, \quad (\chi:S^1 \to \mathbb R).$$ For the transition function to remain single valued, we again require the quantization condition above.
Now the discussion is simple. 
$$ \int_{S^2} F =  \int_{H^+} F + \int_{H^-} F = \int_{\Sigma} A_+ - \int_{\Sigma} A_- = \int_{\Sigma } d \chi = 2\pi n.$$
Let us write this out in more familiar terms: $$\frac{1}{2\pi} \int_{S^2} F = \frac{1}{2\pi} \int \vec{B} \cdot d\vec{S} = q_M.$$
We have just found that our theory admits magnetic monopoles! They are also quantized. We didn't include this in our Lagrangian; it simply followed from consistency of the theory and geometry. In fact, it would be impossible to add a "magnetic current" to the Lagrangian. The equations of motion would be $$d F = j_M$$ which is automatically disallowed as \\(F\\) is closed. In our particular case, the magnetic charge is actually a topological charge.

Nonetheless, we have a valid magnetic charge in our theory and we can add monopole charges to our system by including monopole operators. On the path integral, these are defect operators \\(\mathcal M^\dagger(x)\\)  and defined to remove a point \\(x\\) which imposes the flux condition.  Actually writing what these monopole operators are is theory dependent (even in QED3, it depends on the number of flavors) and one must be careful to have them be gauge invariant. For 1 flavor, the gauge invariant monopole operator needs to be dressed with a fermion and actually carries around electric charge 1. More details can be found in Nakahara or Carl Turner's [notes](https://arxiv.org/abs/1905.12656).



## Instantons 
## D-branes

Of course, the objects that embodies this discussion the most in my opinion, are D-branes in perturbative string theory. At first glance, a surface on which strings can end obviously breaks Lorentz invariance. GSW doesn't even spend much time discussing D-branes. It took until Polchinski showing that D-branes were dynamical to launch the second string revolution and that D-branes were important, fundamental (non-perturbative) objects to having a well defined theory.

If one wrote down the world sheet action for the string
$$S = -\frac{1}{4\pi \alpha'} \int_M d^2\sigma \sqrt{-g}\left(g^{ab} G_{\mu \nu} + i \epsilon^{ab} B_{\mu \nu}\right)\partial_a X^\mu \partial_b X^\nu+i\int_{\partial M} dX^\mu A_\mu $$ 
and considered boundary conditions of the open string, it would be easy to deduce D-branes exist as these open strings should be able to end somewhere. In hindsight, it is clear that D-branes *must* be dynamical. String theory is a theory of quantum gravity so no object, perturbative or not, should be completely static.

There are several ways one can find D-branes are necessary and non-perturbative.

T-duality presents a clear picture for why D-branes must be dynamical. Paraphrasing Polchinski, if one compactifies one direction of space and sends \\(R \to 0\\), the endpoints must land on the other directions. T-duality will then ensure that the endpoints lie on the *same* surface. The Wilson lines will relate the endpoints of the open string to the gauge field. Quanta of these modes will correspond to something geometric: oscillations of the surface. In simple terms, say the string ends on \\(X'^{25} \sim_{(\text{from T-duality})} A_{25}\\). \\(A_{25}\\)  excitations means \\(X'^{25}\\) is moving as well. By looking at the massless string states, one finds states that correspond to gauge fields living on the surface (the modes tangent to the surface) and states (perpendicular to the surface) which correspond to the shape of the surface. Therefore, this surface (the D-brane) is dynamical and has gauge fields living on it. 

One can deduce the tension of the D-branes via string amplitudes+T-duality and find that they are indeed very heavy when string theory is valid perturbatively (small \\(g_s\\)).

In the superstring, D-branes are essential to even define the (type II) theory. There are RR fields in type II theories that need taking care of and it turns out that D-branes carry charge (they are indeed BPS) and source these RR fields. 

