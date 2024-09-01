# Elementary Infra-Bayesianism

## TL;DR: I got nerd-sniped into working through some rather technical work in AI Safety. Here's my best guess of what is going on. Imprecise probabilities for handling catastrophic downside risk.

**May 08, 2022**

**Likes:** 5

**Short summary** : I apply the updating equation from Infra-Bayesianism to a concrete example of an Infradistribution and illustrate the process. When we "care" a lot for things that are unlikely given what we've observed before, we get updates that are extremely sensitive to outliers.

* * *

I've [written previously](https://universalprior.substack.com/p/the-greedy-doctor-problem?s=w) on how to act when confronted with something smarter than yourself. When in such a precarious situation, it is difficult to trust “the other”; they might dispense their wisdom in a way that steers you to their benefit. [In general](https://arbital.com/p/Vinge_principle), we're screwed.

But there are ideas for a constrained set-up that [forces “the other” to explain itself and point out potential flaws in its arguments](https://openai.com/blog/debate/). We might thus leverage “the other”'s ingenuity against itself by slowing down its reasoning to our pace. “The other” would no longer be an oracle with [prophecies that might or might not kill us](https://en.wikipedia.org/wiki/Pythia) but instead a teacher who lets us see things we otherwise couldn't.

While that idea is nice, there is a severe flaw at its core: [obfuscation](https://www.alignmentforum.org/posts/PJLABqQ962hZEqhdB/debate-update-obfuscated-arguments-problem). By making the argument sufficiently long and complicated, “the other” can sneak a false conclusion past our defenses. Forcing “the other” to lay out its reasoning, thus, is not a foolproof solution. But ([as some have argued](https://www.alignmentforum.org/posts/huNvfttDpxCApC3xZ/an-132-complex-and-subtly-incorrect-arguments-as-an-obstacle#:~:text=I%E2%80%99m%20not%20really%20sure%20whether%20I%20expect%20this%20to%20be%20a%20problem%20in%20practice)), it's unclear whether this will be a problem in practice.

Why am I bringing this up? No reason in particular.

#  **Why Infra-Bayesianism?**

Engaging with the work of Vanessa Kosoy is a [rite](https://www.alignmentforum.org/posts/SzrmsbkqydpZyPuEh/my-take-on-vanessa-kosoy-s-take-on-agi-safety) [of](https://www.alignmentforum.org/posts/Zi7nmuSmBFbQWgFBa/infra-bayesianism-unwrapped) [passage](https://www.alignmentforum.org/posts/beLgLr6edbZw4koh2/an-143-how-to-make-embedded-agents-that-reason) in the AI Safety space. Why is that?

  * The [pessimist](https://universalprior.substack.com/p/pop-culture-alignment-research-and?s=w#:~:text=going%20on%20here%3F-,When,-I%20put%20my) answer is that alignment is really, really difficult, and if you can't understand complicated math, you can't contribute.

  * The [optimist](https://universalprior.substack.com/p/im-not-getting-in-that-van?s=w#:~:text=It%27s%20driving%20a%20fire%20engine%20through%20the%20desert%20and%20rejoicing) take is that math is fun, and (a certain type of) person gets nerd sniped by this kind of thing.

  * The realist take naturally falls somewhere in between. Complicated math can be important _and_ enjoyable. It's okay to have fun with it.




But being complicated is (in itself) not a mark of quality. [If you can't explain it, you don't understand it](https://en.wikiquote.org/wiki/Richard_Feynman#:~:text=You%20know%2C%20I%20couldn%27t%20do%20it.%20I%20couldn%27t%20reduce%20it%20to%20the%20freshman%20level.%20That%20means%20we%20really%20don%27t%20understand%20it.). So here goes my attempt at "Elementary Infrabayesianism", where I motivate a portion of Infrabayesianism using pretty pictures and high school mathematic[1](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-1-53997824).

#  **Uncertain updates**

Imagine it's late in the night, the lights are off, and you are trying to find your smartphone. You cannot turn on the lights, and you are having a bit of trouble seeing properly[2](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-2-53997824). You have a vague sense about where your smartphone should be (your prior, panel **a** ). Then you see a red blinking light from your smartphone (sensory evidence, panel **b** ). Since your brain is [really good at this type of thing](https://www.sciencedirect.com/science/article/abs/pii/S0928425704000841), you integrate the sensory evidence with your prior optimally[3](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-3-53997824) to obtain an improved sense of where your smartphone might be (posterior, panel **c** ).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F44d0aa47-0ba6-4a32-8d92-72c7720a16ac_2677x659.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F44d0aa47-0ba6-4a32-8d92-72c7720a16ac_2677x659.png)That's boring old Bayes, nothing to see here; move along.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F08c6c560-5828-4bb9-8252-63e307b47b24_450x240.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F08c6c560-5828-4bb9-8252-63e307b47b24_450x240.png)

Now let's say you are even more uncertain about where you put your smartphone.[4](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-4-53997824) It might be one end of the room or the other (bimodal prior, panel **a** ). You see a blinking light further to the right (sensory evidence, panel **b** ), so your overall belief shifts to the right (bimodal posterior, panel **c** ). Importantly, by conserving probability mass, your belief that the phone might be on the left end of the room is reduced. [The absence of evidence is evidence of absence](https://www.alignmentforum.org/posts/mnS2WYLCGJP2kQkRn/absence-of-evidence-is-evidence-of-absence).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F7fcb60df-dc59-4831-8911-155c6349d3a4_3413x659.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F7fcb60df-dc59-4831-8911-155c6349d3a4_3413x659.png)This is _still_ only boring old Bayes. To go Infra, we have to go weird.

#  **Fundamentally uncertain updates**

Let's say you are _really, fundamentally_ unsure about where you put your phone. If someone were to ~~put a gun to your head~~ threaten to [sign you up for sweaters for kittens](https://universalprior.substack.com/p/the-tale-of-gandhi-and-the-devil?s=w#:~:text=sweaters%20for%20kittens) unless you give them your best guess, you could not[5](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-5-53997824). 

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F0544e483-60e3-435a-acf3-f6a36d62ee9c_1072x659.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F0544e483-60e3-435a-acf3-f6a36d62ee9c_1072x659.png)

This is the situation Vanessa Kosoy finds herself in[6](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-6-53997824)[7](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-7-53997824). With Infra-Bayesianism, she proposes a theoretical framework for thinking in situations where you can't (or don't want to) specify a prior over your hypotheses. 

Because she is a mathematician, she is using the proper terminology while I’m using the handwavy language of Bayesian sensory integration:

  * a _signed measure_ is a generalization of probability distributions,

  * an _indicator function for a fuzzy set_ is a generalization of your observation/sensory evidence,

  * a continuous function g∈C(X,[0,1]) is... wait, what is g?




g tells you how much you care about stuff that happens in regions that become very unlikely/impossible given the sensory evidence you obtain. Why should you care about that, you ask? Great question; let's not care about it for now. Let's set it equal to zero, g=0.

When g=0, the updating equation for our two priors, P1 and P2, becomes very familiar indeed:

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F6992aeaa-d768-491f-b569-5d3805a5c28c_978x236.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F6992aeaa-d768-491f-b569-5d3805a5c28c_978x236.png)

This is basically Bayes' theorem applied to each prior separately. Still, the evidence term (the denominator) is computed in a wonky way[8](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-8-53997824), but this doesn't make much difference since it's a shared scaling factor. Consistently, things also look very normal when using this updating rule to integrate sensory information. We shift our two priors towards the evidence and scale them proportional to how unlikely they said the evidence is.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F38488f90-80ce-427e-b8f9-7ada74e15836_3413x659.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F38488f90-80ce-427e-b8f9-7ada74e15836_3413x659.png)While this picture looks almost identical to the previous section, notice that the posterior is still split in two! Thus, we can still tell which one of our initial guesses turned out to be "more accurate".

#  **Fundamentally** _ **dangerous**_ **updates**

Alright, you know where this is going. We will have to start caring about things that become less likely after observing the evidence. Why we have to care is a bit hard to motivate; Vanessa Kossoy and Diffractor motivate in [three parts](https://www.alignmentforum.org/s/CmrW8fCmSLK7E25sa/p/YAa4qcMyoucRS2Ykr#:~:text=will%20confuse%20you.-,First,-%2C%20what%20sorts%20of) where I don't even get the first part[9](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-9-53997824)[10](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-10-53997824).

Instead, I will motivate why you might care about things that seem very unlikely given your evidence by revealing more information about the thought experiment:

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F08d787c9-83f9-498e-8138-076b5d870433_1072x659.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F08d787c9-83f9-498e-8138-076b5d870433_1072x659.png)

It's not so much that you _can't_ give your best guess estimate about where you put your smartphone. Rather, you _dare_ not. Getting this wrong would be, like, _really bad_. You might be unsure whether it's even your phone that's blinking or if it's the phone of the other person sleeping in the room[11](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-11-53997824). Or perhaps the bright red light you see is the [bulbous red nose](https://astralcodexten.substack.com/p/deceptively-aligned-mesa-optimizers?s=r#:~:text=prime%20minister.-,So,-%3A%20suppose%20we%20train) of somebody else sleeping in the room. Getting the location of your smartphone wrong would be messy. Better not risk it. We'll set g=1.

The update rule doesn't change too much at first glance[12](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-12-53997824):

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F6852a5d0-006d-4697-a0fb-c158d28059be_1168x238.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F6852a5d0-006d-4697-a0fb-c158d28059be_1168x238.png)Again, the denominator changes from one wonky thing (P+) to another (P−); but that still doesn't matter since it's the same for both equations. 

But there is a ϰ that showed up out of nowhere! ϰ is a variable that tells us how good our distribution is at _explaining things we did not get any evidence for_[13](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-13-53997824). Intuitively, you can tell that this will favor the prior distribution that was previously punished for not explaining the observation. And indeed, when we run the simulation:

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F6eae1bd1-b8aa-444e-accb-5ae2a197ff9d_3413x659.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F6eae1bd1-b8aa-444e-accb-5ae2a197ff9d_3413x659.png)

One of the two "distributions"[14](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-14-53997824) is taking off! Even though the corresponding prior was bad at explaining the observation, the updating still _strongly_ increases the mass associated with that hypothesis.

Intuitively this translates into something like:

> You are unsure about the location of your smartphone (and mortally afraid to get it wrong). You follow the red blinking light, but you never discard your alternative hypothesis that the smartphone might be at the other end of the room. At the slightest indication that something is off you'll discard all the information you have collected and start the search from scratch.

This is a _very_ cautious strategy, and it might be appropriate when you're in dangerous domains with the potential for catastrophic outliers, basically what Nassim Taleb calls [Black Swan](https://en.wikipedia.org/wiki/The_Black_Swan:_The_Impact_of_the_Highly_Improbable) events. I'm not sure how _productive_ this strategy is, though; noise might dramatically mess up your updates at some point.

#  **Closing thoughts**

This concludes the introduction to Elementary Infrabayesianism. I realize that I have only scratched the surface of what's in [the sequence](https://www.lesswrong.com/s/CmrW8fCmSLK7E25sa), and there is [more](https://www.alignmentforum.org/posts/gHgs2e2J5azvGFatb/infra-bayesian-physicalism-a-formal-theory-of-naturalized) coming [out](https://www.alignmentforum.org/posts/PrYbdKcj89f8swCkr/infra-topology) every other month, but letting yourself get nerd-sniped is just about as important as being able to [stop working on something and publish](https://universalprior.substack.com/p/via-productiva?s=w#:~:text=Don%27t%20fight%20the%20Hydra.). I hope what I wrote here is helpful to some, particularly in conjunction with the other explanations on the topic ([1](https://www.alignmentforum.org/posts/SzrmsbkqydpZyPuEh/my-take-on-vanessa-kosoy-s-take-on-agi-safety) [2](https://www.alignmentforum.org/posts/Zi7nmuSmBFbQWgFBa/infra-bayesianism-unwrapped) [3](https://www.alignmentforum.org/posts/beLgLr6edbZw4koh2/an-143-how-to-make-embedded-agents-that-reason)), which also go beyond the introduction.

I'm afraid at this point I'm obliged to add a hot take on what all of this means for AI Safety. I'm not sure. I can tell myself a story about how being _very careful_ about how quickly you discard alternative hypotheses/narrow down the hypothesis space is important. I can also see the outline of how this framework ties in with [fancy decision theory](https://www.lesswrong.com/tag/updateless-decision-theory). But I still feel like I only scratched the surface of what's there. I'd really like to get a better grasp of that [Nirvana trick](https://www.lesswrong.com/s/CmrW8fCmSLK7E25sa/p/zB4f7QqKhBHa5b37a#:~:text=to%20formalize%20the%20%22-,Nirvana,-trick%22%20\(elaborated%20below), but timelines are short and there is a lot out there to explore.

[1](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-anchor-1-53997824)

[French high school](https://www.quora.com/Why-do-the-French-love-mathematics-or-consider-it-of-such-import-and-therefore-teach-it-with-such-rigor-to-such-an-extent), though, not [American high school](https://www.businessinsider.com/exchange-students-american-high-schools-easier-2017-3).

[2](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-anchor-2-53997824)

If there's been alcohol involved, I want to know nothing of it.

[3](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-anchor-3-53997824)

despite your alledged disinhibited state

[4](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-anchor-4-53997824)

The idea that alcohol might have been involved in navigating you into this situation is harder to deny.

[5](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-anchor-5-53997824)

Is this ever a reasonable assumption? I don't know. It seems to me you can always pick an [uninformative prior](https://en.wikipedia.org/wiki/Prior_probability#Uninformative_priors). But perhaps the point is that sometimes you _should_ acknowledge your [cluelessness](https://forum.effectivealtruism.org/posts/LdZcit8zX89rofZf3/evidence-cluelessness-and-the-long-term-hilary-greaves). Otherwise, you expose yourself to [severe downside risks](https://en.wikipedia.org/wiki/Black_swan_theory)? But I'm not convinced.

[6](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-anchor-6-53997824)

Not the coming home drunk situation, only the fundamental confusing part. Oh no, that came out wrong. What I mean is that she is trying to become _less_ fundamentally confused. Urgh. I'll stop digging now.

[7](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-anchor-7-53997824)

A proper infradistribution would have to be a convex set of distributions and upper complete and everything. Also, the support of the Gaussians would have to be compact. But for the example I'm constructing, this won't become relevant. The edge points (the two Gaussians) of the convex set fully characterize how the entire convex set changes.

[8](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-anchor-8-53997824)

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Faa5158c4-bd53-465a-b7fb-a024441377be_1668x154.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Faa5158c4-bd53-465a-b7fb-a024441377be_1668x154.png)caption...

rather than

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fd84f2bf7-9c6a-4cba-b0c0-202dba016b54_742x182.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fd84f2bf7-9c6a-4cba-b0c0-202dba016b54_742x182.png)caption...

for an uninformative prior.

[9](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-anchor-9-53997824)

Despite having read it at least twice!

[10](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-anchor-10-53997824)

A more "natural" way to motivate it might be to talk about possible worlds and [updateless decision theory](https://www.alignmentforum.org/tag/updateless-decision-theory), but this is something that you apparently get _out_ of Infrabayesianism, so we don't want to use it to motivate it.

[11](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-anchor-11-53997824)

The story is coming together. This is why you can't turn on the light, btw.

[12](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-anchor-12-53997824)

Actually, in this particular example, it turns out that

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fd134e827-2b05-4b06-8a63-52b891c6ba5f_360x114.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fd134e827-2b05-4b06-8a63-52b891c6ba5f_360x114.png)

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fec7e573f-e150-490d-913a-a9b84220b97b_2294x634.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fec7e573f-e150-490d-913a-a9b84220b97b_2294x634.png)

, since we've got two normalized probability distributions.

[13](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-anchor-13-53997824)

You can't find any ϰ in Vanessa Kosoy's paper because she is thinking more generally about Banach spaces and a situation where there is no [Radon-Nikodyn derivative](https://en.wikipedia.org/wiki/Radon%E2%80%93Nikodym_theorem#Radon%E2%80%93Nikodym_derivative). But if we have a density for our measures, we can write ϰ as 

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F7faa9e4d-8e67-479c-91de-e37c49c57b97_410x132.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F7faa9e4d-8e67-479c-91de-e37c49c57b97_410x132.png)

for an inframeasure (m,b).

[14](https://universalprior.substack.com/p/elementary-infra-bayesianism#footnote-anchor-14-53997824)

I'm still calling them distributions, although we've left that territory already in the last section. More appropriate would be something like "density function of the signed measure" or "Radon-Nikodym derivative".
