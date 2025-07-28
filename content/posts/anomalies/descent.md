+++
title = 'A useful thing from 6d'
date = 2025-07-27T18:04:24-05:00
draft = false
description = "A short note on anomaly descent."
slug = ""
authors = ['yasin']
tags = ['physics-t']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}



This is a continuation of  [Some phenomenology of anomalies](https://yfralam.github.io/posts/anomalies/pheno/).  In this note, we discuss how anomalies in \\(d\\) dimensions really live in \\(d+2\\) dimensions.

Again, this is largely based off of [Vadim's notes](https://web2.ph.utexas.edu/~vadim/Classes/2024f-qft/adf.pdf) and Nakahara. The section on math can be entirely skipped.

In the previous post we found anomalies typically took the form $$ \partial \cdot J \sim -\frac{1}{16\pi^2} \text{Tr}~ (\epsilon^{\mu\nu\rho\sigma} F_{\mu\nu}F_{\rho\sigma})~ ,$$ where the \\(\sim\\) denotes up to some number, say the number of massless fermions. These types of anomalies exist in all even dimensions \\(d=2n\\) and in general, we can write, with [differential forms](https://en.wikipedia.org/wiki/Differential_form), $$ d* J = -\frac{(-1)^n 2 N_f}{(2\pi)^n n!} Q_{(2n)}~ . $$
Here, \\(Q_{(2n)}\\) is a \\(2n\\) form consisting of \\(n\\) 2 forms \\(\mathcal F\\) $$Q_{(2n)} := \text{Tr}~ (\mathcal F \wedge \mathcal F \wedge \mathcal F \cdots \wedge \mathcal F)~.$$ A few mathematical facts:
- \\(Q_{(2n)}\\) is closed. \\( dQ_{(2n)} = 0\\). 
- Acting on \\(Q_{(2n)}\\) with \\(d\\) acts with the covariant derivative \\(D\\) inside the trace.
- Poincare Lemma: On topologically trivial manifolds, closed forms are exact. i.e. $$ d A_p =0 \implies A_p = d B_{p-1} ~.$$
Note that while the equation relating the divergence of the anomalous current to \\(Q_{2n}\\) is only true in \\(d\\) dimensions, you can't stop me from using \\(Q_{2n}\\) in whatever dimension I want. They are perfectly well defined.

## Restatement of the anomaly

In the previous post, we found the non-abelian anomaly with chiral fermions to be 

$$ D \cdot J^a = \frac{-g^2\mathcal Z^{abc}}{16\pi^2} \epsilon^{\mu\nu\alpha\beta} \partial_\mu \left(A_\nu^b\partial_\alpha A_\beta^c - \frac{g}{4}f^{cde}A_\nu^bA_\alpha^d A_\beta^e\right)$$ which we got by expanding \\(\epsilon FF\\) and \\(\mathcal Z^{abc}\\) contains the chiral traces. In differential form notation, this is 

$$ D * J^a = \frac{-\mathcal Z^{abc}}{32\pi^2} d \left(\mathcal A^b \wedge (d\mathcal A + \frac{i}{2} \mathcal A \wedge \mathcal A)^c\right) ~.$$

One should remember what we are doing when computing the current and making sure it's divergence is 0. Under some symmetry transformation, say 

$$U(x) = 1 + i \Lambda(x)~,$$

where the gauge fields change as $$\delta \mathcal A = -D \Lambda~,\quad \delta\mathcal F = -i \mathcal F \Lambda + i \Lambda \mathcal F~,$$ The actions varies \\(S \mapsto S + \delta S(\Lambda)\\) where for us, 

$$\delta S(\Lambda) =  \frac{-\mathcal 1}{32\pi^2} \int_{M_4} \text{Tr}_\chi  \Lambda~ d \left(\mathcal A\wedge (d\mathcal A + \frac{i}{2} \mathcal A \wedge \mathcal A)^c\right) ~. $$
Note that we have swept up the chiral traces \\(\mathcal Z^{abc} \\) into the trace of the gauge fields. 

Now we have everything we need to continue.

## The form of the argument

Minkowski/Euclidean space are topologically trivial. **Anomaly descent is essentially an abuse of Poincare lemma.** Even on nontrivial topologies, the lemma is still valid *locally*, though some more care is needed in the following arguments.

- \\( Q_{(2n)}\\) is closed $$dQ_{(2n)} = 0~,$$ so let us define $$ Q_{(2n)} = d \Omega_{(2n-1)}~. $$ \\(\Omega_{2n-1}\\) are the *Chern-Simons forms*. They are traces over polynomials of \\(\mathcal F\\) and \\(\mathcal A\\).
- \\(Q_{(2n)}\\) are gauge invariant \\( \mathcal F \mapsto U \mathcal F U^{-1}\\), as one can easily see from using cyclicity of the trace.
- \\(\Omega_{2n-1}\\ are not gauge invariant, but \\(d\Omega_{2n-1}\\) *must* be by definition. So if I gauge transform the Chern-Simons form, the difference with the non-gauge transformed form better be 0. $$ d(\Omega_{(2n-1)}' - \Omega_{(2n-1)} ) =0$$
- Again, we use Poincare lemma. The difference of the Chern-Simons forms is closed so $$\Omega_{(2n-1)}' - \Omega_{(2n-1)} = -d H_{(2n-2)}~.$$
- \\(H_{(2n-2)}\\) should depend on \\(\Lambda\\) and be a \\(2n-2\\) form. In general, they take the form of $$H_{(2n-2)} = \text{Tr}(\Lambda~ dK_{2n-3})~.$$


It actually does not take too much work to show this. Consider \\(Q_{(2)}\\). \\(\Omega_{(1)} = \text{Tr}~ \mathcal A\\). Then  $$\Omega_{(1)}' - \Omega_{(1)} = \text{Tr}~ \mathcal A' - \text{Tr}~ \mathcal A = \text{Tr}~ (- D \Lambda) = -d\text{Tr}~ (\Lambda)~ = -d H_{0}~.$$
One can continue playing the same game. For \\(n=2\\), 

$$\Omega_{(3)} = \text{Tr } (\mathcal A \wedge \mathcal F - \frac{i}{3} \mathcal A \wedge \mathcal A \wedge \mathcal A), \quad \text{and} \quad H_{(2)} = \text{Tr }(\Lambda ~ d \mathcal A)$$ and for  \\(n=3\\) (this time dropping the wedges)

$$\Omega_{(5)} = \text{Tr } (\mathcal A \mathcal F^2 - \frac{i}{2} \mathcal A^3 \mathcal F - \frac{1}{10} \mathcal A^5), \quad \text{and} \quad H_{(4)} = \text{Tr }(\Lambda ~ d( \mathcal A d\mathcal A + \frac{i}{2} \mathcal A^3))~.$$

\\(H_{4}\\) should look very familiar. It is in fact (almost) the same shift of the Euclidean action $$\delta S(\Lambda) = (number) \times \int_{M_4} H_{(4)}~.$$ This is true for any (even) dimension. Start from a \\(Q_{(2n=d+2)}\\) form, then find the \\(\Omega_{2n-1}\\) Chern-Simons form, then construct the \\(H_{(2n-2=d)}\\) which is the anomaly in \\(d\\) dimension! We see that it is almost entirely specified by the anomaly polynomial in 2 higher dimensions.

## Some details on the trace

The trace in our original anomaly (going over the chiral fermions) and the trace in \\(H_{(2n-2)}\\) aren't exactly the same. Nonetheless, we could have defined a new \\(2n\\) form with chiral traces (the so called *anomaly polynomial*) 

$$\hat Q_{(2n)} := \text{Tr}_\chi (\mathcal F \wedge \cdots \wedge \mathcal F) = \mathcal F^{a_1} \wedge \mathcal F^{a_2}  \cdots \wedge \mathcal F^{a_n} \times (\text{Tr}_L(t^{a_1} \cdots t^{a_n}) - \text{Tr}_R(t^{a_1} \cdots t^{a_n}))$$

and the argument would not have changed from before. 

The coefficients \\(\mathcal Z^{a_1 a_2 a_3 \cdots a_4}\\) from before which are built out of symmetrization of the chiral traces are essentially related to the Casimirs of degree \\(n = d/2+1\\), \\(R_n(m)\\). 

In \\(d=4\\), we need the cubic Casimirs, which some groups do not have. In \\(d=2\\), we need quadratic casimirs which all groups do have, so getting automatic anomaly cancellation is not in the cards. In \\(d=6\\), there are 2 independent quartic invariants so anomaly cancellation is much harder. The situation in \\(d=10\\) is even worse.

The current plan is to present the index point of view. Then Green-Schwarz and anomaly inflow next before diving into the modern description of anomalies: Dai-Freed.

## Math and Subtleties
In addition to Nakahara, we also have [Bilal's notes](https://arxiv.org/abs/0802.0634).

### Why \\(\Omega_{2n-1}\\)?

\\(Q_{(2n)}\\) is **a** *characteristic class*: a local form of the closed manifold constructed from the curvature or field strength such that the integral over the manifold \\(\int_M Q\\) contains on topological data. In technical terms, characteristic classes measure the non-triviality of a bundle. It is in particular, an invariant polynomial (invariant under gauge transformations).

By the Chern-Weil theorem, \\(Q\\) is closed, but need not be globally exact. Though the difference between two invariant polynomials as exact \\(Q' - Q = d R\\). It can easily be seen that the integrals over two different invariant polynomials contain the same data $$\int_M Q' - \int_M Q = \int_M dR = \int_{\partial M} R = 0~,$$ via Stokes. 

We demand the integral of \\(Q\\) is invariant under deformations of \\(\mathcal A\\). If one defines an interpolating gauge field $$\mathcal A_t = \mathcal A_0 + t(\mathcal A_1- \mathcal A_0) \quad , \quad \mathcal F_t = d \mathcal A_t + \mathcal A_t^2~,$$ between two different connections, it can be shown (from taking the \\(\partial_t\\) derivative and Bianchi) that 

$$R_{(2n-1)} = n \int_0^1 dt \text{Tr}~ (\mathcal A_1- \mathcal A_0) \mathcal F_t^{n-1} $$ where \\(R\\) is the so called transgression. Then

$$Q_{(2n)}(\mathcal F_1) = Q_{(2n)}(\mathcal F_0) + d \left(n \int_0^1 dt \text{Tr } (\mathcal A_1- \mathcal A_0) \mathcal F_t^{n-1} \right)~.$$


*Locally*, \\(Q = d \Omega\\) and we can take \\(\mathcal A_0=0\\)

$$Q_{(2n)}(\mathcal F_1) = d \left(n \int_0^1 dt \text{Tr}~ \mathcal A_1 \mathcal F_1^{n-1} \right)$$
and so we have found that the transgression is nothing but the Chern-Simons form 

$$ \Omega_{(2n-1)} = n \int_0^1 dt \text{Tr}~ \mathcal A \mathcal F^{n-1} = n \int_0^1 dt \text{Tr}~ \mathcal A_1 (t d \mathcal A + t^2 \mathcal A^2)^{n-1}~. $$

Note the definition gives us the Chern-Simons form up to adding an exact form.
As an example, let us compute \\(\Omega_{(3)}\\).
$$ \Omega_{(3)} = 2 \int_0^1 dt \text{Tr}~ \mathcal A (t d \mathcal A + t^2 \mathcal A^2) = \text{Tr}~ \mathcal A (d \mathcal A + \frac{2}{3} \mathcal A^2) = \text{Tr}~ \mathcal A d \mathcal F + \frac{i}{3} \mathcal A^3.$$
### Why \\(H_{2n-2}\\)?

Locally we saw the infinitesimal gauge variation of the Chern-Simons form gave 

$$\delta \Omega_{(2n-1)} = -dH_{(2n-2)}~.$$
For a finite gauge transformation, it can be shown 

$$ \Omega_{(2n-1)} (\mathcal A',\mathcal F') - \Omega_{(2n-1)} (\mathcal A,\mathcal F) = \Omega_{(2n-1)} ((dU)U^{-1},0) + d(\cdots)~.$$ Physically  

$$\int_{S^{2n-1}} \Omega_{(2n-1)} ((dU)U^{-1},0) = \int_{S^{2n-1}} \text{Tr } ((dU)U^{-1})^{2n-1} $$computes the number of times \\(U: S^{2n-1} \to G\\)  maps the sphere to the topological sphere in G, i.e. computes the homotopy class \\(\pi_{2n-1}(G)\\). For good Lie groups, the 3rd homotopy class is \\(\mathbb Z\\), though for infinitesimal gauge transformations, it is always trivial.

In general, it can be shown that 

$$H_{(2n-2)}(\Lambda, \mathcal A, \mathcal F) = n(n-1) \int_0^1 dt (1-t) \text{Tr } \Lambda d(\mathcal A \mathcal F_t^{n-2})~,$$
though algebraically, for any gauge transformation (not just infinitesimal)

$$\Omega_{(2n-1)} (\mathcal A + \Lambda,\mathcal F') - \Omega_{(2n-1)} (\mathcal A,\mathcal F) = H_{(2n-2)}(\Lambda, \mathcal A, \mathcal F)~.$$