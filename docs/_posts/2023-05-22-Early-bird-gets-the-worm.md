---
layout: post
title: "Early bird gets the worm: Analyzing quant-ph arXiv submission timing"
---

One of the goals of science is to produce ideas that improve our understanding of the natural world. But there are a lot of ideas to consider, and so we have to find ways to help us choose what authors we pay attention to and what work we cite. 

In this post I investigate that process appearing in an unexpected way.

## ArXiv submission logic

The arXiv is an online preprint server. You can use arXiv look up articles before they're published in a peer-reviewed journal (hence "preprints"). This is useful because researchers want their work to be read and cited by other researchers. Some researchers really, _really_ want this, for obvious reasons. However there are a lot of preprints to sift through, and so you have to find ways to get your articles seen.

One reliable way to make sure many researchers notice your fresh preprint from among dozens of others submitted that day is to submit your article to arXiv just after 2:00 PM New York time. The mechanism is simple: 

1. Each weeknight, subscribers to arXiv's email lists recieve a daily digest of articles submitted the day before.
2. There is a cutoff time for when "the day before" begins.
3. It is natural to order preprints using the time that they were submitted after that cutoff. 

Submissions are listed in this ordering in both the daily email digest and the [daily list of new submissions](https://arxiv.org/list/quant-ph/new), so that the first preprint seen by everyone is the first preprint that was submitted after the cutoff time of 2:00 PM in New York.[^1] 

![Sample digest screenshot](/assets/2023-05-22/email_screenshot.png)
*An excerpt from the email that I receive every morning listing preprints submitted the previous weekday. The red box highlights when the submitting author sent the paper to arXiv for publication.*

There is a remarkable correlation between an preprint's placement on this list and the number of citations that preprint will go on to have. In high energy physics, the first few entries end up with roughly 200% more citations than entries appearing at the end of the list [(Ginsparg, 2009)](https://arxiv.org/abs/0907.4740)[^2]. One can't say whether appearing at the top of the list _causes_ a preprint to have a greater number of citations[^3], but this is a sound wager to make if every job interview and grant application and basically the entirety of your future career success depends on whether people are reading and citing your articles. And it appears many people are making this bet.[^4]

In the remainder of this post I will study this behavior for the exclusively `quant-ph` ("quantum physics") arXiv category, I am a part of.[^5]

## Ornithology 101

To give an idea of what this behavior looks like, here is a plot of the time of day that each quant-ph preprint was submitted to the arXiv in 2022:

![Figure 1](/assets/2023-05-22/ebgtw_figure1.png)
*The number of quant-ph arXiv submissions in 2022, by the hour. The inset shows a large number of submissions within one minute after the cutoff (and perhaps several that were too early by a few seconds!)*

Clearly there is something happening around 2:00 pm, the cutoff time for new submissions. I will call an article submitted within 5 minutes of the cuttoff an **early bird** submission (remember: these are the articles that appear first on the mail list). 

It is really very easy to analyze trends in the behavior of early bird submissions because the metadata for every submitted preprint are publicly available online. This behavior is becoming more common, which confirms my experience looking at the new submissions list every morning:

![Figure 2](/assets/2023-05-22/ebgtw_figure2.png)
*The number of total submissions and early bird submissions in quant-ph is growing exponentially, though the latter is growing faster. There was a sharp increase in early bird submissions right after Ginsparg published his analysis showing that this behavior was correlated with higher citation count.*

In the last 10 years the fraction of early bird submissions has gone from negligble to about 6%. Currently there's about 30 submissions appearing per day, so on a typical day there's about two early bird submissions appearing at the very top of the lists[^6]. 

## Birdwatching

An interesting aspect of submitting at the arXiv cutoff is that you either know about it or you don't. This means we have to be careful analyzing more detailed statistics of early bird submissions. For example, if we find that an individual submitted 50% of their preprints at the cutoff time, this could mean (1) they submit every other preprint in this way (2) they found out about the early bird trick after they'd already posted several papers but have only ever posted at the cutoff since. Any analysis needs to account for arXiv submission behavior being time-dependent and relatively rare event for any given author.

Keeping this in mind, here is how early bird submissions compare to total submissions among submitters with at least one early bird submission.

![Figure 3](/assets/2023-05-22/ebgtw_app1.png)
*If you've ever made an early bird submission, how did you submit your other papers? A 45-degree line on this plot indicates submitters who have submitted every paper right at the cutoff, while the very first column indicates an author made a single early bird submission so far. Beware: The more left and up you go, the more likely the entry is random noise!*

There are quite a few authors who submitted an early bird preprint as their only preprint in their career (so far). Indeed, this is a growing trend:

![Figure 4](/assets/2023-05-22/ebgtw_figure3.png)
*Blue means the number of first-ever submissions that year, while red is the number of times authors did their first-ever early bird submissions that year. Pink means the author's first-ever early bird submission was also their first-ever submission. The growth of this final category has been constant since 2020, possibly related to the start of the pandemic and a cessation of in-person research activity?*

Finally, we can dive a bit deeper into individual behaviors with a case study of a few prolific early birds. We will look at how the submission behavior changed in time for the set of the 16 submitters who most frequently made early bird submissions:

![Figure 5](/assets/2023-05-22/ebgtw_figure4.png)
*Each box represents a single author. Each point is an arXiv submission, with the vertical axis indicating the total number of early bird submissions by that author. A straight line with an upwards slope indicates a period in which every submission was early bird, while a flat line is a period in which none of the submissions were early bird.*

Presumably these authors never _forget_ the early bird submission trick, but clearly some folks don't keep up with it as time goes on. Maybe they got tenure, or left academia, or moved to a part of the world where 2:00 PM ET is some awful hour of the night. Each line tells its own story. 

## Conclusion

For now, there's a reliable way to get your arXiv preprint seen by a of your scientific subfield (quantum or otherwise) community by having it appear at the top of the email/new submissions list. But a growing number of people are competing for this position, so you'll have to be fast. Prior work suggests that beyond about the 10th position, the correlation between citations and email list rank disappears. If you believe this to be a causal relationship, (and you lose nothing by believing so), you will endeavor towards early bird submissions as close to the cutoff as possible (and you lose nothing by doing so).

Possibly one could employ some kind of program towards this task. But after competing submitters have squeezed all human latency out of the process via automation, a natural next step is to squeeze network latency out of the process too. If submission timing translates to additional citations and additional citations translate to another round of grant funding, maybe earmarking a round trip flight to Ithaca to connect to the local network hosting the submission server is rational behavior. At the least, this would be entertaining perhaps even [book-worthy](https://en.wikipedia.org/wiki/Flash_Boys).

<!-- With exponential growth of arXiv submissions (but only so many 'good' spots in the new submissions list) and the amount of money put towards quantum computing research, there is ample opportunity  

we might imagine a future similar to the chain of events that lead from the discovery of arbitrage opportunities in NYSE(???) to high frequency trading to the construction of a direct fiber-optic line from Chicago to NYC in order gain microseconds of advantage in the latency (Flash Boys) - a future where your survival as an academic has been so closely tied to mundane 'citation hacks' that you would be willing to... -->

Any effect that announcement placements might have on citation/readership outcomes could be nullified by randomizing the order of the daily arXiv digest email per recipient (and by regenerating the new submissions webpage per visitor IP address) such that no submission is ever globally 'first'.

---

## Aftermatter


#### Methodology

I gathered article metadata using the arXiv OAI-PMH interface and arXiv API. I used a cutoff time of 14:00 Eastern for all (initial) submissions after Jan 1, 2017 and 16:00 Eastern before then, EDT or EST depending on daylight savings. 

#### Limitations

This analysis does not control for any authors who may have changed their name or submission email during the timespan considered. I do not try to control for accidental early bird submissions. 

#### Acknowledgements

Parts of the analysis code were written by Github Copilot and GPT-4 (with additional credit due to Stack Overflow and Github users who supplied training data). None of this writeup was produced using LLMs. I used `matplotlib` to produce plots. I used the [`sickle`](https://github.com/mloesch/sickle) OAI-PMH client to access records.

---

[^1]: This is not strictly true: Occassionally a submission from before the cutoff (sometimes by several days) will appear at the top of the list. This is probably because that paper had a run-in with arXiv moderation. Truly the slow rat sometimes gets the cheese. 

[^2]: Paul Ginsparg is the original creator of arXiv.

[^3]: For example, the kind of person who times their submission for a second after the cutoff time might be a generally ambitious or dedicated researcher. Or an early-bird submission might be a way an author signals confidence in a particular manuscript, though this seems unlikely given the analysis.

[^4]: I am unaware of any replication of Ginsparg's research for specifically the quant-ph category. I am interested to find out if the pattern holds.

[^5]: I actually tried to submit a [preprint](https://arxiv.org/abs/2209.05523) right at the cutoff recently but I was about 8 minutes late :(

[^6]: This is a bit of a simplification since the analysis includes submissions that are cross-listed as quant-ph, which appear in an entirely different section than the primary quant-ph submissions, but are otherwise ordered according to their submission after cutoff time.