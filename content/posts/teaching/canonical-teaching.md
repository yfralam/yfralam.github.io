+++
title = 'The canonical to teach quantum mechanics'
date = 2025-08-01T18:37:00-05:00
draft = false
description = "Some discussion on teaching undergraduate quantum mechanics and other core classes. Also \\psi \\in \\mathcal H is not a state."
slug = ""
authors = ['yasin']
tags = ['physics-nt','teaching']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}

Recently, during another procrastination episode, me and some colleagues got into a discussion on the correct way to teach undergraduate quantum mechanics. There seems to be a "canonical" way to teach classical mechanics and electromagnetism, but there are multiple approaches to teaching quantum.

 For classical mechanics, it is very clear that one should start with Newton's laws, distill some intuition within the students, and then move on to Lagrangian and Hamiltonian mechanics. This seems to be the approach in both graduate and undergraduate courses (with the graduate course maybe having some more special topics like chaos).

The books that follow this approach also usually follow this.

Similarly for electromagnetism, the standard undergrad textbook, Griffiths E&M, does a phenomenal job of ordering things in a way that makes sense. Start off with Coulombs law and electrostatics, talk about the electrics fields, potentials, and then the magnetic fields. There is usually ample time to draw analogues to classical mechanics (for example, Coulombs law with Newton's law of gravitation). Then unify them with Maxwell's equations to give a beautiful introduction to electrodynamics. 

These two approaches are standard, and you will be hard pressed to find courses that vary from this point of view. This is not the case for quantum mechanics.

## "Canonical" approaches to quantum mechanics
There are usually two (three) approaches to quantum mechanics:
1) Wave function first (like Griffith's Quantum)
	-  Take the PDE approach to QM. Immediately start with Schrodinger's equation and how to solve it. Discuss things like [infinite potential wells](https://en.wikipedia.org/wiki/Particle_in_a_box) and the wavefunction \\(\Psi(x)\\) as a state.
2) Spin first (like Sakurai)
	- Talk about spin and [Stern-Gerlach first](https://en.wikipedia.org/wiki/Stern%E2%80%93Gerlach_experiment) . Immediately start with Dirac notation \\(\ket{\Psi}\\) as a state and matrix representations.
3) The historical approach (like Weinberg)
	- Discuss the [ultraviolet catastrophy](https://en.wikipedia.org/wiki/Ultraviolet_catastrophe), electrons in an atom, the photoelectric effect, etc. I say there are *two approaches* because this one usually leads to the wave function interpretation first. Weinberg, (whos opinion I must care about only because his office is in front of mine) uses de Broglie to talk about wave packets first which gives a natural flow into the wave function.

Any good physicist should know all three. By the end of any good course, one should know the above and the other canonical topics (harmonic oscillator, hydrogen atom, perturbation theory, etc.). What I mean by "approaches" is how the course gives intuition and first impressions.

![infinite square well particle](/posts/teaching/img/ISW.gif)

Of the three, we all agreed that the wave function first approach a la Griffith's is the worst. The statement of Schrodinger's equation is abrupt and from a mid quantum course, a student can come away thinking that quantum mechanics is just solving PDEs. I think it is difficult to discuss entanglement in this scenario and one can't even discuss the humble qubit. 

Unfortunately, it seems like Griffith's QM is the standard undergraduate text in the US. It takes almost 100 pages to even introduce kets and I think this confuses students who have been instilled with the wavefunction first.


---

Griffiths says a state is \\(\Psi(x) = \braket{x|\psi}\\) which "lives in a Hilbert space", but this is misleading at best. \\(\bra{x}\\) is not part of any Hilbert space. Despite this, the wavefunction works as a state in the algebraic sense: It maps \\(\Psi:x \to \mathbb C\\). More confusion is introduced alongside density matrices (\\(\rho\\)) which Sakurai calls states in addition to \\(\ket{\psi} \in \mathcal H\\). Technically he is right for the density matrices, you can represent a state, pure or mixed, as an operator on the algebra. This still seems disingenuous to me. One jumps through several hoops to avoid the mathematical rigour and reuses the word "state" for several different things. At best this is confusing, at worst, actually wrong. My gripe with both approaches is conveyed by my colleague very nicely [here](https://physicsconcerto.com/presentations_slides/Ainesh_Concerto.pdf). 

This is not supposed to be a technical post so let me move on.

--- 

## My opinions

In an ideal world, I would want to take the functional analysis and operator algebra approach to quantum mechanics. Here, one an rigorously defines states, observables, and measurement. 

I doubt this would be very popular among students. Maybe if they were motivated enough to learn the basics of quantum mechanics themselves, a course could start off with rigour. Graduate students are usually more motivated so it could happen there (next semester there is an "advanced SUSY" course being thought with the prerequisites as QFT I,II, almost all of Wess and Bagger, and some of Weinberg volume 3), but this would be unimaginable for an undergrad course.

![Stern gerlach experiment dirgram from wiki](/posts/teaching/img/sg.PNG)

Out of the two options, I am partial to the spin first approach. I think it clearly introduces the "weirdness of quantum" in a simple concrete way that does not rely on difficult math. Conceptually, Stern-Gerlach and superposition can be explained to anyone that has the intuition coin flips are 50/50. My first introduction to quantum mechanics (and what got me interested in physics) was this [MIT OCW lecture](https://youtu.be/lZ3bPUKo5zc?si=ZNLrJFJDnp-Wz3Dp) where the physics was abstracted out of the experiment and the spins were described as a particle being "black or white" and "hard or soft". I have been told this analogy stems from Feynman.

Moreover, this is the best approach if one wants to discuss quantum information, qubits, entanglement, etc. Mathematically, all that is required is some basic linear algebra and focus can be given to learning standard notation. Indeed, this is the approach that is even approachable to [computer scientists and software engineers](https://www.scottaaronson.com/qclec.pdf).

As for the historical approach, (good) physics undergrads should at least have been exposed to, or learned the historical aspects on their own or in a prior course. In many wave and optics courses (which contain thermodynamics as well), the ultraviolet and similar developments are covered. A short recap may be warranted but I think is unnecessary.

## Statistical mechanics and thermodynamics

The fourth of the core classes is statistical mechanics and thermodynamics. I have taken 2 courses in it and neither I, nor anyone I know, have been given a satisfactory presentation of the course. 

Despite being arguably the oldest and most successful branch of physics, it is (imo) the worst taught. Most classes and books seem to take the historical approach and explain thermodynamics first, then hard pivot into a microscopic description with statistical mechanics. The microscopic description is usually easier; give me a partition function and I know everything. The connection with thermodynamics (heat engines, chemical reactions, gas equations) is difficult and I think unintuitive.

In the microscopic description, entropy has a clear state counting interpretation. In thermodynamics it is $$dS = \frac{\delta Q}{T} ~.$$
What?

What is that supposed to mean intuitively?

Maybe it is my ignorance as a physicist (and even worse, a high energy theorist), but thermodynamics is weird an unintuitive to me. Maybe a mechanical engineer or chemist would have a better intuition than me. 

Somehow when a bunch of degrees of freedom come together, we have a remarkably useful was to describe them using thermodynamics, even in cases when I don't know the microscopic description. If a chemist asked me questions about chemical properties of ethanol and I told them to calculate a partition function, I would probably get smacked.

In conclusion, I'm not sure what a good approach to teach statistical mechanics would be. The above colleague suggested an information theory approach may be useful. Thermodynamics seems to be saying something about the ignorance we have about the system and this seems like an interesting approach.

