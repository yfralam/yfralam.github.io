+++
title = 'On Complexity in QFT and Algebras'
date = 2024-08-02T20:47:12-05:00
draft = false
description = "Some thoughts on algebraic complexity"
slug = ""
authors = ['yasin']
tags = ['physics']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}

## Operators and Black Hole Info
Today, the arxivs have graced us with a paper on [An Operator Algebraic Approach To Black Hole Information](https://arxiv.org/abs/2408.00071) by van der Heijden and Verlinde. In it, they describe using the operator algebra picture to describe some concepts in the information paradox and particularly focus on times much later than the page time. Specifically, they look at the limits with \\(G \rightarrow 0\\) and fixed inverse temperature \\( \beta\\), and are able to say some very interesting things regarding how Bob can reconstruct the dictionary Alice has (rudely) thrown in.

They mainly focus on type I algebras and show in the limit of above, they are able to get II without the crossed product. This is extremely interesting as there may be a hope to unite the type I description (and all the unitary-ness) with the type III geometric picture. Really, it doesn't seem like anything would stop one from adopting [Hong and Sam's approach](https://arxiv.org/abs/2112.12156) to push to a type III.

This also seems like a natural language to talk about QES and Islands as well. 

## Complexity

Complexity, in QIS, has a well known interpretation. It is (roughly) the number of unitaries I need to apply to a reference state to get to a chosen state. Despite this, the notion of complexity in QFTs, with its infinite degrees of freedom, is hard to understand. As far as I am aware, there isn't any concrete proposal that is widely accepted at this point.

At most, there are some notions of placing the theory on a lattice with some small gate set and asserting that this gives a good notion of complexity, though this is ultimately just reducing back to a Type I system. In my opinion, its not really studying (local) QFT (which should directly be III).

It seems like a good notion of complexity may exist in the framework of Algebraic QFT. Indeed, [Hollands and Ranallo](https://arxiv.org/abs/2302.10013) have proposed a measure of channel complexity based on Belavkin-Staszewski (BS) divergence (essentially a generalization of Araki relative entropy, BS can apply to non faithful states) $$ D_{BS}(\phi||\psi) = \sup_{x} \sup_{n \in \mathbf{N}} \left(\phi(1) \log n - \int_{1/n}^\infty \left[ \phi(x_t x_t^\*) + \frac{1}{t} \psi(y_t y_t^\*) \right]\frac{dt}{t} \right)$$  where the complexity of the channels is $$c(T)=D(id||T).$$Notably, the only non-infinite complexities are those of conditional expectation values. Channels that act as unitaries give infinite complexity. Beyond this, the behaviors of this function seem to satisfy what one would want from complexity, additivity, monoticity, positive definiteness, etc.

It seems like a nice interpretation may be channel complexity is how hard it is to perform a measurement.

## Complexity for Black Holes?
It is yet to be seen whether the definition of complexity above is relevant everywhere. A place where complexity pops up over and over is holography, where there seems to be some interpretation in the bulk (yet not on the QFT). This provides a decent playground for initial tests.

A very quick check one may do is as follows: 

In the paper above, at late time, much past the page time, an evaporating black hole of mass \\(M\\) goes to \\(M-E\\). They respectively have algebras \\(\mathcal M\\) and \\(\mathcal N\\) respectively with \\(\mathcal N \subset \mathcal M\\). The Jones index, essentially a measure of the relative size between the two algebras, goes as $$[\mathcal M : \mathcal N] = \exp 2 \beta E.$$ Of course, this is mediated by a channel with conditional expectation value $$\epsilon : \mathcal M \rightarrow \mathcal N.$$ This quantity is related to how much information Bob can get from whatever Alice threw in at the beginning. The complexity for the BS divergence gives a very concrete answer to this, for a channel defined above $$c(\epsilon) = \log [\mathcal M : \mathcal N].$$ If we call this the complexity, we get $$c(\epsilon) = 2 \beta E$$ which is what one would expect to get! The complexity scales linearly at late times, as expected. Maybe this complexity is related to how difficult it is for Bob to measure outgoing radiation of interest? There is some heavy work that needs to be done for interpretation.

There seems to be something very tangible here that still needs to be ironed out! The above construction works in the I and II case but we are primarily interested in III. Nonetheless, the above calculations are all well defined in the type III case, so one should be able to push the construction analogous to Hong and Sam. Though in all likelyhood, it would involve hijinks with the modular operator \\(\Delta^{is}\\).

This seems like a promising avenue, and it should be possible to describe the complexity of items of interest, maybe QES, islands, etc. If nothing else, the operator algebra approach seems well suited to many of these issues. Hopefully, this measure of complexity is what we want for QFT. I've only been looking at van der Heijden and Verlinde's construction for a few hours, so perhaps I'll find a nice cafe and do some more serious calculations this weekend.

Time will tell if this is the correct avenue...