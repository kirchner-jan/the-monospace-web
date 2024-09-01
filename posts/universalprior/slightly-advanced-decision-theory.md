# Slightly advanced decision theory 102: Four reasons not to be a (naive) utility maximizer

## TL;DR: Introduction to decision theory with examples from effective altruism. Resulting optimal strategies differ from "naive" utility maximisation, but match community norms.

**Nov 22, 2021**

**Likes:** 3

_Hello and welcome to everyone who joined from Hacker News or Marginal Revolution after last week’s post[1](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-1-44426436)! I'm Jan and I'm trying to have something interesting to say on this Substack every week. Quality and mass appeal can vary. Hope you enjoy <3_

* * *

# Foundations and Flaws

In high school I learned that there are four fundamental questions in philosophy:

  *  _What can I know?_ ([epistemology](https://plato.stanford.edu/entries/epistemology/))

  *  _What should I do?_ ([moral philosophy](https://iep.utm.edu/ethics/))

  *  _What is beauty?_ ([aesthetics](https://iep.utm.edu/aestheti/))

  *  _What?_ ([metaphysics](https://plato.stanford.edu/entries/metaphysics/))




[Effective altruism](https://www.effectivealtruism.org/) is a movement that attempts to link the second question with the first[2](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-2-44426436)[3](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-3-44426436): _How can I use the things I know to better do the things I should do?_

This leads to an interesting clash of cultures: people interested in "what can I know?" tend to be rather cerebral[4](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-4-44426436), while "what should I do?" attracts people that are more... cordial?[5](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-5-44426436) This mix is often [intriguing](https://www.lesswrong.com/posts/3wYTFWY3LKQCnAptN/torture-vs-dust-specks) and sometimes [sublime](https://mindingourway.com/the-value-of-a-life/). It's a young movement and there are many [foundational questions](https://globalprioritiesinstitute.org/) that need figuring out. In a [previous post](https://universalprior.substack.com/p/on-scaling-academia#footnote-1), I promised that I would dig into the foundations and see if everything _actually_ makes sense to me. This post is the first step down that path.

So buckle up, I'll be diving into expected value reasoning and slightly advanced decision theory. In four bite-sized sections that can be enjoyed in sequence or in isolation, I'll provide theoretical footing for a lot of the things that are already practiced in effective altruism anyway, but that do not follow directly from naively applying expected value reasoning. As mentioned above, I'm partially doing this to satisfy my own need for having a solid theoretical basis for my actions. But beyond that, my hope is also that by articulating these arguments and demonstrating how to use computational toy models to understand complicated dynamics I'm providing useful tools for the community.

#  **Average action**

But before we can talk about tools, let me set the stage. Feel free to skip this section if you are familiar with the central logic and recommendations for action of effective altruism.

I said in the earlier section that effective altruism combines epistemology with moral philosophy. What does that even mean[6](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-6-44426436)? 

We can make this [arbitrarily complicated](https://www.williammacaskill.com/info-moral-uncertainty), but for the sake of the post let us start by picking [hedonistic utilitarianism](https://iep.utm.edu/hedonism/#:~:text=f.%20Hedonistic%20Utilitarianism) as moral philosophy. Hedonistic utilitarianism prescribes that we ought to take the action that produces the greatest net happiness for all concerned. The word "greatest" suggests that we need to be able to [order all actions so that one of them is better than all the other ones](https://en.wikipedia.org/wiki/Greatest_element). At this point, the [Von-Neumann-Morgenstern](https://en.wikipedia.org/wiki/Von_Neumann%E2%80%93Morgenstern_utility_theorem) is usually introduced to argue that under certain "reasonable assumptions" we can get a utility function from an ordering of preferences. The prescription of hedonistic utilitarianism to "produce the greatest net happiness for all concerned" then translates into "choose actions that maximize utility for all concerned". And figuring out which action that is, turns out to be something that we ([sometimes, kind of](https://blog.givewell.org/2011/08/18/why-we-cant-take-expected-value-estimates-literally-even-when-theyre-unbiased/)) can do by looking at the world and figuring out how things work. Thus we arrive in the land of epistemology.

So far, so vague - what does this buy us? It turns out that it is pretty hard to _actually_ apply Von-Neumann-Morgenstern[7](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-7-44426436), therefore the idea to maximize utility is more like a guiding light than an ultimate law. Reality is often messy and we cannot be sure that the action we take ends up having the effect we think they will have. Even the most promising action can fail - and an unlikely "moonshot" project might still end up working out. This probabilistic component leads us to [maximize the ](https://reducing-suffering.org/why-maximize-expected-value/)_[expected](https://reducing-suffering.org/why-maximize-expected-value/)_[ utility](https://reducing-suffering.org/why-maximize-expected-value/) instead of just maximizing utility. This gives us some assurance that as long as we keep trying long enough, eventually, we will produce utility.

Despite these caveats, a handful of recommendations have emerged for the aspiring effective altruist that have a chance to maximize expected utility:

  1. Donate. You are [very likely among the richest five percent of people](https://howrichami.givingwhatwecan.org/how-rich-am-i) living on the planet right now. Your donation can improve someone else's life tremendously.

  2. Donate to an _effective_ charity. Some charities are [up to 100x more cost-effective](https://www.givingwhatwecan.org/charity-comparisons/) than other charities. The same amount of money donated might therefore produce up to 100x the expected utility.

  3. Choose an effective career. If you work on a problem that is '[important, neglected, and tractable](https://80000hours.org/articles/your-choice-of-problem-is-crucial/)', you have a chance of working on something with high expected utility (important) that not enough people are working on (neglected) and that you might _actually_ solve (tractability).

  4. Consider being risk-neutral rather than risk-averse. Our natural instinct is to be [risk-averse](https://en.wikipedia.org/wiki/Allais_paradox) and not to take options that are good in expected value but have a high chance of failure. [Correcting this bias might unlock a lot of additional expected utility](https://80000hours.org/articles/risk/).




#  **Suboptimal solutions**

Are you convinced? I hope not. Here are three points that give me pause:

  1.  **Career choice**. I [often meet effective altruists](https://80000hours.org/speak-with-us/?int_campaign=2021-08__primary-navigation#:~:text=We%E2%80%99ve%20helped%20over%201%2C000%20people) who struggle hard to make "the most important decision of their life" regarding which field to study. The intersection between personal fit, uncertain future, and (de facto) incommensurability of different cause areas makes this a devilishly hard question. But - from personal experience - this question also mostly turns out to be a [false dilemma](https://en.wikipedia.org/wiki/False_dilemma). You _can_ have your cake and eat it too. Sometimes, at least.

  2.  **Risk-neutrality**. The point about risk-neutrality doesn't sit well with me at all. Call me risk-averse, but I can't argue myself into dropping my Ph.D. and starting a start-up[8](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-8-44426436). I'm all for [skin in the game](https://en.wikipedia.org/wiki/Skin_in_the_Game_%28book%29) and I can hear Taleb calling me an [IYI](https://medium.com/incerto/the-intellectual-yet-idiot-13211e2d0577), but something about the logic doesn't sit well with me. Almost as if there is a hidden risk that doesn't go into the expected value calculation…

  3.  **Donation splitting**. Expected utility reasoning implies that some cause areas are more impactful than others. Perhaps we can't figure out which ones they are, but if we _could_ , then, according to naive expected value reasoning, we should [completely discard](https://funds.effectivealtruism.org/help/20ApN8qGQIW8OS02KOA0WA) the others. This is clearly nonsense to me - and to the majority of effective altruists, I believe. If we found out that [insect suffering](https://reducing-suffering.org/the-importance-of-insect-suffering/) turns out to be really important, would we just drop everything else and focus on insects?




Let's see if we can untangle this and see where the discord is coming from.

###  **Diverse detours.**

On the topic of career choice: I have the impression that[ too much importance is assigned to the choice of a career](https://80000hours.org/about/#:~:text=your%20choice%20of%20career%20is%20probably%20your%20best%20opportunity%20to%20do%20that). 80.000 hours writes:

> If you want to have a positive impact with your life, your choice of career is probably your best opportunity to do that.

Framing the situation like this makes it sound like a monolithic decision that locks in your future impact. I'm sure this is not the intended message; but from talking to people at the beginning of their careers, this is often the impression I get.

An alternative approach was recently [outlined by Holden Karnofsky](https://forum.effectivealtruism.org/posts/bud2ssJLQ33pSemKH/my-current-impressions-on-career-choice-for-longtermists). Rather than monolithic paths into a career, Holden talks about aptitudes, which "one can build in a wide variety of roles and causes". This matches my own perspective; I've consistently found it more beneficial to collect skills and friends as they present themselves to me, rather than to stubbornly grind towards a fixed goal. I've also made it a habit to say "yes" to _any_ interesting opportunity that comes up[9](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-9-44426436).

So what can I add that's not already in Holden's post? A mathematical argument, of course! 

Let's first look at one example of what a monolithic life decision might look like. Imagine you are evaluating several options (from [biorisk](https://www.effectivealtruism.org/articles/biosecurity-as-an-ea-cause-area-claire-zabel/) research to [cause X](https://forum.effectivealtruism.org/tag/cause-x) research). Each of them has an expected impact and you compare them to identify the winner:

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fe1f74094-cbf8-410f-af04-4e9280b429a2_1172x1553.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fe1f74094-cbf8-410f-af04-4e9280b429a2_1172x1553.png)

Since “cause X research” has the highest expected impact, you decide to pick that and drop the rest. In equations, you have opportunities 

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F27edb592-649d-4c13-9c8d-5fdda336c492_242x70.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F27edb592-649d-4c13-9c8d-5fdda336c492_242x70.png)

and you decide to pick the one that has the highest expected value:

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F0255e450-dc2b-4a48-bba2-a0ab95f5ea53_564x90.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F0255e450-dc2b-4a48-bba2-a0ab95f5ea53_564x90.png)

While this is fine, and certainly has a higher impact than exclusively focusing on knitting, I believe we can do even better. In particular, the _expected value of the maximum is larger than or equal to the maximum of the expected values_ :

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F8537e5c4-c8c8-494a-a30f-b5ac59b63a25_954x80.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F8537e5c4-c8c8-494a-a30f-b5ac59b63a25_954x80.png)

I know this mathematical theorem as the "[race model inequality](https://link.springer.com/article/10.3758/s13414-015-1018-y)"[10](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-10-44426436), but I'm sure it is known under different names in different fields. What it cashes out to is the following decision rule: When you have the choice between (ex-ante) picking one thing and getting the result from that thing, or (ex-post) seeing the result from all the things and picking the one you like best, you should always pick the latter (ex-post) option.

Or, in less fancy terms,

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fb7321be7-3cbc-4bd1-8336-9ff083d12b99_1433x932.jpeg)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fb7321be7-3cbc-4bd1-8336-9ff083d12b99_1433x932.jpeg)

Instead of _only_ researching Cause X, also keep one foot in AI safety research, have a reading group on policy, and [knit as if your life depends on it](https://en.wikipedia.org/wiki/Arachne). Since there is variance in your actual outcome (you might end up being a terrible researcher, but your knitting skills inspire the countries of the world to unite and sing praise), it is better to hedge your bets and try multiple things.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc9ce7759-272b-4844-9b2a-fdbb40bd0648_1600x1437.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc9ce7759-272b-4844-9b2a-fdbb40bd0648_1600x1437.png) **a** Ex-post outcome (do all the things and pick the thing that worked best) compared with ex-ante outcome (only do the one thing with the highest expected value. **b** Average ex-ante and ex-post outcomes. Code is [here](https://colab.research.google.com/drive/1enMNClWabFr2KhmMOe1mRSP9MkVsU6kx?usp=sharing).

One (reasonable) objection might be that I'm neglecting an important limiting factor: humans can't do _all the things_. If you try to do five things at the same time, they might, in combination, end up worse than if you had done one thing "properly". 

But whoever says this underestimates [the power of the ](https://en.wikipedia.org/wiki/Extreme_value_theory)_[maximum](https://en.wikipedia.org/wiki/Extreme_value_theory)_. We can cut the expected value of all our opportunities in half (since we will not be able to do everything "properly") and still take almost no hit to the ex-post expected value.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F696fcba2-46bd-44f0-8e3e-46a20f33f35e_779x1600.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F696fcba2-46bd-44f0-8e3e-46a20f33f35e_779x1600.png)

There are only two conditions: We should focus on opportunities that have at least broadly comparable expected values and that have a big amount of variability[11](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-11-44426436). Doing a zany coding project with your friends that probably won't work out but will revolutionize how we wear our socks if it does? Go for it! Read a textbook from a field that sounds extremely relevant to your work but that none of your colleagues cares about? Absolu-telly. Go to that weird party that you were totally invited to by accident and that you will very likely leave a little embarrassed? Yep, even that.

“Maximize variance”, a friend once told me. Those are words to live by.

###  **Intoxicated imagination.**

(For comedic effect I'm putting these sections back to back.)

Stay. Away. From. Variability.

While 80000 hours inconspicuously whispers into my ear about the [potentially very large impact of a tech startup founder](https://80000hours.org/career-reviews/tech-entrepreneurship/), AppliedDivinityStudy shouts at me to[ become a billionaire already](https://applieddivinitystudies.com/billionaire/). While unlikely to work, _if_ it does, it'll be awesome. High risk, high gain. Sure, _you_ will likely fail, but if enough people try, [someone is bound to succeed](https://fortune.com/2021/07/29/sam-bankman-fried-crypto-billionaire-ftx/).

I don't even want to push back on this too strongly. There are [strong incentives that contribute to the risk-averseness of academics](https://d-nb.info/1152136895/34) and I try to stay aware of my biases. However, here is an important concept that is often ignored when high-risk opportunities are advertised: [absorbing states](http://ce.sharif.edu/courses/90-91/1/ce695-1/resources/root/Notes/Lec-8b.pdf).

> An absorbing state is one in which the probability that the process remains in that state once it enters the state is 1.

The most famous absorbing state is death. Less permanent absorbing states are imprisonment, [persistent vegetative states,](https://en.wikipedia.org/wiki/Persistent_vegetative_state) and cult membership. There are also pseudo-absorbing states, like [bankruptcy](https://www.nolo.com/legal-encyclopedia/starting-business-after-bankruptcy.html), [depression](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5769037/), and [debt](https://www.thebalance.com/hard-to-pay-off-debt-960855).[12](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-12-44426436) If your amazing high-risk opportunity puts you in danger of ending up in one of those states, say " _No thank you_ " and put some distance between you and the opportunity. 

Joke aside, there are certain [situations when it is okay to risk imprisonment](https://www.aljazeera.com/news/2021/10/16/seven-hong-kong-activists-jailed-over-unauthorised-protest-in-2020). But I want to argue that absorbing boundaries should not be underestimated. Here is another toy model:

Let's say you get offered a series of opportunities with positive expected value, but high variability. If you accept sufficiently many of them, you are almost guaranteed to end up with a large positive payoff. In the process of getting there, you will experience substantial fluctuations, but they will cancel out and the positive expected value of the opportunity will accrue.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F619bca5c-11d5-43e3-984d-3a125f39a23c_3169x1793.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F619bca5c-11d5-43e3-984d-3a125f39a23c_3169x1793.png) **a** Value of the opportunity as a function of time. Multiple equally distributed time series are shown. The dashed line in red indicates zero value. **b** Histogram plot of payoffs (value of opportunity at time point 100). The dashed line in red indicates average payoff. Code is [here](https://colab.research.google.com/drive/1b2xENV91mZfsf_BzMGufpGdl5-ldeTMW?usp=sharing).

However, things look very different when we introduce an absorbing boundary at zero. Due to the low start value and the large variability, almost all instantiations of the scenario end up in the absorbing boundary (bankrupt, dead, or worse)

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fcd401872-75d3-4c8e-8ce5-8223c04cdf49_3062x1655.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fcd401872-75d3-4c8e-8ce5-8223c04cdf49_3062x1655.png)As the previous figure, but with all opportunities that hit zero clamped to zero.

So what does that mean? Should we avoid opportunities with high variability under all circumstances?

No, in particular in light of my argument from the previous section this would be too extreme. I'm only arguing that we need to be aware of the existence of absorbing boundaries. When they exist, you should still go for a high expected value - but additionally, you might want to try and minimize variability.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F40cbb7e6-0e88-4ef5-9958-3536e82ef601_1600x1281.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F40cbb7e6-0e88-4ef5-9958-3536e82ef601_1600x1281.png)Expected payoff for different combinations of expected value and variance of the driving noise process. Colorbar is on a log scale. Note how a medium-sized expected value with low variance might result in a higher payoff compared to a high expected value with high variance.

(There is another fun little insight that we get from this toy model. Notice how in the left half of the figure variance has a _positive_ effect on payoff? This makes sense - if you have very little to gain and will likely end up in the absorbing state anyways then it pays to strive for highly variable outcomes. You can only win. So in that spirit: Ask that woman/man/creature you like out on a date. You can only win.[13](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-13-44426436))

* * *

Now we turn to the last point on my list: the unintuitive notion that you[ ought to discard](https://reducing-suffering.org/why-maximize-expected-value/) any charitable cause that has less expected impact than the other causes. I'm afraid this sounds like a [straw man](https://en.wikipedia.org/wiki/Straw_man) since nobody in the community actually acts like this[14](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-14-44426436). Somehow it is implicitly acknowledged that there is no "one true charity" with the highest expected impact and if we only knew which one it is, then we'd just scrap the rest. But still, there are [several](https://reducing-suffering.org/why-maximize-expected-value/#What_about_mixed_strategies)[ posts](https://funds.effectivealtruism.org/help/20ApN8qGQIW8OS02KOA0WA) out there arguing against donation splitting. And, anecdotally, I can confirm that some EAs are a bit confused about why that should apply to them personally but not to the institutions at large.

In the next two sections, I'll present two more arguments for why it's (sometimes) fine to spread your efforts across multiple opportunities.

###  **Gotta catch them all.**

Imagine you are caught in a psychology student's nightmare and have to choose between two sources of reward. One provides rewards on 70% of occasions where you approach it, the other only on 30%. The standard answer from decision theory is that you ought to always go to the first source[15](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-15-44426436).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F34d8bc82-4826-43c2-ae7b-22218e526383_3820x1856.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F34d8bc82-4826-43c2-ae7b-22218e526383_3820x1856.png) **a** Likelihood of success (fraction of trials where you guess correctly) as a function of the matched probability (fraction of trials where you pick source one). Different colors denote different "true biases" (the actual fraction of trials where the reward is at source one). Red arrows indicate the optimal choice of matched probability for different underlying true biases. **b** Optimal matched probabilities (red arrows in **a** ) as a function of the true bias. Code is [here](https://colab.research.google.com/drive/1Soj_HJ6XZZm84-clCGoKRfRCOvoZUGnv?usp=sharing).

(This is basically the argument for why you [should not split your donations](https://reducing-suffering.org/why-maximize-expected-value/#What_about_mixed_strategies). Splitting your donations, or alternating between the sources, _will_ reduce your expected utility.)

However, humans _love_ to mix things up. This behavior is called is [probability matching](http://naturalrationality.blogspot.com/2007/11/probability-matching-brief-intro.html),

> a widely observed phenomenon in which subjects match the probability of choices with the probability of reward in a stochastic context.

In the example from the psychology student's nightmare, probability matching means that 30% of the time you would go for one source and 70% of the time, you go for the other. This behavior is suboptimal from the perspective of maximizing expected reward[16](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-16-44426436), but humans _still_ do it all the time. There is an [ongoing debate](https://zenodo.org/record/1067055/files/article.pdf) about what to make of this (are humans dumb or just extra smart?), but I actually would like to focus on one aspect of the problem that hasn't been explored extensively yet. In the game with the two sources of reward, it's implicitly assumed that the two kinds of reward are [fungible](https://en.wikipedia.org/wiki/Fungibility), i.e. that they are interchangeable in the same way that money is interchangeable. Having a reward from _only_ one of the sources is acceptable.

What happens when we make things... [non-fungible](https://www.thisworldthesedays.com/source28.html)? That is, what happens if you definitely need _at least one_ from either source? You can come up with your own favorite example here[17](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-17-44426436), but I like to think about [existential risk](https://theprecipice.com/). If there is an asteroid about to impact the earth _and_ a supervolcano about to erupt, then it doesn't make sense to ask to pick either _or_ the other. In that situation it is pretty clear that to achieve your goal, you have to divide your efforts.

Divide them how? Turns out, you pretty much have to do inverse probability matching.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa76f11fa-f722-4701-b55c-8c60d0b8ae73_3816x1721.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa76f11fa-f722-4701-b55c-8c60d0b8ae73_3816x1721.png)Same as the previous figure, but with “success” defined as “getting at least one reward from both sources”. The dashed line in **b** indicates one minus the identity. Code is [here](https://colab.research.google.com/drive/1CUKhnxJi9BJVSUS95ZeYV0Yv7rkKkBex?usp=sharing).

As you need a reward from _both_ sources, you ought to frequently visit the source that rarely provides reward to make sure that you end up getting it when it shows up. In contrast, you can rarely visit the source that often provides reward, since on those rare occasions you are guaranteed to pick up the reward.

If we translate the toy model into the domain of existential risk prevention, then the model predicts that you should allocate your resources to existential risk prevention causes in proportion to how hard the risk is to prevent. I’m pretty sure this way of thinking is related to [Nick Bostrom’s Maxipok rule](https://www.existential-risk.org/concept.pdf):

> Maximise the probability of an ‘OK outcome’, where an OK outcome is any outcome that avoids existential catastrophe.

Under the maxipok rule, we don’t care about whether we get an unholy amount of reward from one of the sources, we only care about making sure that nothing _terrible_ flies under the radar.

###  **The first and the tenth Oreo cookie.**

While the argument from non-fungible goods is already sufficient to justify splitting donations across existential risk prevention charities, no discussion of the topic would be complete without mentioning [diminishing returns](https://forum.effectivealtruism.org/tag/diminishing-returns). I expect that most people are familiar with the concept, but I'm having a _lot_ of fun with my toy models and with making pretty figures, so here we go.

More of a good thing is not always more good. Utilities are context-sensitive and can depend on time. The first Oreo cookie is great, the tenth is kind of good, the one hundredth _will_ make you sick. In your hypothetical decision theory 101 class[18](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-18-44426436), you typically consider the following simple _linear_ model that links inputs **x** to expected returns **r** :

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F60d615d6-cd34-493d-9c8e-2080d812a212_254x68.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F60d615d6-cd34-493d-9c8e-2080d812a212_254x68.png)

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F115171b2-2e45-4102-9454-3336f096bece_1327x1321.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F115171b2-2e45-4102-9454-3336f096bece_1327x1321.png)Expected return as a function of income. Different colored lines indicate different opportunities with different scaling factors “a”. The dashed line indicates the identity. Code is [here](https://colab.research.google.com/drive/1cz5PLAwbKEaBP-bOs82jzvI0NU2eLJ7I?usp=sharing).

 _Linear_ means that if you invest twice as much input, you will get exactly twice as much output. This assumption is justified when we are talking about "[relatively small](https://en.wikipedia.org/wiki/Taylor_series) **x** ".

Let's say we have different opportunities 

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F7b518818-51c0-448c-b424-cac1a521f4ea_334x70.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F7b518818-51c0-448c-b424-cac1a521f4ea_334x70.png)

, but only a limited budget (time, money, motivation). How should we split our budget across the different opportunities?

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F5d96ea80-ad5e-43da-9bc4-fb14e7273069_282x92.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F5d96ea80-ad5e-43da-9bc4-fb14e7273069_282x92.png)

In this case, we can derive that the optimal choice is to go _all-in_ on the most promising opportunity, i.e. the one that has the highest scaling factor **a**[19](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-19-44426436).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F2ebdb303-853b-48a8-b9f6-bd8a99834d3f_1327x1321.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F2ebdb303-853b-48a8-b9f6-bd8a99834d3f_1327x1321.png)Same as the previous figure, but now with red arrows indicating the optimal split of budget to different opportunities. Note how only one opportunity (the one with the largest scaling factor **a** ) has a nonzero amount of budget allocated.

When charitable donations in EA consisted of [a few graduate students giving away their spare change](https://harvardpolitics.com/new-social-movement-generation-effective-altruism/#:~:text=Givewell%20co%2Dfounder%20Toby%20Ord%20donated%20ten%20percent%20of%20his%20income%20while%20living%20on%20a%20graduate%20student%E2%80%99s%20salary%20at%20Oxford), the linear model applied and dictated that they should donate everything to the most effective charity.

Well, [that was then and this is now](http://youtube.com/watch?v=H8i2tOfzyfk). Now that we are doing decision theory 102, we are not talking about [small amounts of money anymore](https://forum.effectivealtruism.org/posts/zA6AnNnYBwuokF8kB/is-effective-altruism-growing-an-update-on-the-stock-of#How_many_funds_are_committed_to_effective_altruism_). Consequently, the linear model no longer applies and we need to take other factors into account: the ability of a charity to [absorb additional funding](http://forum.effectivealtruism.org/tag/room-for-more-funding), [general equilibrium effects](https://economics.stackexchange.com/questions/26892/what-are-general-equilibrium-effects), and [scalability](https://80000hours.org/articles/problem-framework/#how-to-assess-scale). One way to bundle all of these effects into a tractable mathematical model is to think about [diminishing returns](https://forum.effectivealtruism.org/tag/diminishing-returns): investing twice as much input will lead to _less than_ twice as much output[20](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-20-44426436).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fcd24c357-d144-467c-a20d-7633b549da0d_516x90.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fcd24c357-d144-467c-a20d-7633b549da0d_516x90.png)

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F038bf967-88a3-4bee-b9a4-300348982bc9_1355x1265.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F038bf967-88a3-4bee-b9a4-300348982bc9_1355x1265.png)Same as the previous figure, but with a wider range on the x-axis. You now notice that the function in the previous figure has been a logarithm all along that just _looked_ linear locally.

When the **x** is small, then we are still in the "basically linear" regime and the optimal strategy of not splitting the budget remains the same. However, when the **x** gets large enough that we experience diminishing returns, then also our optimal strategy changes: Now we should split our budget proportional to the scaling factor of the opportunity[21](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-21-44426436):

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ff8d16861-ba57-478b-909d-8ce0d7c74c84_308x94.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ff8d16861-ba57-478b-909d-8ce0d7c74c84_308x94.png)

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fd03100a4-25e2-44b8-9a9f-b3fe2fc6aec8_1266x1265.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fd03100a4-25e2-44b8-9a9f-b3fe2fc6aec8_1266x1265.png)Same as…. You know the spiel.

Now, clearly, if the **a** of some opportunities are [orders of magnitude larger](https://www.effectivealtruism.org/articles/prospecting-for-gold-owen-cotton-barratt/) than others, then those other opportunities still should receive approximately 0% of our donations (sorry [sweaters-for-kittens](https://universalprior.substack.com/p/the-tale-of-gandhi-and-the-devil)). But if there are multiple equally promising opportunities, it is o.k. to split your budget.

###  **Concluding thoughts**

In this post, I have re-derived some of the community maxims that have naturally emerged over the years. In particular, I argued that

  1. the [race model inequality](https://link.springer.com/article/10.3758/s13414-015-1018-y) can be used to argue that it is good to _do multiple things that have a potentially large positive impact,_ rather than to channel all your energy into just one thing.

  2. in situations where [absorbing states](http://ce.sharif.edu/courses/90-91/1/ce695-1/resources/root/Notes/Lec-8b.pdf) are relevant (almost always), it can be better to optimize for high mean **and** low variance, rather than just for a high mean.

  3. when there are [diminishing returns](https://forum.effectivealtruism.org/tag/diminishing-returns) or when the types of reward from different opportunities are not fungible (like different [existential risk scenarios](https://www.existential-risk.org/concept.pdf)), then it is admissible to split donations.




There is a saying that " _knowing a little economics is worse than knowing no economics_.[22](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-22-44426436)" [The implication is clear, most models that are easy enough to be taught to a beginner are not powerful enough to be useful in the real world](https://en.wikipedia.org/wiki/Ludic_fallacy). I don't think the situation is _that_ bad for effective altruism, knowing a _little_ effective altruism doesn’t make your decisions _worse_. The [impressive track record](https://www.youtube.com/watch?v=2HeDdCFZmKc&ab_channel=CentreforEffectiveAltruism) of effective altruism demonstrates clearly that the movement is doing something right.

This is in part because the competition is very weak. Even if you _naively_ implement the maxim of maximizing expected utility, you will still have more positive impact compared to someone who doesn't think about impact at all. But the reality is complex and maximizing utility is not straightforward sometimes, so there are a lot of “nontrivial” tricks that can be used to squeeze out even more good. A turn [away from earning to give](https://forum.effectivealtruism.org/posts/LrKFNQxjETPvzXQcv/should-you-switch-away-from-earning-to-give-some), away from career “tracks” and [towards career “aptitudes”](https://forum.effectivealtruism.org/posts/bud2ssJLQ33pSemKH/my-current-impressions-on-career-choice-for-longtermists), and the peaceful co-existence of [diverse effective charities](https://www.givingwhatwecan.org/best-charities-to-donate-to-2021/), attest that the community is flexible enough not to fall into the obvious traps posed by naive utility maximization.

[1](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-1-44426436)

The post got more than 20.000 (pairs of) eyeballs! Gasp!

[2](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-2-44426436)

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_lossy/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F0fbc67d8-6d45-4fb7-ac53-3b25f42abf39_498x278.gif)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F0fbc67d8-6d45-4fb7-ac53-3b25f42abf39_498x278.gif)

[3](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-3-44426436)

Note how "[postrats](https://threadreaderapp.com/thread/1206339190352437255.html)" are focused on questions three and four instead.

[4](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-4-44426436)

Or "[scoutish](https://universalprior.substack.com/p/soldiers-scouts-and-albatrosses)".

[5](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-5-44426436)

I guess that is the appropriate opposite of cerebral. Less charitable, they can also be called[ soldiers](https://universalprior.substack.com/p/soldiers-scouts-and-albatrosses).

[6](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-6-44426436)

This is a tough problem in philosophy. David Hume says it’s impossible, see [Hume’s Guillotine](https://en.wikipedia.org/wiki/Is%E2%80%93ought_problem).

[7](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-7-44426436)

And hedonistic utilitarianism has some[ nasty pathological solutions](https://en.wikipedia.org/wiki/Wirehead_%28science_fiction%29).

[8](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-8-44426436)

Maybe later though… * _stares off into the distance_ *

[9](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-9-44426436)

A long time ago (long before I started to obsessively note down sources for things I hear) I heard this terrifying story about how actors in Hollywood never get _told_ that their career is over. At some point, the phone just stops ringing.

[10](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-10-44426436)

I really hope this particular combination of terms doesn't get picked up by the search engines.

[11](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-11-44426436)

Well, technically there is a whole cartload of[ caveats and special cases](https://en.wikipedia.org/wiki/Extreme_value_theory), and I haven't even talked about long tails. But I think the general argument is clear.

[12](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-12-44426436)

I guess none of those are _technically_ absorbing states as the probability to remain in the state is not 1. But this is _my_ Substack, therefore I get to make technically-not-quite-correct statements.

[13](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-13-44426436)

This little excursion channeled my inner [Putanumonit](https://putanumonit.com/) for a second.

[14](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-14-44426436)

Except perhaps in the context of the latent rift between "traditional EA" (global health & poverty, animal suffering) and "fancy EA" (longtermism, AI safety).

[15](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-15-44426436)

Quick demonstration:

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa2c75080-e3ab-4101-9d61-5c8e0c409265_612x92.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa2c75080-e3ab-4101-9d61-5c8e0c409265_612x92.png)

[16](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-16-44426436)

Resulting in only <r> = 2pp-2p + 1 expected reward.

[17](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-17-44426436)

Happiness and love, wisdom and beauty, a monster truck, and a[ Rocky from Rock II cardboard cutout](https://advancedgraphics.com/rocky-from-rocky-ii-cardboard-cutout-2786/)

[18](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-18-44426436)

We skipped that one since it’s much more interesting to write about advanced stuff.

[19](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-19-44426436)

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F2b745173-e1a5-4a5b-8ca8-d569c6779fdb_1712x616.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F2b745173-e1a5-4a5b-8ca8-d569c6779fdb_1712x616.png)

[20](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-20-44426436)

I'm using a logarithm function, inspired by [the presumed power-law relationship between income and happiness](http://danluu.com/dunning-kruger/#:~:text=think%20they%20know.-,Income%20%26%20Happiness,-It%27s%20become%20common).

[21](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-21-44426436)

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F05b45e31-68a9-4ea7-bc65-50ca645fbc7b_1566x246.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F05b45e31-68a9-4ea7-bc65-50ca645fbc7b_1566x246.png)

[22](https://universalprior.substack.com/p/slightly-advanced-decision-theory#footnote-anchor-22-44426436)

Usually, I have a source for everything, but here I'm pulling a blank. Perhaps the statement came to me in a dream. It certainly _feels_ true. Edit: Ah, [found it](https://www.theatlantic.com/business/archive/2017/01/economism-and-the-minimum-wage/513155/)!
