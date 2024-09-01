# Trust-maximizing AGI

## TL;DR: In the context of the AI Safety camp, Karl and I developed the idea of the "trust-maximizer". This write-up makes the case for "trust" as a potentially desirable goal for advanced AI.

**Feb 25, 2022**

**Likes:** 4

Possibly [deceptive behavior](https://www.alignmentforum.org/posts/Y76durQHrfqwgwM5o/lcdt-a-myopic-decision-theory) of an advanced AI is a core problem in AI safety. But what if we gave an AGI the goal of maximizing human trust in it? Would this change the relative attractiveness of deception compared to honesty from the point of view of the AGI? While we are aware of several technical difficulties and limitations, we hope this essay will offer some insights into the interesting properties of trust as a goal.

Our entire civilization is built on trust. Without trust in the value of money, trade would be impossible. Without some level of trust in the law and the government, democracy is inconceivable. Even dictators need the trust of at least a small number of people who keep them in power. At the same time, scammers, criminals, and some politicians are experts at exploiting the trust of others to further their selfish interests. 

Due to the convergence of instrumental goals, any AGI will seek to maximize its power over the world ([Bostrom 2012](https://www.nickbostrom.com/superintelligentwill.pdf)). One obvious way of achieving this would be to manipulate humans through persuasion, bribery, bullying, or deception. Since in most cases humans will want to limit the power of the AGI, but are relatively easy to deceive, deception will often be the easiest way for an AGI to circumvent limits and restraints and increase its power. After all, humans usually are the weakest link in most modern security environments ([Yudkowsky 2002](https://www.yudkowsky.net/singularity/aibox), [Christiano 2019](https://www.lesswrong.com/posts/hjEaZgyQ2iprDhkg8/security-amplification)). On top of that, inner alignment problems may lead to [“deceptive alignment”](https://www.lesswrong.com/posts/zthDPAjh9w6Ytbeks/deceptive-alignment) during training.

Against this background, suppose we give an AGI the goal to “maximize the total expected trust in it by human adults”. Let’s call this the “trust-maximizer”. Would that be a good idea, assuming that we are able to define “total expected trust” in a reasonable and implementable way?

The problems with this idea are obvious. Although trust is usually seen as a result of honesty, it can also be achieved through deception. In many cases, it may be easier to gain people’s trust by lying to them or making false promises than by telling them the truth. So the optimal strategy for a trust-maximizer could be to deceive people into trusting it.

However, there is a certain [asymmetry](https://universalprior.substack.com/p/task-decomposition-and-scientific) in maximizing trust over time: Like a tree that needs a long time to grow but can be cut down in minutes, trust is often hard to gain, but easy to lose. Just one uncovered lie can completely destroy it in an instant. Therefore, trust gained through deception is hard to maintain in the long term. False promises can’t be fulfilled, lies may sooner or later be uncovered. Even a superintelligent AGI, although it would likely be very good at deception, might not be able to ensure that humans won’t see through its lies at some point. Honesty, on the other hand, can easily be maintained indefinitely. While trust gained by deception will become more unstable over time ([Yudkowsky 2008](https://www.lesswrong.com/posts/wyyfFfaRar2jEdeQK/entangled-truths-contagious-lies)), honesty is becoming a stronger trust-building strategy the longer it is maintained.

Why, then, are people using deception as a trust-gaining strategy all the time? One reason is that for them, other people’s trust is just an [instrumental goal towards whatever ultimate goal they have](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned). As such, they need it only for a limited time. Therefore, long-term stable trust is often not a priority. Politicians, for example, need people’s trust only as long as they stay in office, or in some cases only until the election is over. A scammer needs the victim’s trust for an even shorter time. If the deception is uncovered afterward and trust is destroyed, they will still have achieved their goals. So deception can be an optimal strategy in these cases.

This might change if trust is not just an instrumental goal, but the ultimate goal. In this case, whether deception is the optimal strategy depends on the total discounted sum of trust over time it can gain, compared to a strategy of honesty. 

**Factors influencing honesty as an optimal strategy for a trust-maximizer**

There are several factors determining the sum of trust over time (fig. 1), for example: 

  * The average initial level of trust

  * The absolute limit for trust, given an honest or deceptive strategy

  * The time it takes to build trust through deception vs. the time needed by honesty

  * The probability that deception is uncovered (depending, in part, on the deception skills of the deceiver)

  * The time it takes for the deceiver to regain trust after deception is uncovered

  * The potential effect of false accusations on the honest strategy

  * The relative weight of future trust vs. current trust (discount factor)




[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F88fe5789-0459-4843-a489-1703715207da_1600x759.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F88fe5789-0459-4843-a489-1703715207da_1600x759.png)Fig. 1: Trust gained by deception and honesty over time

A strategy of honesty may take longer to gain trust, but might be more stable in the long term. Once deception is uncovered, trust decreases drastically. However, even people who have deceived others can, over time, sometimes regain some of the trust they lost when the deception was uncovered. Also, there may be a long-term limit to the trust you can get by being honest, which in principle could be lower than the short-term limit accessible through deception. And it is possible for a rival to reduce or even destroy trust in someone who is always honest, for instance through false accusations. There is also usually an initial level of trust people are willing to give to things or people they don’t know, but expect to be beneficial to them, which may be based on personality, culture, and prior experience.

It is of course possible to influence these factors. For example, the general level of trust, which determines average initial trust in an AGI and the time it takes to build trust, could be raised by fostering a culture of openness and honesty. Strengthening security and law enforcement can make it more likely that deception is uncovered, making an honest strategy more attractive. The discount factor in a goal function determines the relative importance of long-term over short-term trust.

Many of these influencing measures could be pursued by the trust-maximizer itself, so it would be able to increase the success probability of both the honest and the deceptive strategy, if it chose to pursue one or the other. For example, if it follows an honest strategy, it could try to increase the overall level of trust by reducing conflicts, fostering education and rationality, strengthening democratic institutions and law enforcement, and actively fighting disinformation, corruption, and crime. This way, it might even be able to increase the limit of trust it can gain through honesty over time close to one hundred percent. In a trust-based utopia, an all-knowing, all-powerful trust-maximizing AGI might even be able to completely dispel any deception and lies, creating an atmosphere of total trust. Chances are that this could be an optimal strategy for maximizing trust in the long run.

There is another significant advantage of choosing the honest strategy: it fosters cooperation, both with humans and with other AGIs. Typically, humans will only help each other if there is at least some level of trust between them. A strategy of deception to maximize trust would be even harder to maintain in a complex environment where the AGI depends on cooperation with other systems, institutions, or individual humans. Like the old saying goes: You can fool all people for some time, or some people all the time, but you can’t fool all people all the time.

Of course, if the trust-maximizer is superintelligent and self-improving, it may be able to increase its ability to deceive humans and other AIs over time. While honesty doesn’t require any particular skills, deception becomes easier with increased intelligence and knowledge, so over time deception might become more attractive as a strategy relative to honesty. The trust-maximizer might also be able to switch from an honest to a deceptive strategy at any time, although the reverse switch would be more difficult.

 **Instrumental goals of an honest trust-maximizer**

The arguments above indicate that rather than remaining passive, a trust-maximizer following an honest strategy would pursue certain instrumental goals beneficial to its ultimate goal. For example, it might

  * increase its own explainability in order to make its decisions better understandable, and thus easier to trust

  * try to be helpful to people, because they will trust a system that is beneficial to them more easily

  * follow a long-term strategy rather than short-term goals, because this strengthens reliability, an important factor for trust

  * fight disinformation and deception by others (both AI and humans)

  * increase general welfare

  * improve education

  * promote rationality and science

  * strengthen democracy and law enforcement

  * fight corruption.




Of course, on top of this, it would still follow the classic instrumental goals of securing its own existence and gaining power in the world to further its goal. But it would likely do so in a way that wouldn’t violate its honest trust-maximizing strategy. For example, instead of deceiving or manipulating them, it might try to convince people with truthful arguments that giving it access to more computing power would enable it to help them even more.

 **Defining and measuring “trust”**

Of course, in order to specify a valid goal function for an AGI, “expected total trust” must be defined in a way that is both clear and measurable. We are not trying to solve this problem here. Psychological literature shows that there are [different kinds of trust](https://www.researchgate.net/profile/Devon-Johnson-2/publication/222706072_Cognitive_and_Affective_Trust_in_Service_Relationships_Journal_of_Business_Research/links/5bf982de458515a69e387619/Cognitive-and-Affective-Trust-in-Service-Relationships-Journal-of-Business-Research.pdf), for example “cognitive” trust based on a more logical approach towards an expected behavior in contrast to “affective” trust that is based on emotions, affections, and prior behavior, e.g. feeling “cared for” by someone. Trust can be measured in surveys or derived from actual behavior, often leading to [conflicting or inconclusive results](https://www.econstor.eu/handle/10419/35525). However, since trust is an important concept that is already broadly applied both in economic theory and practice (e.g. in brand building), we hope it should be possible to find a solution to this problem.

One important factor to consider when defining and measuring trust is [“reward hacking”](https://deepmind.com/blog/article/Specification-gaming-the-flip-side-of-AI-ingenuity). For instance, if trust was measured through surveys, the trust-maximizer could try to bribe or force people into giving the “right” answer, similar to so-called “elections” in autocratic regimes. To reduce this risk, multiple “trust indicators” could be used as reward signals, including the actual behavior of people (for example, how often they interact with the trust-maximizer and whether they follow its recommendations). It should also be made clear in the definition that trust in this sense can only be gained from clear-minded adults who are able to make rational informed decisions, free of influences like drugs or psychological pressure. Of course, any such influencing by the trust-maximizer would be considered a deception and is therefore incompatible with an honest strategy.

As stated above, an important question is the relative weight of future trust against current trust. [Myopia has been discussed](https://www.alignmentforum.org/posts/Y76durQHrfqwgwM5o/lcdt-a-myopic-decision-theory) as a strategy to limit deceptive behavior in some cases. However, because of the described asymmetry, for a trust-maximizer a focus on the short-term might increase the relative attractiveness of a deceptive strategy. Maximizing trust over time, on the other hand, might also lead to the instrumental goal of securing the future of humanity for as long as possible. However, maximizing expected trust in the far future could lead to severe restrictions for current generations. For example, the AGI could decide to imprison all people in order to prevent self-destructive wars until it has found a way to colonize other planets. This could be a valid strategy even for an honest trust-maximizer because even though it would minimize trust within the current population, future generations would probably see its decisions as far-sighted and might even be grateful for them. To prevent this, future trust could be discounted by some factor. The specific value of this factor would strongly influence the relative attractiveness of an honest strategy compared to the deceptive alternative. It is beyond the scope of this post to suggest a specific value.

Another open question is what exactly is meant by “it” in the goal statement. An AGI could be a network of loosely connected systems, each with its own reward function. It is also possible that the AGI could create copies of itself, to prevent destruction and to improve its effectiveness and efficiency. One possible solution would be to connect trust not to a particular machine, but to a brand, like “Google”. Brands have the function of creating and maintaining trust in a company’s products. That is the reason why people are willing to pay significantly more for the same product if it is labeled with a “trusted” brand. The AGI would then have a strong instrumental goal of controlling how and where its brand is used. One obvious way would be to label any user interface the AGI controls with the brand. But other products could carry the brand as well, for example, books the AGI has written. It could even license its brand to other AIs that comply with its high standards of honesty and trust.

One potential drawback of using a brand in the goal would be that in principle, a brand can be attached to anything. So the AGI could for example try to buy well-trusted products and label them with its brand, instead of attaching it to its own output. This hack must be prevented in the definition of “it”. Again, it is beyond the scope of this post to solve this problem.

 **Potential loopholes and additional restrictions**

We are not proposing that the trust-maximizer described so far would be “safe”. While we think that an honest strategy could be optimal for a trust-maximizer under certain conditions, it is not entirely clear what these conditions are, and how to ensure them. There could also be a sudden strategic shift in the future: If the system becomes extremely powerful, it may be so good at deception that humans could never uncover its lies, in the way a dog could never understand the tricks its master plays on it. However, to get to this point, the AGI would probably have to pursue an honest strategy for some time, and it is unclear what might motivate it to switch to deception. Still, we cannot rule out this possibility. There may be other loopholes we haven’t yet thought of.

So far, we have only described a very simple goal. To prevent the problems mentioned, one could add additional restrictions. For example, the AGI’s goal could be restated as “maximize the total expected trust in it while always being honest”. Given a practical definition of “honest”, this would force the AGI into an honest strategy. Other restrictions are possible as well. However, the purpose of this post is to show that, in our view, “trust-maximizing by being honest” could be an optimal strategy for an AGI even without such restrictions.

There is one additional caveat: While an honest trust-maximizer would probably be beneficial to humanity, it would have some disadvantages against an AGI of the same power that uses deception or other means to manipulate humans. As we have seen, deception can lead to a faster, if short-lived, increase in trust. If an honest and a dishonest AGI of roughly the same power were to compete for the same resources, the dishonest AGI might win the race and use the additional resources to thwart the honest competitor. 

For this reason, the honest trust-maximizer might try to prevent the development of potentially deceptive AGIs, or at least maintain a significant advantage over them in terms of intelligence and power. Ultimately, this might lead to a [“benevolent dictator”](https://futureoflife.org/2017/08/28/ai-aftermath-scenarios/) scenario where the trust-maximizer effectively rules the world, but most people wouldn’t mind it.
