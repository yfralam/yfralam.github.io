+++
title = 'Some phenomenology of anomalies'
date = 2025-07-20T13:26:38-05:00
draft = false
description = "A few comments on visible aspects of anomalies."
slug = ""
authors = ['yasin']
tags = ['physics-t']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}


I've recently gotten interested in anomalies for a variety of reasons and more specifically [anomaly inflow](https://arxiv.org/abs/2003.11550), mostly due to an offshoot of a current project. But before diving into things from higher dimensions, SPT phases, and cancellations in depth, I wanted to ground myself in some observable effects. 

I don't say anything new here. Most of what I cover can be found in more depth in [Vadim's notes](https://web2.ph.utexas.edu/~vadim/Classes/2024f-qft/anomaly.pdf) and [Quevado and Schachner's notes](https://arxiv.org/abs/2409.09211) the purpose of this is to rephrase things for my own understanding. Some Feynman diagrams are from there as well.

**Guide**
> The most technical part is QED. 
> 
> On first pass it is good enough to read the physical consequences, baryon and lepton, and standard model sections.
> 
> The section for GS does not go into the mechanism, just discusses why it was a big deal.

## Global Anomalies

### QED

While I don't mean to derive the anomalies, it is worth saying some things about where they come from. Inevitably, the best place to start is QED (where we will unfortunately use Dirac spinors)

$$ Z[A_\mu] = \int \mathcal D \Psi \mathcal D \bar \Psi e^{-S_{QED}[\Psi,\bar \Psi, A]} ~. $$
There is a famous axial anomaly corresponding to 

$$ \Psi \to e^{i \theta \gamma^5}\Psi~, \Psi^\dagger \to \Psi^\dagger e^{-i \theta \gamma^5} $$ such that the current \\(J^5\\) is not conserved past the classical level: 

$$\langle \partial_\mu J^{\mu5} \rangle = \langle\partial_\mu (\bar \Psi \gamma^\mu \gamma^5 \Psi) \rangle \neq 0 ~.$$ In momentum space, this is just 

$$ q_\mu \text{Tr}( \gamma^\mu \gamma^5 S(p)) $$ where \\(S(p)\\) is the propagator for the spinor in the EM background. In terms of Feynman diagrams, this is: 
![Feynman diagram corresponding to axial anomaly.](/posts/anomalies/img/dJ.PNG)


where the diagram with 0 external photons cancels by conservation of momentum \\(q=0\\), the ones with 1 or 3 photons cancel due to charge conjugation symmetry, and the diagrams with \\(n_\gamma >3\\) we can cancel as their superficial degree of divergence shows they are no worse that log divergent. We can shift momenta such that diagrams will end up cancelling.

Adding covariant higher derivative terms for the photon ( \\(\mathcal L \supset F (\partial^2/\Lambda^2)^n ) F\\) ), one can show (as ABJ did) that higher loop effects will cancel.

![The only type of diagram that contributes](/posts/anomalies/img/triangle.PNG)

Thus, we are left with the conclusion that the axial anomaly is *one loop exact*. The only contributions come from the triangle diagrams we know and love. This is a big deal. Almost always the anomaly is one loop exact. In simple terms, the deep reason behind this is that the anomaly is a topological term (as we will see), which takes integer values, and thus, **cannot vary continuously**. 

There is a deeper reason coming from supersymmetry and localization, but we can go down that avenue in the future.

Once we have the diagrams, it is a simple (tedious) exercise to calculate. One finds the total anomaly to be

$$\mathcal M^{\mu \nu} = \frac{e^2}{2\pi^2} \epsilon^{\alpha\nu\beta\mu}k_{2\alpha}k_{1\beta}~. $$

Reattaching the photons, 

$$\langle \partial_\mu J^{\mu5} \rangle = \mathcal M^{\mu\nu} \cdot \frac12 A_\mu(k_1) A_\nu(k_2) = \frac{-e^2}{16\pi^2} \epsilon^{\mu \nu \rho \sigma}F_{\mu\nu}F_{\rho\sigma} ~,$$ where in the last step, we went back to position space. It is now clear this is a topological term.

To preview what we will cover at a later date, one can follow Fujikawa's method to derive the anomalies. Such method clearly shows that the anomaly (in the PI formalism) comes from the non-invariance of the PI measure under the symmetry and presents a clear connection with the geometric nature of the anomalies.

The integral over the anomaly gives the difference in the zero modes of different chiralities. Via Atiyah Singer, one can show this represents an integral of the relevant Chern character 

$$ \nu_+ - \nu_- = \int_M dx \partial_\mu J^{\mu5} = \int_M \text{ch}_2(F)~. $$
Further details can of course be found in Nakahara.


### Negative Magnetoresistance

We have essentially found that 

$$ \partial_\mu J^{\mu5} = \frac{-e^2}{16\pi^2} F_{\mu\nu}\tilde F^{\mu\nu} ~.$$
If we rewrite this in terms of familiar 3-vector E&M, this is 

$$ \partial_\mu J^{\mu5} = \frac{-e^2}{2\pi^2 \hbar^2 } \vec E \cdot \vec B ~,$$
which tells us the divergence of the axial current (difference in the number of left and right handed particles) is not conserved. 

In principle, this is observable, I can construct a parallel plate capacitor with a solenoid inside of it so the e field and b field go the same way.

![Parallel plate capacitor with a solenoid inside of it such that both the B field and E field go in the same direction.](/posts/anomalies/img/capacitor.PNG)

If \\(\nabla \cdot \vec{J}^5 = 0\\), we literally get

$$\dot{Q}^5 = \frac{-e^2}{2\pi^2\hbar^2}\int d^3 x EB~.$$

Indeed, related to the chiral anomaly, one can directly observe negative longitudinal magnetoresistance in Weyl semimetals. Generically (in simple systems), the conductivity is inversely related to the magnetic field (See Ashcroft and Mermin), but In the presence of parallel electric and magnetic fields though, there is a current of charge carriers which reduce the resistance. 
![Experimental data where conductivity spikes when the E field and B field align.](/posts/anomalies/img/weyl.PNG)

Incredibly, this effect was observed experimentally only around the mid 2010's!  The plot above is from [this 2016 paper ](https://www.nature.com/articles/ncomms10735) which worked with TaAs. You can see that the conductivity spikes when the fields are parallel.

Again, just to drive home how incredible this is, this comes from a **one loop anomaly**, a purely quantum effect that we can observe in a modest lab; without smashing two rocks into each other at high speeds).

I should introduce a word of caution. I say "related to the chiral anomaly" because the condensed matter system is more complicated than the anomaly we just described. The crystal structure changes the space and one must be careful with the gauge fields and topology. Nonetheless, the phenomenon exhibits some characteristics we would expect from the anomaly.
### (\\(\pi^0 \to \gamma\gamma\\))

We "derived" the anomaly above for QED but generically, for some non-abelian symmetry generated by \\(T_A\\) and having \\(N\\) fermions 

$$J^{\mu5}[T_A] = \bar \Psi \gamma^\mu \gamma^5 T_A \Psi~,$$which should be taken as a matrix equation, we get 

$$\partial \cdot j^5[T_A] = \frac{-g^2}{16\pi^2}\text{Tr~}( T_A \epsilon^{abcd}F_{ab}F_{cd})~,$$
where the trace is over other quantum numbers.


The poster child of anomalies having observable consequences is \\(\pi^0 \to \gamma\gamma\\). In massless QCD for the quark doublet charged under electroweak, \\(Q\\) with \\(u,d\\) there is a \\(SU(2)\_L \times SU(2)\_R \times U(1)\_V \times U(1)\_A \\). Ignoring the \\(U(1)\\)'s, we essentially have \\(SU(2)\_V \otimes SU(2)\_A) with 

$$j^{\mu5}[T^i] = \bar Q \gamma^\mu \gamma^5 T^i Q~,$$
where the \\(T^i\\) are generators of \\(SU(2)\\). There is a possible contribution to the anomaly from the gluons which we don't need to worry about as \\(\text{Tr}~T^i \lambda^a \lambda^b =0\\) where \\(\lambda\\) are \\(SU(3)\\) generators.

There is however, a contribution from QED. The relevant diagram is

The electric charge operator acts as \\(Q_e = T^3 + Y\\) where \\(Y\\) is the hypercharge. On the quarks, this gives (times e) \\(Q_e Q = \text{diag}(\frac 23,-\frac 13)\\). The full anomaly is then

$$\partial_\mu J^{\mu5}[T^3] = \frac{-1}{16\pi^2}\times 3\times \text{Tr~}(T^3 Q_e^2 \epsilon^{abcd}F_{ab}F_{cd}) = \frac{-1}{16\pi^2}\times 3 \times \frac{e^2}{6}(\epsilon^{abcd}F_{ab}F_{cd})_{EM}~.$$
So how does this lead to the decay?

Let us first note some things about the symmetry. The axial symmetry, if unbroken, would map a hadron to another hadron of the opposite chirality. No such thing exists in nature, so we have experimentally verified that this must be spontaneously broken. Indeed,

$$SU(2)_V \otimes SU(2)_A \to SU(2)_V $$
as the quarks condense \\( \langle \bar Q Q \rangle \neq 0\\). The (psuedo-) goldstones that we get from this are the pions. If one writes down the most general EFT respecting this symmetry, it turns out to be the Effective Chiral lagrangian.

To get the connection to the pions with the current, we must invoke the PCAC hypothesis. Covering it would take (several) more posts so I will just say for more details, there is a wonderful chapter in Sydney Coleman's notes section 41 or Peskin and Schroeder chapter 19.

Essentially, the pions form an isospin triplet and have odd parities. Thus they can be created by the axial current. Then

$$ \langle 0| J^{\mu 5a}(x) | \pi^b(p) \rangle = -i p^\mu f_\pi \delta^{ab}e^{-ipx}~. $$ a,b are isospin indices and \\(f_\pi=93 MeV\\) is the pion decay constant. Of course, one can then see that the divergence of the LHS will give a \\(p^2\\) on the RHS. 

We can write 

$$J^{\mu 5}[T^3] = -f_\pi \partial^\mu \pi^0 + \text{multi-pions}~.$$
Taking the divergence (and putting mass back in)

$$\partial_\mu J^{\mu 5}[T^3] = -f_\pi (\partial^2 +m_\pi^2) \pi^0 + \text{multi-pions}=\frac{e^2}{32\pi^2}(\epsilon^{abcd}F_{ab}F_{cd})_{EM}.$$This is just the EOM for \\(\pi^0\\). To get this, the effective lagrangian would need a term of the form

$$ \mathcal L \supset \sim \frac{ e^2}{f_\pi}\pi^0 F \wedge F. $$
Thus we see that there is a decay channel for the process in question. A direct computation of the scattering amplitude yields

$$\mathcal M(\pi^0 \to \gamma \gamma) = -8 \frac{e^2}{32\pi^2 f_\pi}(\epsilon^{abcd}(k_a e_b^\*)_1(k_c e^\*_d)_2~.$$

One can open up the PDG and find that this process occurs with branching 99%. The other 1% is largely \\(\pi^0 \to e^+ e^- \gamma\\).

## Chiral Anomalies (Baryon and Lepton)
The standard model is a chiral theory. The left handed quarks and leptons are in the **2** of \\(SU(2)\\) while the right handed are singlets. For chiral theories,

$$\delta \psi_L = i \epsilon T_L \psi_L~,\quad \delta \psi_L = i \epsilon T_R \psi_R$$

In the same way as before (triangle diagrams), one finds generically for a non-abelian theory

$$ \partial \cdot J^a = \left(\sum_{l} A(R_l) - \sum_r A(R_r)\right) \frac{g^2}{128\pi^2} d^{abc} \epsilon^{\mu\nu\alpha\beta} F_{\mu\nu}^b F_{\alpha\beta}^c$$

where the sum is over the left(right) handed Weyl fermions and \\(A(R_l)\\) is the anomaly coefficient under representation \\(R_l\\) (\\(A(R_r)\\) with \\(R_r\\)) and \\(d^{abc} = 2 \text{Tr} T^a{T^b,T^c}\\).

In more concrete terms, with non-abelian generators \\(t^a = \frac12 \lambda^a\\), the anomaly is  

$$ \partial \cdot J = \left(\text{Tr}\_{LHWF}(T_L t^a t^b) - \text{Tr}\_{RHWF}(T_R t^a t^b)\right) \frac{g^2}{32\pi^2} \epsilon^{\mu\nu\alpha\beta} F_{\mu\nu}^a F_{\alpha\beta}^b ~.$$

If there is an imbalance between the left and right charges, the current may be anomalous. This leads to interesting consequences.

### Lepton and Baryon number anomaly

If we look at \\(SU(2)\\) weak, we know the right handed quarks and leptons do not transform. Then the RHWF trace from above just gives 0. For any chiral symmetry, 

$$ \partial \cdot J^a = \text{Tr}\_{LH doublets}(T_L) \frac{g_W^2}{64\pi^2} \epsilon^{\mu\nu\alpha\beta} F_{\mu\nu}^a F_{\alpha\beta}^b ~.$$The standard model has a \\(U(1)\\) lepton symmetry where leptons have charge +1 and quarks are uncharged. There are three doublets, \\((\nu_e,e^-), (\nu_\mu, \mu^-), (\nu_\tau,\tau^-) \\) with +1 and 9 quark doublets with 0. Then 

$$ \text{Tr}\_{LHWF}(L) =3 \times 1 + 9 \times 0 = 3$$

and therefore, lepton number *is in fact anomalous.* 

One can play the same game for Baryon number. Quarks have 1/3 and leptons have 0.

$$ \text{Tr}\_{LHWF}(B) =3 \times 0 + 3 \times 3 \times \frac13 = 3~.$$

One can calculate the net change in baryon or lepton number 

$$\Delta = \int d^4x \partial \cdot J[B,L] = 3 \times I \in 3 \mathbb Z$$
\\(I\\) is the topological term from before that takes integer values. Here it has interpretation as an instanton which signals tunneling between different vacua. This essentially maps between different superselection sectors, adding or subtracting 3 baryons or leptons.


### Physical Consequences 

- Experimentally, the \\(\pm 3\\) B number would allow processes like $$\text{deuteron} \to \text{antiproton + 3 positrons}$$b ut would be exponentially suppressed \\(\sim 10^{-81}\\) so we will probably never see it in places like the LHC.

- In general, writing terms that violate lepton or baryon number is useful. One can try $$ \mathcal L_{SM} \supset \frac{1}{\Lambda} \ell \ell H^\dagger H^\dagger $$ which would give neutrinos mass. Terms like \\( qqq\ell, q \bar{u^c} \bar{d^c},q \bar{u^c} \bar{d^c}\ell, u^c u^c d^c e^c \\) would allow for proton decay.

- Note that while B and L are anomalous, \\(B-L\\) is perfectly fine. It is very hard to write down terms that violate B or L separately while obeying B-L and they are usually very high dimension.
	- In principle B-L should also be broken somewhere along the way at high enough energies. There should be no global symmetries in quantum gravity.
- The situation above can be related to sphalerons in minkowski space. They could have been made in the early universe and allow for Leptogenesis to explain the baryon-antibaryon asymmetry we see IRL.

## Gauge Anomalies

The gauge anomalies actually take the same form as the Chiral anomalies. We would just take \\(T\\) to be a generator of the gauge group. There is one *massive* difference though: gauge symmetries aren't really "symmetries", they are redundancies of our description. It does not make sense for them to be anomalous. They usually lead to a breakdown in unitary. 


If you find a gauge symmetry is anomalous, something has gone horribly, *horribly*, wrong. You are completely dead in the water (or SOL) and need to go back to the drawing board.  

### The beauty of the standard model

Let's say I have been handed the entire standard model in all its chiral glory. I've been told that it has $$ SU(3)_C \times SU(2)_W \times U(1)_Y $$and that the matter content has all kinds of charges. Some of the quarks and leptons are charged under electroweak, some aren't. The hypercharge's look weird, and there's a Higgs floating around somewhere...

Naively it seems hopeless that this specific set matter transforms correctly enough in order to cancel all the gauge anomalies but if god is in his heaven the anomalies **must** cancel.

And miraculously, it does! The standard model is *completely* free of anomalies! All of the gauge symmetries (all the triangle diagrams I can write down) are non-anomalous. 

It is not just so simple as to the traces individually giving 0 (although this happens sometimes), the charges are set up in such a way that everything cancels non-trivially! The \\(u_R\\) quark doesn't have hypercharge +4/3 because I want it to, it is because it *has* to be +4/3. And I can verify this **experimentally**.

Even when I couple gravity and look at triangle diagrams with two gravitons, there is *still* no anomaly.

![Feynman diagram corresponding to chiral anomaly with gravitons.](/posts/anomalies/img/grav.PNG)

The standard model is absolutely beautiful. For matching with experiment and seeing all the specifies of matter and forces that we do, there is **nothing else I could have written down.**

### Green and Schwarz

While the standard model is lovely, it is not UV complete (\\(U(1)\_Y\\) has a Landau pole which kills the theory just below the Planck scale). It cannot answer questions about the early universe or black holes or deep quantum gravity questions. Not to mention, the Einstein Hilbert action is non-renormalizable.

This gives some inkling on the difficulty of building a consistent theory of quantum gravity which is good up to arbitrarily high energies.  For the standard model, we put the matter and gauge fields in, then had to go *back* to make sure it wasn't anomalous. 

For a theory of quantum gravity, I have to worry about the gauge anomalies, *and* the anomalies that might come from diffeomorphism invariance. Gravity is after all, a type of gauge theory. The underlying physics should not depend on the coordinates I choose.

But I have no idea what the full spectrum of the theory is, I don't know all the gauge group representations, and I don't know how they transform under gravity at all energy scales because I have no idea what quantum gravity looks like at high energies.

The situation is essentially hopeless. I have no idea where to even start.

This is what makes the Green-Schwarz anomaly cancellation in string theory such a big deal. It is a *built in* mechanism  for canceling anomalies. By including the Kalb-Ramond field in string theory, one can exactly cancel the all of the anomalies that would have been present. 

Instead of trying to guess what the matter content is first and then praying for anomaly cancellation, I am handed a UV complete, anomaly free theory from the start with matter specified. *Then* I can try and drive down to the low energy limit and try to get the standard model and it is guaranteed to be consistent.

This is the calculation that launched the first superstring revolution.


In a follow up we'll discuss anomaly polynomials, relations to topology, and anomaly descent.
