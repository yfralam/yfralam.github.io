+++
title = 'On the (un)reasonable effectiveness of self-consistency in physics'
date = 2026-07-16T20:33:03-05:00
draft = false
description = "A vibes based talk on how consistency can be used to predict and explain phenomena in physics. I point out several historical examples where self-consistency leads to discoveries or explanations and lightly comment on string theory. Despite the title, there is no math in this post. I hope (barring the quantum Hall section) that this article is quite accessible."
slug = ""
authors = ['yasin']
tags = ['physics-nt','history']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}

Back in 1960, Wigner wrote a famous article, [*The Unreasonable Effectiveness of Mathematics in the Natural Sciences*](https://web.archive.org/web/20210212111540/http://www.dartmouth.edu/~matc/MathDrama/reading/Wigner.html) to point out the amazing fact that mathematical concepts very often find applications in the natural sciences and in particular, physics. Two particularly noteworthy examples are:
- The law of gravitation formulated by Newton and
- Quantum electrodynamics (QED).
Wigner points out that while the law of gravitation was formed in part out of experience, the theory of QED is purely mathematical and yet, the predictions agree to experiment beyond any other theory thus far.[^1]

Suffice to say, these days, we take for granted if we want to take part in physics (or the natural sciences as a whole), we need mathematics. After all, mathematics is the language of physics.[^7]

Wigner's point was that we can use the laws of mathematics to make predictions about the world, but it is also worth pointing out that if we go ahead and trust the math, we can explain previous findings in physics or even better, predict new physics. 

What do I mean by "trust the math"? We use math to describe our theories and for those theories to make sense, the theory should be internally consistent. For example, if I flip a coin and ask, "what is the probability for heads?" I can make sense of any value from 0% to 100%. But as soon as you tell me the probability is greater than 100% or less than 0%, I have no idea how to interpret what you have told me. What does it mean for a coin to land on heads -7% of the time?

There are absolutely theories that are self-consistent, yet do not have any application in the physical world (yet); however, if a theory is mathematically **inconsistent**, then it **definitely** cannot describe the physical world, at least not completely. Moreover, if I trust the mathematical consistency,[^8] it can lead to interesting physical phenomena which we will cover below.
## Predictions from self-consistency

In the early days of quantum mechanics, the Schrodinger equation was very successful in describing the physics of bound states like the hydrogen atom. Despite this, there were a number of failings such as the equation not playing well with special relativity and it's failure to describe the "duplexity" of electron states in an atom (what we now call spin). 

In 1928, Dirac proposed his famous equation which accounted for the above, and yet had "negative-energy" solutions. At first glance, these negative energy solutions to the equation are not quite physical and yet, the theory itself was mathematically consistent. Through a series of papers from 1928-1932, Dirac found that the equation described a positively charges particle[^2] with the same mass as the electron. 

In 1932, Anderson discovered the positron. The discovery of antimatter is probably the cleanest example of a mathematically consistent theory predicting new physics.

Another famous example are black holes being predicted by general relativity (GR). Originally they were viewed as mathematical curiosities but they seem rather common nowadays to the point where we can take pictures of them and detect black hole mergers. 

The standard model includes the Weak force which mediates interactions between nuclei. Just like the photon mediates the electromagnetic force, the Weak force is mediated by W and Z bosons. However, W and Z bosons are massive. The issue with massive bosons, is that the probability for them to interact with each other at high energies is greater than one. In other words, the theory completely breaks down at high enough energy and is not mathematically consistent. 

Around the energies at which the breakdown occurs, new physics must arise to keep the probabilities between zero and one (AKA keeping the theory unitary). There are a few solutions to this, but the popular one which turned out to be correct is the Higgs particle. Once electroweak theory and spontaneous symmetry breaking became the top contender, the Higgs was inevitable. While unitarity was not the only reason the Higgs was so favored, it was one of the excellent motivations to look for the Higgs. 

Other predictions that are worth at least mentioning:
- Maxwell's equations predicting light as electromagnetic phenomena, waves, etc.
- The GIM mechanism *requiring* the existence of a 4th quark to work (while at the time, only 3 were known to exist)
- Gravitational wave solutions were would in the mid 1910s and not observed until nearly a century later by LIGO.

## Postdictions from self-consistency

Even when a physical phenomena is already observed, the consistency of mathematics can still be used to explain *why* things are the way there are. We can call these *Self-consistency postdictions*. 

The standard model has several particles with a dizzying amount of charges. The electron has charge -e while a quark might have charge 2/3 e. At first glance, the assignment of these charges may seem haphazard, even if they do agree with experiment very well; however, the assigned charges can be shown to be essentially unique. Any other combination of charges (up to rescaling) would produce a so called "anomaly" which eventually leads to a breakdown of unitarity. i.e. probabilities higher than 1.[^3] The mathematical consistency of the theory forces the charges of the standard model to be what they are.

In 2d electronic systems at low enough temperatures, some materials exhibit the *integer quantum Hall effect* where the conductance of the material takes quantized values (\\(\sigma \sim e^2 \nu/h \quad \nu \in \mathbb{Z}\\)).  The explanation can be chalked up to the necessity of the partition function \\(Z(A)\\) being well defined. The partition function can be thought of as a function that knows everything about the physical state, and is a function of the applied electromagnetic field \\(A\\). In order for the partition function to be well defined, it better be a function. That is, one value of \\(A\\) should correspond to one number 

$$A \mapsto Z(A)\in\mathbb{C}.$$
However, we can do gauge transformations to \\(A\\) (say a gauge transformation take \\(A\mapsto A^g\\) which should not affect the physics. In other words, the partition function applied on \\(A\\) and \\(A^g\\) should give back the same number

$$ Z(A) = Z(A^g).$$ 
However, it can be shown for the integer quantum Hall system the transformation goes as 

$$ Z(A^g) = e^{2 \pi i \nu} Z(A)$$ and for this to be consistent, \\(\nu \in \mathbb{Z}\\) so that \\(e^{2 \pi i \nu} =1\\) and the theory is genuinely well defined. Again we see that the mathematical consistency of the theory demands the conductance is quantized.

I should point out that this is not how the integer quantum Hall effect was predicted or discovered. Some researchers at the University of Tokyo did an approximate calculation which predicted it in 1975 and von Klitzing discovered the effect which won him the Nobel prize in 1985. The link between gauge invariance and the integer effect was only put forth later by Laughlin.

To be fair, the argument that the standard model be anomaly free is essentially the same as what we did for the integer quantum Hall effect. Anomalies happen when partition functions aren't really functions.
## When all you have is mathematics

There are certain times where all we have for now is mathematical evidence for a phenomenon or worse, if a phenomenon is out of reach for being tested, all we may have is mathematical consistency.  

An example of the first is the fact that all the particles we observe have quantized electric charges. In a first years electromagnetic course, one of Maxwell's equations say that there are no monopoles \\(\nabla \cdot \vec B = 0\\ ); however, a famous result by Dirac is that if there exist magnetic monopoles, the electric charge is automatically quantized. Considering the existence of quantized electric charges, this makes the non-observance of magnetic monopoles quite curious. 

An example of the second is in the regime of quantum gravity. By it's very nature, there is no way to test quantum gravity [^4] at accessible energies on earth. Gravitons, the force carriers of the gravitational force, suffer from the same issue as massive bosons in QFT. Namely, at high energies, the probability of an interaction to occur exceeds 1 and the theory breaks unitarity. 

It actually turns out to be exceedingly difficult to put together a mathematically consistent theory of quantum gravity which resolves this issue (and several others). This is both a blessing and a curse. On one hand, the only game I can play is mathematical consistency, on the other hand, because it is so difficult to put together a good theory in the first place, any theory that *is* mathematically consistent is worth some effort to study.

There are so far two solutions to the issue above:

1) String theory or string theory like models with an infinite number of particles.
2) Asymptotic safety.

Loop quantum gravity (LQG) may or may not be able to address the unitarity issue, but after speaking to Ashtekar, it is something the LQG still needs to work on. Asymptotic safety cannot be counted out, yet to me, it seems like a bit of a stretch.

Among these options, the most successful has without question been string theory. At every turn, when it seemed like string theory may be mathematically inconsistent, there has been a new mechanism that just happens to work out so that string theory is consistent. At times, string theory has demanded new math to exist to be mathematically consistent and it has met all challenges thus far.  When the only game I can play is mathematical consistency[^5], string theory is really, *for now*, the only game to exist.[^6]

## Self-consistency à la Monnier

This post was in part inspired by a [paper from Monnier](https://arxiv.org/abs/1903.02828) and I'd like to quote it here as I think it is very well written and also served as some inspiration for when I first started learning about anomalies. Part of my philosophy certainly stems from the 2nd paragraph.

> Practical constraints restrain the type of experiments we can perform to test our understanding of the world. In particular, barring unlikely scenarios, quantum gravity effects are expected to be relevant at energies close to the Planck scale, well out of reach of current or foreseeable experiments. A legitimate question is then: Why do string theorists have a hope of constructing a fundamental theory of quantum gravity, given that there is direct experimental input on this problem? This question is asked repeatedly by outsiders, but seems to rarely get an appropriate answer, with negative consequences for the image of string theory among the general public.
> 
> String theorists believe they can construct a fundamental theory of quantum gravity because self-consistency overconstrains string theory. This not only leads to a unique way of constructing the theory, but provides in addition powerful consistency tests. Epistemologically, these tests are no different from experimental tests, in the sense that their irremediable failure would rule out string theory as a theory of quantum gravity. This very fact is what makes string theory hard science rather than a bundle of conjectures.
> 
> For a historical perspective, it is useful to remember how general relativity was constructed. Requiring that the laws of mechanics and electromagnetism hold in accelerated reference frames, Einstein was able to derive general relativity purely from consistency considerations. Hewas lucky that general relativistic effects happened to be within experimental reach, allowing the theory to be tested experimentally right away. We do not seem to have such luck with string theory, but the methodology consisting in constructing the theory from self-consistency is completely analogous. Of course, this kind of situation is rather exceptional in physics. The typical situation is illustrated by particle physics: the realm of quantum field theories contains an infinite number of consistent theories, and experimental data was absolutely necessary to select the Standard Model over other consistent quantum field theories.
> 
> In this context, an important task is to understand in great detail the consistency constraints that string theory should satisfy.



[^1]: Wigner explicitly mentions the Lamb shift, but a better comparison these days may be the measurement of g-2 for the electron which is known to 1 part in 10 billion.

[^2]: He took several wrong turns through these years including proposing the positive charge particle to be the proton.

[^3]: For more, you can see my post [here](https://yfralam.github.io/posts/anomalies/why-is-the-charge-of-an-electron-e/).

[^4]: as an EFT. Let us leave the details of UV/IR mixing, Swampland, and others to later discussion.

[^5]: While quantum gravity might only be studied at high energies, string theory is a theory of everything and can make [low energy predictions](https://yfralam.github.io/posts/string-theory/uniqueness/) for the other sectors.

[^6]: That is not to say crossover between different fields doesn't happen. For instance, there has been much interest iin the string theory community for concepts like area operators or the Hamiltonian formalism of GR which was developed in large part by the LQG community .

[^7]: The reason for the (un) in the title is that if you take mathematics to be the language of physics, it is in my opinion quite reasonable to trust the self consistency of a theory as a check of the possible validity.

[^8]: If there is one criticism I have for myself, it is that I often swap between "mathematical consistency" and "self-consistency". Whenever I use the prior, I really mean the latter. There are certainly many things in physics that are not mathematically rigorous, yet self consistent within physics. For instance, the path integral measure. For this and to my more mathy friends, I apologize.  
