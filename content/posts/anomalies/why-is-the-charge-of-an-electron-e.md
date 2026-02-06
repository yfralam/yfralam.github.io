+++
title = 'Why does the electron have charge -e?'
date = 2026-02-05T21:08:37-06:00
draft = false
description = "The electron has charge -e while the up quark has charge 2/3e (in units of e = 1.6 * 10^-19 C).  Why is this the case? The reason is precisely related to anomaly cancellation. Anomalies show up in almost every single area of physics, from high energy physics to condensed matter systems and have very observables consequences. I cover some basic things about anomalies as consistency checks of theories. The main part of the text requires no field theory knowledge and can be understood with just a basic undergraduate education of the core courses. The appendix contains some content that people that know QFT may find helpful but is in no way necessary. This is the 2nd version of the post after I gave a talk recently. "
slug = ""
authors = ['yasin']
tags = ['physics-t']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}

## Why care?

The electron has charge - 1 e while the up quark has charge 2/3 e. In fact most of the particles in the Standard Model have some type of electric charge.

![The standard model](/posts/anomalies/img/sm.PNG)


At first this seems to be haphazard and random. Why are these the charges for certain particles? The answer lies in symmetry and what we even mean by *electric* charge. 

It turns out symmetries of forces may be anomalous (they could be broken at the quantum level) which would kill the theory. These anomalies are related to the charges of the particles and changing the charges affects the anomaly.

At the end of this blog, you will see that (up to multiplying all the charges by the same number), the charges of the Standard Model are uniquely fixed. There is no other set of charges I could have written down. 

### What are charges?

The key takeaway is that when we say a particle has a charge, we mean it acts a certain way under a symmetry. 

Lets say \\(\psi_q(x)\\) is a particle of charge q. The electron would have charge \\(q=-e\\). You can take this to be the field of the particle or the wavefunction of the particle, it doesn't really matter. Under a symmetry \\(G\\), the particle transforms in some way. You can think of the "action" as multiplying the particle by some matrix or operator. 

![A symmetry acting on a particle](/posts/anomalies/img/sym.PNG)

In the case of \\(G = U(1) \\) group (refresher in appendix), the action would just be multiplication by a phase 

$$ G \circ \psi_q(x) = \psi_q(x)' = e^{iq \theta} \psi_q(x)$$
where we should note that the phase is precisely proportional to \\(q\\). This is what we mean by when we say the electron has charge \\(-e\\) under electromagnetism. The symmetry of electromagnetism is \\(U(1)\\) and the electron transforms as 

$$\psi_{-e}(x)' = e^{-ie \theta} \psi_{-e}(x)$$


Again, when we say a particle is charged under some symmetry \\(G\\), we mean it transforms with respect to some action under \\(G\\).

The Standard Model has a set of gauge symmetries which the particles are charged under
$$SU(3)_c \times SU(2)_L \times U(1)_Y$$which correspond to respectively, the strong force, the weak force, and hypercharge. The electric charges are actually born out of a combination of the weak and hypercharges (see appendix for an example with the leptons). The charges of the fermions are given below

| Field        | SU(3)           | SU(2)      | U(1) |
| ------------ | --------------- | ---------- | ---- |
| LH quarks    | \\(\Box\\)      | \\(\Box\\) | 1/6  |
| RH up        | \\(\bar \Box\\) |            | 2/3  |
| RH down      | \\(\bar \Box\\) |            | -1/3 |
| LH leptons   |                 | \\(\Box\\) | -1/2 |
| RH electrons |                 |            | -1   |
- Here, the first 3 rows are the left handed and right handed quarks. 
- The last 2 rows are the left handed and right handed leptons. The left handed electron is a lepton.
- The \\(\Box\\) are not charges in the same way as they were in the \\(U(1)\\) case, they denote how the fields transform under the non-abelian symmetries. If an entry is blank, the particles do not transform under the symmetry.

The question we are asking: why does the charge of the electron have charge \\(-e\\) is really a question of why the particles above have the charges under the \\(SU(3)_c \times SU(2)_L \times U(1)_Y\\) symmetries. To continue, we need to learn what these symmetries are.

### Gauge symmetries

Symmetries are a guiding principle in physics. They give us an extreme amount of control which we can use to make predictions. A particular class of symmetries called **gauge symmetries** are especially important. They are used to describe the physics of forces. This included electromagnetism, the strong and weak force, and even gravity.

In certain cases, gauge symmetries can be **anomalous**. That is, symmetries at a classical level, may not be symmetries at a *quantum* level. This is a massive issue. 

Gauge symmetries are not "real" symmetries, they are redundancies in description. As an example, in electromagnetism, shifting the vector potential 

$$ \vec{A} \to \vec{A}'=\vec{A} + \nabla \lambda$$ does not change the magnetic field $$\vec{B} = \nabla \times \vec{A}.$$
If the gauge symmetry is broken, there is something seriously wrong with the theory and it cannot be consistent. 

Remember there is also a conserved current in electromagnetism given by the continuity equation

$$ \partial \cdot J:=\frac{\partial \rho}{\partial t} + \nabla \cdot I = 0 $$
and one can show the current is a consequence of the \\(U(1)\\) symmetry from Noether's theorem. When the symmetry is good, the current is conserved. If the symmetry is broken, this current will no longer be conserved \\( \partial \cdot J  \neq 0\\).

- **In quantum field theory, anomalous gauge symmetries lead to probabilities bigger than one. This means the theory is sick and cannot be consistent as is.** 

1) In a nutshell, symmetries give us conserved currents \\( \partial \cdot J  = 0\\)
2) At a quantum level, these currents may not be conserved (divergence is non-zero)

But what do I mean "at the quantum level?"
## Classical and quantum symmetries

Recall the Lagrangian from classical mechanics \\(\mathcal L \\). The action is just the lagrangian integrated over all space $$S = \int \mathcal L.$$

### Classical symmetries

Classical symmetries leave the action invariant. For example, take the Lagrangian to depend on out field/wavefunction \\(\psi_q(x)\\) from earlier \\(\mathcal{L}\[\psi\] \\). Then a symmetry is 

$$G \circ S[\psi] = S[\psi'] = S[\psi].$$
From Noether's theorem, one can find the current \\(J\\) and show that it is conserved \\(\partial \cdot J\\).


### Quantum symmetries

To pass to quantum symmetries, all we need is to recall the partition function from statistical mechanics

$$Z := \sum_{states} e^{-\beta E}$$ which should in principle know everything about the theory. If we want to calculate the expectation value for some observable \\(O\\) (for example the average energy), we can just stick it into the partition function and divide by the original partition function 

$$ \langle O\rangle := Z^{-1} \sum_{states} O e^{-\beta E}. $$

In quantum field theory (QFT), we do essentially the same thing except the partition function is the path integral. 

$$ Z[\psi_1,\psi_2,\cdots] = \int D\psi_1D\psi_2 \cdots~ e^{-S[\psi_1, \psi_2, \cdots]} $$
where this is essentially an instruction to sum over all configurations of the fields. To compute observables, we do the exact same thing as in statistical mechanics
$$\langle O\rangle := Z^{-1}\int D\psi_1D\psi_2 \cdots~ e^{-S[\psi_1, \psi_2, \cdots]} O. $$

**At the level of QFT we demand that symmetries leave the partition function invariant, not just the action.**

$$G\circ Z[\psi_1,\psi_2,\cdots] = Z[\psi_1',\psi_2',\cdots] = Z[\psi_1,\psi_2,\cdots].$$
However, things can go wrong. 

$$ G \circ Z[\psi_1,\psi_2,\cdots] = \int D\psi_1'D\psi_2 '\cdots~ e^{-S[\psi_1', \psi_2', \cdots]} $$ but by definition, the action is invariant so the only possible change is the measure
$$
            = \int \boxed{D\psi_1'D\psi_2 '\cdots}~ e^{-S[\psi_1, \psi_2, \cdots]} \neq Z[\psi_1,\psi_2,\cdots].$$

From this perspective, we can chalk up anomalies to be due to the possible non-invariance of the *measure* under gauge transformations 
$$ \text{if } D\psi' D\bar \psi' \neq D\psi D\bar \psi D  \implies \text{Broken symmetry}.$$

How do we relate this back to the conservation of the current? Let us define $$e^{-W_{eff}} := Z[\psi_1,\psi_2,\cdots]$$ where we have swept up all the data about the path integral into \\(W_{eff}\\). One can show 
$$(G\circ W_{eff}) -W_{eff} =\int \langle\partial \cdot J\rangle $$
so the non-invariance of the path integral is precisely just the quantum divergence of the current (the divergence in expectation values).[^3]

$$\boxed{\langle\partial \cdot J\rangle \neq 0 \implies \text{Broken symmetry}.}$$
Now all we have to do is study the divergence of the current to see if the symmetry is fine or not. 




### How are anomalies and charges related?

I spent the past few paragraphs explaining anomalies, what do they have to do with charges?

Earlier we mentioned 

$$\langle\partial \cdot J\rangle \neq 0 \implies \text{Broken symmetry}.$$
There is a general form of this quantity. The left-hand side is always proportional to the *anomaly coefficient*. 

$$\langle\partial \cdot J\rangle \simeq \sum_{LH}\text{gauge charge}-\sum_{RH}\text{gauge charge}$$
Let us break this up:
- The gauge charges are essentially just the charges of the particles we are talking about under the specific gauge group.
- The sum over LH and RH mean to only sum over the charges of the left hand or right handed fermions.
- For the symmetry to be non-anomalous, the sums of the charges must cancel.

Let us take electromagnetism as an example. We have 1 left handed electron and 1 right handed electron.  We now have all the information we need to make sure the \\(U(1)\\) symmetry in electromagnetism is non-anomalous.

First let us write the charges. We only have to worry about the fermions \\(\psi\\).

| Field       | U(1) charge |
| ----------- | ----------- |
| LH electron | -e          |
| RH electron | -e          |
In 4 dimensions, we need to insert 3 charges. The reason is intimately connected to topology In terms of *anomaly coefficients*, this means we cube the charges

$$\boxed{\langle\partial \cdot J\rangle \simeq \sum_{LH}Q_l^3-\sum_{RH}Q_r^3 = e^3 - e^3 =0.}$$
So now we have found that the \\(U(1)\\) gauge symmetry survives at the quantum level! A few notes

- QED is "non-chiral". This means there are the same number of left handed and right handed fermions and then have the same charges. Therefore, it is no surprise that the anomaly cancelled.
- We only get the relevant gauge anomalies we are talking about when the theory is "chiral".
- We could have changed the charges in this example because the theory is "non-chiral" but we still can't change the left hand charge and right hand charge independently. If the left handed electron is charge -e but the right handed is charge -2e, the cancellation wouldn't work.

## The Standard Model

Above we just saw that chiral theories have the possibility of being anomalous. 

Remember that anomalies are given by 3 symmetries and all of these symmetries must be non-anomalous. This means we have to check every combination of 3 currents and every single combination must be non-anomalous, else the Standard Model would be dead. This would look like checking \[SU(3)SU(3)SU(3)\], \[SU(2)SU(2)U(1)\], \[U(1)U(1)U(1)\], etc. 

As a sample calculation, let us check that \\(U(1)^3\\) hypercharge is non-anomalous.

$$\langle\partial \cdot J\rangle \simeq \sum_{LH} Y^3 - \sum_{RH} Y^3 .$$ Here \\(Y\\) are the charges. 

The difficulty is in the sum over fermions. For example, naively one would thing the contribution of the left handed quarks is just \\((1/6)^3\\). This is not that case. There are multiple quarks because there are charged under the other gauge groups. The contribution would instead be 

$$3 \text{ generations} \times 3 \text{ from SU(3)} \times 2 \text{ from SU(2)} \times \left(\frac16\right)^3 = \frac{3}{36}.$$ Hopefully it is clear that the counting can be complicated. Let us go back now.

$$\sum_{ferm} Y^3 = 3\cdot(3\cdot2\cdot Y_Q^3 + 2 \cdot Y_L^3 -(Y_{e}^3 + 3\cdot Y_u^3 +3 \cdot Y_d^3)$$
$$= 3(3\cdot2\cdot (1/6)^3 + 2 \cdot (-1/2)^3 -((-1)^3 + 3\cdot (2/3)^3 +3 \cdot (-1/3)^3)$$

$$\boxed{=0}$$

So the \[U(1)U(1)U(1)\] current is in fact non-anomalous! If we changed one of these charges, this anomaly would not cancel. We still have to check all the other combinations too. The non-abelian calculations are a bit different but the spirit of the calculation is the same.

Let us check \[SU(2)^2 U(1)\].

$$ \sum_{\text{charged under } SU(2)} Y = 3(Y_L + 3 Y_Q) =3(-\frac12 + 3 \cdot \frac16)  $$
$$\boxed{=0}$$
This one cancels too!

**In fact, *all* of the possible anomalies of the Standard Model cancel.** [^2] Better yet, these anomalies give be a set of equations I must solve (around 4 or 5) and this sets uniquely sets what the charges could be. **Any other combination would produce an anomaly somewhere!**

It is a miracle that **all the anomalies of the Standard Model cancel**. Better yet, to describe the underlying physics we know and observe, there is nothing else we could right down in terms of the charges (up to rescaling everything).

## Victory

The Standard Model is free of gauge anomalies!

The left handed quarks don't have hypercharge 1/6 because we want them to, they have hypercharge 1/6 because if they didn't, the anomalies would not cancel. It is a very important note that the *electric charges* come from the \\(SU(2) \times U(1) \\) symmetry. Once we fix our units, this is of course something that we can observe. For example, we can establish the fractional charges of quarks beyond reasonable doubt due to proton-electron collisions such as those at SLAC.

It is worth emphasizing again if the gauge anomalies do not cancel, the theory is utterly broken. It would mean that if we predict the probability for two electrons to scatter into photons may be bigger than 1. Utter nonsense.

As a final note, we only discussed the gauge anomalies here which are quite boring compared to global anomalies. Global symmetries are those that act the same at every point in time and are "real symmetries". When global symmetries are anomalous, this does not kill the theory, instead one can make real predictions about the model. For example, the reason a neutral pion can decay into two photons is precisely because there is a global axial anomaly in the Standard Model. For detail see my notes [here](https://yfralam.github.io/posts/anomalies/pheno/).




## Appendix

### Groups

A quick refresher for [groups](https://en.wikipedia.org/wiki/Group_(mathematics)) in case you haven't seen them in a while. A group \\(G\\) is a set endowed with some operation \\( \circ \\) that acts on 2 elements of the group. An element of a group is denoted \\( g \in G\\). An example to keep in mind is the integers \\( \mathbb{Z} = \\{\cdots, -2,-1,0,1,2,3, \cdots \\} \\) with operation addition \\( \circ \equiv + \\) .

A group has the following properties:


| \\(G\\)                                                                                                                                                  | \\(\mathbb{Z}\\)                                                     |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| If we act with the group operation \\( \circ \\) on two elements of the group, the resulting element is still in the group \\( g_1 \circ g_2 = g_3  \\). | If we add two integers, we end up with an integer: 1+2=3.            |
| The group has an identity element \\(e\\) which doesn't affect the other element \\( g \circ e = g\\).                                                   | \\(e=0\\) as any number plus 0 is that number: 0 + 1 = 1.            |
| The group has an inverse element \\(g^{-1}\\) where \\(g \circ g^{-1} = e\\).                                                                            | The inverse element of some integer \\(x\\) is \\(-x\\): 1 + (-1) =0 |
| The group operation is associative, it doesn't matter what order you do it in \\((g_1 \circ g_2) \circ g_3 = g_1 \circ (g_2 \circ g_3) \\)               | The order you add numbers in doesn't matter: (1+2) + 3 = 1+ (2 + 3)  |


The \\(U(1)\\) group we case about is essentially just rotations on a circle. If you take a circle and rotate it, it is still a circle.  An element of \\(U(1)\\) is of the form

$$z_1 = e^{i \theta_1}$$
and obeys all of the above along with one more condition. The norm of \\(||z_1|| = z_1 z_1^* = 1 \\) where \\(\*\\) is complex conjugate \\(z_1^* = e^{-i \theta_1}\\) . The operation is multiplication
- \\( g_1 g_2 = g_3 = e^{i (\theta_1 + \theta_2)} \\) which is still just a phase and has norm 1.
- The identify element is just \\(1 = e^{i 0} \\).
- The inverse is just the complex conjugate as \\(z_1 z_1^* = 1\\).
- The group is associative \\((e^{i \theta_1}e^{i \theta_2}) e^{i \theta_3} = e^{i \theta_1}(e^{i \theta_2}e^{i \theta_3}) \\)


### Electric Charges 

Electric charge is combination of \\(SU(2)_W \times U(1)_Y\\): It is defined \\(Q:= \frac12 \sigma_3 + Y\\) where the sigma is the z Pauli matrix and Y is the hypercharge of the particle. 

As an example, let us look at the LH leptons. They are a 2 dimensional vector that contains the neutrino and electron.[^4]
![Charges for neutrino an electron](/posts/anomalies/img/electroweak.PNG)



So we see the neutrino has no electric charge and the electron has \\(-1\\) electric charge (in units of e).
### A QED example

For the rest of this, we will pass to a description of quantum field theory. First let us talk about classical symmetries. Consider a simple Lagrangian 

$$ \mathcal{L} = \bar \psi(i \gamma^\mu\partial_\mu-m)\psi $$
along with the \\(U(1)\\) symmetry that does not depend on position

$$\psi_q(x) \to \psi_q'(x)=e^{iq\lambda}\psi_q(x).$$
The \\(\psi\\)'s are fermions, and the \\(\gamma^\mu\\) is just a matrix. The Lagrangian is invariant under this symmetry

$$ \mathcal{L'} = \bar \psi'(i \gamma^\mu\partial_\mu-m)\psi'= e^{-iq\lambda}\bar \psi(i \gamma^\mu\partial_\mu-m)e^{iq\lambda}\psi=\mathcal{L}.$$
This is a global symmetry as \\(\lambda\\) is just a constant. But what if it depends on position \\(\lambda \equiv \lambda(x)\\)? Then the derivative hits the exponential and the Lagrangian is not invariant anymore.

$$ \mathcal L \to \mathcal L'=\bar \psi{e^{-iq\lambda(x)}} (i\gamma^\mu \partial_\mu +m)(e^{iq\lambda(x)} \psi)$$

$$= \bar \psi (i\gamma^\mu\partial_\mu +m)\psi + i q \gamma^\mu\partial_\mu \lambda(x)\bar \psi \psi$$
$$= \mathcal L+ i q \gamma^\mu\partial_\mu \lambda(x)\bar \psi \psi$$
This second term proportional to the charge must be canceled. To fix this, we must introduce a gauge field, the photon, which will cancel this new term and restore the symmetry.


This gives us quantum electrodynamics (where I will drop the \\(F_{\mu\nu} F^{\mu\nu}\\)  term. The Lagrangian is given by 

$$ \mathcal{L} = \bar \psi(i \gamma^\mu[\partial_\mu + ieA_\mu]-m)\psi .$$
Here, \\(\psi, \bar \psi\\) are the fermions (electrons/positrons fields) and \\(A_\mu\\) is the electromagnetic four-potential (the photon), and \\(e\\) is the charge of the electron. 

This Lagrangian has a classical \\(U(1) \\) symmetry. This means it is invariant under the following transformation:

$$\psi(x) \to \psi'(x)=e^{ie\lambda(x)} \psi(x), \quad \bar \psi(x) \to \bar \psi'(x)=e^{-ie\lambda(x)} \bar \psi(x), \quad A_\mu(x) \to A_\mu'(x)=A_\mu(x)-\partial_\mu \lambda.$$
Now the fermions transform with a phase proportional to their charge \\(e\\). In terms of the action, 
$$ S = \int d^4x \mathcal{L} \to S' = S + \delta S = S.$$Let us check this. Doing the transformation, 

$$\mathcal{L}'= e^{-ie\lambda} \bar \psi(i \gamma^\mu\partial_\mu + ie\gamma^\mu(A_\mu-\partial_\mu \lambda)-m)e^{ie\lambda} \psi$$
Simplifying, we get 

$$=i(e^{-ie\lambda} \bar \psi \gamma^\mu \partial_\mu (e^{ie\lambda} \psi(x)) -e\bar \psi \gamma^\mu (A_\mu-\partial_\mu \lambda) \psi -m\bar \psi \psi$$
$$=i \bar \psi \gamma^\mu \partial_\mu \psi -e\bar \psi\gamma^\mu\partial_\mu \lambda \psi - e \bar \psi \gamma^\mu A_\mu +e\bar \psi\gamma^\mu\partial_\mu \lambda \psi - m \bar \psi \psi$$
$$=i \bar \psi \gamma^\mu \partial_\mu \psi - e \bar \psi \gamma^\mu A_\mu - m \bar \psi \psi=\mathcal {L}.$$
We have returned to the same Lagrangian. Note that the charges of the electrons and positrons are chosen in such a way to cancel the \\(e\\) in front of the photon field \\(A_\mu\\). I could not have chosen \\(0.5 e\\) or \\(2e\\). 

One could ask, "If I scale the charges together, shouldn't the Lagrangian be gauge invariant?" Indeed it would, scaling all the charges together is fine. But imagine if there were more gauge fields and matter fields, all interacting with each other with their own charges. If you scale one set of charges and not other, you may ruin the gauge invariance of another term. With many fields, choosing the correct charges is hard already at the classical level. 

To this symmetry, there is an associated current (you can think about it as the analog of electric current), given by Noether's theorem

$$ j^\mu = \bar \psi \gamma^\mu \psi.$$ It's fine if you don't know where this comes from, the important part is it can be checked that on the equations of motion, the current is conserved, i.e. 

$$\boxed{\partial_\mu j^\mu = 0.}$$ We can take this to mean the symmetry is *fine*. 


[^2]: You can find all the other cancellations [here](https://arxiv.org/abs/2409.09211) on page 179. If nothing else, it is impressive to see several massive calculations all boil down to "=0" for every combination.

[^3]: I have not exactly been kosher with this derivation, really I should introduce a background gauge field and do the symmetry transformations but I think the spirit of the calculation carries over. For people curious Nakahara covers the above (known as Fujikawa's method). An alternate derivation can be done with the classic triangle diagrams which I've done [here](https://yfralam.github.io/posts/anomalies/pheno/).

[^4]: Forgive the image, for some reason I haven't figured out how to do matrices yet on here.
