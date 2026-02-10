+++
title = 'Site Updates and Comments'
date = 2026-02-09T21:17:28-06:00
draft = false
description = "Changed comments and other things"
slug = ""
authors = ['yasin']
tags = ['test']
categories = []
externalLink = ""
series = []
enableComments = true
+++
{{< katex >}}


## Updates

Some updates on site specific things. 

1) The name of the blog has been updated to ``Lightly Caffinated`` thanks to a suggestion by my friend Manu.
2) [Utterance](https://github.com/utterance/utterances) for some reason wasn't playing well with LaTeX so I switched to [giscus](https://giscus.app/) . This is for a number of reasons.
3) Comments have also been moved from issues to discussions for more features and easier management.
## LaTeX in comments

LaTeX is now supported in comments. One can use a single $ to make a comment in line (\$2 + 2=4\$) or surround an equation with  \n \$ \$ 2+2=4 \$ \$ \n to make it display (no spaces in between the dollar signs). For display to work, there should be newlines around the display equation. For example
> text 
> 
> \$ \$ 1+1=2 \$ \$
> 
> text

There are still some things that don't render correctly, for example, scripts like \mathbb or \mathcal but if necessary one can import the relevant symbols with Unicode. For your convenience, one can find them here: https://en.wikipedia.org/wiki/Mathematical_Alphanumeric_Symbols

The gold standard would be mathjax but as far as I know, most discussions routed through github don't support this.

The ideal would be to use Discourse as a commenting software. It uses mathjax and one does not need to use github to post comments. Unfortunately, it either costs money to host a 3rd party server or I have to host my own server. Maybe one day I will but for now I can't justify the commitment. 

For now, the comments will have to be regulated by requiring a GitHub account which hopefully isn't too big of a deal.

