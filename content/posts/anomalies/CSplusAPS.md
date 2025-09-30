+++
title = 'A fancy way of deriving triviality'
date = 2025-09-30T17:41:39-05:00
draft = false
description = "An accidental derivation that the 3d Chern-Simons theory needs to carry a gravitational Chern-Simons term through the APS theorem."
slug = ""
authors = ['yasin']
tags = ['physics-t']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}

## Some naïve motivation

Recently I have been studying the [\\(SL(2,\mathbb Z)\\)-gravitational mixed anomaly](https://arxiv.org/abs/1803.07366) of 4d free Maxwell theory. It can be shown as arising from the \\( 8 \in H^2(BSL(2,\mathbb Z),\mathbb Z) = \mathbb Z_{12}\\). Through some investigation, the group also shows the invertible phase in 3d that is left over, after applying the operation \\( (ST)^3 \\) on a boundary theory coupled to Maxwell in the bulk, is also related to this [\\(8 \in \mathbb Z_{12}\\)](https://arxiv.org/abs/2009.10099).

Ideally, I wanted to do a computation on the boundary to show that the invertible phase that was left over is order 3, just like the anomaly in 4d free Maxwell. Instead, I ended up using a lot of fancy language for no reason to derive 3d Chern-Simons requires a gravitational part.

At some point I'll probably email Tachikawa or one of my more knowledgeable friends about my original question.

## Derivation using APS theorem 

Let us write the partition function of level 1 Chern-Simons following [Hsieh, Tachikawa, and Yonekura](https://arxiv.org/abs/1905.08943). We must first pick a spin structure. Then we can split the gauge field into a sum of flat but topologicaly non-trivial part and a non-flat topologically trivial part. Assuming the flat connections are isolated, we have 

$$Z_{U(1) CS}(M_3) = \left[\int DA_{top,trivial}e^{\pi i \int (A/2\pi) (F/2\pi) }\right] \times \left[\sum_{A;flat}e^{\pi i \int (A/2\pi) (F/2\pi) }\right]$$The first term can be written in terms of eta invariant of signature operator \\(*d\\)

$$ \exp\left({-\frac{2\pi}{8} \eta_{sig}}\right)$$and the second term can be written 

$$\exp\left({2\pi \sum_{c\in H^2(M_3,\mathbb Z)} q(c) =: 2\pi Arf(q)}\right)$$ where \\(c = c_1(F)\\) is the first Chern class and \\(q(c)\\) is the exponentiaed level 1 classical action on a flat \\(A\\). One should take all the arguments of the expression above to be \\(\mod \mathbb Z\\).

It is known that 

$$ -\frac18 \eta_{sig} + Arf(q) = \eta_{ferm}$$where the RHS is a invariant for the Dirac operator of a 2+1 d fermion with infinite mass.

Now we use the APS theorem. In 3d, it says (see [here](https://arxiv.org/abs/2003.11550)) 
$$ -\eta_{ferm} = \int_{Z_4} \left(\frac12 F_A \wedge F_A + \hat A_1(R)\right) \mod \mathbb Z.$$The RHS is the quadratic refinement and defined on a 4d manifold \\(Z_4\\) with boundary \\(Y_3\\) and the Eta invariant of the fermion is with respect to the Dirac operator in 3d \\(Y_3\\).

Thus, our level one CS theory partition function is solved as
$$Z_{U(1)CS}(M_3) = \exp{2\pi i \eta({D}_{Y_3})}$$
so through APS:

$$Z_{U(1)CS}(M_3) =\exp\left(-2\pi i\int_{Z_4} \frac{1}{2} F_A \wedge F_A + \hat A_1(R)\right).$$
Concretely, the A-roof is just the 4-form part of the expansion in terms of Pontryagin classes

$$ \hat A_1(R) = -\frac{1}{24}p_1=\frac{1}{24\cdot 8\pi^2} \text{tr} (R \wedge R). $$ So now, the integral over this \\(R^2\\) is essentially just the signature. Our theory basically splits up into a part that is \\(F \wedge F\\) and \\(R \wedge R\\). One should note that I have been loose with defining F as a form but in reality and in general it is an element of some cohomology class.

Please don't take these expressions as concrete. I have absolutely also been loose with factors of \\(2\pi,i\\),  etc.

## We have done nothing

It is nontrivial to show (but not too difficult using Wu classes) that 

$$ \exp \left(\sim \int_{Y_3} A \wedge F \right)= \exp\left(\sim \int_{Z_4} F \wedge F\right)$$ when \\(\partial Z_4 = Y_3\\). Therefore, part of our partition function is just the \\(CS(A)\\) term that one would expect.

One can similarly show

$$ \exp \left(\sim \int_{Y_3} CS(\omega) \right)= \exp\left(\sim \int_{Z_4} \text{Tr} R \wedge R\right)$$ where \\(\omega\\) is the connection for the \\(SO(n)\\) tangent bundle of the manifold and 

$$CS(\omega) = \text{Tr}~ \omega \wedge d\omega + \frac{2}{3} \omega \wedge \omega \wedge \omega.$$ Note that \\(R = d\omega + \omega \wedge \omega) \\) and the reader is free to verify \\(d CS(\omega) \sim R^2\\) as one would expect.

Note that at the very least we did the path integral and ended up with an invertible phase as expected.

## Physically what did we do?

We knew there was a duality between Chern-Simons theories and fermions on its boundary. We split the Chern-Simons partition function into Eta and Arf invariants and used the fact that it is equal to the Eta invariant of a fermion. Then we used the APS theorem to rewrite the Eta invariant in terms of [characteristic classes ](https://yfralam.github.io/posts/anomalies/descent/#math-and-subtleties) which we rewrote in terms of their boundary expressions.

We just derived that in order for Chern-Simons to be well defined, we need a gravitational CS term. This is a simple fact that any condensed matter theorist or high energy theorist could have told you without this machinery, but at least we can be assured the APS theorem and duality holds.

