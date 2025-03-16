+++
title = 'Homology is DEI?'
date = 2025-03-16T14:23:14-05:00
draft = false
description = "A rant on the current situation with academia and politics. Also a short analysis on the NSF grants that were flagged as DEI or neo-Marxist."
slug = ""
authors = ['yasin']
tags = ['physics-nt','life']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}

## Funding Uncertainty
Over the past few months, the current government has taken a hammer to scientific funding in the form of several proposals to cut federal grants. This affects several areas, but especially academia. 

To give an idea of how this usually works, someone will write a grant proposal in year 20XX and send it in to a government committee (for example, the NSF). Then the committee (composed of experts in the field) will take all the grant proposals they received and then rank them. The committee actually doesn't know how many they will be able to fund until congress passes the budget for 20XX++. Once the committee knows how much money they have, they go down the list funding the proposals until they run out of money. 

For example, lets say I get 3 proposals: States \\( \ket \psi\\)  in quantum mechanics ($5),  \\( \mathcal N = 12\\) ) SUSY ($3), and Random walks in video game economies ($10)). I would rank these: 
1) Random walks in video game economies
2)  \\( \mathcal N = 12\\)  SUSY in d=17
3) States \\( \ket \psi \\)  in quantum mechanics.

Then I learn that congress gives me a budget of $14. I can now fund the first two and have to pass on the third. 

As you might imagine, during election years the process is a bit more volatile. Politics is inextricably linked with academia in this way. The people that are elected may support academia and science in general, or we could be in the current situation. 

At the current moment, there is uncertainty on when (and which) federal grants will be disbursed (if at all) which affects both labs (resources to keep them running) and personnel (salaries, travel funding, graduate students, postdocs). 

Personally, I know several people that have been hit by this, either by losing funding or are currently in danger of losing funding. This is also an especially difficult year for admissions into already selective graduate programs. With the uncertainty in funding, on top of the above potential funding cuts, many programs are vastly limiting the number of students they accept, letting none in at all, or even withdrawing offers that have *already* been given out. I know one person that this has happened to.

There's a lot to be said about the current political situation (including the situation on campuses and science in general) but instead, we'll take just a small look at the justification behind this.

## "Woke DEI"
DEIA (Diversity, Equity, Inclusion, and Accessibility) is being targeted as a questionable motivation by the current administration and any program considering "DEI factors" is on the guillotine (See the [official White House statement](https://www.whitehouse.gov/presidential-actions/2025/01/ending-radical-and-wasteful-government-dei-programs-and-preferencing/)). This contributed to the NSF freezing the annual grant review. As of now, any proposal or program that had (or has) "DEI factors" has been red flagged. At UT specifically, we had a program that acted as a mini review course for incoming graduate students that got cut due to these orders as it was technically under the umbrella of "DEI".

Part of the justification of all this is an [investigation led by Ted Cruz](https://www.commerce.senate.gov/2025/2/cruz-led-investigation-uncovers-2-billion-in-woke-dei-grants-at-nsf-releases-full-database) which claimed to **identify 3,400 "woke DEI" grants or grants that "advanced neo-Marxist class warfare propaganda"** which had previously been funded.  They graciously linked to the dataset "[Public Database_Release (1) (1).xlsx](https://www.commerce.senate.gov/index.cfm?a=files.serve&File_id=94060590-F32F-4944-8810-300E6766B1D6)". Instead of doing one of several calculations my collaborators have been asking for, preparing for my qualifier, or doing any real work, I dusted python off to take a look at this data.

Some basic facts:
- There are 3,484 proposals totaling $4,117,435,830.
- Each is split into 4 categories for which it was flagged: "social justice", "race", "gender", or "environmental justice". Note a single proposal can trigger more than one flag, or none at all. The split is:
	> Social justice: 2585
	> 
	> Race: 689
	> 
	> Gender: 1058
	> 
	> Environmental justice: 362
- The overlaps are plotted below (They may be easier to see in light mode):
- ![Graph of number of categories overlapped.](/posts/physics_life/img/overlaps_all.png)
- It's interesting to note that, although one would expect there to be some correlation between the different categories (if one proposal supports race, they would also support gender), there is virtually no correlation between the categories. It seems like whoever made this list found the first thing that flags as DEI and just threw it into that bin.
 ![Correlations of different categories](/posts/physics_life/img/cats.png)
Of course, there are indeed math and physics proposals in this database, 152 total (which is a very small percentage of the total). Lets take a look at some of the advanced scientific research proposals advancing woke DEI and neo-Marxist warfare. Taken from [here](https://www.reddit.com/r/math/comments/1ioo2x9/database_of_woke_dei_grants/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button), I repeat the list and add some others:

**Social Justice Category**
- Elliptic and parabolic partial differential equations
- Isoperimetric and minkowski problems in convex geometric analysis
- Stability patterns in the homology of moduli spaces
- Stable homotopy theory in algebra, topology, and geometry
- Log-concave inequalities in combinatorics and order theory
- Harmonic analysis, ergodic theory and convex geometry
- Learning graphical models for nonstationary time series
- Statistical methods for response process data
- Homotopical macrocosms for higher category theory
- Groups acting on combinatorial objects
- Low dimensional topology via Floer theory
- Uncertainty quantification for quantum computing algorithms
- From equivariant chromatic homotopy theory to phases of matter: Voyage to the edge
- Field theories and holography

**Gender Category**
- Geometric aspects of isoperimetric and sobolev-type inequalities
- Link homology theories and other quantum invariants
- Commutative algebra in algebraic geometry and algebraic combinatorics
- Moduli spaces and vector bundles
- Numerical analysis for meshfree and particle methods via nonlocal models
- Development of an efficient, parameter uniform and robust fluid solver in porous media with complex geometries
- Computations in classical and motivic stable homotopy theory
- Analysis and control in multi-scale interface coupling between deformable porous media and lumped hydraulic circuits
- Four-manifolds and categorification
- Scattering in quantum gravity: symmetries and holography
- Theoretical and numerical investigation of symmetric mass generation

**Race Category**
- Stability patterns in the homology of moduli spaces
- Precision measurement of coherent elastic neutrino-nucleus scattering from reactor anti-neutrinos
**None**
- Theoretical particle physics and cosmology at UC Irving
- Emergent quantum phenomena in epitaxial thin films of topological Dirac semimetal and its heterostructures
Indeed, it is clear that items like "homotopy" or "homology" are clearly just woke DEI initiatives.

In fact several of these proposals just have "DEI" keywords included in their proposals. Including the prior, we have "inclusion maps, representations, inequalities,"  and a host more. Of the 152, there were 49 (~30%) that had "DEI" keywords like the one above within the first few words.

Some facts about this subset:
- The split is:
	> Social justice: 116
	> 
	> Race: 17
	> 
	> Gender: 74
	> 
	> Environmental justice: 3 (So apparently, the physical sciences really don't care about the environment.)

- In all these cost $38,648,187 which is 0.93 % of the total cost.
- The distribution with respect to the  other data is given here (note both axis are log):
-  ![Histograms of costs of grants](/posts/physics_life/img/costs.png)
While its nice to get some gallows humor out of DEI terms in math and physics, realistically, most of these grants were chosen due to some part of them dedicating money to allow access to those that may not have the resources to learning the material. For example, a workshops on the topic that ensures underrepresented individuals have the opportunity to attend. 

These have been the default in grant proposals and generally included under "broader impacts" where the proposal would outline how their work would benefit society outside the field. Now, these proposals need to be either reworded or these parts must be left out.

All in all, academia is in a weird state right now with respect to politics. We'll see what happens going forward.