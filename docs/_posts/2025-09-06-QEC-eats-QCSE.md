---
layout: post
title: "Is QEC eating quantum"
---


Quantum error correction (QEC) is a hot research topic among quantum computing researchers. This is a short analysis of just _how popular_ QEC is.



### QEC eats QCSE?

[[Quantum Computing Stack Exchange]](LINK) (QCSE) is a Q&A site for quantum information topics. Here we see more evidence of a shift in interest towards QEC, as reflected by trends in QCSE questions. Last month, for the first time ever, over half of the questions asked on QCSE were quantum error correction! Is this more evidence that interest in QEC displaced a broader curiousity about quantum computing?

**Not really.** Instead, the overall user base of QCSE is fleeing, while the number of QEC questions is holding strong. This is driven in part by a steady stream of questions about `stim`, a software library for simulating QEC whose creator - Craig Gidney - is very helpful and prolific on QCSE.

If we categorize questions according to their tag (indicates what the question topic is), we find a steep increase in QEC-related tags (left). But this hides a (huge drop)[https://quantumcomputing.meta.stackexchange.com/questions/669/why-the-lull-in-traffic-is-it-network-wide] in the total number of user questions (right):

![QEC question fractions](/assets/2025-09-06/qcse_fractions.png)
*The average fraction of questions with a QEC-related is approaching 50% (shading reflects the confidence interval assuming a Binomial distribution, just to give an impression of variance). Total QCSE usage has been trending downward in the last 12 months, but there's still a steady stream of QEC interest.*

The drop in questions coincides with the `o1` GPT model being released. This makes sense: Reasoning models are usually good at answering basic questions, and even more so when there is a lot of relevant source material available on the internet. But (right now), out-of-the-box AI chatbots are weak at coding tasks involving newer packages (e.g. there's few code examples to scrape from stackoverflow). This would at least explain why the tag for `stim` (a popular python package for QEC research) continues to go strong.

What we see is at least _consistent_ with a trend in research interest towards QEC, though its indirect evidence since we can't determine how the user base of QCSE divides among researchers versus a broader community of people interested in quantum. To focus on researchers specifically, we can take a look at the arXiv.

### QEC eats quant-ph?

If we categorize every `quant-ph` arXiv submission according to keywords appearing in its abstract+title[^1], we can get a _rough idea_ of trends in manuscript topics. After assembling a reasonable set of keywords (see Methods) for QEC-related submissions, and also preparing a set of keywords for "noisy intermediate scale quantum" (NISQ), we see this trend:

![QEC question fractions](/assets/2025-09-06/qec_nisq.png)
*The fraction of arXiv submissions mentioning quantum error correction (and related topics) is trending upwards, while mentions of NISQ have flattened out.*

So, NISQ has lost a bit of steam. But the fantastic growth rate of research in QEC leaves me wondering - what research comes after quantum error correction?

### Bonus: QML is hot

Out of personal curiousity, I took a look at how QEC compares to another hot subfield, "quantum machine learning". Since 2020, the fraction of `quant-ph` submissions involving QML has grown about .7% per year. Even with all the hype and misguided industry plays that QML has a bad reputation for, this growth rate is slightly lower than QEC in the same time period! 

![QEC question fractions](/assets/2025-09-06/qml_fractions.png)


### Methods

The keywords for categorizing `quant-ph` submissions are below. Note that these lists are short, so the trend lines can be thought of as lower bounds. For finding QEC submissions, the token "code" is too cross-disciplinary and gives thousands of non-QEC hits.

```
QEC hits:
	error correct: 3144
	error-correct: 1152
	logical qubit: 830
	fault toleran: 475
	stabilizer code: 510
	surface code: 751
	toric code: 475
	qudit code: 11
	error detect: 172
	quantum code: 651
	convolutional code: 40
	CSS: 287
	color code: 198
	parity check: 133
	logical gate: 242
	logical error: 327
	bicycle: 116
	cubic code: 21
	qec: 8
```
For NISQ, I've used the following barebones keywords. I have not included arguably-NISQ algorithms like VQE and QAOA, because those have sort of become subfields of their own and are not exclusively confined to NISQ devices.

```
NISQ hits:
	intermediate scale: 256
	hardware-efficient: 251
	intermediate-scale: 1176
	error mitigation: 647
	nisq: 1424
	hardware efficient: 41
	zero-noise extrapolation: 70
```

For QML, I kept things straightforward but with the addition of "barren plateau", which has a non-negligble effect on the overall trend.

```
QML hits:
	qml: 374
	quantum neural network: 564
	quantum machine learning: 1265
    barren plateau: 307
```

#### Acknowledgments

I used the `scirate` python package, so thanks to Vincent Russo.

---

[^1]: The entire metadata for arXiv is available on Kaggle: (link)
