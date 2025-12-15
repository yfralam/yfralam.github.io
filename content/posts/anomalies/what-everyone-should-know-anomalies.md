+++
title = 'What every physicist should know about (gauge) anomalies'
date = 2025-12-14T17:57:37-06:00
draft = false
description = "Anomalies show up in almost every single area of physics, from high energy physics to condensed matter systems and have very observables consequences. I cover some basic things about anomalies as consistency checks of theories. The first part should be accessible to everyone but the second part is aimed at those interested in particles."
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

Symmetries are a guiding principle in physics. They give us an extreme amount of control which we can use to make predictions. A particular class of symmetries called **gauge symmetries** are especially important. They are used to describe the physics of forces. This included electromagnetism, the strong and weak force, and even gravity.

In certain cases, gauge symmetries can be **anomalous**. That is, symmetries at a classical level, may not be symmetries at a *quantum* level. This is a massive issue. 

Gauge symmetries are not "real" symmetries, they are redundancies in description. As an example, in electromagnetism, shifting the vector potential 

$$ \vec{A} \to \vec{A}'=\vec{A} + \nabla \lambda$$ does not change the magnetic field $$\vec{B} = \nabla \times \vec{A}.$$
If the gauge symmetry is broken, there is something seriously wrong with the theory and it cannot be consistent. 

- **In quantum field theory, anomalous gauge symmetries lead to probabilities bigger than one. This means the theory is sick and cannot be consistent as is.** 


1) In a nutshell, symmetries give us conserved currents (see Noether's theorem)
2) This means the divergence of the current should be 0
3) At a quantum level, these currents may not be conserved (divergence is non-zero)
4) The divergence of the currents is proportional to the charges of the particles 

The standard model has gauge symmetries as well. For the standard model to be a "good" theory, all of its gauge symmetries must not be anomalous. Hopefully by the end of this you can see why the standard model has the charges it does.
## Classical and quantum symmetries


For the rest of this, we will pass to a description of quantum field theory. First let us talk about classical symmetries. A simple example is with quantum electrodynamics (where I will drop the \\(F_{\mu\nu} F^{\mu\nu}\\)  term. The Lagrangian is given by 

$$ \mathcal{L} = \bar \psi(i \gamma^\mu[\partial_\mu + ieA_\mu]-m)\psi .$$
Here, \\(\psi, \bar \psi\\) are the fermions (electrons/positrons fields) and \\(A_\mu\\) is the electromagnetic four-potential (the photon), and \\(e\\) is the charge of the electron. 

### Classical symmetries

This Lagrangian has a classical \\(U(1) \\) symmetry. This means it is invariant under the following transformation:

$$\psi(x) \to \psi'(x)=e^{ie\lambda(x)} \psi(x), \quad \bar \psi(x) \to \bar \psi'(x)=e^{-ie\lambda(x)} \bar \psi(x), \quad A_\mu(x) \to A_\mu'(x)=A_\mu(x)-\partial_\mu \lambda.$$
Not the fermions transform with a phase proportional to their charge \\(e\\). In terms of the action, 
$$ S = \int d^4x \mathcal{L} \to S' = S + \delta S = S.$$Let us check this. Doing the transformation, 

$$\mathcal{L}'= e^{-ie\lambda} \bar \psi(i \gamma^\mu\partial_\mu + ie\gamma^\mu(A_\mu-\partial_\mu \lambda)-m)e^{ie\lambda} \psi$$
Simplifying, we get 

$$=i(e^{-ie\lambda} \bar \psi \gamma^\mu \partial_\mu (e^{ie\lambda} \psi(x)) -e\bar \psi \gamma^\mu (A_\mu-\partial_\mu \lambda) \psi -m\bar \psi \psi$$
$$=i \bar \psi \gamma^\mu \partial_\mu \psi -e\bar \psi\gamma^\mu\partial_\mu \lambda \psi - e \bar \psi \gamma^\mu A_\mu +e\bar \psi\gamma^\mu\partial_\mu \lambda \psi - m \bar \psi \psi$$
$$=i \bar \psi \gamma^\mu \partial_\mu \psi - e \bar \psi \gamma^\mu A_\mu - m \bar \psi \psi=\mathcal {L}.$$
We have returned to the same Lagrangian. Note that the charges of the electrons and positrons are chosen in such a way to cancel the \\(e\\) in front of the photon field \\(A_\mu\\). I could not have chosen \\(0.5 e\\) or \\(2e\\). 

One could ask, "If I scale the charges together, shouldn't the Lagrangian be gauge inveriant?" Indeed it would, scaling all the charges together is fine. But imagine if there were more gauge fields and matter fields, all interacting with each other with their own charges. If you scale one set of charges and not other, you may ruin the gauge invariance of another term. With many fields, choosing the correct charges is hard already at the classical level. 

To this symmetry, there is an associated current (you can think about it as the analog of electric current), given by Noether's theorem

$$ j^\mu = \bar \psi \gamma^\mu \psi.$$ It's fine if you don't know where this comes from, the important part is it can be checked that on the equations of motion, the current is conserved, i.e. 

$$\boxed{\partial_\mu j^\mu = 0.}$$ We can take this to mean the symmetry is *fine*. 

- If the current is not conserved (\\(\partial_\mu j^\mu \neq 0\\) ), then the symmetry is broken.

### Quantum symmetries

What would imply the gauge symmetry is broken at the quantum level? Well, all we would need to do is throw the divergence of the current into a correlator 

$$\boxed{\langle \partial_\mu j^\mu \rangle \neq 0 \implies \text{Broken symmetry}.}$$
In quantum field theory, we can concretely compute these and see whether the symmetry is fine or not. 

- They are given by triangle Feynman diagrams.

An alternative way of viewing this is through the path integral (essentially just a partition function). For a symmetry to be non-anomalous, the partition function must be invariant under the gauge transformation 

$$ Z \to Z' = Z.$$The path integral tells us to integrate over all configurations of the fields 

$$ Z = \int D\psi D\bar \psi D A_\mu e^{iS[\psi,\bar \psi, A]}.$$ Under the gauge transformation, 

$$Z \to Z' = \int D\psi' D\bar \psi' D A_\mu' e^{iS[\psi',\bar \psi', A']},$$
but the action is invariant under the gauge transformations so 
$$ Z' = \int D\psi' D\bar \psi' D A_\mu' e^{iS[\psi,\bar \psi, A]}.$$
 From this perspective, we can chalk up anomalies to be due to the non-invariance of the *measure* under gauge transformations 
$$ \text{if } D\psi' D\bar \psi' D A_\mu' \neq D\psi D\bar \psi D A_\mu \implies \text{Broken symmetry}.$$

### Anomaly coefficients

Earlier we mentioned 

$$\langle \partial_\mu j^\mu \rangle \neq 0 \implies \text{Broken symmetry}.$$
There is a general form of this quantity. The left-hand side is always proportional to the *anomaly coefficient*. 

$$\langle \partial_\mu j^\mu \rangle \simeq \sum_{LH}\text{gauge charge}-\sum_{RH}\text{gauge charge}$$
Let us break this up:
- The gauge charges are essentially just the charges of the particles we are talking about under the specific gauge group.
- The sum over LH and RH mean to only sum over the charges of the left hand or right handed fermions.
- For the symmetry to be non-anomalous, the sums of the charges must cancel.

For QED, we wrote the Lagrangian in terms of a Dirac spinor. This means that 
$$\psi = \psi_L + \psi_R$$ so every left handed fermion comes with a right handed fermion. We now have all the information we need to make sure the \\(U(1)\\) symmetry in QED is non-anomalous.

First let us write the charges. We only have to worry about the fermions \\(\psi\\).

| Field        | U(1) charge |
| ------------ | ----------- |
| \\(\psi_L\\) | e           |
| \\(\psi_R\\) | e           |
For a triangle diagram, we need to insert 3 charges. In terms of *anomaly coefficients*, this means we cube the charges

$$\boxed{\langle \partial_\mu j^\mu \rangle \simeq \sum_{LH}Q_l^3-\sum_{RH}Q_r^3 = e^3 - e^3 =0.}$$
So now we have found that the \\(U(1)\\) gauge symmetry survives at the quantum level! A few notes

- QED is "non-chiral". This means there are the same number of left handed and right handed fermions and then have the same charges. Therefore, it is no surprise that the anomaly cancelled.
- We only get the relevant gauge anomalies we are talking about when the theory is "chiral".

## The Standard Model

Above we just saw that chiral theories have the possibility of being anomalous. The Standard Model has gauge group 

$$SU(3)_c \times SU(2)_L \times U(1)_Y$$ and is may be *dangerously anomalous*. Only the left handed fermions transform under \\(SU(2)\\). We now write the charges.

| Field       | SU(3)  | SU(2) | U(1) |
| ----------- | ------ | ----- | ---- |
| \\(Q_L^i\\) | **3**  | **2** | 1/6  |
| \\(u_R^i\\) | **3̅** | **1** | 2/3  |
| \\(d_R^i\\) | **3̅** | **1** | -1/3 |
| \\(L_L^i\\) | **1**  | **2** | -1/2 |
| \\(e_R^i\\) | **1**  | **1** | -1   |
- Here, the first 3 rows are the left handed and right handed quarks. 
- The last 2 rows are the left handed and right handed leptons. 
- The bolded numbers are not charges in the same way as they were in the \\(U(1)\\) case, they denote how the fields transform under the non-abelian symmetries.

Remember that anomalies are given by triangle diagrams and all of these diagrams must be non-anomalous. This means we have to check every combination of 3 currents and every single combination must be non-anomalous, else the standard model would be dead. This would look like checking \[SU(3)SU(3)SU(3)\], \[SU(2)SU(2)SU(2)\], \[SU(2)SU(2)U(1)\], \[U(1)U(1)U(1)\], etc. 

As a sample calculation, let us check that \\(U(1)^3\\) hypercharge is non-anomalous.

$$\langle \partial_\mu j^\mu \rangle \simeq \sum_{LH} Y^3 - \sum_{RH} Y^3 .$$ Here \\(Y\\) are the charges. 

The difficulty is in the sum over fermions. For example, naively one would thing the contribution of the left handed quarks is just \\((1/6)^3\\). This is not that case. There are multiple quarks because there are charged under the other gauge groups. The contribution would instead be 

$$3 \text{ generations} \times 3 \text{ from SU(3)} \times 2 \text{ from SU(2)} \times \left(\frac16\right)^3 = \frac{3}{36}.$$ Hopefully it is clear that the counting can be complicated. Let us go back now.

$$\sum_{ferm} Y^3 = 3\cdot(3\cdot2\cdot Y_Q^3 + 2 \cdot Y_L^3 -(Y_{e}^3 + 3\cdot Y_u^3 +3 \cdot Y_d^3)$$
$$= 3(3\cdot2\cdot (1/6)^3 + 2 \cdot (-1/2)^3 -((-1)^3 + 3\cdot (2/3)^3 +3 \cdot (-1/3)^3)$$

$$\boxed{=0}$$

So the \[U(1)U(1)U(1)\] current is in fact non-anomalous. We still have to check all the other combinations too. The non-abelian calculations are a bit different but the spirit of the calculation is the same.

It is a miracle that **all the anomalies of the Standard Model cancel**. Better yet, to describe the underlying physics we know and observe, there is nothing else we could right down in terms of the charges (up to rescaling everything).

The left handed quarks don't have hypercharge 1/6 because we want them to, they have hypercharge 1/6 because if they didn't, the anomaly would not cancel. It is a very important note that the *electric charges* come from the \\(SU(2) \times U(1) \\) symmetry. Once we fix our units, this is of course something that we can observe.

We can establish the fractional charges of quarks beyond reasonable doubt due to proton-electron collisions such as those at SLAC.

Hopefully it is clear how non-trivial anomaly cancellation is and how they can lead to real predictions. There are most comments that one can find in my blog post [here](https://yfralam.github.io/posts/anomalies/pheno/) as well as some non-abelian calculations. 


