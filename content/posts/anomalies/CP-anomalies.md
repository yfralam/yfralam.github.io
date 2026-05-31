+++
title = 'Global CP Anomalies and Pin'
date = 2026-04-30T16:13:02-05:00
draft = false
description = "Some discussion on addressing the strong CP problem and gauging CP. Also some discussion on ongoing work generalizing to more interesting setups. Also a short appendix on pin+ vs pin-."
slug = ""
authors = ['yasin']
tags = ['physics-t']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}


## Strong CP problem

The Standard Model's QCD sector has a CP problem in the sense that a \\(\theta\\) angle term,

$$ \mathcal{L}_{QCD} \supset \frac{\theta g^2}{32 \pi^2} F \tilde F, $$ is allowed in the Lagrangian. This term breaks CP symmetry. Despite this, the effective \\(\theta\\) angle (with contribution from the quarks) is experimentally determined to be almost 0:

$$ \theta_{eff} < 10^{-10}.$$

Experimentally this is determined from the neutron electric dipole moment 

$$d_N = (5.2\times 10^{-16} \text{ e}\cdot\text{cm}) ~\theta_{eff}$$ where the current value lies at \\(d_N < 10^{-26} \text{ e}\cdot\text{cm}\\). The theta term is purely a topological term and has no contribution from perturbation theory. Thus, this is an interesting manifestation of non-perturbative physics.

There are a whole host of solutions to the strong CP problem (why the angle is so close to 0), chief among them are axions (which are also a dark matter candidate) through the Peccei-Quinn mechanism. 

Another possibility is that CP is an exact symmetry in the UV but then spontaneously broken in the IR. In this case, we can consider the case where CP is a gauge symmetry[^1]. Before we can even discuss this scenario, we must discuss anomalies. Gauge symmetries must not have any anomalies, else the theory is broken[^2]. Thus, we must first check that there are no local, and more importantly for CP, nor global anomalies. 

## No global CP anomalies

This is indeed what Yonekura[^3] did in his [recent paper](https://arxiv.org/abs/2602.11475). The key piece of information is the following:

Normally, the Lorentz group is taken to be \\(SO(d)\\). However, when there are fermions, one must lift to the group \\(Spin(d)\\), the double cover of \\(SO(d)\\)[^4]. Even when there are no fermions, one can choose \\(Spin(d)\\) as the symmetry; this is nothing more than a choice of theory, just as one can choose the gauge group \\(G\\) for a theory. 

We can consider a theory with gauge group \\(G\\). Before gauging CP, the symmetry of the theory is \\(Spin(d) \times G\\). When we gauge CP, the relevant symmetry to study is then 

$$ Pin^+(d) \ltimes G.$$
Here, just as \\(Spin(d)\\) is the double cover of \\(SO(d)\\) , \\(Pin(d)\\) is the double cover of \\(O(d)\\), we just got rid of the "special '\\(S\\)' ". 

The group \\(O(d)\\) has a reflection operator \\(\tilde R\\) which obeys \\(\tilde R^2 =1\\). If I reflect across an axis, then reflect again, it is as if I didn't reflect at all. Because \\(Pin^+\\) is the double cover of \\(SO(d)\\), there are two elements that map to the same \\(\tilde R\\), 

$$ \pi : Pin^+(d) \to O(d), \quad \pi(R_1) = \tilde R, \quad \pi(R_2) = \tilde R. $$
The plus is to signify that \\(R_1^2 = R_2^2 = 1\\). In \\(Pin^-\\), it would square to \\((-1)^F\\).

The result is the following:

**In \\(d=4\\), take the gauge group \\(G\\) to be connected and simply connected \\(\pi_0(G) = \pi_1(G) = 0\\). Suppose there are no anomalies before gauging CP (G is anomaly free), then there is no new anomaly for the symmetry \\(Pin^+(4) \ltimes G\\) after gauging CP.** 

This is good new for the phenomenologists. Among the theories that this works for, we have the standard model, \\(SU(5)\\), and \\(Spin(10)\\) GUTS. the various string theory realizations of these models are also fine.

Because any CP anomalies would be global (they do not contribute to triangle diagrams), the proof involves a careful consideration of what it means to gauge CP (what the relevant principal bundle is), Dai-Freed anomalies,[^5] and the relevant bordisms.

## What about Pin^- ?

The above discussion works for \\(Pin^+\\), but what about \\(Pin^-\\)? This question is interesting for top down model building and inflow but my colleague, Sanjay, suggested it may be interesting for phenomenological reasons. This is because **to have a \\(Pin^-\\) structure, one needs an even number of fermions.** 

The standard model has 15, but when the right handed neutrinos are thrown in[^6], there are 16. It is worth considering whether we can gauge CP with a \\(Pin^-\\) structure when we have an even number of fermions. 

It turns out that by following Yonekura, we can indeed show that for theories with 

$$Pin^-(d=4)\ltimes G$$ symmetry, there are no anomalies once we gauge CP. Therefore (representation permitting), if we throw the right handed neutrinos into the standard model we can gauge CP no problem, no matter the Pin structure we choose[^7]. 

While the choice of pin structure is global data, it will change model building (from string theory, compactifications, etc.) and inflow arguments (Bordisms would need to have a \\(Pin^-\\)) structure; it also has [experimentally observable implications](https://arxiv.org/abs/math-ph/0012006). Taking a look at top down models is an interesting next step, as is looking for any mixed anomalies with the discrete subgroup of B-L found in [here](https://arxiv.org/abs/1808.00009) for the Pin+ case.  

We're in the middle of having conversations with Yonekura and I'm quite excited to see where this goes.

## Math appendix: Pin+ vs Pin-

Just as \\(Spin(d)\\) is the double cover of \\(SO(d)\\), \\(Pin(d)\\) is the double cover of \\(O(d)\\). There exist nice short exact sequences  

$$
0 \to \mathbb{Z}_2 \xrightarrow[\iota]{} Spin(n) \xrightarrow[\pi]{} SO(n) \to 0 ,
$$

and  

$$
0 \to \mathbb{Z}_2 \xrightarrow[\iota]{} Pin^\pm(d) \xrightarrow[\pi]{} O(d) \to 0  .
$$

Any element of \\(O(d)\\) can be written as \\(\tilde M \in SO(d)\\) and \\(\tilde M \tilde R\\) where \\(\tilde R \in O(d)\\). We label the image of \\(\mathbb{Z}_2\\) as \\(\text{im}(\iota)=\{1,(-1)^F\}\\). Then this is also \\(\ker{\pi}\\).  

For a given \\(\tilde M\in SO(d)\\), there are two elements in \\(Spin(d)\\) that project down to the same \\(\tilde M\\). Let \\(M\in Spin(d)\\), then \\(\pi(M)=\tilde M\\) and \\(\pi(((-1)^F) M)=\tilde M\\) as \\(((-1)^F)\\) is in the kernel of \\(\pi\\). \\(((-1)^F)\in Spin(d)\\) is the “\\(2\pi\\)” rotation colloquially.  

Now consider \\(\tilde R_n \in O(d)\\), there are two elements in \\(Pin(d)\\) that map onto the same \\(\tilde R_n \in O(d)\\). They are \\(R_n\\) and \\(((-1)^F) R_n\\). However, in \\(O(d)\\), \\(\tilde R_n^2=1\\). Thus, in \\(Pin^\pm(d)\\), we have a choice of whether \\(R_n\in Pin^\pm(d)\\) obeys \\(R_n^2 = \pm1\\), after all, both branches get mapped to identity  

$$
R_n\in Pin^+(d) \implies \pi(R_n^2) = \pi(1) = 1,
$$

$$
R_n \in Pin^-(d) \implies \pi (R_n^2)=\pi(((-1)^F)) = 1  .
$$





[^1]: The folklore is there are no global symmetries in theories of quantum gravity. Thus, it is natural to consider CP as a gauge symmetry instead of a global symmetry.

[^2]: See [this]() for a high level introduction to (local) anomalies.

[^3]: He also seems to be a very nice guy. He responded to our email immediately and with nice positive feedback.

[^4]: As an example \\(Spin(3) \cong SU(2)\\) which is the double cover of \\(SO(3)\\).

[^5]: I have note yet made a blog post describing Dai-Freed anomalies yet but will get around to it eventually. If one is interested, Yonekura gives the nicest introduction to Dai-Freed that I have seen in the paper above. 

[^6]: There is very good motivation for the right handed neutrinos. Among them, neutrinos have a mass. Additionally, it has been shown that there is an anomaly in a discrete subgroup of B-L which can be removed by the inclusion of the right handed fermions. 

[^7]: One needs to be a bit careful about these statements. The pin- structure and the necessity that there must be an even number of fermions makes selecting the representations of the gauge group subtle. Getting *just* the standard model out is a bit subtle but can be done. 
