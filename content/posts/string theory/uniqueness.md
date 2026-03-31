+++
title = 'Comments on UV uniqueness and IR testability'
date = 2026-03-29T21:41:51-05:00
draft = false
description = "Motivated by some recent discussion and some recent(ish) results, I make some comments on the uniqueness of amplitudes at high energies. Furthermore, I discuss a possible low energy predictions of string theory related to minimal dark matter."
slug = ""
authors = ['yasin']
tags = ['physics-t']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}


## Uniqueness of amplitudes at high energies

This post was partially inspired by some discussions among friends and this nice [Quanta article](https://www.quantamagazine.org/are-strings-still-our-best-hope-for-a-theory-of-everything-20260323/). It is a good read, but not necessary for this post. The point is the following:

> Using bootstrap methods and certain well motivated assumptions, the only consistent high energy amplitudes are Virasoro-Shapiro/Veneziano. These are the amplitudes of scattering strings.

One sign that signals something has gone wrong in a theory is an inconsistent amplitude. For example, if at high energies the probability of a process occurring is \\(>1\\), the theory is inconsistent. 2 examples where this happens:
1) For massive vector bosons like the W and Z without the Higgs. Once we had discovered the W and Z boson, this was one of the reasons why the Higgs was so well motivated.
2) For fields charged under anomalous gauge symmetries.[^1]

The uniqueness of these amplitudes was I think first put together by Clifford Cheung, but  Henriette Elvang and Grant Remmen also have results towards this direction. Quoting Henriette, 
> “To really be able to say, ‘I’m just using field theory; I’m not assuming anything about the higher-order theory,’ … and then string theory comes out of just field theory— that’s really, really fun, I think."

 Of course mathematical consistency can only take us so far, but it's essentially the only game I can play at high energies. I want to emphasize that even though it is crude, mathematical consistency can still get us quite far. It can help predict new objects (ex. 1 above) or new phenomena (integer quantum hall is required by consistency of the partition function[^2]). 

One can of course ask questions about removing assumptions, but I think it's an interesting result that bears keeping in mind.

## Some low energy predictions

Quantum gravity is inherently something that must be tested at high energies. At low energies, any viable theory should [reproduce the effective field theory result](https://golem.ph.utexas.edu/~distler/blog/archives/000639.html) (Einstein-Hilbert + corrections). Despite this, string theory is a theory of everything, so one could hope to test the parts of it that aren't gravity.

There are many phenomenologically motivated theories of *minimal* dark matter that try to explain dark matter by adding **a single** particle (either a stable heavy fermion[^3] or boson). Such a particle couples to the weak sector \\( SU(2)\\) of the standard model and neutral under strong and electric forces (or else we would have seen it by now).

$$ \mathcal L = \mathcal L_{SM} + \frac{1}{2}\bar \chi(i \gamma^\mu D_\mu - M) \chi$$

I want to emphasize that the search for such particles is either well within reach (for colliders, ATLAS or CMS should be able to place good bounds) or are turning on right now or in less than a decade (for direct-detection).

What is the point here? According to [*How to falsify string theory at a collider*](https://arxiv.org/abs/2412.13192)[^5],

> string theory *cannot* reproduce this minimal dark matter model. 

In more technical terms, string theory cannot produce just a single massive fermion or boson that is a \\(\mathbb{Z}\_{\text{odd}}  \geq 5 \\) of \\(SU(2)\\). It always comes with something else (say two or three of these particles). In other words, string theory cannot reproduce one of the most well studied dark matter models. 

If such a particle is detected and nothing else, it would be a major experimental blow to string theory. This is not an issue like supersymmetry which can just be pushed to higher and higher energies, this is a direct result of the representation theory. If such a particle is detected, string theory would require other particles around the same energy to come with it. 

Of course, *absence of evidence is not evidence of absence*[^4], but I imagine after searching for several years or decades around the relevant energies, moods would start to sour if nothing is found.

I think this is also something to keep in mind when thinking whether string theory can describe the real world. In another universe, I think this paper also could have been covered in the same Quanta article from above.




[^1]: See [here](https://yfralam.github.io/posts/anomalies/why-is-the-charge-of-an-electron-e/) for more.

[^2]: To avoid being facetious, I don't believe this is how the integer quantum hall effect was first theoretically predicted.

[^3]: Below we have the proposed fermion action.

[^4]: -A.S.

[^5]: This paper also provides improves bounds on ATLAS and other future searches.
