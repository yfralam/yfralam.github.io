+++
title = 'Borsuk Ulam'
date = 2025-08-26T20:24:26-05:00
draft = true
description = "A project with a friend on looking for points and their antipode on Earth with the same temperature and pressure as expected from Borsuk-Ulam. Plus some words about learning math in general."
slug = ""
authors = ['yasin']
tags = ['coding','physics-nt']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}

This is a companion piece to my friend's post where they talk more about the coding side of this project.

![A screenshot of the Borsuk-Ulam app](/posts/compsci/img/borneo.png)
## Colombia and Borneo sometimes have the same temperature

Recently, for a variety of reasons I'll get into later, I've gotten interested in learning algebraic topology. While going through [this](https://youtu.be/9jgMqz1Dchw?si=vUwpZNWQI1YkYupk) series of lectures, I found one interesting result to be the [Borsuk-Ulam theorem](https://en.wikipedia.org/wiki/Borsuk%E2%80%93Ulam_theorem). It says for a continuous map $$f:S^n \to \mathbb{R}^n , ~\exists x \in S^n \text{ s.t. }f(x)=f(-x).$$ What does this mean in laymen's terms? 

\\(f\\) is a function that eats coordinates on a sphere (say longitude and latitude on Earth) and spits out two numbers (say temperature and pressure). Essentially, if we let \\((\theta,\phi) \\) be coordinates on Earth, $$f(\theta,\phi) = (T,P)~,$$
then we are guaranteed by Borsuk-Ulam that there are *at least* two points on opposite sides of the planet have the same temperature and pressure. The title is an allusion to the fact that (at the time of this post) there seems to be a matching between east Colombia and west Borneo that happens relatively often.

Note that temperature and pressure aren't special here, it's just the mandatory example that must be covered every time Borsuk-Ulam is brought up in a class.

Crucially, the proof of this theorem isn't constructive, it just asserts that there exists a point \\(x\\) on the sphere that does this. 

After the lecture, I thought to myself, "well, it seems like you could code something up to actually find these points for you," and I reached out to my friend to help me. We came up with a [program that looks for these points](https://borsuk-ulam-tp.streamlit.app/) (though honestly I was more there for emotional support). The project turned out even better than I imagined, starting its life as a jupyter notebook and then ending up as a program with an entire dashboard. 

You can learn more about the code and some troubles we faced on his blog. For now, I promised to cover some math.

### A (sketch of the) proof for the circle

I'll try to sketch a proof with as little complicated math as possible. At the very least, one can understand the baby example (\\(f:S^1 \to \mathbb{R}\\) ) with just some knowledge of calculus 1. 

Some notation here. \\(S^1\\) is just the regular old circle. So we are looking for (continuous) functions (basically functions that you can draw without taking your pen off the page) that take in a coordinate of the circle \\(\theta\\) and spit out a number \\(f(\theta)\\). An example would be \\(f(\theta) = \sin \theta\\) .

![Gif of a random function on the circle](/posts/compsci/img/maptos.gif)

Let's take \\(x\\) to be a point on the circle and \\(-x\\) to be a point on the opposite side. In practice, we would take \\(x=\theta\\) and \\(-x = \theta+\pi\\) (180 degrees around the circle). 

We want to show that there exists a point \\(x\\) such that \\( f(x) = f(-x)\\). Let us define $$g(x) := f(x) - f(-x).$$
Here is the key insight: note that when \\(f(x) = f(-x)\\), \\(g(x) = 0\\). Also note that $$g(-x) = f(-x) - f(x) = -g(x).$$
> Let's say you pick a random point on the circle and find \\(g(x)>0\\). 
> 
> The point \\(x\\) you chose does not satisfy \\(f(x) = f(-x)\\). 
> 
> But on the opposite side of the circle, we know \\(g(-x) = -g(x) < 0\\).
> 
> So our function \\(g\\) went from positive on the circle to negative on the circle, which means that at some point, it **must have crossed 0** (intermediate value theorem) somewhere along the circle. \\(\Box\\)

In the gif above, I picked a random function that has sines and cosines. a point and its antipode are plotted. The green line is the function \\(g(x)\\) and when it hits zero, we can see that the circle lights up green.

### A (not even sketch of the) proof for the sphere
The sphere case is analogous, though a bit harder. There are a number of ways to prove it. Instead of ***covering it***, I'll just point to [3blue1brown's](https://youtu.be/yuVqxCSsE7c?si=90Kfi2pUuntoNaso) video which does a better job than I ever could and also has helpful visuals. It also has the benefit of showing how it could be useful in the real world. 

Because my motivation is algebraic topology, I'll give the punchline for the algebraic topology proof. The so called fundamental group \\(\pi_1(S^1) = \mathbb{Z}\\) measures how many ways there are to wrap a circle around a circle and come back to the point you started at. It is isomorphic to the integers.

For instance, \\( \[0\] \in \mathbb{Z}\\) means no wrapping around the circle. \\( \[1\] \in \mathbb{Z}\\) means to wrap around once counterclockwise and \\(\[-1\]\\) clockwise. We can add these just like the integers, \\(\[1\] + \[1\] = \[2\]\\), or just that wrapping around once 2 times is equivalent to wrapping around twice once. In other words: $$ 1+1=2.$$
If we assume that Borsuk-Ulam does **not** hold, it can be shown that you can only wrap around the circle an odd number of times, not an even number of times. This is obviously false, why would I only be able to go around the circle 1,3, or 5 times and not twice? Thus, Borsuk-Ulam must hold \\(\Box\\).