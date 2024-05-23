---
layout: post
title:  "The false dichotomy of Quant-Qual analysis and the real tradeoff of data-driven product development"
date:   2019-07-17 15:52:40 +0100
categories: growth
---

Some people intuitively assume (perhaps inspired by the 'rational-humanist' dichotomy) that there's a spectrum with taking data-driven decisions on one hand, and 'qualitative'/intuitive/user-feedback-driven insights on the other. That's incorrect. Data-driven product development doesn't trade off qualitative insights: The best teams I've seen (e.g, at Facebook) are integrating both. Qualitative, case-by-case feedback from user interviews provides the observations around which we build hypotheses. We then test these with the data. Using only data will leave us blind to most phenomena, and using just qualitative insights will drive us randomly without a sense of magnitude, hence priority, of the opportunity. Many of my best optimizations in growth came from observing users use the product - then measuring the scale of a problem they encounter. First round just posted a great discussion of the value of qualitative research.

There is one key trade-off to being data driven, however. That trade-off is speed. It both directly costs resources to invest in measuring the state and the effect of almost everything you do, and it slows you down indirectly because data-driven decision making takes time: You need to gather evidence from queries (DB, surveys, experiments, etc.), and then process it with decision-makers - that's a lot of work. This is why we also want to be wise and measured about what to measure.

> "Not everything you can count counts, and not everything that counts is countable".

Some concrete examples:

A) 'Fail fast' in experiments: stop experiments once they show either:

i. There's a better outcome - even before we have narrow confidence intervals around how much better it is [1].

ii. The confidence intervals are narrow enough to show us the magnitude of the effect is not worthwhile pursuing. If an experiment happens to show we can move time spent between minus one second to adding 3 seconds per user per week, who cares?

B) Don't try and measure the most metrics, or sometimes the most correct version of a metric, or sometimes even the outcome of every decision. Arbitrary precision requires arbitrary time: Avoid analysis paralysis and focus on the few decisions that matter. Jeff Bezos says it well here: There are only a few decisions that matter for which you want to invest your time in making correctly.

[1] This is the opposite of the practice researchers do for a scientific journal publication (except under the minimization of harm doctrine in some human/animal-subject studies)
