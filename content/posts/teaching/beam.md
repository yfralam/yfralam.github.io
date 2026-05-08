+++
title = 'A simple statics problem'
date = 2026-05-07T21:46:28-05:00
draft = false
description = "A uniform beam has 3 supports and is at rest. How much weight is on the middle beam?"
slug = ""
authors = ['yasin']
tags = ['physics-t','teaching']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}

## The problem

The final problem covered in my undergraduate classical mechanics class by my professor, Artem Abanov, was as follows: 

![picture of system](/posts/teaching/img/ribeam.png)

A  uniform beam of length \\(L\\) and mass \\(m\\) is on 3 supports. There are two supports at either end and one in the middle (\\(x=0,~x=L/2,~x=L\\)). How much weight is on the middle support? 

In other words, what is the normal force, \\(N_C\\), of the middle pivot?

## Solution I

This seems like a simple problem anyone that has taken physics 1 should be able to solve. In fact, one can just guess that each support has an equal amount of weight on it:

$$ N_L = N_R = N_C = \frac{1}{3} mg.$$

However, let us try to show this statement is true by using 1st year physics; balancing torques and forces. As a brief reminder, the net force \\(F\\) and net torque \\(\tau = F\cdot d\\) should be 0. 

By symmetry, we can see \\(N_R=N_L\\). Let us call this \\(N\\). but if you don't believe me, we can choose the center as a pivot point and balance the torques[^1]

$$N_L \frac{L}{2} = N_R \frac{L}{2} \implies N_L=N_R=:N.$$

Then the force equation gives us 

$$ 2N + N_C  = mg.$$


Finally, we can try the torque equation using the left side as a pivot

$$N L +N_C \frac{L}{2} = mg \frac{L}{2}.$$
Simplifying we get 

$$ 2N + N_C = mg.$$
Yikes, this looks familiar. This is *exactly* the same equation we got from balancing the forces. We have 2 unknowns and only 1 equation. 

**Despite the simplicity of the system, this problem *cannot* be solved, it is [*indeterminate*](https://ocw.mit.edu/courses/1-050-solid-mechanics-fall-2004/d9fdb1614653b59fcfc8088da0c3b354_emech5_04.pdf).** 


Indeterminacy does not mean we cannot find a solution, but it does mean that we cannot find a *single, unambiguous, unique solution.* Obviously \\(N_L,N_C,N_R\\) as \\(1/3,1/3.1/3\\) works but so does \\(1/2, 0, 1/2\\) or \\(0,1,0\\). 

The reason is hidden in an assumption we implicitly made at the beginning: we assumed the rod was rigid. In indeterminate systems, we often have to relax this assumption in order to get a consistent answer. The price to pay for this is a more complicated setup.

### Answer I

The real answer is 

> $$N_C = \frac{5}{8} mg,\quad N_L=N_R=\frac{3}{16}mg .$$

In order to get this answer, we need to do some elastics. In particular, we will need [Euler-Bernoulli beam theory](https://en.wikipedia.org/wiki/Euler%E2%80%93Bernoulli_beam_theory)

It seems quite cruel (yet a good lesson) to give us an elastics problem at the end of the course. Undergraduate physics programs usually do not cover elastics in a classical mechanics course (at least in the U.S.) Of course, despite all the time we spent learning mechanics, there is always more to learn in a given subject.

On an unrelated note, this seems to be a great problem to give to students to figure out if they are using AI. They should not be able to get an answer, especially if you explicitly tell them to assume rigidity. If they get 5/8, they are either cheating or not supposed to be in that class.
## Solution II

To get the real solution, we must assume the beam can deform. Euler-Bernoulli theory can be used to calculate the deformation of a beam under a load. It is valid for small deformations, though one can build on it to do more complicated things (time dependence, large deformations, etc.).

I will use the notation on the wikipedia page. Furthermore, I tried to give this problem to AI, but it kept pulling equations out of thin air and not telling me where they came from. Thus, the following derivation is mine and so are any mistakes.

The action for the beam is 

$$ S = \int_0^L dx\left[-\frac12 EI\left(\frac{d^2 w}{dx^2}\right)^2 + q(x)\right] $$ where \\(w(x)\\) is the deflection of the beam up or down, \\(E\\) is the elastic modulus, and \\(I\\) is the 2nd moment of area of the beams cross section. We will take \\(E\\) and \\(I\\) to be constant and they will end up cancelling in the final answer. 

![picture of non-ideal system](/posts/teaching/img/ngbeam.png)

\\(q(x)\\) is the load on the beam. For instance

> - Uniform load implies \\(q(x) = C\\), just a constant across the entire beam. This will be how the weight of the beam is distributed.
> 
> - Load at a point implied \\(q(x) = C \delta(x-a) \\) where \\(a\in \[0,L\]\\) is where the load is. The normal force of the middle support will act as a point. 

The load has units of \\(force \cdot \ell ength^{-1}\\), the analogue of pressure in 1d. 

The Euler-Lagrange equations give us 

$$ EI \frac{d^4 w}{dx^4} = q(x) .$$

Our job will be to solve for the deflection of the beam given it's weight, then the deflection from the middle support, and then assert that they are equal (the middle does not move).

To do this, there are some useful quantities that we can write down. 

> - \\(w\'(x)\\) is the slope of the beam.
> 
> - \\(M(x) = -EI w\'\'(x)\\) is the bending moment in the beam.
> 
> - \\(Q(x) = -(EI w\'\'(x)))\'\\) is the shear force in the beam.

For these to be consistent we have 

$$dQ = -q(x) dx, \quad \text{and } \quad dM = Q(x) dx. $$

Now we have all the tools to solve for deflection.


### Uniform load

We consider a uniform load, the weight of the beam itself. This is 

$$ q_w(x) = \frac{mg}{L},$$
just a constant. Then we can get the shear force by integrating once 

$$ Q(x) = -q_w x + A,$$
and the bending moment by integrating once more
$$ M(x)=-\frac{q_wx^2}{2} + A x +a.$$

To fix \\(A\\), we recognice the physical constraint that the supports at \\(x=0\\) and \\(x=L\\) cannot provide a torque so the support cannot sustain a nonzero bending moment. Thus, we require \\(a=0\\) and

$$M(0) = M(L) = 0 \implies A = \frac{q_wL}{2} = \frac{mg}{2}.$$

Thus, our bending moment is 
$$ M(x)=-\frac{q_wx^2}{2} + \frac{q_wL}{2} x. $$

Now we must solve for the deflection \\(w(x)\\) using 
$$ M(x) = -EI \frac{d^2w}{dx^2}.$$

We have 
$$ - EI w\'\'(x) = -\frac{q_wx^2}{2} + \frac{q_wL}{2} x.$$
Integrating once gets us 

$$-EI w\'(x)=-\frac{q_wx^3}{3!} + \frac{q_wLx^2}{2\cdot2} + B,$$
and once more for 

$$ -EI w(x) = -\frac{q_wx^4}{4!} + \frac{q_wLx^3}{2\cdot3!} + Bx + C.$$
The supports at either end do not allow for deflection so 

$$ w(0) = w(L) = 0, $$

which fixes

$$C = 0 \quad \text{and} \quad B = -\frac{L^3q_w}{4!}.$$

Thus, the deflection due to a uniform load is 

$$ -EI w(x) = -\frac{q_wx^4}{4!} + \frac{q_wLx^3}{2\cdot3!} + -\frac{L^3q_w}{4!}x.$$

Particularly at the middle point, we have 

$$w(L/2) = \frac{5q_w L^4}{384EI}. $$

To state a direction, \\(w>0\\) is a deflection down while \\(w<0\\) is a deflection up.
### Support at a point

The procedure for a load at a point is analogous. This time

$$q_C(x) = -N_C \delta(x-L/2),$$
where the minus sign is to denote a support rather than a load. 

Just as before, we integrate to get 

$$ Q(x) = N_C (-1 + \Theta(2x-L))+A, $$
where \\(\Theta(x)\\) is the Heaviside step function, and once more to get 

$$ M(x) = -N_Cx + Ax + B+\left( N_Cx-\frac{LN_C}{2} \right)\Theta(2x-L).$$

Again, the boundary conditions \\(M(0)=M(L) = 0 \\) give 

$$B = 0 \quad \text{and} \quad A = \frac{n}{2}.$$
Then 

$$ M(x) = -\frac{N_Cx}{2} + \left( N_Cx-\frac{LN_C}{2} \right)\Theta(2x-L).$$
In simpler terms, 

$$M(x) = -\frac{N_Cx}{2} \quad \text{for} \quad x<L/2 $$
$$ M(x) = \frac{N_C(x-L)}{2} \quad \text{for} x\geq L/2.$$

Now we can finally solve for \\(w(x)\\). Integrate to get

$$ -EI w\'(x) = -\frac{N_Cx^2}{2\cdot 2} + C_1 \quad \text{for} \quad x<L/2$$
$$ -EI w\'(x) = \frac{1}{2\cdot 2}N_Cx(x-2L) + C_2 \quad \text{for} \quad x\geq L/2.$$
and once more for 
$$ -EI w(x) = -\frac{N_Cx^3}{2\cdot 3!} + C_1x + D_1 \quad \text{for} \quad x<L/2$$
$$ -EI w(x) = \frac{1}{2\cdot 3!}N_Cx^2(x-3L) + C_2x+D_2 \quad \text{for} \quad x\geq L/2.$$

Our boundary conditions are now

$$w(0)=w(L) = 0\quad \text{and} \quad w_{x<L/2}(L/2) = w_{x\geq L/2}(L/2).$$

The \\(w(0)=0\\) condition sets \\(D_1=0\\). By symmetry about the midpoint, the slope of the beam must be 0. Thus \\(w'(L/2) =0\\) so 

$$-EIw\'(L/2) = 0 \implies C_1 = \frac{N_C L^2}{16}.$$


\\(w(L)=0\\) sets 
$$ D_2 = -C_2 L + \frac{L^3N_C}{6} .$$
Matching at \\(L/2\\) then sets 

$$C_2 = \frac{3 L^2 N_C}{16}.$$

All in all,

$$ -EI w(x) = \frac{1}{48}N_Cx(3L^2 - 4x^2) \quad \text{for} \quad x<L/2$$
$$ -EI w(x) = -\frac{1}{48}N_C(L-x)(L^2-8Lx+4x^2) \quad \text{for} \quad x\geq L/2.$$

Wikipedia already has a nice graph for this case so I will shamelessly copy it here. Note the graph is for a load, so just multiply everything by a minus or flip the graph to get our case. In order from top to bottom we have \\(M,Q,w\\).

![graph of beam with central load](/posts/teaching/img/wiki.png)

We can now solve for the contribution to the midpoint deflection from the point support. 

$$w(L/2) = -\frac{L^3N_C}{48EI}$$


### Answer II

So now we can solve for our answer. The contribution from the uniform weight of the beam at the midway point is 

$$ w_W(L/2) = \frac{5q_w L^4}{384EI} = \frac{5mg L^3}{384EI},$$
and the contribution from the support in the middle is 
$$w_C(L/2) = -\frac{L^3N_C}{48EI}.$$
Because the middle is supported, we require the deflection to be zero. Thus

$$w_W(L/2) + w_C(L/2) = 0 = \frac{5mg L^3}{384EI} -\frac{L^3N_C}{48EI}.$$

Solving for \\(N_C\\), we obtain 

$$ \boxed{N_C = \frac{5}{8}mg.} $$

Thus, we have arrived at the promised answer. 



[^1]: These are technically all vectors, but allow me to be lax about putting directions on all these quantities. The system is one dimensional so I think it should be obvious.
