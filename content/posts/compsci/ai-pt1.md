+++
title = 'AI, Research, and Why I Left Computer Science(ish) Pt. 1'
date = 2024-09-29T00:57:34-05:00
draft = false
description = "My experience doing research on AI, some general thoughts on where AI is now, and why I decided to leave the field."
slug = ""
authors = ['yasin']
tags = ['artificial-intelligence','physics']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}


## Abstract

As some may know, I completed an undergraduate degree in computer science, primarily focusing on AI and reinforcement learning. Before what I know becomes too outdated, I'd like to detail my experience doing research on AI, some general thoughts and criticisms on where AI research is now, and why I decided to (for the most part) leave the field.

Of course, one should take this entire manuscript with a heavy pinch of salt. Competent individuals should almost always take care to not place much weight on people that speak outside of their fields. Much of what will be said here is opinion, and the scientific remarks may or may not be right (or simply just outdated). I am more than happy to be corrected in discussions.

As the manuscript was getting a bit long, I've decided to split this into two parts, with the first being more my personal experience, and the second being some criticisms and opinions.

## Introduction

I should take some time to set up my (few) credentials and some context. I completed my CS degree at Texas A&M In the Fall of 2022. Up to this point, I was decently involved and kept up with AI research. I was mainly doing work on Reinforcement Learning (RL) under [Yoonsuck Choe](https://yschoe.github.io/); an excellent AI researcher mainly working on AI in the way I envisioned one *should* be doing it, really studying the inner workings of AI through the lens of neuroscience (as opposed to adding 47 more layers to a neural network (NN), spending millions training it, then declaring success). 

To summarize the last part of the title, here are the bullet points of what led me to leave computer science:
>- I simply liked physics more and thought there were deeper, more crucial questions to ask in this field.
>- I did not like the direction AI was going when I was finishing up my degree.
>- It turns out, after three years of suffering through a CS degree, I really, *really* hate coding.

While I was rather confident that I wanted to continue on in physics in grad school, what really cemented this in my brain was an interaction in my AI class. I remember a guest lecturer stood at the podium, asked if anyone here was a physicist, and when I raised my hand, looked into my eyes and said, "I'm sorry to say this, but physics is a dead field, there's nothing more to discover. All future interesting discoveries will be in the field of artificial intelligence". This statement was so preposterous I didn't have the words to reply. Off the top of my head, I could list off a dozen open issue that would have massive implications for our understanding of the universe or technologies. 

At this point I realized that, although AI research was were interesting (and profitable), my heart was really with physics.

Lastly, I never really had the patience for coding. Especially with regards to AI, it always felt like an obstacle to getting the results that I wanted; however, CS is much more than coding, and this point I will save for last.
## My Work

Here I'll detail exactly what I did for research, some good points, and some points where I really dropped the ball. To start off, I need to describe reinforcement learning (RL). 

In my opinion, RL is probably the most robust form of AI and the most likely to provide insight into intelligence or sentience.  It lends itself to experiments and playgrounds very naturally. You can use the framework in real world simulations, video games, or interactions.

As opposed to setups where the problem is a black box:
> - Give the NN an image and it tells us if it is a cat or dog (say [YOLO](https://arxiv.org/abs/1506.02640)),
> - Given a word, predict the next word (say [chat-gpt](https://openai.com/index/chatgpt/)),

the setup for RL has an agent living in an environment. The agent can act on the environment, and in response, the environment can act on the agent.
### Quick Intro to RL

I worked in the subfield of AI called RL. Really I should talk about Markov Decision Processes, but that is too much depth. All you need to know is that the setup consists of an environment \\(\mathcal E\\), an agent that can do some action \\(\mathcal A\\), and a reward \\(\mathcal R\\) that the environment gives the agent depending on whether the agent did something desirable. 
![Rl algorithm](/posts/compsci/img/reinforcement.png)
The canonical example is cartpole (which my friend did an intro to [here](https://vajralakushal.github.io/posts/basic-rl/cart-pole/)). Essentially, the setup is a cart that is trying to balance a pole. When the cart moves to the left or right (does \\(\mathcal A\\) ), \\(\mathcal E\\) sees whether the pole is still balanced or not and gives the agent \\(\mathcal R\\) accordingly. 
![Cartpole robot](/posts/compsci/img/cart_pole.gif)


### Intrinsic Motivation

Note that in the previous example, \\(\mathcal E\\) was responsible for giving a reward. There are also systems where instead of the environment giving the reward, the agent draws a reward from themselves without regards to the the environment. This is called intrinsic motivation. For example, curiosity $$ \mathcal R = 
\begin{cases} 
      0 & \mathcal A \text{ has already been done before} \\\\
      1 & \mathcal A \text{ has never been done before} \\
   \end{cases}
$$ where the agent gets a reward if it does something novel. An interesting exhibition of this can be found [here](https://pathak22.github.io/noreward-rl/), where a group of researcher using intrinsic motivation to train [Mario](https://youtu.be/J3FHOyhUn3A?si=MLqWpekOc8MbTnCh).

Details can be found in [my thesis](https://oaktrust.library.tamu.edu/items/05fef447-455f-475e-b9d4-7c47d879c53e) where I tried to study intrinsic motivation and tried to disentangle intrinsic motivation from extrinsic motivation (actions taken due to feedback from \\(\mathcal E\\) ). I essentially found that spikes in improvement of the agent were correlated (or sometimes even *preceded*) by spike in intrinsic motivation.

I'll save you the trouble of opening the link, I truly think this is a terrible thesis.

### The Bad 
> - I wanted to propose a metric for intrinsic motivation using information theory, but the "metric" is mathematically not even a metric.
> - The environments were too simple: even if the "metric" had worked, the agents did not display complex enough behavior to where one could meaningfully, experimentally, seen a big difference
> - I did not do my diligence for literature review. While not studied explicitly in the context of intrinsic motivation, studies of AI with information theory are certainly not new. I did not take a careful look at these.
> - I spent way too much time trying to think of a theoretical framework in which to work in instead of just coding agents and studying information theoretic quantities of these agents. 

I was much too focused on developing a whole "theory" when I didn't even have any experiments to base my theory off of. In physics, we at least have sacred concepts like like symmetries and unitarity to keep us from writing down anything. For what I was doing, I either did not have these, or didn't know I had these.

In short, I was too ambitious and really didn't know what I didn't know.

### The Good
Despite these short comings, there are a few points in this thesis that are morally interesting.
> - The idea to describe intrinsic motivation with information theoretic is not a bad one.

Instead of jumping straight to trying to define a "metric", it is interesting enough (and I should have) to consider entropies of the agent, environment, and rewards as the system evolves, or the mutual information between them. 

This is the direction my advisor was pushing me towards. Take different agents and environments and just ask what the info quantities look like. Whether by arrogance, or laziness to avoid coding more, I decided to ignore this advice. If I could go back, this is the main thing I would change, and leave finding a "metric" to some future goal. 

> - The model was small enough to where internal dynamics of the agent could studied.

It is said that AI are black boxes to which their inner workings cannot be explained. This is *virtually* true. Todays powerful AI models are so big that trying to describe their internal dynamics is almost impossible. They are, for all intents and purposes, black boxes that we just hit run on and pray work.

I chose rather small agents (In terms of size of NNs) to work with such that I could describe the aforementioned quantities explicitly. While I don't think the approach is new, exploring the internal dynamics of an agent to fully grasp what the (to borrow a phrase from physics) "[moduli space](https://en.wikipedia.org/wiki/Moduli_space)" is, is interesting. 

> - To say a major point in short, it taught me (in hindsight somewhat) several points on how to do/not do research, what questions were good to ask, and how to break a problem into smaller problems.

It was also one of the first forays I had into the difficulties of getting funding and how difficult it was to train AI models on expensive hardware.

## Part 2
In the next section, I have some more general thoughts on AI, criticisms, and CS in general.

