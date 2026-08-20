+++
title = 'SO(3) Instantons'
date = 2026-08-20T00:03:23-05:00
draft = false
description = "SO(3) instantons can take values in half integers on spin 4 manifolds and quarter-integers on oriented 4 manifolds. This is not too difficult to show."
slug = ""
authors = ['yasin']
tags = ['physics-t']
categories = ['tqft']
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}

Recently I've been going through the [*Reading between the lines paper*](https://arxiv.org/abs/1305.0318) where they mention that \\(\mathrm{SO}(3)\\) instantons take values in the half integers (on oriented spin manifolds) instead of the integers like for \\(\mathrm{SU}(2)\\). This is actually not too difficult to show.

## On a spin 4 manifold

The instanton number is defined as 

$$k(P) = -\frac14 \langle p_1(P),[X] \rangle, $$
where \\(P\\) is some principal G-bundle (for now take \\(\mathrm{SO}(3)\\)) and \\(X\\) is a spin 4-manifold.

The first Pontryagin classes is related to the Pontryagin square operation as 

$$p_1(P) = \mathcal{P}(w_2 (P)) \mod 4,$$
where \\(\mathcal{P}: H^2(X;\mathbb{Z}\_2) \to H^4(X;\mathbb{Z}\_4)\\) and \\(w_2\\) is the 2nd Stiefel-Whitney class.

Take an element \\(x \in H^2(X;\mathbb{Z}\_2)\\). The Wu formula gives

$$\langle x \smile x, [X]\rangle = \langle x \smile w_2(TX),[X]\rangle .$$
However, because \\(X\\) is a spin manifold, \\(w_2(TX)=0\\). Thus 

$$ \langle x \smile x, [X]\rangle = 0.$$
Now we can use \\(\mathcal{P}(x) \mod 2 = x^2\\). We need to mod by 2 as the Pontryagin square on a manifold lands us in \\(\mathbb{Z}\_4\\)[^3]. We now have 

$$\langle \mathcal{P}(x),[X]\rangle \mod 2 = \langle x^2,[X]\rangle=0. $$

This means that 

$$ \langle\mathcal{P}(x),[X]\rangle=\\{0,2\\} \subset \mathbb{Z}_4.$$

Now we can go back to the instanton number. Let \\(x = w_2(P)\\) so that 

$$\frac14 \langle p_1(P),[X] \rangle = \frac14 \langle \mathcal{P}(w_2(P)),[X] \rangle \mod 4 .$$
So the instanton (dropping the minus) can take two classes:
$$ k(P) = \frac14 \times (\\{0,2\\} \mod 4).$$
If on the RHS we have \\(0 \mod 4\\), then (\\(n \in \mathbb{Z}\\))

$$k(P) = \frac14 \times 4n \in \mathbb{Z}$$and the instanton number is actually an integer.[^1] 

The other case is more interesting. If the RHS has \\(2 \mod 4\\) then 

$$k(P) = \frac14 \times (4n+2)\in \mathbb{Z}+\frac12.$$

In all, for an arbitrary \\(\mathrm{SO}(3)\\)) bundle, 

$$k(P) \in \frac{1}{2}\mathbb{Z} .$$
In other words, the instanton angle is not \\(2 \pi \\) periodic[^2], but \\(4 \pi \\) periodic (\\(\theta \sim \theta + 4 \pi \\) ).
## On a non-spin 4 manifold

What happens on a non-spin manifold? Well, then \\(w_2(TX) \neq 0\\) and 

$$\langle \mathcal{P}(x),[X]\rangle \mod 2 = \langle x^2,[X]\rangle $$
is not necessarily zero. Let us consider the case where it is not. Then the RHS of the above equation is \\(1\\) and 
$$ \langle\mathcal{P}(x),[X]\rangle=\\{1,3\\} \subset \mathbb{Z}_4.$$

Following the same arguments as above, 

$$ k(P) = \frac14 \times (\\{1,3\\} \mod 4)$$
so that 

$$k(P) = \frac14(4k+1) \quad \text{or} \quad \frac14 (4k+3) $$
respectively. This means that the instanton number doesn't have to take half integer values, but 

$$ k(P) \in \frac14 \mathbb{Z} $$
or in other words, 

$$ \theta \sim \theta + 8\pi .$$

Of course, because \\( p_1(P) \in H^4(X;\mathbb{Z})\\), naively the instanton number is already a quarter-integer, but where's the fun in just saying that?

[^1]: In the case that \\(w_2(P)=0\\),  there exists an honest to god uplift of the \\(\mathrm{SO}(3)\\)) bundle to the \\(\mathrm{SU}(2)\\)) bundle. Another way to say this is that the instanton angle is genuinely \\(2 \pi\\) periodic \\(\theta \sim \theta + 2\pi \\).

[^2]: Normally in the path integral, the instanton number enters as $$e^{i \theta k}$$ so to preserve the single valuedness, if k is an integer we can just have 2 pi periodicity. If k is a half integer then we need 4 pi in theta periodicity.

[^3]: In fancier words, the Pontryagin square is a \\(\mathbb{Z}\_4\\) valued quadratic refinement of the ordinary mod-2 cup product pairing. One can check on their own time that it satifies the properties of a quadratic refinement: \\(Q(x+y) = Q(x) + Q(y) + 2(xy)\\).
