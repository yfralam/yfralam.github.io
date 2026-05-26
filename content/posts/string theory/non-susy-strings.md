+++
title = 'On non supersymmetric strings'
date = 2026-05-25T20:13:08-05:00
draft = false
description = "Me and a colleague found an expression for the orientifold charge of certain non-supersymmetric strings."
slug = ""
authors = ['yasin']
tags = ['physics-t']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}

## Non-supersymmetric strings

It is often (incorrectly) said that string theory requires supersymmetry (SUSY) to work. Even during the earliest days of string theory, people knew of the type 0 strings which were not supersymmetric[^1], but had the misfortune of having a tachyon. 

Even beyond the type 0 strings, there are actually a few theories that we know of that do not have SUSY *not a tachyon*. Among these are the [Sagnotti](https://arxiv.org/abs/hep-th/9509080) and [Sugimoto](https://arxiv.org/abs/hep-th/9905159) strings. They have gauge groups \\(\mathrm{U}(32)\\) and \\(\mathrm{USp}(32)\\) respectively[^2]. These strings are much less studied, yet very interesting. Only recently have rigorous anomaly (including global anomaly) cancellations been shown. 

## D-brane and orientifold charges

It is an elementary Polchinski statement that D-branes carry RR charge. It is less elementary on what that actually means or what really *is* an RR charge. The purpose of the post is not to explain this. Instead, I just want to present some facts and a novel finding. 

In the type II strings, the RR charges are quantized in differential K theory, not ordinary cohomology as in Maxwell (see [here](https://arxiv.org/abs/hep-th/0002027) for more). The K theory interpretation can be obtained by studying brane-anti-brane annihilation and the connections on them (as Ashoke Sen did). The D-branes have gauge fields living on them which are connections of some principle \\(\mathrm{U}(N)\\) bundle (for a stack of N Dp-branes). Branes should be allowed to annihilate if the bundles are the same leading to an interpretation of adding and subtracting vector bundles and thus, K theory. In the type I string, instead of the charges being quantized in K theory, they are quantized in KO theory.

It turns out that orientifolds also carry RR charges which belong to K (and friends) theory classes.  

In general, the RR coupling terms are of the form 

$$ \int C \wedge \left(\mathrm{ch}(V) \sqrt{\frac{\hat A(M)}{\hat A(N)}} - 2^{\dim(M)-6}\sqrt{\frac{L(R_M/4)}{L(R_N/4)}}\right) $$
where \\(C\\) are a formal sum over odd (or even) RR p forms, \\(V\\) is some complex vector bundle, \\(\mathrm{ch}(V)\\) is the Chern character[^3], M is the submanifold \\(M \subseteq X_{10}\\) of the full space time \\(N\\) is the normal bundle, \\(\hat A\\) is the A-roof genus and \\(L\\) is the L-genus. 

For space filling branes and orientifolds (D9's and O9's), there is no normal bundle so the expression collapses to 
$$ \int C \wedge \left(\mathrm{ch}(V) \sqrt{\hat A(M)} - 16\sqrt{L(R_M/4)}\right).$$

These charges are extraordinarily important for several reasons, including anomaly cancellation and Green-Schwarz[^5], anomaly inflow, imposing consistency on compactifications, intersections of branes, predicting new non-perturbative objects[^4], etc. One can study dualities, content of theories, necessary gauge groups, etc. out of these. It is hard to overemphasize the importance of the above. 

The R/4 is quite curious, it pops up in all of the theories we study.
## The 11d anomaly theory

Recently Tachikawa and friends applied some more modern techniques and machinery to study [type I anomaly cancellation](https://arxiv.org/abs/2505.07933) and also the Sugimoto and Sagnotti strings. They write down an 11d RR theory in terms of the relevant quadratic refinement of a differential K(O/Sp/etc) theory in order to cancel global and perturbative fermion anomalies. 

The following section is technical and I won't go into definitions or details[^8]. When necessary I will point to a place in Tachikawa's paper. 

In the quadratic refinement, there are terms of the form[^7] 

$$ Q(\check a) \subset \sim \int C \wedge (\sqrt{\hat A} \mathrm{ch}(V) - f) $$

which play the role of the expressions above. The \\(f\\)'s are formal sums of \\(4n\\) forms. They are related to the center of the quadratic refinement[^6] . 

$$ f = \sqrt{\hat A} R(\check \mu) $$
\\(f\\) can be recursively solved for by imposing the gauge invariance of the APS eta invariant and applying the APS theorem 

$$ \frac12 \eta(D_{Y 
    \times 0 + \overline{Y \times 1}}(\tilde B_{\Lambda^2V})) = \frac12\int_Z \hat A \frac12(\mathrm{ph}(\tilde B)^2 - \mathrm{ph}(2\tilde B))$$

where \\(\tilde B\\) is a homotopy between connections \\(B_0\\) and \\(B_1\\) on the antisymmetrized bundle. Using the fact that \\(C\\) varies by \\(\sqrt{\hat A}\mathrm{ph}(B)\\) and studying the term \\(\sim \int C \wedge X\\), we obtain 

$$f \sqrt{\hat A}\mathrm{ph}(B)|\_{12} = \frac12 \hat A \mathrm{ph}(2B)|\_{12}. $$

This is what happens for the case of Type I string theory. For the other theories, even though naively expressions look different, we will end up getting the same \\(f\\)'s. They are

$$ f_0 = 32, \quad f_4=\frac{p_1}{3}, \quad f_8 = -\frac{-p_1^2}{320} + \frac{7p_2}{720} $$
and 

$$ f_{12} = \frac{79p_1^3}{1935360} - \frac{5p_1p_2}{32256} + \frac{31p_3}{120960}.$$

It is natural to identify the orientifold term with that of \\(f\\).

### Type I orientifold charge

The relevant term in the type I quadratic refinement (Eq. 4.14) is

$$-\frac12 \int C \wedge f = -16\int C \wedge \sqrt{L(R/4)} $$
exactly as expected. Thus, by constructing the quadratic refinement and imposing gauge invariance, we have found the correct orientifold charge. Indeed, we reproduce Eq. 8 in orientifold precis for the space filling branes

$$ 32\sqrt{L(R/4)} = \sqrt{\hat A(R)} R(\check \mu). $$

### Sagnotti string

In the Sagnotti string, the D-branes must come in pairs. They takes values in  \\(KO^0(M) \oplus KO^0(M)\\). The gauge group is \\(\mathrm{U}(n)\\). The relevant quadratic refinement is 

$$ Q(\check a)\_{\text{sagnotti}} = -\eta(D\_{\Lambda^2 V}) + \frac12 \int C \wedge dC + 2C\wedge X$$

so the orientifold/brane term is 
$$ Q(\check a)_{\text{sagnotti}}\supset -\frac12\int 2 C \wedge f =-32\int C \wedge \sqrt{L(R/4)} $$
or twice the type I orientifold charge. This by itself is quite interesting, I don;t think the entire topological expansion is known in the literature. 

### Sugimoto string

The Sugimoto string is a O9\\(^+\\) of type IIB while the O9\\(^-\\) leads to type I string theory. The branes take values in \\(\mathrm{KSp}\\) now and the vector bundles have some symplectic structure. It turns out that the  orientifold charges seem the same and the effect of going from KO to KSp is encoded in the quantization conditions of the RR fields. At the level of space filling branes, we don't seem to get anything new.


## Further work

In conclusion, we showed that the orientifold charges in the Sagnotti string carry double the type I string orientifold charges. Physically this seems reasonable as D-branes must come in pairs. 

For some further work, it seems unsatisfying to only have expressions for space filling orientifolds. We miss out on all the features of the normal bundle and the subtle cahrges of the lower dimensional orientifolds. Furthermore, with non-space filling branes, one could turn on the B field which has the effect of twisting the K theory class. Then one would be studying branes and orientifolds taking values in twisted differential K(and friends) theory.

One thing to do to learn about lower dimensional orientifolds and branes would be to compactify on a torus and then apply T-duality. Indeed, one can get the type IIB data from type I like this. By generalizing Tachikawa's work above, one can do a lot to learn about the content of the non SUSY strings. 




[^1]: Really the worldsheet is supersymmetric, but the spacetime spectrum is not. Thus, the spacetime theory only contains bosons.  

[^2]: Also see Kaidi, Tachikawa, and Yonekura's non-susy heterotic [paper](https://arxiv.org/abs/2411.04344). 

[^3]: One should be careful on exactly what they mean by this, whether this should really be the Pontryagin character or whether I'm working on a complexified bundle \\(V_{\mathbb{R}} \otimes \mathbb{C}\\). For us we'll be quite careless.

[^4]: For instance, the R7 brane and IIA/IIB domain wall originally found by Jacques and friends [here](https://arxiv.org/abs/0906.0795)

[^5]: This is the more modern (yet not completely modern) way of viewing Green-Schwarz. This can be seen by looking at the 12 form expressions. 

[^6]: To explain this statement would take too long and is not relevant for the point of this post beyond some intermediate steps so I encourage a look at orientifold precis (see footntoe 4) or Tachikawa's paper.

[^7]: See section 4.2 of Tachikawa's paper. 

[^8]: In many posts I attach a small review for the interested reader. I am unfortunately unable to find one at this time. Maybe I should write one. 
