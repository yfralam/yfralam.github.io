+++
title = 'Doing actual string theory in AdS/CFT'
date = 2024-12-21T15:24:48-06:00
draft = false
description = "A rundown on how the RR fluxes in AdS5 make doing actual string theory difficult."
slug = ""
authors = ['yasin']
tags = ['physics-t']
categories = []
externalLink = ""
series = []
enableComments = true
+++

{{< katex >}}

## Not a lot of string theory in AdS/CFT

In the most well understood version of AdS/CFT, we stack N D3-branes and then see that the near horizon geometry is \\(AdS_5 \times S^5\\). Usually though, we don't do string theory on this geometry because to support the spacetime, we need the RR fields (\\(p\\)-branes naturally couple to \\(p+1\\) forms). Instead, we go to the SUGRA picture where we can just deal with the fields, and in some cases, can just do the classical gravity calculation. 

But this isn't technically string theory. Actual string theory on curved backgrounds is still woefully understood (barring one set of systems). It was bothersome to me that I didn't know exactly how the RR fields make computations difficult (most papers just say they are), so I took it upon myself to go through the literature and find out.

After some review of strings on curved spacetimes, we primarily follow [Berenstein and Leigh](https://arxiv.org/abs/hep-th/9904104) and [Polyakov](https://arxiv.org/abs/hep-th/9812044). By no means is this meant to be exhaustive, but it should at least tell you what to look for.

## Strings on a curved background
Before continuing, it is worth reviewing how strings look on curved backgrounds. We'll just follow Polchinski. The natural thing to do on the worldsheet, is just promote the flat metric to a curved metric \\(\eta \to G\\), such that the worldsheet action is 
$$S_\sigma = \frac{1}{4\pi \alpha'}\int_M d^2 \sigma \sqrt{g} g^{ab} G_{\mu\nu}(X) \partial_aX^\mu \partial_bX^\nu ,$$
where due to the metric dependence on \\(X\\), the action this that if a non-linear sigma model. But because the curved background should be a state of string theory, this change doesn't seem stringy enough. 

To justify this, we write \\(G = \eta + \chi (X)\\) and place in into the path integral. Then the integrand is just $$e^{-S_p} \left(1 - \frac{1}{4\pi \alpha'}\int_M d^2 \sigma \sqrt{g} g^{ab} \chi_{\mu\nu}(X) \partial_aX^\mu \partial_bX^\nu + \dots\right) ,$$ where \\(S_p\\) is just the free Polyakov action and the \\(\dots\\) are higher order terms. But the second term in parenthesis is indeed just the graviton vertex operator. In all, the integrand will look like $$e^{-S_p}(1 + VO + \frac12 VO^2 + \frac16 VO^3 + \dots) = e^{-S_p}e^{VO}  .$$ 

So we see that the sigma model, an interacting 2d CFT, is just the same working with the free CFT and including the exponentiated vertex operators into the path integral. Equivalently, if I want to compute an amplitude, I can still use the free propagators, I just need to include the exponentiated VOs in the correlator.

This is hard. I can try to do things order by order, but a naive approach is difficult as I would need to compute an infinite number of correlators with the VOs, and the wick contractions get more or more complicated. Still, there is hope, but we'll find the RR fields will dash it.


## Why RR fields are difficult

Remember (from Polchinski v2) that the Ramond VOs generally look like $$\mathscr{V} = e^{-\phi/2} \Theta(z)$$ where \\(\phi(z)\\) are free fields that appear in the bosonization of NSR superconformal \\(\beta,\gamma\\) ghosts and \\(\Theta\\) is a spin field. Note that a difficulty with spin fields is they have branch cuts at operators. VOs are generally labeled by their \\(\phi\\) (and \\(\tilde{\phi}\\) ) charges. The R VO above has charge \\((-1/2,0)\\), or is in the \\((-1/2,0)\\) picture. In general, we say an operator is in the \\((q,\tilde{q})\\) *picture*. 

Our earlier prescription would have us stick these spin fields into the worldsheet lagrangian which leads to unclear formulas at the very least. Worse, it **destroys the superconformal invariance of the worldsheet** that is the main motive behind the NSR formalism. Instead, we can try to include them into the amplitudes as VOs.

Also note we will be needing *picture changing operators* (PCOs) to insert into the amplitudes as to prevent anomalies, the amplitude vanishing, or diverging. In general, the total number of PCOs should be, on a surface of genus \\(g\\), $$n_X=2g-2 + n_B + n_F/2,$$
where \\(n_B,n_F\\) are the number of bosonic and fermionic operators respectively. Remember that on the curved background, we need to exponentiate these VOs, which means we need to include a different number of PCOs at *all levels*. In addition, to compute amplitudes to arbitrarily high genus, we have to integrate the VOs and the PCOs over Super Riemann surfaces, which is not an easy task (remember the **RR VOs get branch cuts when they hit another operator**). There are some tricks one can play and a good resource is Witten's [perturbative superstring theory revisited](https://arxiv.org/abs/1209.5461).

## The need for the RR fields

If we stack \\(N\\) D3-branes, we automatically have contributions to the RR sector to the 4 form potential \\(C_4\\) with total unit flux \\(N\\) as \\(N = \int_{S^5} F_5 \\). This calculation was done by Polchinski by computing tadpoles of the graviton and RR 4-form potential with branes. By the same calculation, by scattering gravitons off of the D-brane, we find the metric to be

$$g_{\mu \nu}(X) = \tilde{G}(X)(\delta_{\mu\nu}^\perp - \delta_{\mu\nu}^{||}),$$
where \\(\tilde{G}(X) = \frac{R^4}{2r^4}\\), and \\(R\\) is the AdS radius. Note the manifest \\(SO(1,3) \times SO(6)\\) symmetry.

In the (-1/2,-1/2) picture, the RR vertex operator (for the 5 form) takes the form 

$$\mathscr{V}_{RR} = e^{-\phi/2} e^{-\tilde{\phi}/2} \Sigma^\alpha \bar{\Sigma}^\beta  \Gamma^{\mu_1\dots \mu_5}\_{\alpha\beta} F\_{\mu_1\dots \mu_5}$$ where the \\(\Sigma\\)'s are spin fields. Note that 

$$\Gamma^{\mu_1\dots \mu_5}\_{\alpha\beta} F\_{\mu_1\dots \mu_5} = \Gamma_{||}\Gamma^\alpha \partial_\alpha G(X).$$

Because the RR fields are directly supporting the \\(AdS_5 \times S^5\\) geometry, we have no choice but to include them. Another way to see this is to just write down the stress energy solution in the GS formalism, then translate over to NSR. It is given by 

$$T_{zzNSR} = \frac12 \partial X^m \partial X_m + \frac12 : (\Gamma + \Gamma\Gamma) \psi^m \partial \psi_m: + \epsilon^{p_1\dots p_4} [e^\phi \psi_{p_1}\psi_{p_2}\psi_{p_3}\psi_{p_4}\psi_{p_t}\partial y^t + \partial(e^\phi \psi_{p_1}\psi_{p_2}\psi_{p_3}) \partial\tilde{x}_{p_4}] + ghosts]$$
where \\(\Gamma\\) is the PCO, t runs from 4 to 9, p from 0 to 3, and m from 0 to 9. Actually, up to the PCOs, the stress energy tensor is exactly the same as that of flat space with no branes. Therefore, the PCO term is directly due to the RR fluxes. The way to see this is nontrivial. If a RR vertex is placed on a vertex and a boundary is present, the holomorphic and anti-holomorphics ghost and spin operators are no longer independent, but related to each other. This also occurs with the GS string for the fermionic variable \\(\theta\\) and \\(\bar \theta \\) when we included the D3-branes. Thus, without the D3-branes, there would be no relation between the holomorphic and antiholomorphic parts, and the 5 form and 3 form terms in the stress energy tensor would vanish.

Alternatively, it is much much easier to see this from IIB SUGRA. Including the D3-branes and solving Einstein's equations give us the 5-form on the RHS sourcing the AdS geometry.

In anycase, we now need to include these VOs into the action or exponentiate and throw in a correlator. This is hard in itself, but one could theoretically go order by order. It is not fun. You can see the last part of Polyakov's paper above to get a taste of it. At the end, GS formalism will start to look appetizing.

## So what now?
This unfortunately puts a damper on doing string theory on \\(AdS_5 \times S^5\\), so what should we do now?

Well, if we still *really* want to work with the D3 branes, we can work in the GS formalism (or the Hybrid formalism). The calculations (outside of a few nice gauges) are rather difficult, but we don't run into this issue with the RR fields. Alternatively, we could just try to deal with it and go order by order to learn something, or maybe try and figure out a nice way to deal with the PCOs or the super Riemann surfaces. 

There *is* a place where we get around this issue with the RR fluxes though, and can do actual string theory. These are [\\(AdS_3 \times \mathcal{M}\\) ](https://arxiv.org/abs/hep-th/9902098)solutions. There's a lot of power here with sigma models being controllable due to having a nice target space, U-duality, or setups that don't need RR fluxes. For instance, for \\(\mathcal M = S^3 \times \mathcal X_4\\), the geometry can be supported by NSNS 2 forms (the setup being F1 and NS5 branes). 

I've recently been quite interested in the [\\(AdS_3 \times S^3 \times T^4\\) ](https://arxiv.org/abs/2406.14605)setup as it seems like there are still several open questions. Namely, the relation between IIB string theories and an apparent relation to a grand canonical ensemble of free symmetric orbifold CFTs. The relation between this and ensemble averaging is also interesting. Generally, a set of central charge \\(c\\) CFTs are averaged in these lower dimensions to give a gravitational theory (really just an effective one). Additionally, we already know that incorporating the other compact dimensions leads to [novel solutions,](https://arxiv.org/abs/2412.01885) but it would be exciting to see the stringy side of these things. Additionally, it would be interesting to see how the SCFT's decoupled 4-torus sector shows up in the string theory.

