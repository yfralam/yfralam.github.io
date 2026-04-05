+++
title = 'AI will always hallucinate'
date = 2026-04-04T19:06:57-05:00
draft = false
description = "A short discussion of the paper by Kalai et al. The prove some lower bounds on the hallucinations of LLMs (large language models) in general and show that even in the best case scenario where a corpus has absolutely no errors, there will always be some probability for LLMs to generate false information. For certain unlearnable concepts, the upper bound (P(error) <=1) may be saturated. With some human/external input in post-training, some of these hallucinations can be mitigated."
slug = ""
authors = ['yasin']
tags = ['artificial-intelligence']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}

## Base LLMs will always hallucinate
A paper came out a few months ago, [*Why Language Models Hallucinate*](https://arxiv.org/abs/2509.04664) by the OpenAI group[^2] where they proved for base language models (LMs that haven't gone through post-training[^1]), hallucinations are inevitable. Hallucinations are when LMs like ChatGPT generate a document or set of text that seems plausible, but turns out to have inconsistencies or are incorrect. We call these generative errors. Examples are as follows:
- **Prompt:** How many D's are in DEEPSEEK? **Output:** 2
- When LMs generate false references when you ask for sources. This one is particularly harmful to academics and a waste of time.
- When LMs answer a question confidently (bluff) but are incorrect. For instance, guessing someone's birthday incorrectly. 

It turns out the reason for the hallucinations are due to statistical factors contributing to errors in a simpler binary classification problem. The binary classification problem is whether a set of text or string of words is correct or incorrect. The main result is *Theorem 1* which we can roughly state as 

$$ \text{generative error rate} \gtrsim 2\cdot \text{binary misclassification error}. $$

In post-training, it may be possible to reduce the hallucination rate and the authors comment on why they (at the current moment), survive post-training.

*Disclaimer: One should always be wary about listening to someone talking outside of their field. Not just in their experience in the field, but in their ability to choose a relevant and good article. I'm talking about this article because it has many citations and the authors seem credible. I primarily discuss the mathematical results but underlying subtleties about the field may be lost on me. The best resource is to read the paper or watch the IAS talk yourself or talk to someone working in the field. I am more than happy to be corrected by a scientist working in the field.*

## The inequality

The generative errors (hallucinations) are the set of plausible strings which contain "incorrect" information. On the LHS, the generative error rate is the probability that the LM will produce a hallucination. On the RHS of the inequality, the binary classification formally considers *Is-It-Valid* (IIV) classification which has a training set that has a training set of strings that are correct or wrong. Whether a string is considered correct or incorrect can depend on spelling, counting, or objectively correct information. I've taken the following figure straight from their paper. 
![Errors in binary classification.](/posts/compsci/img/Capture.PNG)

Note that the response "IDK (I don't know)" is  perfectly valid correct response. 


- The model on the LHS of the inequality outputs strings of words.
- The model on the RHS of the inequality outputs whether a string of words is correct or incorrect.

It can be shown that the RHS will be almost surely[^3] be greater than zero and in fact the classification error may be almost 1/2. This is the worst case scenario as randomly guessing would give me 50/50. 

There really is no way to get out of the bound above. The fact that LMs can generate hallucinations originate in errors of the binary classification problem. If incorrect statements cannot be distinguished from facts, the binary classification model will inherently make errors and so will the generative model. 

Whether LMs are just "stochastic parrots" is a separate discussion but I think this bound is relevant. 

## Post-Training

Despite this, one can try and do some post-training. This is indeed why the hallucination rate seems to have dropped and we don't see as many of the following errors:

![Errors in binary classification.](/posts/compsci/img/error.PNG)
 When I turn on thinking, this issue goes away (at least for the words I took).

Still, despite the post-processing, LMs still hallucinate and often refuse to say IDK. The authors claim this is due to existing benchmarks preferring hallucinations as opposed to IDKs. 

Binary evaluations of language (the current norm) don't give credit for IDK answers so it is always at an LMs advantage to attempt a guess. Abstaining from an answer is sub-optimal. The answer seems to be to just penalize wrong answers more than IDKs but this is a difficult balancing game. It is known in the literature that LMs can take the easy way out and give IDKs to almost every response. 

The analogy that they give are with test takers (and LMs in evaluations are indeed taking tests). In the SAT, one is not penalized for guessing an incorrect answer. In other tests like the JEE, incorrect answers are penalized and the student has to think about whether it is worth guessing.

For now, until a better balancing act is put forth, LMs will continue to hallucinate.

## Technical result of the inequality

This section may be skipped.

Let us describe explicitly the LHS and RHS. A **base model** \\(\hat p\\) is a probability distribution on a set \\(\mathcal X\\). An element \\(x\in \mathcal X\\), an **example**, is a plausible string, document, set of words, etc. This is a possible output the LHS could generate. These examples have errors \\(\mathcal E\\) and valid example \\(\mathcal V\\) so \\(\mathcal X = \mathcal E \cup \mathcal V\\). Then the generative error rate is

$$\text{err}:= \hat p(\mathcal E) = \text{Pr}_{x\sim \hat p}[x\in\mathcal E],$$
the probability that an example drawn from the distribution belongs to the error set.

The training distribution is denoted at \\(p\\) and ideally \\(p(\mathcal E) = 0 \\), i.e. there are no errors in the training distribution. A perfect model would have \\(p = \hat p\\). The paper makes the assumption that the training distribution is perfect so *in the real world, the error rate would be even higher*.

On the RHS, the classifier is specified by 

$$ f:\mathcal X \to \{-,+\},~ f(x\in\mathcal V) = +,~f(x\in\mathcal E) = -$$ which takes an example and classifies it into correct or incorrect. The distribution examples are drawn from \\(D(x)\\), are 50% samples from \\(p\\), and 50% uniform random errors. On the RHS the error of the binary misclassification is 

$$ \text{err}\_{iiv}:= \text{Pr}\_{x\sim D}[\hat f(x) \neq f(x)], $$
where 

$$\hat f(x):= \pm \text{ if } \hat  p(x) \gtrless 1/|\mathcal E| .$$ This statement is just saying that \\(\hat f\\) returns + if the probability of the example \\(x\\) is greater that some percentage of the number of errors. If \\(|\mathcal E| =5\\), as long as the probability of \\(x\\) is more than \\(1/5\\), the answer is correct.

The main statement is given in Corollary 1:

*For a perfect training distribution \\(p\\) and base model \\(\hat p\\),*

$$\text{err} \geq 2\cdot \text{err}_{iiv} - \frac{|\mathcal V|}{|\mathcal E|} - \delta, $$
where the last two terms on the RHS are small. The delta is simply the difference in pulling an example out out the bag between the training distribution and model distribution. One can show it is generically small.

An important point is all base models will error on inherently unlearnable IIV facts where \\(\text{err}\_{iiv} \\) is large. For example, if the birthday for the person we are asking for is absent from the training data. There are 364 times more incorrect claims than the correct one. In the case where the size \\(|\mathcal E|\\) is large and \\(\delta\\) is small, \\(\text{err}\_{iiv} \sim 1/2\\) and the error rate of the model may be close to \\(1\\).

It is worth pointing out that even if the model is provided with all of the objectively correct information, there are inherently things that cannot be know like [undecidable problems](https://en.wikipedia.org/wiki/Undecidable_problem). The bound here is a strong statement as the IIV will always have inherently unlearnable facts. They show the bound is nontrivial even if there are only one correct answer per prompt (the IDK answer) or if the size of errors is 1.





[^1]: Connecting the LM to external resources including humans, databases, calculators, etc. and giving hard coded instructions.

[^2]: Also see the IAS talk [here.](https://youtu.be/0dRouBLcvMs?si=2lvoYAo9Z9YnzMTO)

[^3]: In the colloquial sense.
