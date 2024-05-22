---
layout: post
title:  "'Additive' and 'Substractive' measures, or how to goal for stuff that shouldn't happen"
date:   2019-10-23 19:01:17 +0100
categories: growth
---

In a data-driven organisation, most of the stuff we measure is about adding up events. Revenue is made of sales events, active user counts are 
made up of adding (unique) visitation events, and marketing results are about adding up how many people saw everything we did, or clicked on it [1]. Usually, these events are so frequent the measurement becomes 'smooth' - it's a 'line' we can forecast to predict next year's goal. We can talk about the 0.4% increase caused by a change we made in the product or operation.

But this isn't the only way we make a company succeed. All companies also deal with preventing negative events. Legal, PR teams, security, site 
reliability and devops teams explicitly deal with risk reduction as part of their responsibilities. Even teams that aren't used to thinking in 
risk reduction terms are also responsible for not screwing things up - engineering, client support teams and operational teams that need to 
prevent downtime, churn and business mishaps.

How do you measure "risk reduced"? How do you value work that's meant to prevent bad things from happening? Is this even something that we 
should goal on?

Yes, we should absolutely goal on everything that's crucial to the success of the business. Goals guide prioritization and add clarity. 
Teams whose main prerogative in a given half is to reduce risk should goal on it. But there's a method for doing it. When setting goals on 
these 'subtractive' metrics (meaning, we want to reduce bad stuff to 0, rather than increasing, e.g, revenue to $100M), we need to recognize 
a few things:

**Sparsity inhibits feedback:** Most of these are hard because they involve rare events. If your goal was to reduce, for instance, the number of 
meetings taken at a large company, you'd have no problems measuring it and targeting a reduction of 10% this half, because with thousands of 
meetings a day you can track your progress every day, identify which meetings involve the most people or are most frequent and justify tackling 
these to meet the goal. But it's hard to effectively goal on preventing something that never happened or only happened once from happening 
again - there's no ongoing feedback to guide you if you're on the right track.

**No causation:** They are also hard because they are unexpected. Additive metrics are usually the ones where a proactive action we take 
(e.g run an ad campaign) creates the outcome we measure. What I term 'subtractive' metrics are usually reactive (prevent churn, prevent 
lawsuits, ...). We don't take the action, we just build the forts - it's even harder to track progress when, once the fort is up, the 
enemies never attack because they see the fort! Not knowing the counterfactual, forts are always an unjustified expense [2].

**No place for the meter:** Additive goals are usually defined in terms of an important outcome that results from activity 'funneling' into 
some place we set up measurement. For example, measuring revenue is looking at the finance department's spreadsheet, where all the business activity ended up. Number of users are webserver hits triggering some code flows ending in a DB. There's a path where actions trigger a measurement. An instructive exception is perhaps sales in an enterprise business - all sales people need to be disciplined (and incentivized) to manually key in which clients are in what step of the funnel to enable tracking. (Even that's being more and more automated by CRM software). Subtractive measures, however, are usually defined broadly: We want to prevent any incident, no matter who or what its cause is, so they are hard to measure automatically because they can happen "anywhere".
The solution to measuring, and setting goals, on 'rare, unexpected, bad outcomes' then, is tackling these three challenges.

First, we need to make what we measure a more common aspect of the problem we want to solve. Instead of tracking just bad events when they occur, 
we track near misses. These are events which could've been disastrous but were caught somewhere along the way. They may have been caught by a 
system or process we already put in place to prevent them - demonstrating that it's working. Or, they were caught before causing damage by 
chance, and could inform us of a potential hole. These near-misses are more frequent than full on crashes, so they give us a denser time 
series, with more information about whether preventative measures are worth the investment, and which ones to set up.

Next, we should measure proxies of the disaster we're trying to prevent, which history and intuition tell us are correlated with it. 
Essentially, we're looking for the build up of water before the dam collapses. Facebook sends you less notifications if you stop 
opening a few. This signals you're not interested and the app should throttle notifications - before you turn them off altogether, 
a practically irreversible action. Most B2Bs track engagement with the product as an early indicator of churn, and good devops teams 
'canary' a new release to risk very few servers and users before rolling it out to 100%. Answering both (1) and (2), we also broaden the 
definition as much as reasonable to encompass smaller mishaps as much as the large ones. A spate of unsophisticated phishing e-mails may 
indicate we're now a target for an imminent big cybersecurity attack.

Finally, addressing point (3) has unfortunately no other solution I know of than accountability. In great organisations, everyone has the 
discipline to help measure these incidents (especially with the harder to notice 'near misses'). This only works when people are 
incentivised to do so and when major figures in the company are deeply invested in driving this process. That's why we should never 
set goals on having some (low) X number of incidents - that would directly go against the incentives of measuring as many as you can. 
Instead, we focus on reducing the Time-To-Detect (TTD), Time-To-Mitigate (TTM) and % of incident followup actions executed, believing 
these together with a strong DERP (Detection, Escalation, Remediation, Prevention) process [3] take care of improving the incident rate 
itself. The number of incidents (as well as the false alarm rate for detection systems) would both still be measured, of course, but 
they would not be a goal [4].

To measure, goal and motivate work on preventative tooling in a data-driven, prioritized and cost-effective way you don't need much 
more than a spreadsheet to (yes, manually) track the incidents and near-misses or proxy events that happened, their detection and 
resolution times - but you do need to start with a process and a commitment to follow it through.

[1] This was well put as "all of data science is just counting and normalizing - the hard part is figuring out what the denominator should be".

[2] Black Swan by Nassim Taleb opens with a great hypothetical about an unsung heroic FAA agent that after campaigning for years manages to get a 
regulation enacted requiring all cockpit cabins be locked with a keypad, starting Sep 10th, 2001...

[3] In Facebook, the incident review process was exactly the same across dozens of offices and thousands of teams, orchestrated, audited, 
updated and motivated by the global VP of Engineering, Jay Parikh.

[4] They're impossible to goal on anyway, given the business creates new processes, products and systems so rapidly and these grow in their 
own varying rates.
