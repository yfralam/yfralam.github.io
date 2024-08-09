+++
title = 'Dead Ends, Flat Holography, and 7d SCFTs'
date = 2024-08-08T18:46:24-05:00
draft = false
description = "d=7 works"
slug = ""
authors = ['yasin']
tags = ['physics']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}

Every now and then, one pursues an idea thinking it could lead to something interesting, but then soon finds a dead end. Despite this, there may be one or two concepts that are interesting to talk about, yet not worthy of publication. While searching for Carroll SCFT, symmetries and unitarity bounds seem to suggest 7d SCFTs exist if they are Carroll.
## Naïve Unraveling of \\(AdS_5 \times S^5 \\)
One goal of the flat holography program is to obtain an S-matrix for flat space holographically. As [Polchinski](https://arxiv.org/abs/hep-th/9901076) has shown, a way that one could do this is to take the limit $$R \rightarrow \infty$$ where \\(R\\) is the radius of AdS. There are some stringent consistency conditions that make this much harder than expected. [Recently](https://arxiv.org/abs/2406.19343) it has been shown by taking Carroll limits of Witten diagrams, one is able to obtain amplitudes that make sense.  Nevertheless, these programs (celestial holography included) really only talk about the boundary theory and bulk kinematically. What one really wants is a "dictionary" analogous to AdS/CFT.

Ideally, one would figure out a boundary theory that immediately reproduces string amplitudes ( \\(g_s\\) should be finite) in the bulk with its CFT correlators. Carroll CFTs seem to have the correct symmetry group for this. One may want to say $$\text{Carroll SYM } \sim \text{IIB string theory in flat}$$ and this does seem to be the most promising take.

For now, a naïve (top down) approach may be to unravel the 10d AdS spacetime with compact dimensions but there immediately seems to be problems with this. In addition to difficulties in specifying the asymptotic states (see Polchinski), the AdS radius is the same as the sphere radius, the naïve limit would give $$AdS_5\times S^5 \rightarrow \mathbf R^{1,9}.$$ So what seems to be the problem? If I believe in holography,. I should have a 9d theory living at null infinity, right?

Well, some questions immediately come up. What happens to the R-charges? In the well understood description, the \\(SU(4) \sim SO(6)\\) R-symmetry is identified with the \\(S^5\\) isometry. Something is going on here and it doesn't seem like the naïve approach is the one to take. 

## 9d (probably) does not work

Some might be screaming an obvious fact at this point. If you have passed 5th grade, you know SCFTs do not exist past 6d. This stems from [Nahm](https://linkinghub.elsevier.com/retrieve/pii/0550321378902183) and [Minwalla](https://inspirehep.net/literature/452061) and is easy to see from unitarity and symmetry arguments. In the graded Lie superconformal algebra, the even part (with SO(d+2)) needs to be represented spinorially on the odd part. This exists up to SO(8) where the vector and spinor representations are permuted under automorphisms. After this, for d>6, we fail. 

In a straightforward construction, it is obvious that 9d SCFTs do not exist simply from this fact. Nonetheless, one could persevere and hope that somehow, for Carroll SCFTs, this doesn't hold. Indeed, when studying the theory, we do get some interesting behavior. In the Carroll limit, the Hamiltonian becomes central and the (finite part of the) algebra becomes iso(d+1). 

In smaller words, the effective "dimension" compared to regular CFTs drops by one. You can immediately see this by looking at unitarity bounds with descendants. Say, from the scalar primaries $$||a^{\mu \nu} P_\mu P_\nu \ket{[0]_\Delta}||\geq0$$ we get $$\frac{d-3}{2} \geq \Delta \text{ instead of }\frac{d-2}{2}.$$ With some more tedious calculations, you will find the same for vectors and spinors. You are effectively left with all the interesting dynamics going on in the other d-1 dimensions once the Hamiltonian becomes central, so all one needs to do is find a spinorial representation for so(d+1). Assuming the same reasoning holds, this all suggests that Carroll SCFTs can exist in 7 dimensions.

## Dead Ends

So this kind of puts a damper on finding a 9d dual to flat space in 10d.  Something more complicated is going on and in taking the limit for \\(R \rightarrow \infty\\), one needs to be more careful. 

At least 7d SCFTs probably works. Is there something interesting to do here? Maybe. Do I care? Not really.

It is well known that the [super-BMS](https://inspirehep.net/literature/17666) group is good for any dimension. BMS is the algebra one finds at null infinity for asymptotic flat spaces. In addition to regaining Poincare, you get an infinite algebra.  It has been conjectured that superconformal Carroll in d is isomorphic to super-BMS in d+1. This has been tested up to 4d (as far as I know, maybe 5d?) but this seems to suggest this isomorphism does not hold for arbitrary dimension.

For now, it seems a bottom up approach would be more fruitful in establishing a dictionary. As of now, I'm working on taking the Carroll limit directly of 4d SYM. This seems to be producing some more directly interesting things...

