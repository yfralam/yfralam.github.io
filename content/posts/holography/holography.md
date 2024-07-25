+++ 
draft = false
date = 2024-07-20T22:24:28-05:00
title = "On Holography for Laymen"
description = "A layman's intro to holography"
slug = ""
authors = ['yasin']
tags = ['physics']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}

## Introduction

Imagine a 3d solid cylinder. The 2d "boundary" is what wraps the cylinder (the thing with area \\( A=2\pi R h\\) ) while the 3d "bulk" is the inside of the cylinder. As another example, if you take a soda can, the "bulk" is the soda and the "boundary is the aluminum." Now if you walk around the boundary of the cylinder, hit it with a hammer, or otherwise do any action on the surface, there is an *entirely equivalent* process happening inside the bulk. In other words, just by studying the boundary of this cylinder, I can understand what is happening inside. This is the essence of *holography*. ![A cylinder being unwrapped](/posts/holography/img/cylinder.png) 
### Who is this for?
Part of what I do in Physics is doing Holography (AKA AdS/CFT Correspondence, Gauge/Gravity Duality, etc.) As a slightly ambitious topic, I'd like to attempt making a (somewhat) Laymen's guide. There are certainly many pop science articles and videos on the internet that explain the topic, but in a largely handwavy manner that I find not very satisfying. On the other hand, if you try to go deeper, you will quickly find that most sources expect you to have some knowledge of quantum field theory (QFT) and general relativity (GR) to make some headway. This post is dedicated to those in between, maybe having a background in science or math, but not knowing the aforementioned fields (pun non intended).

We'll have to delay discussions of stacking D-branes, computing correlators, or entanglement entropy to another day. For now, if you have any background in QFT/GR, I find Veronica Hubeny's [note](https://arxiv.org/abs/1501.00007) a wonderful introduction. If you don't feel like reading on, I'll write the thesis here:

$$\text{Quantum Gravity in D dim} \cong \text{Gauge Theory in D-1 dim}.$$
In other words, for a quantum gravity (QG) theory living on some space D-dismensional space \\(\mathcal M \\), a gauge theory (a QFT) on the boundary of the space, \\( \partial \mathcal{M} \\), can explain the dynamics of \\(\mathcal M \\). In this case, we say the theory on \\(\mathcal M \\) is *dual* to the theory on its boundary \\( \partial \mathcal{M} \\). This is also knows as the ***Holographic Principle***. 

The organization is as follows.
> - "Why do I care?" details some introduction on why one would want to study holography
> - "Motivation" draws some inspiration from black holes
> - "AdS/CFT" provides a concrete model realizing holography. On first readthrough, this section can be skipped
> - "All Thogether Now" restates the keypoints of the previous section and 'derives' the duality
> - "The Real World" ends with some comments on applications and outlooks

### Why do I care?

Our best theories of nature are quantum. The [standard model](https://en.wikipedia.org/wiki/Standard_Model), arguably the most successful model of nature ever made, describes the quantum interactions of fields (like the electromagnetic field \\(\vec E(x) \\), where there is a value assigned to every point in space. Often we will denote fields as \\(\phi(x)\\)). This model applies well to (relatively) small scale physics. Included in this are the 3 forces: 

- Electromagnetic: Responsible for almost everything in our everyday lives
- Weak: Responsible for particle decays
- Strong: What holds quarks together

Additionally, we know how QFTs work relatively well. Note QFT is a framework of which there are many concrete models. 

The other successful theory is GR, which gives us the force of gravity. It predicts several observed phenomenon at large scales including the precession of Mercury, gravitational lensing, and gravitational waves. 

Together, these form our understanding of the universe.  Yet, gravity is not included in the standard model. We believe (with good reason) that there should be a force carrying particle called the graviton that is not included. Really what I want, is a theory of *quantum gravity* which tells me how gravity works at very small scales. This is relevant to regimes like black holes, the big bang, and high energy regimes. This [Snowmass whitepaper](https://arxiv.org/abs/2210.01737) does a very good job of explaining why QG is important.

Unfortunately, QG is notoriously difficult. There is a perfectly fine *effective field theory*, but if I want to describe any regimes of interest, I quickly realize that a naïve quantization wont work. I need new tool to describe QG. This is why I care about holography, it gives me a tool to study a theory of QG, something I don't understand that well) by using a QFT because *the physics between these two theories are essentially equivalent*. 

As a general idea, that's all there is to it. For those that want a bit more detail, read on.

## Motivation

### Spin Lattice

Let's consider a cubic box of volume \\(V\\). Subdivide it into smaller boxes with side length \\( a \\) where \\(a^3 < V \\). We want to place a single (distinct) particle inside every single box of side length \\( a \\). This particle has 2 possible states it can be in, up or down. ![A box of volume b with smaller boxes of volume a3 with a spin inside each box.](/posts/holography/img/lattice.png)In total, we have $$ \text{number of particles} = \frac{V}{a^3}.$$
If we want to count all the configurations my states can take, or multiplicity \\( \Omega, \\) we just need to add up how many possible permutations of each particle:  $$\Omega = 2^{V/a^3}.$$For example, take a box that has \\(V=2a^3\\), then the multiplicity is \\( \Omega = 2^2 = 4 \\). To list all of them, we have: UU, UD, DU, or DD. Entropy, \\( S \\), is nothing but the log of multiplicity, which essentially counts the degrees of freedom in the system, or $$S = \log \Omega = \log 2^{\frac{V}{a^3}} = \frac{V}{a^3} \log 2,$$where we see that the entropy is directly proportional to volume. In fact, we could have guessed this. If we make the box of volume \\( V \\) bigger, the entropy should increase directly as well as it is directly related to the number of total particles. 

### Fun with Black Holes

However, let's look at a regime of interest for us, black holes. These objects are a high energy theorists playground. They are completely described by their mass, angular momentum, and charge; yet are rich enough to lead to very complex questions. Back in the day, Bekenstein and Hawking showed us that black holes surprisingly have a temperature. Even more surprisingly, the entropy of a black hole is given by $$S_{BH} = \frac A 4$$where \\( A \\) is the area given by the event horizon.  The entropy is not proportional to the volume, but the area! Somehow, when QG enters the picture, we drastically lose a number of my degrees of freedom. This is what led Susskind, t'Hooft, and others to propose the so called *holographic principle*. Somehow, all we need to know about what happens in the black hole, is to study the boundary of it. 

The study of black holes led to many a research program today. The information paradox,  study of entanglement entropies and use of quantities in quantum information science (yes, the same stuff as they use for quantum computers) can all trace their roots back to this.

## AdS/CFT Correspondence

So the entropy of a black hole scales with the area, so what? While there were hints of more concrete models before, it took until [Maldacena's 1997 paper](https://arxiv.org/abs/hep-th/9711200) where he proposed a correspondence between a theory of QG and a QFT. Arguably, gauge/gravity duality stands on its own two feet, but it has roots in string theory (in Jacques' words, the [only promising candidate](https://golem.ph.utexas.edu/~distler/blog/archives/000639.html) for QG). To state the original correspondence in full, $$\text{String Theory on } AdS_5\times S^5 \cong \mathcal N = 4 \text{ SU(N) Super Yang Mills}.$$Don't be overwhelmed at this point, we'll take each point slowly and break the above statement down. 

On the LHS, string theory is a theory of QG and Anti-de Sitter (AdS) is the spacetime that the string theory "lives on". On the RHS, \\(\mathcal N = 4\\) denotes the amount of supersymmetry, a symmetry between forces and matter, and an SU(N) Super Yang Mills is a CFT (A QFT with conformal invariace, which we will discuss later) analogous to the strong force.  It will be helpful to include the math, but I will try to demarcate what the necessary information is so you don't need to go into it if you don't want to. This is a concrete realization of the aforementioned holographic principle.

![AdS3](/posts/holography/img/AdS3.png)

**On first read through, it is sufficient to skip to "All Together Now.**" The keypoints from the bottom section will be listed.

Despite my best intentions, the best I can do is a pale mimicry of what AdS/CFT correspondence really is. Without discussing how the correspondence arises, stacking N D3-branes and looking at the perturbative expansion of large N theories and string theory, the understanding is only surface level. You *need* the math. For those that want this detail, I think Hong Liu's [MIT OCW](https://ocw.mit.edu/courses/8-821-string-theory-and-holographic-duality-fall-2014/) on the topic is excellent and has plenty of exercises. Other than that, for now just trust me.

### Geometry

#### Measuring Distance
In everyday life, on a flat piece of paper, you will find Euclidean space. Here the shortest point between two lines is a straight line, in other words, to find the distance \\(s\\) between two points, you just need to use the Pythagorean theorem )$$s^2 = (x_2-x_1)^2 + (y_2-y_1)^2.$$Instead of using the differences in the two points, let me consider a super small interval, \\(x_2-x_1 = dx\\) or an infinitesimal. Then I can rewrite this as $$ds^2 = dx^2 + dy^2.$$This is a *metric*, it tells me how to measure the distance on my space. Of course, generally, our space may be curved; for instance: we might be on a [sphere](https://en.wikipedia.org/wiki/Spherical_coordinate_system).  If you have taken a course in multivariable calculus, in the coordinates \\((r,\theta,\phi)\\), the metric is given by $$ds^2 = dr^2 + r^2(d\theta^2 + \sin^2 \theta \text{ } d\phi^2).$$This is a space with curvature, unlike the Euclidean case. 
#### What about AdS?
AdS is also a space with curvature. Notably, it has a boundary. Instead of the 2 dimensional space in the Euclidean example, or the 3 dimensional space of the sphere, \\(AdS_5\\) is 5 dimensional. The \\(S^5\\), denotes the 5 sphere. It means associated to every point in \\(AdS_5\\), there are 5 extra dimensions that look like a sphere. This boundary, when you zoom in on it, looks like 4-d flat space (similar to Euclidean).

If you are curious, a metric for AdS (in convenient coordinates) is $$ds^2 = \frac{R^2}{z^2}(dz^2 -dt^2 + dx_1^2 + dx_2^2 + dx_3^2).$$ where \\(R\\) is the radius of AdS and \\(z\\) controls how close we are to the boundary. Scaling the metric conformally (see next section) and taking \\(z \rightarrow 0\\) (to the boundary), we get $$ds^2 = -dt^2 + dx_1^2 + dx_2^2 + dx_3^2$$ which is the [spacetime](https://en.wikipedia.org/wiki/Spacetime) version of flat.

Note that symmetries are extremely important in physics. You don't need to know what it means, but AdS has an isometry group of SO(2,4) in 5 dimensions. 


Side Note: If you try to visualize a 5d sphere, you will find it quite difficult (impossible). I once had a colleague that worked with a mathematician that studied manifolds. One day, after gaining the experience over decades, he said to my colleague, "I think I can start to envision a 3-sphere". So maybe not impossible, you just need a few decades to try and get to a 3-sphere, maybe a few centuries to get to a 5-sphere.
### Conformal Field Theory

I have struggled with explaining Conformal field theories to a Laymen. At some point I hope to revisit this, but for now, I will state some basic facts. 

As some groundwork, let me describe the idea of a mapping coordinates. Wecan always choose to take my coordinates from one form to another. As an example, imagine taking Euclidean coordinated from $$x \rightarrow x'= \lambda x \quad y \rightarrow y'=\lambda y$$ where \\(\lambda\\) is just a number. Then the metric transforms to $$ds'^2 = dx'^2 + dy'^2 = \lambda^2 (dx^2+dy^2)= \lambda^2 ds^2.$$This is an example of a simple conformal transformation.  

Conformal transformations are special transformations on my coordinates such that my metric changes only by some overall factor $$x \rightarrow x' = f(x) \quad ds^2 \rightarrow ds'^2 = \Omega^2(x) ds^2.$$ In response, the fields \\(\phi(x)\\), which depend on the coordinates, also scale $$\phi(x) \rightarrow \phi'(x')=\lambda^{-\Delta}\phi(x)$$where \\(\Delta\\) is called the scaling dimension. All you need to know is that this is a special type of QFT with some extra symmetries. Notably, CFTs have a conformal symmetry group of SO(2,4).


### String Theory

There are many things I can say about string theory, but let me summarize by saying it is the only promising theory of quantum gravity thus far. Usually, in most areas of physics, we describe particles as point-like (0 dimensional); however, in string theory, the fundamental particle is a string (1-dimensional).  We would expect that we wouldn't gain much from using a higher dimensional object besides being entangled (pun indented) in a more complex framework. 

If you quantize (apply the rules of quantum mechanics to) a string, you get an infinite number of states (particles). First starting from massless states, and then going up in mass. Surprisingly, in the very first set of particles you find, the massless ones, you immediately get a graviton. 

This means by quantizing a string, you ***immediately get a theory of quantum gravity***. 

You cannot ignore this graviton either. Moreover, string theory is UV complete, meaning that at high energies, the theory is still well controlled; that at high energies wedon't get nonsense answers. This is a feature that the standard model does not possess. If you try to compute the 137th order of \\(\alpha \sim 1/137\\) correction to a process in Quantum Electrodynamics, all hell breaks lose.

Of course, string theory is only consistent in 10 dimensions and has criticisms for "testability", but this we will talk about in another post. For now, I will say the [swampland program](https://arxiv.org/abs/2205.12293) is starting to put some bounds on how QG theories must act and is making predictions for compact dimensions, dark matter, and dark energy. For instance, the force of gravity should go as \\(1/r^3\\) instead of the \\(1/r^2\\) that you learned about in kindergarten when at the micron scale. Right now our tools are good up to 30 microns so this seems possible to test soon.
#### Perturbation Theory 

The way we calculate physical processes (particles interacting with each other) is usually with perturbation theory.  When we analyze a theory, we usually start with a free theory (the particles can't interact with other particles), and then we add the interactions controlled by some number (the coupling) \\(\lambda\\) which tells me how strong the interaction is. Usually this looks like $$A + \lambda B + \lambda^2 C + \dots$$
where A is part of my free theory, and B,C,D,... are my interactions. If lambda is small \\(\lambda <<1\\). I can ignore the other terms D,E,F, etc. 

So if I want to calculate the probability of a particle interaction, it will usually look like $$ \text{Prob } = \lambda a + \lambda ^2 b + O(\lambda ^3)$$ where \\(a,b\\) are just some numbers. It turns out that string theory has interactions built in automatically; I do not have to add them by hand. The shape a string traces out is essentially a cylinder, but the interactions look like topologies with a given [genus](https://en.wikipedia.org/wiki/Genus). The coupling for string theory essentially denotes which genus the interaction is taking place over, whether a sphere, torus, or higher genus shape. Summing over all genus gives me the total probability.  

There is a much richer discussion of couplings to be had using Renormalization Group flow. In fact, AdS/CFT can also be well understood by this, but this is well out of the scope of this introduction. For now, it is sufficient to understand that at different couplings, theories behave differently.

### All Together Now 

Lets take the keypoints from each section:

AdS: 
> - \\(AdS_5 \times S^5\\) is a 10d theory 
 >- AdS has a boundary
 >- The boundary looks like 4d flat space
 >- AdS has isometry SO(2,4)
 
CFT: 
>- CFTs are a special type of QFT with more symmetries
>- CFTs in 4 dimensions have a have a conformal symmetry group of SO(2,4)
>- The CFT of interest to us is Super Yang Mills (SYM) on 4d flat space

String Theory/Perturbation Theory
> - Is a theory of Quantum Gravity
> - Couplings dictate how "likely" an interaction will happen
> - At different couplings, theories behave differently.

You can start to see how these two things may start coming together, The symmetry groups of AdS and CFT are the same. Furthermore, it turns out that the structure of the scattering amplitudes (how likely particles scatter off of others), with respect to the couplings, *looks exactly the same* between string theory and large *N* \\(SU(N)\\) gauge theories.  

Maldacena made the following insight. String theory in specific configurations, at strong couplings, looks like strings "living" on AdS. However, at weak couplings, it looks like \\(\mathcal N = 4 \quad SU(N) \\) SYM with large N which is geometrically on the boundary of AdS. But because the coupling on the gauge theory should be good anywhere, the conjecture is the full $$\text{String Theory on } AdS_5\times S^5 \cong \mathcal N = 4 \text{ SU(N) Super Yang Mills}.$$ 
The correspondence has been extraordinarily useful and has resulted in a dictionary directly relating objects on the LHS to the RHS.

## The Real World?

As a whole, AdS/CFT and holography has been extraordinarily useful in exploring quantum gravity and has pushed our understanding of QFT. Despite this, it cannot be denied that we do not apparently live in AdS \\(\Lambda < 0\\). It appears that our universe has a slight positive curvature, \\(\Lambda > 0\\) (meaning there is no boundary) which means there is nowhere for our CFT to live if we naively want to consider de Sitter/CFT Correspondence. As a side note, it does seem that [recent data from DESI](https://www.desi.lbl.gov/2024/04/04/desi-y1-results-april-4-guide/) suggests the cosmological constant may not be constant, though let's see if this plays out.

Nonetheless, the program has been extraordinarily useful in explaining general "truths" about QG, even if they describe another universe. *A* robust theory of QG is better than *no* theory of QG. Generically, we are able to leverage AdS/CFT and holography to say things that should apply to any universe.

Beyond this, it has seeped into condensed matter physics, quantum information science, and many other fields. For instance, you can describe the physics of [superconductors](https://arxiv.org/abs/1002.1722) with holography or calculate [entanglement entropies](https://arxiv.org/abs/1609.01287), complexities for systems (I have thoughts on the complexities of QFT that I will leave for a more technical post) and error correcting codes. 

While holography is where this idea is most well understood, there are several other correspondences in other dimensions and with other geometries, including flat and de Sitter. A good chunk of people are now working on how holography may look in flat spacetimes (including me) and the prospects seem to indicate it is possible. There also seems to be some ways of rephrasing the dualities with [gravitational algebras](https://arxiv.org/abs/2212.13266) which is still a work in progress. Over the past 25 years, it has continued to make great strides and there does not seem to be any stopping for the foreseeable future.


