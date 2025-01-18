+++
title = 'Aspen 2025: Observables in QG'
date = 2025-01-17T15:14:54-07:00
draft = false
description = "Some thoughts on Aspen's conference: Observables in Quantum Gravity" 
slug = ""
authors = ['yasin']
tags = ['physics-nt']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}

I've just gotten back from [Aspen's workshop](https://indico.cern.ch/event/1422457/overview) on observables in quantum gravity where the main goal was to have experimentalists and theorist come together to talk about what could be observed in quantum gravity and how the experimentalists could actually go into the lab and observe it.

## On the theory end

From the theorists, the primary focus was on the algebra of observables which has gotten popular over recent years. There were really two camps on this front (though they frequently interacted with each other and are closely related). 

One camp was trying to detail the emergence of space time holographically and study the limits of large N theories to say something concrete about emergent geometry. The other camp wanted to understand the role of the observer better and the structure of the crossed product algebra. Included on this end is how to construct diffeomorphism invariant observables and what it means to do so.

One might ask what the point of these von Neumann algebras are and I think Elliot Gesteau put it in a great way. Broadly in math, there are two fields: algebra and analysis. In algebra we find the science of structures (lie algebras, groups, etc.) and in analysis, we find the science of limits (calculus, functional analysis, etc.). Von Neumann algebras are of course under the domain of analysis.

To put it another way, if you want to understand the structure of a theory, look at the groups, the representations, and look at particles, von Neumann algebras are really not the right framework to use. Instead, von Neumann algebras are useful for understanding *limits* of theories and their constituents. This is what makes it a natural venue to talk about subregions. Therefore it is natural that it is useful for trying to describe observables for *local* theories or the emergence of spacetime for large N theories.

There was a significant amount of progress during this conference. It was incredible to have almost everyone that works on the topic in the same place for once (the first time this has happened I believe) and it was wonderful to bounce ideas off of each other and pave a path forward. For the first party above, the task seemed to be to analyze what the consequences of large N theories are for the emergence of spacetime, what the corrections mean, and whether one can make sense of spacetime at large but finite N (and its consequences for current and previous results \*cough\* *no global symmetries* \*cough\*  ). On the latter party's end, what exactly should the observables be invariant other? Should they include the large diffeos as well? What does the soft structure look like and what role do they play for the algebra? Exactly when can we introduce this "observer degree of freedom" \\(L^2(\mathbb R)\\) and do we need the crossed product to do this, or is there an alternative way? Is there a top down was to construct and "course grain" the necessary quantities to get current answers?

## On the experiment end

The conference title has both "theory" and "experiment" in the title, so roughly half the talks were experiment. This camp too, was split into two. One camp that wanted to understand quantum gravity by simulating it on a quantum computer or many body system and then invoking holography to make some statements. Primarily the theoretical tool of choice for this endeavor seems to be the SYK model which is dual to JT gravity. They seems to be making good headway and are looking for good observables to test (in the sense that they are interesting, yet reasonable to measure within the next few years and a lab). I have my own thoughts of this approach but I'll leave it to next time.

The second camp is not so much trying to study a theory of quantum gravity, but to just verify gravity is quantum in the first place. One proposal is to do this by entangling a macroscopic(ish) particle with some other masses such that space itself is in a superposition. The argument seems to be the scale at which we can measure gravitational effects is getting smaller and smaller every year, while the size of objects we can entangle is getting bigger and bigger. At some point these seem like they will meet. 

Another proposal, (that I am a bit more skeptical of) says that they will create a causal diamond and with lasers and then measure the fluctuations of the size. The argument given was that they can use the area operator to measure the size, but the derivation was lackluster at best. This operator takes one out of the Hilbert space as it has infinite norm wrt any state. The claim during the talks was that it could be regulated, but this was confusing to me as I didn't understand what exactly they were regulating wrt. The end result gave an expression that suggested a sufficiently big causal diamond could have its area variation measured but the derivation seemed sketchy at best. The allusions to flat holography really didn't make sense and I don't think can be trusted.

Only when I talked to Temple He at dinner did he tell me they were regulating wrt the size of the causal diamond itself. This makes a bit more sense, but I still think in order to measure any variation of the causal diamond size, it would be much larger than what one could construct on earth.

I also had the chance to talk to Markus Aspelmeye who told me about his experiment to probe gravity at the 10 micron scale. For him, it was just something he wanted to do for the sake of doing it, but when Vafa realized this would be within reach of the Dark dimension/swampland predictions for extra dimensions, he got extremely involved (to the point where he is apparently making suggestions to the experiment).

As a side note, during Dan Carney's public talk, someone asked, "I think physics made a wrong turn when it decided to discard aether, what do you have to say about that?" I've never seen someone try and swallow a frog, but I'm pretty sure that's the expression he made.
## TLDR

The theorist mainly discussed von Neumann algebras (emergent spacetime and/or dressed observables), while the experimentalists focused trying to show gravity is quantum in the first place and many-body/quantum computing realizations of theories with a gravity dual.

All in all, I met some great people there, learned a lot, got some ideas for new projects, and confirmation that some of my other ideas weren't completely idiotic. 


![The aspen center for physics](/posts/conference/aspenjpg.jpg)



