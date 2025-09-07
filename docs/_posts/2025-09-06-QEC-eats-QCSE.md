---
layout: post
title: "Is quantum error correction taking over QCSE?"
---

Anecdotally, quantum error correction (QEC) seems like its becoming a very popular topic to research among quantum computing researchers (more on that later). [[Quantum Computing Stack Exchange]](LINK) (QCSE) is a Q&A site for quantum information topics. This post asks, can we find any evidence of a shift in interest towards QEC reflected by trends in QCSE questions?


**Short answer**: Kind of. It seems like the overall user base of QCSE is fleeing, but the rate of QEC questions is holding strong (driven in part by a steady stream of questions about `stim`).

If you categorize questions according to their tag (indicates broadly what the question topic is) and then plot the fraction of QEC-related tags, you find a steep increase:

![QEC question fractions](/assets/2025-09-06/qcse_fractions.png)
*The fraction of questions with a QEC-related is approaching 50%. Shading reflects the confidence interval assuming a Binomial distribution, just to give an impression of variance.*

The issue with this trend is that it is hiding a (huge drop)[https://quantumcomputing.meta.stackexchange.com/questions/669/why-the-lull-in-traffic-is-it-network-wide] in the total number of user questions:


![Total questions asked](/assets/2025-09-06/qcse_totals.png)
*Total QCSE usage has been trending downward in the last 12 months or so, but there's still a steady stream of QEC interest.*

The drop in questions coincides with the `o1` GPT model being released. This makes sense: Reasoning models are usually good at answering basic questions, and even more so when there is a lot of relevant source material available on the internet. But (right now), out-of-the-box generative AI tends to be weak at coding tasks involving packages that are relatively new (e.g. there's few code examples to scrape from stackoverflow). This would explain why at least the tag for `stim` (a popular python package for QEC research) continues to go strong.

However, overall QEC question rates are going strong against a backdrop of decreasing site activity. This is at least _consistent_ with a trend in research interest towards QEC, though its indirect evidence at best since we can't determine how the user base of QCSE divides among researchers versus a broader community of people interested in quantum.

