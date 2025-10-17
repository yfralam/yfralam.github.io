+++
title = 'Classically quantum systems'
date = 2025-10-16T21:39:28-05:00
draft = false
description = "There are many systems in the quantum world in which there are no classical analogues. In fact, most systems one could cook up actually have no classical description. Nonetheless, it is absolutely worthwhile studying these class of systems."
slug = ""
authors = ['yasin']
tags = ['physics-nt']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}

There are many systems in the quantum world which have no classical analogues. There is still ample reason to care about these systems. One example of this is the humble qubit system which takes two values: spin up or spin down. 

Famously, it is difficult to explain spin as there is no classical analogue. The common trope goes, "it's like a spinning ball, except it's not spinning, and it's not a ball." Obviously, study of such a system is relevant to quantum computers which we can actually make.
## Classical Systems
In physics, given some system we want to describe, say a ball that someone has thrown, we like to write down concrete expressions governing it's dynamics. In simple terms, we like to write down $$\vec F = m \vec a ~,$$ the equations of motion.
In the case of the thrown ball, this gives us a simple differential equation that anyone that has taken calculus 1 can solve: $$0 = m \frac{d^2x(t)}{dt^2} , \quad mg = m \frac{d^2y(t)}{dt^2}$$ where \\(x(t),y(t) \\) describe the balls motion. 

When forces are conservative, it is often much more useful to use the Lagrangian formalism. The Lagrangian is nothing but the kinetic energy minus potential energy $$ \mathcal L = KE - PE .$$
In the example above, this would be nothing but $$\mathcal L = \frac12 m \left(\dot x^2 + \dot y^2\right) - mgy~.$$

In fact, to solve for the equations of motion, we can use the Euler-Lagrange equations: $$\frac{d}{dt} \left(\frac{\partial \mathcal L}{\partial \dot y}\right) = \frac{\partial \mathcal L}{d y}, \quad \frac{d}{dt} \left(\frac{\partial \mathcal L}{\partial \dot x}\right) = \frac{\partial \mathcal L}{d x}~.$$ 
It is easy to check that these equations give the same differential equations that we wrote above using \\(F = ma\\). When systems get very complicated, it is easier to use the Lagrangian formalism (which deals with energy) than the Newtonian formalism (which deals with the forces directly). Of course, they yield the same result (the same EOM).

## Quantum systems

When we pass to quantum field theories, one largely does the same. We can write down a Lagrangian, then find it's equations of motion. A field is just a function that takes a value at every point in space. For example, think of an electric field.

The simplest example one can construct is a 2d free massless scalar field. It is sufficient to think about it as a function that eats two coordinates and outputs a number \\(\phi(t,x) = \text{number} \\). Here the coordinates are time and space. The equation of motion is then $$\frac{\partial^2\phi(t,x)}{\partial t^2} =  \frac{\partial^2\phi(t,x)}{\partial x^2} .$$ 
This is nothing but the wave equation. In classical mechanics, if one were to solve for the the motion of a vibrating string, they would find the same thing
 $$\frac{\partial^2y(t,x)}{\partial t^2} =  \frac{T}{\mu}\frac{\partial^2y(t,x)}{\partial x^2} .$$ 
 Here, \\(y(t,x)\\) is the position of the string and \\(T,\mu\\) are the tension and mass per unit length respectively.

The Lagrangian that produced the wave equation for our field looks like $$\mathcal L = -\frac12\left(\frac{\partial\phi}{\partial t}\right)^2 + \frac12\left(\frac{\partial\phi}{\partial x}\right)^2.$$

The quantization procedure for a field (How to make this field a *quantum object*) is straight forward and not relevant to the discussion. **What I want to convey is that, once given such a Lagrangian, there is a formulaic way to make sense of it in the quantum theory.**

We can even add other terms to this Lagrangian, for example, $$\mathcal L = -\frac12\left(\frac{\partial\phi}{\partial t}\right)^2 + \frac12\left(\frac{\partial\phi}{\partial x}\right)^2 + \frac16\lambda \phi^3.$$ \\(\lambda\\) is just some number that tells us how how far from the free theory the system is. The equation of motion would get modified to 
$$-\frac{\partial^2\phi(t,x)}{\partial t^2}+\frac{\partial^2\phi(t,x)}{\partial x^2} + \frac\lambda2 \phi^2= 0 .$$ Classically, this makes complete sense; however, when we pass to the quantum description, we must perturb around the free solution. This means we need \\(\lambda\\) to be *small* in order to make sense of the theory. In technical terms, the "perturbative theory" makes sense as a quantum theory when \\(\lambda\\) is small and we call this "weakly coupled".


## Quantum-non classical systems

It would be nice if all the quantum field theory systems we cared about could be written with a perturbative description. Electromagnetism (at low energies) is such a theory. However, to describe what happens in an proton (with QCD) or strongly interacting condensed matter systems (like high temperature superconductors or quantum hall systems), we must study the strongly interacting theories ..

This makes our lives much harder, but can be done a variety of ways: numerically, RG arguments, or dualities between a strongly interacting theory and a weak one.

Despite this, there are monsters hiding in the shadows. **There exist theories that have no known (and indeed, cannot have a) perturbative description.** **These are in fact, *the vast majority* of quantum systems.**

This means there is no sense in which one can write down a Lagrangian or even hope to get a good grasp of it's dynamics using this formalism.

An example of these theories are quantum field theories in six dimensions. If one tries to write down a Lagrangian description, they quickly find that it fails as a quantum theory.  **The only way we know the six dimensional theories exist are because they come from string theory.** These theories can be studied but are notoriously difficult.

One can actually reduce these theories to 4d and learn about properties of the 4d system which come from the 6d system. In some cases, the 4d theory can even be Lagrangian. This perspective is actually very useful to make sense of certain properties of the theories. 

For example, regular old electrodynamics has an electromagnetic duality (If I swap electric and magnetic fields, things stay the same). One can ask, "why does this happen?" If we start with a particular 6d theory and compactify two dimensions to be a torus (a donut), the electromagnetic duality is inherited from properties of the torus. In this way, we can directly see where this electromagnetic duality comes from. 

## Some closing remarks

Most systems one can think of actually don't have a classical analogue. I mentioned the qubit and 6d theories but there are countless more.

I recently gave a talk on the construction of these 6d SCFTs  from the top down construction using IIB/M-Theory so this was fresh in my mind. The discussion here was the first 5 minutes of motivation. I thought I may be able to convey at least the motivation to a general lay audience via this post. 

I toyed with the idea of trying to explain the top down construction and ADE classification in a bit more detail but decided against it. I do not know if it can be done, but it certainly cannot be done by me.