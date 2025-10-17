---
layout: post
title: "Is QEC eating quantum?"
---


Quantum error correction (QEC) is a hot research topic among quantum computing researchers. This is a short analysis of just _how popular_ QEC is.

### QEC eats QCSE?

Quantum Computing Stack Exchange ([QCSE](https://quantumcomputing.stackexchange.com/)) is a Q&A site for quantum information topics. Here we see more evidence of a shift in interest towards QEC, as reflected by trends in QCSE questions. Last month, for the first time ever, over half of the questions asked on QCSE were quantum error correction! Is this more evidence that interest in QEC displaced a broader curiousity about quantum computing?

**Not really.** Instead, the overall user base of QCSE is fleeing, while the number of QEC questions is holding strong. This is driven in part by a steady stream of questions about `stim`, a software library for simulating QEC whose creator - Craig Gidney - is very helpful and prolific on QCSE.

If we categorize questions according to their tag (indicates what the question topic is), we find a steep increase in QEC-related tags (left). But this hides a [huge drop](https://quantumcomputing.meta.stackexchange.com/questions/669/why-the-lull-in-traffic-is-it-network-wide) in the total number of user questions (right):

<div style="display: flex; justify-content: center;">
  <img src="/assets/2025-09-06/qcse_fractions.png" alt="QEC question fractions" style="width: 80%; max-width: 800px;">
</div>

<div style="width:80%; margin:auto; font-size: 0.9em;">
  <em>
    The average fraction of questions with a QEC-related tag is approaching 50% (shading reflects the confidence interval assuming a Binomial distribution, just to give an impression of variance). Total QCSE usage has been trending downward in the last 12 months, but there's still a steady stream of QEC interest.
  </em>
</div>

<br>

The drop in questions coincides with the `o1` GPT model being released. This makes sense: Reasoning models are usually good at answering basic questions, and even more so when there is a lot of relevant source material available on the internet. But (right now), out-of-the-box AI chatbots are weak at coding tasks involving newer packages (e.g. there's few code examples to scrape from stackoverflow). So the tag for `stim` (a popular but recent python package for QEC research) continues to go strong.

This is at least _consistent_ with a trend in research interest towards QEC, but its indirect evidence since we can't determine how the user base of QCSE divides among researchers versus a broader community of people interested in quantum. To focus on researchers specifically, we can take a look at the arXiv.

### QEC eats quant-ph?

If we categorize every `quant-ph` arXiv submission according to keywords appearing in its abstract+title[^1], we can get a _rough idea_ of trends in manuscript topics. After assembling a reasonable set of keywords (see Methods) for QEC-related submissions, and also preparing a set of keywords for "noisy intermediate scale quantum" (NISQ), we see this trend:

<div style="display: flex; justify-content: center;">
  <img src="/assets/2025-09-06/qec_nisq.png" alt="NISQ vs. QEC" style="width: 80%; max-width: 600px;">
</div>

<div style="width:80%; margin:auto; font-size: 0.9em;">
  <em>
	The fraction of quant-ph arXiv submissions mentioning quantum error correction (and related topics) is trending upwards, while mentions of NISQ have flattened out.
  </em>
</div>

<br>

So, publication activity in the area of QEC and fault tolerance is blowing up super-exponentially (as evidenced by a sharp increase in the _fraction_ of an already exponentially growing number of `quant-ph`). Meanwhile, NISQ has lost a bit of steam (now what are we supposed to do with all these noisy uncorrected qubits?). 

While counting `quant-ph` submissions is a decent proxy for what researchers are interested in and spending time on, it doesn't tell us whether QEC is _cool_. 

### QEC eats Scirate?

[Scirate]() is an online ~~popularity contest~~ platform that lets people upvote and comment on arXiv submissions. It is used almost exclusively by the quantum computing research community. Usage of scirate is growing rapidly, as the number of `quant-ph` submissions balloons beyond what is easily skimmable in a daily email[^2]. I don't really know what an upvote on Scirate means[^3], but to match the social media theme of the site, we will say a paper is _cool_ if it gets a nontrivial number of upvotes on Scirate, and _uncool_ otherwise[^4]. 

<div style="display: flex; justify-content: center;">
  <img src="/assets/2025-09-06/qec_scirate.png" alt="QEC scirate question fractions" style="width: 80%; max-width: 600px;">
</div>

<div style="width:80%; margin:auto; font-size: 0.9em;">
  <em>
	Among papers that get attention (at least 5 upvotes) on Scirate, QEC represents a growing fraction. It is a cool subfield. In contrast, NISQ is becoming less-cool even as its overall publication rate holds steady.
  </em>
</div>

<br>

Here, we can see here that QEC-related manuscripts make up a growing fraction of cool submissions[^5]. Furthermore, this analysis shows that NISQ publications are, in some sense, becoming less popular even as the number of publications holds steady. There is an interesting disconnect between what the median researcher is willing to publish, versus what the median scirate user is willing to upvote.


## Discussion

The clear takeaway is that QEC's popularity is growing rapidly. In a way, this is both expected and healthy: we expect fault tolerance (FT) to be necessary for many of the promised speedups in quantum computing. NISQ was the idea that we could develop useful quantum algorithms before building an FTQC, but the revealed preferences of the quantum community cast doubt on that idea. We should perhaps keep an eye on this trend, since there will come a day when we have the FTQCs and now we need to run something on them.

Its great to be forward-looking, but the fantastic growth rate of research in QEC leaves me wondering - what research comes after quantum error correction? For example, I strongly suspect that classical error correction makes up only a tiny fraction of computer science research today. Will QEC research go the same way as classical error correction?


### Bonus: is QML cool or uncool?

Out of personal curiousity, I took a look at how QEC compares to another hot subfield, "quantum machine learning" (QML). Even with all the hype that QML has a (bad) reputation for, the growth rate for submissions in this subfield is actually slightly lower than QEC in the same time period! But, as is clear from Scirate, QML papers make up a shrinking fraction of the cool papers, and again we see a disconnect between publishing activity and scirate popularity. 

<div style="display: flex; justify-content: center;">
  <img src="/assets/2025-09-06/qml.png" alt="QEC scirate question fractions" style="width: 100%; max-width: 800px;">
</div>

<div style="width:80%; margin:auto; font-size: 0.9em;">
  <em>
	The number of QML-related submissions is growing rapidly, but this topic is decidedly uncool as measured by Scirate voters.
  </em>
</div>

<br>

In contrast with NISQ, QML algorithms are often designed to run on FTQCs, so this is fall in popularity is rather damning. What would it take to make QML cool again?

### Methods

The keywords for categorizing `quant-ph` submissions are below. Note that these lists are short, so the trend lines can be thought of as lower bounds. Obviously this is a fuzzy matching process and submissions can be cross-disciplinary, so treat these numbers as loose estimates.

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

I used [SEDE](https://data.stackexchange.com/) and ChatGPT for analyzing QCSE trends, the [arXiv Kaggle dataset](https://www.kaggle.com/datasets/Cornell-University/arxiv) for `quant-ph` trends, and the `scirate` API for Scirate trends. 

#### Acknowledgments

I used the `scirate` API, so thanks to Vincent Russo.

---

[^1]: The entire metadata for arXiv is available on Kaggle: [link](https://www.kaggle.com/datasets/Cornell-University/arxiv)
[^2]: I mean this literally, in the sense that daily arXiv digest emails for `quant-ph` are now sometimes longer than the email length that gmail is willing to display by default, meaning that some submissions will not even appear in the email unless you [exploit arXiv's ordering system](https://peterse.github.io/2023/06/06/Early-bird-gets-the-worm.html).
[^3]: Early on there was some debate among people using Scirate, and to this day it is unclear to me what an upvote on scirate means. This is not a new issue: e.g. see the conversations [here](https://groups.google.com/g/scirate/c/WAHKx8TAUo8). My personal guess is that the median scientist has a reflexive-but-exagerrated belief in their own objectivity, and is therefore extra susceptible to social persuasion. But to be useful, any theory of what a scite means should be grounded in the behavioral patterns we can observe on Scirate. 
[^4]: This is tongue-in-cheek; please don't actually update your research tastes -- or any tastes really -- towards things that get ``likes'' on social media.
[^5]: Its actually really hard to do statistics on Scirate behavior, since upvotes are highly nonstationary (the  number of daily Scirate users grows over time) but also have very limited statistics (less than 50ish papers per day with large fluctuations). For example, comparing a submission's scites to the average number of scites requires computing a moving average with a window that is small enough to reflect a roughly-stationary process but large enough to be meaningful.
