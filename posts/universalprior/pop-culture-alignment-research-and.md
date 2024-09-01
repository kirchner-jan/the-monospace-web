# Pop Culture Alignment Research and Taxes

## TL;DR: A quick recap of all the AI progress published recently, a shortcoming of the alignment tax definition, and a dynamical systems model of AI progress.

**Apr 16, 2022**

**Likes:** 1

_Previously in this series:[Cognitive Biases in Large Language Models](https://universalprior.substack.com/p/cognitive-biases-in-large-language?s=w), [Drug addicts and deceptively aligned agents - a comparative analysis](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned?s=w), [Inferring utility functions from locally non-transitive preferences](https://universalprior.substack.com/p/inferring-utility-functions?s=w)._

#  **[All Bad Ends All](https://www.youtube.com/watch?v=oD4anv60ow8&ab_channel=TheBooks-Topic) (click for soundtrack)**

It's been a couple of exciting weeks.

  * Google DeepMind [published a paper](https://arxiv.org/abs/2203.15556) showing we've been training our language models in a suboptimal way. Their new model (continuing the rodent-themed naming scheme), [Chinchilla](https://en.wikipedia.org/wiki/Chinchilla), fixes that issue and manages to compete with/beat the much larger [Gopher](https://en.wikipedia.org/wiki/Gopher).

  * Google Brain didn't get that message in time (also not the message about the rodent-themed naming scheme)[1](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-1-52299921) and [published a paper](https://arxiv.org/abs/2204.02311) where they train a model that's even larger than Gopher, but with the old, suboptimal training scheme. That model can now solve logic puzzles that _I_ could not solve in a thousand years[2](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-2-52299921).

  * The new kid on the block, Anthropic, is not dragging its feet and [published a paper](https://arxiv.org/abs/2204.05862) where they show that reinforcement learning from human values meshes well with their "Helpful, Harmless, ~~and Honest~~ " [approach](https://www.lesswrong.com/posts/oBpebs5j5ngs3EXr5/a-summary-of-anthropic-s-first-paper-3)[3](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-3-52299921). This paper contains the first plot I've seen with a language model score better than a human expert on a relevant metric[4](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-4-52299921) \- but that doesn't mean it didn't happen before. I don't pay super close attention to the metrics.

  * Finally, OpenAI [published a paper](https://arxiv.org/abs/2204.06125) where they trained a new type of text-to-image model based on their previously released [CLIP](https://openai.com/blog/clip/). The result is... mind-blowing, to the point where people on Twitter [announce the end of traditional visual art forms](https://twitter.com/VividVoid_/status/1512140765656338432)[5](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-5-52299921).




Through a series of wacky coincidences (TBA), yours truly got access to the beta version of OpenAI’s new image generation technology and has been updating the thumbnails of his Substack (see [here](https://universalprior.substack.com/about) for a disclosure).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa6a82b12-7c7a-47a8-afba-b69112452b37_1600x534.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa6a82b12-7c7a-47a8-afba-b69112452b37_1600x534.png)Three images created by me with OpenAI’s DALL-E 2. The prompts are: "A painting of Leonardo Da Vinci holding a slice of pizza.", "A painting of a chinchilla and a gopher dancing.", "A painting of a painting of a painting of a painting."

Not coincidentally, one of the founding figures of AI Safety published an April Fool's post announcing that their new strategy is [just giving up](https://www.lesswrong.com/posts/j9Q8bRmwCgXRYAgcJ/miri-announces-new-death-with-dignity-strategy), accompanied by a fair [amount](https://www.lesswrong.com/posts/j9Q8bRmwCgXRYAgcJ/miri-announces-new-death-with-dignity-strategy?commentId=QMfBRH3rydbukCosb) of [despair](https://www.lesswrong.com/posts/Cf2zBkoocqcjnrNFD/emotionally-confronting-a-probably-doomed-world-against) in the [community](https://www.lesswrong.com/posts/wrkEnGrTTrM2mnmGa/retracted-it-s-time-for-ea-leadership-to-pull-the-short). More moderate voices are [willing to bet money](https://www.lesswrong.com/posts/X3p8mxE5dHYDZNxCm/a-concrete-bet-offer-to-those-with-short-ai-timelines) that AI doom is not imminent and that we still have _at least_ ten years[6](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-6-52299921). Prediction markets [have](https://www.metaculus.com/questions/3479/date-weakly-general-ai-system-is-devised/)[ reacted](https://www.metaculus.com/questions/5121/date-of-first-agi-strong/) to the news by decreasing median timelines by 5 to 10 years but still placing it 10 to 20 years in the future. Notably, this is less than the [typical 30 years implied by Platt's law](https://astralcodexten.substack.com/p/biological-anchors-a-trick-that-might?s=r#:~:text=Law%20Taketh%20Away-,Eliezer%E2%80%99s,-other%20argument%20is), but these estimates are notoriously hard to interpret[7](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-7-52299921). 

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa34ca65e-397d-49b5-9921-aa9852d6d2c6_966x332.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa34ca65e-397d-49b5-9921-aa9852d6d2c6_966x332.png)From [source](https://www.metaculus.com/questions/3479/date-weakly-general-ai-system-is-devised/). Note that the y-axis is logarithmic.

In my experience, the best strategy in response to a big, exciting thing is to [ignore it](https://universalprior.substack.com/p/via-productiva?s=w#:~:text=Don%27t%20listen%20to%20Cassandra.). Enough smart people will already be thinking about the topic, and all the important details will reach you through [social osmosis](https://en.wikipedia.org/wiki/Social_osmosis)[8](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-8-52299921) in due time. 

Consequently, I focus on the [B-story](https://stevenpressfield.com/2012/08/the-a-story-and-the-b-story/) that develops parallel to all the exciting rush. I look at whether there currently is any alignment tax, whether the alignment tax might be negative (temporarily), and how we might expect the alignment tax to change.

#  **Pop culture alignment problem**

Let's recap one line of argument for what we might expect advanced AI to look like:

[In the early days](https://www.lesswrong.com/posts/AuMk9g8BhjFKooSdq/my-recollection-of-how-this-all-got-started) when people started to think about advanced AI, there was a pretty even divide on whether an advanced AI will tend to be [friendly](https://www.rivendellinstitute.org/wp-content/uploads/2018/02/McDermott-on-Singularity.pdf) or [unfriendly](https://intelligence.org/files/CFAI.pdf) "by default"[9](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-9-52299921). With this debate as a backdrop, Nick Bostrom [posited](https://www.nickbostrom.com/superintelligentwill.pdf) his Orthogonality thesis in 2012:

> Intelligence and final goals are orthogonal axes along which possible agents can freely vary.

The orthogonality thesis is an idea we are very familiar with from pop culture. Fictional characters can be heroes or villains, and they can be capable or inept. Have a look at this alignment chart that took me way too long to make:

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F2de22e27-b796-4b32-a661-e238aea47dab_1350x1600.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F2de22e27-b796-4b32-a661-e238aea47dab_1350x1600.png)I don't _know_ what half of these characters do, but I hope I placed them approximately right. Please have extensive discussions about this chart in the comments.

None of these characters are real, and [arguments from fictional evidence](https://www.lesswrong.com/posts/rHBdcHGLJ7KvLJQPk/the-logical-fallacy-of-generalization-from-fictional) shouldn't convince anyone. But we don't have to search long to find _real_ examples of very capable evil ([factory farming](https://www.effectivealtruism.org/articles/cause-profile-animal-welfare), [drug cartels](https://en.wikipedia.org/wiki/Drug_cartel), or [Wall Street psychopaths](https://hbr.org/2012/03/psychopaths-on-wall-street)) or very inept good ([petition to end poverty](https://petition.parliament.uk/archived/petitions/62900), [plastic straw bans](https://www.bbc.co.uk/news/uk-england-54366461), or [sweaters for kittens](https://universalprior.substack.com/p/the-tale-of-gandhi-and-the-devil?s=w#:~:text=sweaters%20for%20kittens)). 

The category "capable neutral", however, is the weirdest one. Surprisingly, it contains some striking examples from advanced AI systems:

  * The YouTube recommendation algorithm used to be only [really good at presenting people with content they wanted to watch](https://www.nytimes.com/column/rabbit-hole). As a negative byproduct, they contributed to polarization and misinformation.

  * The Microsoft chatbot Tay used to be only [really good at learning from what people tweeted at it](https://en.wikipedia.org/wiki/Tay_%28bot%29). It quickly became [very ugly](https://www.theverge.com/2016/3/24/11297050/tay-microsoft-chatbot-racist).

  * The Amazon hiring software used to be only [really good at predicting resume scores based on previously observed and evaluated resumes](https://becominghuman.ai/amazons-sexist-ai-recruiting-tool-how-did-it-go-so-wrong-e3d14816d98e). It took way too long until they realized it also incorporated a pretty bad bias against female applicants.




Note that none of these cases resemble "The Joker" - these systems did not have the explicit goal of harming someone or causing chaos. The bad effects I list are only _side_ -effects of the thing the system is designed to do. 

**Systems in the "neutral" or "evil" row are called[unaligned](https://en.wikipedia.org/wiki/Misaligned_goals_in_artificial_intelligence) or [misaligned](https://proceedings.neurips.cc/paper/2020/file/b607ba543ad05417b8507ee86c54fcb7-Paper.pdf), and the problem of pushing them more into the top row is called [The Alignment Problem](https://www.amazon.de/-/en/Brian-Christian/dp/0393635821).** Some people argue that solving the alignment problem could be [one of the most important challenges](https://www.alignmentforum.org/posts/krsjmpDB4kgDq6pdu/axrp-episode-12-ai-existential-risk-with-paul-christiano). Such claims are made about [different](https://www.gvi.co.uk/blog/6-critical-global-issues-what-are-the-worlds-biggest-problems-and-how-i-can-help/) [things](https://www.businessinsider.com/world-economic-forum-world-biggest-problems-concerning-millennials-2016-8?r=US&IR=T) [all the time](https://www.bbvaopenmind.com/en/articles/15-global-challenges-for-the-next-decades/). But when we see how our AI systems are getting exponentially more capable, we can imagine that problems like those with the YouTube recommendation algorithm, Tay AI, and the Amazon hiring software might also grow exponentially in severity. And the same way that more capable AI systems exhibit qualitatively new capabilities, there is also the possibility that we will encounter [qualitatively new problems](https://www.lesswrong.com/posts/FkgsxrGf3QxhfLWHG/risks-from-learned-optimization-introduction).

#  **The only certainty in life**

We might want to be very careful when designing a new system to avoid these problems. We might want to [run many tests before deployment](https://en.wikipedia.org/wiki/AI_box) and build the system to [steer it away from bad failure modes](https://arbital.com/p/corrigibility/). (Or perhaps we could “just” decide [not to develop the system in the first place](https://www.lesswrong.com/posts/vaHgLF2BCEdK3KxQd/convincing-all-capability-researchers).) 

All of these proposals come with a certain _cost_[10](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-10-52299921); they might

  * delay deployment, 

  * make the project more expensive, 

  * and/or decrease performance. 




Paying these costs might be worth it _ex-post_ (YouTube, Microsoft, and Amazon probably wish they had done those things only to avoid the bad PR). Still, ex-ante, the danger of being scooped by a faster rival or the possibility that the safety precautions turn out to be unnecessary are more salient.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ff4488ded-61d7-4bea-9ed2-9cb68e5e6a26_770x1448.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ff4488ded-61d7-4bea-9ed2-9cb68e5e6a26_770x1448.png)Schematic of the alignment tax. The label on the y-axis is debatable. The tax can not only be paid in performance but also in development time or system complexity (in which case the relationship reverses).

 **The additional cost imposed by making a system safe is called the[alignment tax](https://forum.effectivealtruism.org/tag/alignment-tax).** The idea came [originally from Eliezer Yudkowsky](https://arbital.com/p/aligning_adds_time/), but [Paul Christiano popularized the term](https://youtu.be/-vsYtevJ2bc?t=541). The term [popped](https://www.lesswrong.com/posts/HEZgGBZTpT4Bov7nH/mapping-the-conceptual-territory-in-ai-existential-safety#:~:text=about%20the%20subject.-,Alignment,-tax%20and%20alignable) up [repeatedly](https://www.lesswrong.com/posts/X2fRsTjd2kQ89pipE/an-74-separating-beneficial-ai-into-competence-alignment-and#:~:text=to%20image%20below%https://www.lesswrong.com/posts/HEZgGBZTpT4Bov7nH/mapping-the-conceptual-territory-in-ai-existential-safety#:~:text=about%20the%20subject.-,Alignment,-tax%20and%20alignable5D-,Rohin%27s,-opinion%3A%20Here%20are) in the following years, with some people arguing that the tax [could be pretty low](https://forum.effectivealtruism.org/posts/Ayu5im98u8FeMWoBZ/my-personal-cruxes-for-working-on-ai-safety#:~:text=put%20to%20use-,Good,-alignment%20solutions%20will) or [infinitely high](https://www.alignmentforum.org/posts/tmyTb4bQQi7C47sde/safety-capabilities-tradeoff-dials-are-inevitable-in-agi#3__A_better_way_to_think_about_it___alignment_tax_). An infinite tax corresponds to an unsolvable problem (there is no way to make the system safe). A tax close to zero means that it will take very little additional effort to include the safety features (possibly because other researchers have made it very easy to include them).

Arguments on this topic have, however, an unmistakable theoretical bent. We can only determine the actual cost of the alignment tax in retrospect once you realize all your mistakes. And maybe not even then; we don't only care about the actual cost but also the _probability_ of failure. If something works 99% of the time but has a bad failure mode in 1% of cases, [we still want to have good mechanisms to handle the 1%](https://www.lesswrong.com/posts/zzBbRotDubk33YdGd/nuclear-preparedness-guide#Nuclear_Power_Plant_Meltdown). Just because the 1% didn't happen doesn't mean it was the right decision not to prepare for it.

We can (and should) sit down and [think about how AI can go wrong](https://www.lesswrong.com/posts/HBxe6wdjxK239zajf/what-failure-looks-like) and what it would cost to prevent it. If that number comes out to be ∞ or some number larger than anything we could ever reasonably afford, well, [that's not actionable](https://www.lesswrong.com/posts/Cf2zBkoocqcjnrNFD/emotionally-confronting-a-probably-doomed-world-against). If that were the number I came up with, I'd want to keep the argument in mind, hope I'm wrong, and try to do the things I _can_ do.

#  **The Impossibility Of A Negative Alignment Tax**

All of this was a rather longwinded intro[11](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-11-52299921) for an interesting result from the [InstructGPT paper](https://www.arxiv-vanity.com/papers/2203.02155/) and the new [Anthropic paper](https://www.arxiv-vanity.com/papers/2204.05862/) (emphasis is theirs):

>  **We were able to mitigate most of the performance degradations introduced by our fine-tuning.** \--[ Training language models to follow instructions with human feedback](https://www.arxiv-vanity.com/papers/2203.02155/)

> Smaller models experience severe ‘alignment taxes’ – their performance on a wide variety of evaluations declines after RLHF training. However, we find a variety of **alignment bonuses** , with our 13B and 52B RLHF-trained models performing better at zero-shot NLP evaluations, and the same at few-shot evaluations. --[ Training a Helpful and Harmless Assistant with Reinforcement Learning from Human Feedback](https://www.arxiv-vanity.com/papers/2204.05862/)

Note that both papers use a technique called ' _reinforcement learning from human feedback_ ' ([RLHF](https://www.deepmind.com/blog/learning-through-human-feedback)) to [finetune a language model](https://universalprior.substack.com/p/making-of-ian) to produce output that scores well when rated by humans. Both of these papers observe that this finetuning can be done without deteriorating performance on the benchmarks. And both papers observe that the finetuned models became a lot _better_ on things we care about[12](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-12-52299921). And both papers mention that there doesn't appear to be a huge alignment tax (or that we can mitigate it), Anthropic going even so far as to talk about an _alignment bonus_. **What's going on here?**

When I put my [skeptical hat](https://www.alignmentforum.org/posts/X2i9dQQK3gETCyqh2/chris-olah-s-views-on-agi-safety) on, the answer is a bit dismissive: " _RLHF does not provide any degree of safety worth mentioning, and even if it did, it would not continue to work once we have models that are a lot more capable and dangerous. Applying the "alignment tax" concept to these models is a_[category error](https://en.wikipedia.org/wiki/Category_mistake) _and produces misleading intuitions._ "

That's a fair point[13](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-13-52299921), but still, _something_ is going on, and [we need some terminology](https://www.lesswrong.com/posts/9iA87EfNKnREgdTJN/conceptual-engineering-the-revolution-in-philosophy-you-ve). I think about it this way: remember the orthogonality thesis from the beginning. Agents can vary along the two axes "good <-> evil" and "capable <-> inept". When we think of the abstract space of AI techniques, the current state-of-the-art is a point in that space. **Each innovation translates into moving the state-of-the-art in some direction**. At each time, we choose between pushing for innovation in the "safety" or the "capability" direction.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc398a692-7c8a-4a00-ac46-9593b5f3cdbc_1600x525.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc398a692-7c8a-4a00-ac46-9593b5f3cdbc_1600x525.png) **2D picture of AI innovations. a.** The current state-of-the-art (grey dot) lies in the alignment chart space from section 1. At any time, we can consider the direction in which a “safety” intervention (blue) or a “capability” intervention (orange) pushes the state-of-the-art. **b.** In an “alignment tax situation”, the two vectors have a strictly negative dot product. **c.** In an “alignment bonus” situation, the two vectors have a strictly positive dot product.

This model allows us to explain:

  * how a safety technique can improve capabilities: To some degree, safety is a capability. If a system is not safe at all, it's also not useful at all.

  * how an alignment tax might come about; at some point, we might have to decide between pushing more in the "capable" or the "good" direction _,_ and there might be hard trade-offs between the two.




The model also allows us to visualize possible failure modes:

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F69f12e8e-4d06-4c12-a56a-4fb384406869_1600x506.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F69f12e8e-4d06-4c12-a56a-4fb384406869_1600x506.png)

The picture shows three scenarios I could come up with:

  *  **The automobile model.** When we built the first cars, they were [insanely](https://eu.detroitnews.com/story/news/local/michigan-history/2015/04/26/auto-traffic-history-detroit/26312107/) [dangerous](https://americanhistory.si.edu/america-on-the-move/essays/automobile-safety). Figuring out how to not make them as dangerous was pretty central to the mission of making them useful. But eventually, we figured out how to not make [cars explode](https://www.youtube.com/watch?v=hVbpGmX890I&ab_channel=FilmsbytheYear), and we reached the point where safety measures make the experience of riding a car worse[14](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-14-52299921). We have now reached a point where some features that would substantially improve safety[15](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-15-52299921) are not implemented because they would deteriorate capabilities too much[16](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-16-52299921).

  *  **The deception scenario.** With the help of a psychiatrist friend, I've written previously on how drug addicts can be[ incredibly good at deception](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned). They will credibly signal all the things that make you believe that this time they have _really_ changed - and then disappear with your microwave. As far as I can tell, there is no empirical evidence of deceptive AI yet[17](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-17-52299921). But there are [theoretical arguments](https://www.lesswrong.com/posts/zthDPAjh9w6Ytbeks/deceptive-alignment) for why it might happen once capabilities increase. In this scenario, everything appears to be going super smoothly, and all the safety features we implement keep pushing in the same direction as the capability features. The AI is an overwhelming sweetheart - helping old ladies across the street and everything - until it isn't. Our measure for "good" and "bad" was not reliable, and by the time we found out[18](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-18-52299921), it was too late.

  *  **The "what failure looks like" scenario.** This one is speculative and inspired by [an alignment failure story](https://www.lesswrong.com/posts/AyNHoTWWAJ5eb99ji/another-outer-alignment-failure-story) but appears like a very real possibility. We might try to apply safety innovations at each point of the process, but they don't seem to be _doing_ anything beyond some point. The situation is gradually getting more severe, but we can't put the finger on the issue. Whenever we run a diagnostic, we get "everything is going according to plan". And at some point, the entire system is so opaque that nobody can tell what is going on anymore.




These scenarios are not meant to be comprehensive, but I hope they illustrate the usefulness of the 2D model.

#  **Closing thoughts**

I’m undecided about whether it’s a good thing that safety research and capability research are pushing in the same direction. On the one hand, [incentives matter](https://equilibriabook.com/), and having strong incentives to do safety research is (ceteris paribus) a good thing. On the other hand, things are already moving fast and _any_ push in the capabilities direction is [seen as a threat by some](https://www.lesswrong.com/posts/kipMvuaK3NALvFHc9/what-an-actually-pessimistic-containment-strategy-looks-like). But independent of any moral judgment of what is happening, knowing that it’s happening, and having better terminology to communicate it, appears useful.

Now I really have to head out! If you’re at EAG London let me know - would love to meet you, dear reader :)

[1](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-anchor-1-52299921)

I like "[Giant Hutia](https://en.wikipedia.org/wiki/Heptaxodontidae)" or "[New York Pizza Rat](https://www.youtube.com/watch?v=UPXUG8q4jKU&ab_channel=MattLittle)".

[2](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-anchor-2-52299921)

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F5b967bf9-d7f3-4745-9b36-f1b18da9b0a4_1566x732.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F5b967bf9-d7f3-4745-9b36-f1b18da9b0a4_1566x732.png)

From Figure 19 of [source](https://arxiv.org/pdf/2204.02311.pdf). Someone on Twitter pointed out that Leonardo is more likely to hold a slice of pizza, so the answer should be Italy. I'm happy that we've reached this level of criticism.

[3](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-anchor-3-52299921)

They leave out “honest” because it's really hard to evaluate for non-expert humans.

[4](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-anchor-4-52299921)

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F2a24fe50-0a9f-42a8-96e0-88c4054e07be_854x596.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F2a24fe50-0a9f-42a8-96e0-88c4054e07be_854x596.png)

From Figure 1 of [source](https://arxiv.org/pdf/2204.05862.pdf). The green triangle is just outside the "Professional Writer" region. That point represents the set-up where the model was explicitly fine-tuned to be helpful, neglecting harmlessness.

[5](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-anchor-5-52299921)

That's Twitter, though. An artsy friend of mine is now considering changing career tracks to go into "AI art", something that wasn’t really on the menu a few weeks ago.

[6](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-anchor-6-52299921)

To those not familiar with this type of talk, yeah, ten years is still a _lot_ shorter than what the median person on the street or even [some experts](https://www.alignmentforum.org/posts/KrJfoZzpSDpnrv9va/draft-report-on-ai-timelines) would guess. I don't have robust reasoning for how different "timelines" should affect what I do on a day-to-day basis, so I tend not to think about the question too much.

[7](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-anchor-7-52299921)

There has been an influx of new people on those questions in the last two weeks for the prediction markets. It's probably fair to assume that those are not experts (who would have thought about the question even before the new wave of papers) but people who decided to participate _because of_ the papers. And beyond prediction markets, there's this [ongoing discussion](https://astralcodexten.substack.com/p/biological-anchors-a-trick-that-might?s=r) about whether forecasting AI is possible.

[8](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-anchor-8-52299921)

Or, let’s be honest, [LessWrong](https://www.lesswrong.com/).

[9](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-anchor-9-52299921)

i.e. if we don't put a lot of work into pushing in one direction or the other.

[10](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-anchor-10-52299921)

Imagine being the poor schlub who has to tell their boss that the system won't be ready for another year because the team has decided to lock it in a box to perform psychoanalysis.

[11](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-anchor-11-52299921)

I'm traveling this weekend, and this was supposed to be just a quick & dirty, lightweight post. [If I had more time, I’d write a shorter post.](https://quoteinvestigator.com/2012/04/28/shorter-letter/)

[12](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-anchor-12-52299921)

As opposed to the benchmarks, which don't capture what we care about super well once they are pushed to an extreme.

[13](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-anchor-13-52299921)

thank you, skeptical hat

[14](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-anchor-14-52299921)

[seatbelts were massively unpopular](https://www.wpr.org/surprisingly-controversial-history-seat-belts) when they were first mandated

[15](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-anchor-15-52299921)

like [limiting the speed of a car on highways](https://www.youtube.com/watch?v=VejNuZ3RrMs)

[16](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-anchor-16-52299921)

Also, we cannot adopt [other](https://www.bloomberg.com/news/features/2020-08-12/why-are-cars-still-so-dangerous-to-pedestrians)[ technologies](https://en.wikipedia.org/wiki/Unsafe_at_Any_Speed) for some reason, although they appear to be an improvement in _both_ safety and capabilities. This would be an interesting topic to dive deeper into - is it the "evil greedy company," or is it some [inadequate equilibrium](https://equilibriabook.com/)?

[17](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-anchor-17-52299921)

Which might be a good or a _really_ bad thing.

[18](https://universalprior.substack.com/p/pop-culture-alignment-research-and#footnote-anchor-18-52299921)

the [milliseconds before everyone dies](https://www.lesswrong.com/tag/ai-takeoff#:~:text=easier%20to%20engineer.-,Hard%20takeoff,-A%20hard%20takeoff).
