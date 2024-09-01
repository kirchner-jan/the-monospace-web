# Drug addicts and deceptively aligned agents - a comparative analysis

**Nov 05, 2021**

**Likes:** 2

Edit: The nice folks at the [Nonlinear Library](https://forum.effectivealtruism.org/posts/JTZTBienqWEAjGDRv/listen-to-more-ea-content-with-the-nonlinear-library) turned this post into an audio version [here](https://podcasts.google.com/feed/aHR0cHM6Ly9zcGt0LmlvL2YvODY5Mi83ODg4L3JlYWRfODYxN2QzYWVlNTNmM2FiODQ0YTMwOWQzNzg5NWMxNDM/episode/cEZYRUc5QzVtMlg1aDJ5aXE?sa=X&ved=0CAgQuIEEahgKEwi4yLOmrfj0AhUAAAAAHQAAAAAQngM).

## Addicts and AIs

 _A young man, let’s call him Dave[1](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-1-43628201), starts consuming different kinds of illegal drugs (mostly heroin) as early as age 14, as a reaction to the divorce of his parents. Even though he is from an otherwise stable family, he becomes homeless after fights about his drug consumption. Repeatedly, Dave returns to his family's home, crying and asking to sleep on the couch for a few nights. Repeatedly, the family takes him in, believing that this time he finally has a change of heart. And time and time again, Dave will disappear after a few days, taking with him all money or any other valuable thing that is not nailed down._

As a doctor on the psych ward, I (Nadia) have encountered situations like this over and over. The first few times as a health professional, [you might get fooled](https://en.wikipedia.org/wiki/Scrubs_\(season_3\)#:~:text=63,of%20Un-Truth%22) by a patient with addiction. But soon, you learn to be skeptical and stop paying attention to what they _say_ they did and how they appeal to your empathy. Instead, you start to pay close attention to what you can _observe_ people doing (and what others _tell_ you they did). Luckily, most doctors are smarter than addicts, especially after the addict’s cognitive ability [starts to decline](https://www.sciencedirect.com/science/article/abs/pii/S0376871607000816?via%3Dihub) due to substance abuse. Still, treating addicts requires constant vigilance and attention to details and potential contradictions. This is a sad state of affairs, but the simple fact that “[addicts](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4250346/) [lie](https://scholar.googleusercontent.com/scholar?q=cache:d_J0tVYoi-YJ:scholar.google.com/+alcoholics+lie&hl=en&as_sdt=0,5#:~:text=All%20alcoholics%20lie.%20It%20is%20intrinsic.)”[2](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-2-43628201) has become one of the central axioms of psychiatric practice.

Intriguingly, a very similar situation has emerged in AI Safety[3](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-3-43628201), albeit from a very different direction. One of the central intuition pumps of AI Safety is that of the [single-minded, utility-maximizing artificial agent](https://www.alignmentforum.org/tag/paperclip-maximizer), whose actions end up being harmful due to a misalignment of values. While (luckily!) no pure version of this agent exists yet, theoretical studies allow us to make inferences about properties that such an agent is likely to have. This includes f.e. the properties incentivized by [instrumental convergence](https://en.wikipedia.org/wiki/Instrumental_convergence) or the property of [nontrivial inner alignment](https://www.alignmentforum.org/posts/zthDPAjh9w6Ytbeks/deceptive-alignment). However, theory is theory, and some have questioned the [likelihood of instrumental convergence](https://www.alignmentforum.org/posts/WxW6Gc6f2z3mzmqKs/debate-on-instrumental-convergence-between-lecun-russell) actually occurring. Examples of instrumental convergence remain “[hypothetical](https://en.wikipedia.org/wiki/Instrumental_convergence#Hypothetical_examples_of_convergence)” and we only know of one [reported example of inner alignment failure](https://www.youtube.com/watch?v=zkbPdEHEyEI&ab_channel=RobertMiles) in a computer model. We believe that this is problematic, as reality is complex and (theoretically) simple concepts can end up being very complicated/different in practice.

In this post, we want to outline how an addict’s astounding ability to [optimize for getting more drugs](https://slatestarcodex.com/2014/05/25/apologia-pro-vita-sua/) has striking similarities to the [relentless optimization capabilities](https://deepmind.com/blog/article/Specification-gaming-the-flip-side-of-AI-ingenuity) of modern AI systems. We argue that addicts exhibit a weak form of _instrumental convergence_ and that _deceptiveness_ naturally emerges in a setting where the optimization process requires cooperation from an uncooperative interlocutor. The phenomenon of drug addiction might thus serve as a useful “real world” example of many of the theoretical predictions of the AI Safety community. Additionally, we examine common approaches from addiction therapy and evaluate whether they can provide insight into the problem of AI safety. Finally, we highlight some limitations of this approach.

* * *

If you are running low on time, here is a TL;DR of our analysis:

Drug addicts serve as a real-life example of a(n approximate) single-minded utility optimizer

They show properties consistent with instrumental convergence, fulfilling 3 out of 5 features [highlighted by Nick Bostrom](https://www.nickbostrom.com/superintelligentwill.pdf) (resource acquisition, technological perfection, and goal-content integrity)

Addicts use deception extensively as a tool for achieving their instrumental values. We interpret this as an extreme form of an [epistemic strategy](https://suspendedreason.com/2021/05/12/epistemic-strategies-pt-1/)

We find potential analogon of addiction therapy for AI Safety:

  * Group therapy might be applicable to multipolar scenarios for AI development

  * Anti-Craving and substitution medication might translate to interpretability work, esp. [model editing](https://distill.pub/2020/understanding-rl-vision/#model-editing)

  * [Preventive measures](https://www.bzga.de/home/key-topics/drug-prevention/) might translate to [agent foundations](https://intelligence.org/files/TechnicalAgenda.pdf) research




* * *

## Ontogenesis and characteristics of an addict

[Koob and Volkov](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6135092/) define addiction as:

>  _a chronically relapsing disorder, characterised by compulsion to seek and take the drug, loss of control in limiting intake, and emergence of a negative emotional state (eg, dysphoria, anxiety, irritability) when access to the drug is prevented._

While much of early research has focused solely on the role of dopamine and the reward system in addiction, it is now becoming clear that the transition from occasional use to chronic use involves substantive changes at the molecular, cellular, and neurocircuitry levels. Here is [Adinoff](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1920543/):

>  _The persistent release of dopamine during chronic drug use progressively recruits limbic brain regions and the prefrontal cortex, embedding drug cues into the amygdala [...] and involving the amygdala, anterior cingulate, orbitofrontal cortex, and dorsolateral prefrontal cortex in the obsessive craving for drugs._

These structural changes carve out grooves in the addict's brain that can lead to a strong and immediate relapse of recovering addicts following a single dose of the drug, a contextual cue, a craving sensation, stress, or distress. Another (particularly destructive) effect of drug abuse is the hijacking of the reward system. [Volkov et al](https://www.sciencedirect.com/science/article/abs/pii/S1074742702940992):

>  _These findings suggest an overall reduction in the sensitivity of the reward circuits in the drug-addicted individual to natural reinforcers and possibly to drugs that are not the drug of addiction, thereby providing a putative mechanism underlying the [sadness and discomfort] experienced during withdrawal._

As a consequence, addicts can become extremely single-minded in their desires: they lose interest in [food](https://pubmed.ncbi.nlm.nih.gov/21933297/), [sex](https://www.sciencedirect.com/science/article/abs/pii/S0306460302002666), and their [previous social circle](https://www.ncbi.nlm.nih.gov/books/NBK248421/box/ch6.box5/?report=objectonly), creating a vicious cycle of progressive bodily and mental decline. In the language of moral philosophy, drug use evolves from having [instrumental value](https://www.sciencedirect.com/science/article/pii/S0166432820303715) (f.e. to disinhibit, to improve performance, or to alleviate pain) to having intrinsic value (drug use for reducing the desire for drugs).

Interestingly, the further the addiction progresses, [the more the addict resembles a rational expected utility maximizer](https://www.jstor.org/stable/1830469)[4](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-4-43628201). Consistently, the [escalation of drug use](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3866817/) is a hallmark of addiction and addicts rapidly deplete [social and financial capital](https://www.tandfonline.com/doi/full/10.1080/02673843.2021.1908376) to enable continued drug use. They resemble thus the archetypical[5](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-5-43628201) [paperclip maximizer](https://www.huffpost.com/entry/artificial-intelligence-oxford_n_5689858#:~:text=Suppose%20we%20have%20an%20AI%20whose%20only%20goal%20is%20to%20make%20as%20many%20paper%20clips%20as%20possible.):

>  _a hypothetical artificial intelligence whose utility function values something that humans would consider almost worthless_.

* * *

## Instrumental convergence in addicts and AIs

This resemblance is particularly interesting, as addicts share additional features with the hypothetical paperclip maximizers. They exhibit (a limited form of) [instrumental convergence](https://en.wikipedia.org/wiki/Instrumental_convergence). Nick Bostrom formulates the [instrumental convergence thesis](https://www.nickbostrom.com/superintelligentwill.pdf) as:

>  _Several instrumental values can be identified which are convergent in the sense that their attainment would increase the chances of the agent’s goal being realized for a wide range of final goals and a wide range of situations, implying that these instrumental values are likely to be pursued by many intelligent agents._

Among the instrumental values proposed by [Bostrom](https://www.nickbostrom.com/superintelligentwill.pdf) are:

  *  **Resource acquisition** : Having more resources allows the agent to more efficiently maximize its final goals. In the case of addicts, [access to money for drugs is a common motivation for property crimes](https://journals.sagepub.com/doi/abs/10.1177/0011128715591696?journalCode=cadc) and other activities including [drug sales, and prostitution as well as legitimate income and the avoidance of expenditures](https://journals.sagepub.com/doi/abs/10.1375/acri.35.2.187?journalCode=anja).

  *  **Technological perfection** : Seeking more efficient ways of transforming some given set of inputs into valued outputs. This can be seen for heroin addicts, who often [transition from snorting or smoking heroin to injecting it intravenously](https://www.uofmhealth.org/health-library/uq2454#:~:text=When%20a%20person%20injects%20heroin%20directly%20into%20a%20vein%20or%20smokes%20heroin%2C%20the%20rush%20occurs%20within%20seconds%2C%20whereas%20it%20takes%20at%20least%2010%20minutes%20when%20the%20drug%20is%20sniffed.) to [increase the intensity of the high](https://americanaddictioncenters.org/heroin-treatment/snorting#:~:text=eventually%20turn%20to%20smoking%20or%20injection).

  *  **Goal-content integrity**[6](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-6-43628201): Preventing alterations of the final goals. Even though this is (probably) not executed intentionally by the individual addict, the formation of and the involvement in [drug culture](https://www.ncbi.nlm.nih.gov/books/NBK248421/) constantly reinforces the addict’s relationship with the drug[7](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-7-43628201). As drug cultures explicitly [distance themselves from the rest of society](https://www.ncbi.nlm.nih.gov/books/NBK248421/box/ch6.box5/?report=objectonly), they make it more difficult for the addict to stop using. In fact, a central step in drug recovery programs is to replace the drug culture with a [culture of recovery](https://www.ncbi.nlm.nih.gov/books/NBK248421/box/ch6.box12/?report=objectonly) such as alcoholics anonymous. 




Interestingly, not all instrumental values proposed by Bostrom are pursued by addicts:

  *  **Self-preservation** : Trying to be around in the future, to help the agent achieve its present future-oriented goal. As mentioned above, mental and physical health tends to deteriorate rapidly once substance abuse escalates. In addition, [suicide attempts are very common among ](https://onlinelibrary.wiley.com/doi/abs/10.1046/j.1360-0443.1999.9422095.x)addicts. This accentuates [myopic tendencies that are common among drug users](https://www.jstor.org/stable/2565738).

  *  **Cognitive enhancement** : Improving rationality and intelligence. While there is some work on how addicts act [rational given their circumstances](https://www.google.com/url?q=https://www.jstor.org/stable/1830469&sa=D&source=docs&ust=1635625398863000&usg=AOvVaw3QOu_XciX94tnKwYecXlUB), they do not actively search out cognitive enhancement[8](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-8-43628201). This is presumably because cognitive enhancement is not easily achievable compared to other instrumental values.




* * *

## Deceptiveness in addicts and AIs

As we have alluded to in the introduction, beyond being somewhat [myopic](https://www.alignmentforum.org/posts/Y76durQHrfqwgwM5o/lcdt-a-myopic-decision-theory#The_looming_shadow_of_deception), addicts are often also [deceptive](https://www.alignmentforum.org/s/r9tYkB2a8Fp4DN8yB/p/zthDPAjh9w6Ytbeks). Beyond [dishonesty towards a therapist about drug use](https://onlinelibrary.wiley.com/doi/abs/10.1002/jclp.22894), [feigning physical illness to receive medication](https://www.sciencedirect.com/science/article/abs/pii/0740547294900825), and [extensive self-deception](https://pubmed.ncbi.nlm.nih.gov/26820418/), addicts also tend to [manipulate emotions](https://journals.sagepub.com/doi/10.1177/0022042619853299):

>  _Lying and dishonesty are, indeed, quite frequent in people with addiction (Ferrari et al., 2008; Sher & Epler, 2004), who often tend to manipulate others close to them to continue their substance use because they are jeopardized by their addiction and intense craving. Some common manipulation tactics refer to making empty promises, playing the victim, making excuses for irresponsibility, making others feel uncomfortable or guilty with the aim of satisfying unreasonable requests, threatening to self-harm, and so on._

Now, _why_ do addicts deceive? Here we are running into issues with our analogy, as there appears to be [no fully satisfying definition of AI deception yet](https://www.alignmentforum.org/posts/Y76durQHrfqwgwM5o/lcdt-a-myopic-decision-theory). Addicts are clearly not myopic enough to rule out deceptive behavior entirely[9](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-9-43628201). While it is somewhat compelling to regard drug culture as a mechanism for preserving an addict’s goal over time, addicts don’t appear to be under the immediate threat of modification that would justify [deceptive alignment in the technical sense](https://www.alignmentforum.org/s/r9tYkB2a8Fp4DN8yB/p/zthDPAjh9w6Ytbeks)[10](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-10-43628201). The motivation for deceptive behavior rather appears to be an [epistemic strategy](https://suspendedreason.com/2021/05/12/epistemic-strategies-pt-1/), executed to manipulate beliefs and decisions. Suspended Reason [writes](https://suspendedreason.com/2021/05/12/epistemic-strategies-pt-1/):

>  _[L]iving organisms [are] not just physically but epistemically manipulable: their ability to anticipate and optimize, to short-term and conditionally adapt oneself into greater fitness with the environment—is their greatest strength and greatest vulnerability. Affect their priors, or their desires and preferences, and they may make a different decision. Our expression games include but are far from limited to speech—the superset here is the manipulation of appearances and the manipulation of representations, be it by linguistic account or [symbolic] implication._

This is intuitively plausible. The addict’s goals (drug use) are incompatible with some of the goals (to stop drug use) of some of their peers (family, friends, doctors). The addict requires cooperation from their peers to achieve instrumental goals (shelter, money, prescription). The peers are unwilling to cooperate with the addict as long as they believe the addict’s goals are misaligned with their own. Thus, the addict is incentivized to behave in a way that changes the beliefs of their peers and to pretend to be aligned. The result is that the addict uses their model of the peers to act and speak in a way that makes them believe that their goals are aligned until they achieve their instrumental goal and return to the behavior appropriate to achieving their final goal.

At this point, it is worth pointing out the obvious: these epistemic strategies are not unique to addicts. Carefully managing other people’s believes is [hypothesized to underlie the disproportionately large cortex of humans](https://www.pnas.org/content/103/45/16823), is [present in other animals](https://www.jstor.org/stable/4534456)[11](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-11-43628201), and might indeed [permeate pretty much all of human culture](https://www.overcomingbias.com/2021/06/our-big-wealth-status-mistake.html#more-32881). The single-mindedness of addicts in terms of final values just makes them a particularly clear case in which to study epistemic manipulation. Simultaneously, the pervasiveness of deception (intentional and unintentional) might also further compel us to assume deception as the default, rather than as a rare property of pathological agents.

* * *

## Epistemic transfer from drug addiction therapy to AI safety

Is there something we can learn from drug addiction therapy that translates into AI safety?

Right out of the gate: Addictions of all kinds are among the hardest mental disorders to treat, with the [majority of patients relapsing](https://doi.org/10.1176/APPI.PS.56.10.1282) within ten years after successful treatment. Nonetheless, success stories exist. From working with patients on addiction recovery, we learn that self-motivation is [absolutely](https://www.sciencedirect.com/science/article/abs/pii/S0740547203001259) [essential](https://psycnet.apa.org/buy/2013-40800-001). Nobody will stay sober if they don’t want to stay sober (at least most of the time). Other predictors are [religion/spirituality, family, and their job/career](https://www.sciencedirect.com/science/article/abs/pii/S0740547203001259), i.e. their social circle. In the language of AI safety, this is consistent with removing goal-content integrity as an instrumental goal. The addict must _want_ to change and the composition of the social circle (drug culture vs. recovery culture) is a strong predictor of how successfully the goal-content can be changed.

Self-motivation alone, however, isn’t enough in most cases. There are several additional approaches with wildly varying degrees of success:

 **Anti-Craving medication** : [Acamprosate](https://medlineplus.gov/druginfo/meds/a604028.html) and [Naltrexone](https://www.webmd.com/drugs/2/drug-7399/naltrexone-oral/details) are among the few medications that are approved for addiction treatment. Naltrexone is an opioid antagonist, blocking receptors normally causing euphoria from opioid consumption as well as endogenous opioids that are released when doing fun stuff. Acamprosate is less well understood, but it seems to lower cravings.

 _AI Safety analogon_ : Similar to the difficulty of finding suitable medication for modifying the motivational system in humans, [identifying the mechanism for the internalized reward model in AI is not trivial](https://distill.pub/2020/understanding-rl-vision/). Assuming that the reward model can be interpreted, [model editing](https://distill.pub/2020/understanding-rl-vision/#model-editing) appears as a feasible strategy for correcting misalignment[12](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-12-43628201). Similar to an addict, this strategy can only be executed with the “cooperation” of the AI, i.e. the lack of goal-content integrity, or in an inpatient setting, where the actions of the AI are severely restricted.

 **Substitution medication** : In some cases, the disorder is too severe to aim for abstinence. Reducing harm is key; not just for the individual patient, but for society as a whole, reducing crimes related to obtaining illegal substances (violent crime, sex work). Famous examples include [methadone](https://www.webmd.com/mental-health/addiction/what-is-methadone) and [buprenorphine](https://go.drugbank.com/drugs/DB00921), which belong to the opioid family, but cause less euphoria than the real stuff and are taken by mouth. Methadone and buprenorphine connect to the receptors more tightly than diamorphine (Heroin) or oxycodone, so that any consumption after taking the substitute won’t have the desired effect.

 _AI Safety analogon_ : It is interesting to consider whether we can (once we have identified a potentially harmful goal of an AI) offer non- (or less-) harmful substitutes[13](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-13-43628201). A paperclip maximizer might not be satisfied with anything else than paperclips, but the reality is likely to be more nuanced, especially in [multipolar scenarios](https://aiimpacts.org/event-multipolar-ai-workshop-with-robin-hanson/).

 **Motivational interviewing** : [This](https://en.wikipedia.org/wiki/Motivational_interviewing) can be the start of a longer treatment for substance use disorders. Cards with values like love, honesty, or success are handed out to the patient and they are asked to pick those that matter most to them. The patient is asked to explain why those values are close to their heart, and how they incorporate them into their lives. At some point or another, there will be a clash between “continue substance use” and “basically anything people value”, ideally helping with behavior change and resolving ambivalence in favor of intrinsic motivation.

 _AI Safety analogon_ : In light of how we argued earlier how drugs hijack the motivational system and make addicts single-minded, motivational interviewing is intended to restore the influence of other final values. However, these other values (love, honesty, or success) are qualitatively different from drug use, in particular, they are a lot less immediately _actionable_. Including those values into the motivational system of AI appears desirable[14](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-14-43628201), but essentially equivalent to the alignment problem.

 **Group therapy** : All kinds of groups exist, but most clinics will, for example, have a group centered around relapse prevention. The most famous example of non-medical, but nonetheless effective group therapy, is Alcoholics Anonymous. There seems to be something particularly effective about having role models and being held accountable by peers, who don’t judge you as harshly as your relatives might do.

 _AI Safety analogon_ : The mental image of an AI Anonymous group therapy meetup has undeniable charm. More realistically, we could imagine collaborative [anomaly detection](https://www.alignmentforum.org/posts/AwMb7C72etphiRvah/unsolved-ml-safety-problems#Anomaly_Detection) in a [multipolar scenario](https://aiimpacts.org/event-multipolar-ai-workshop-with-robin-hanson/), where multiple AIs constantly monitor each other for evidence of misalignment. This of course requires that either the majority of AIs (or [the group as a whole](https://www.alignmentforum.org/posts/LpM3EAakwYdS6aRKf/what-multipolar-failure-looks-like-and-robust-agent-agnostic)) are (/is) aligned most of the time.

 **Preventive measures** : Famously, there is no glory in prevention; the people responsible likely won’t get the reward they deserve. In the case of substance abuse (with its dismal prognoses and high costs for society at large), prevention plays a particularly important role. Limiting access to substances[15](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-15-43628201) (alcohol, first and foremost) and advertising, especially for young people, appears to be the most promising ways for fewer victims of addiction.

 _AI Safety analogon_ : This translates into the obvious: the best way to fix misalignment is to never have it occur in the first place. [In the strongest form](https://intelligence.org/files/TechnicalAgenda.pdf), this would involve constructing a system with certain mathematical guarantees of safety or, if that is not possible, to at least come very close to these guarantees.

* * *

## Limitations and Conclusions

While there are some striking similarities between addicts and AIs, there are some very important differences that limit comparability:

  1. As we have pointed out, the cognitive ability of addicts [tends to decrease with progressing addiction](https://www.sciencedirect.com/science/article/abs/pii/S0376871607000816?via%3Dihub). This provides a natural negative feedback loop that puts an upper bound on the amount of harm an addict can cause. Without this negative feedback loop, humanity [would look very different](https://unsongbook.com/chapter-33-the-doors-of-perception/)[16](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-16-43628201). This mechanism is, by default, not present for AI[17](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-17-43628201).

  2. Addicts are humans. To the extent that they are a useful model for thinking about AIs, they are also potentially dangerously misleading. A lot of our preconceived notions and cultural norms still apply to addicts, making them easy for us to model mentally. This does not translate to AI, who might (without any deceptive intent) [misunderstand everything we say in the most terrible way possible](https://www.belfercenter.org/publication/coming-ai-hackers#:~:text=If%20I%20asked%20you%20to%20get%20me%20some%20coffee). Thus, we propose this analogy not as an intuition pump that can extrapolate outside of the bounds of established validity, but rather as a tool for inference within these bounds[18](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-18-43628201). 




In conclusion, we have demonstrated a number of parallels between addicts and misaligned AIs: both can be interpreted as utility maximizers, both exhibit a form of instrumental convergence and both have a tendency to be deceptive. We translate insights from addiction treatment into the language of AI Safety and arrive at a few interesting ideas that appear to us to be worth exploring in future work. Beyond this, we have demonstrated how epistemic transfer from other fields into AI Safety can look like and are excited about the possibility of investigating this further.

[1](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-anchor-1-43628201)

Doctor-patient confidentiality requires us to change the details and to mix several stories.

[2](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-anchor-2-43628201)

There are, of course, exceptions to the rule, and figuring out those exceptions is an art in itself. Importantly, the propensity of addicts to lie [appears to be limited](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2821802/) to situations where they can actively gain something from the lie.

[3](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-anchor-3-43628201)

We (Nadia & Jan) sometimes struggle to communicate to friends and family why artificial intelligence (AI) safety is a difficult problem. There is the pervasive (and intuitive) belief that “ _If_ we can create truly powerful AI, it will just figure out human morality [by default](https://www.alignmentforum.org/posts/Nwgdq6kHke5LY692J/alignment-by-default). And even _if_ malicious intent should creep into the system somehow, we’ll surely notice and “[just pull the plug](https://medium.com/swlh/can-we-just-turn-off-dangerous-ai-6cf3ca6d83ba)”. As an extreme solution, we might just figuratively [“lock” the AI in a box](https://xkcd.com/1450/). Then we can audit the AI extensively (through interacting with it via text) before we decide if we let it out into the world or not.” We believe that the example of the deceptive drug addict in this post could serve as one (certainly not the only) useful example for illustrating the difficulty of safely aligning AI.

[4](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-anchor-4-43628201)

Gaining utility is equated with drug consumption here. There are some interesting [twists and turns](https://sites.duke.edu/econ206_01_s2011/files/2015/04/14_TeamGrossman_RationalAddiction.pdf) here about whether it really makes sense to model an addict as a _rational_ agent. (This requires f.e. the assumption that an addict’s “awareness of the future consequences is not impaired.”) For the purpose of this post, it is only important that the addict attempts to maximize utility (drugs), not that they do so in an optimal/rational way. Also [this](https://imgflip.com/i/5sgmhx).

[5](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-anchor-5-43628201)

(and occasionally scoffed at)

[6](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-anchor-6-43628201)

Okay, yes, this one is a stretch. But hear us out.

[7](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-anchor-7-43628201)

These cultures are highly complex, vary depending on the [substance used, the geographic location, the socioeconomic status of the users, change over time](https://www.ncbi.nlm.nih.gov/books/NBK248421/box/ch6.box2/?report=objectonly), and commonly [evolve hierarchies](https://www.tandfonline.com/doi/abs/10.1080/01639620701876486).

[8](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-anchor-8-43628201)

[Like, f.e., an M.S. in organic chemistry](https://breakingbad.fandom.com/wiki/Gale_Boetticher). And while there is the myth of streetsmart psychopathic addicts, this is not [actually born out in the data](https://psycnet.apa.org/record/2010-07749-002).

[9](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-anchor-9-43628201)

In the [linked article](https://www.alignmentforum.org/posts/Y76durQHrfqwgwM5o/lcdt-a-myopic-decision-theory), myopia (short-sightedness) is proposed as an “overapproximation” of non-deceptiveness. In short, an agent that is myopic in a strictly technical sense, _can’t_ be deceptive, since they can’t plan ahead far enough to come up with something really bad. The reverse obviously doesn’t hold: You can clearly imagine someone non-myopic, but also non-deceptive.

[10](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-anchor-10-43628201)

The [linked article](https://www.alignmentforum.org/s/r9tYkB2a8Fp4DN8yB/p/zthDPAjh9w6Ytbeks) provides a list of requirements for deceptive alignment to arise and one of the requirements is “ _The mesa-optimizer must expect the threat of modification to eventually go away, either due to training ending or because of actions taken by the mesa-optimizer._ ” We don’t see a clean way for mapping this onto the addiction model.

[11](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-anchor-11-43628201)

[Seagulls do it](https://www.washingtonpost.com/archive/opinions/1987/09/13/they-lie-cheat-and-maybe-think/032e22d2-5412-4e5d-b328-2ce55a3dc951/), so we must assume that [albatrosses do, too](https://universalprior.substack.com/p/soldiers-scouts-and-albatrosses).

[12](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-anchor-12-43628201)

Certainly a less extreme intervention than “[just pulling the plug](https://medium.com/swlh/can-we-just-turn-off-dangerous-ai-6cf3ca6d83ba)”.

[13](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-anchor-13-43628201)

A reviewer (Leon Lang) made the following interesting remark: “ _from the point of view of the AI, humans that try to make the AI satisfied while actually not producing "the real thing" (e.g., paperclips) almost seem like... misaligned humans?_ ”

[14](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-anchor-14-43628201)

Although we can imagine that an excess of either love, honesty, or success (especially when optimized with practically unlimited cognitive resources) could be just as destructive as drug use.

[15](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-anchor-15-43628201)

While keeping the mistakes of prohibition in mind.

[16](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-anchor-16-43628201)

The link leads to a (long) fiction novel by Scott Alexander where Mexico is controlled by people constantly high on peyote, who become extremely organized and effective as a result. They are scary & dangerous.

[17](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-anchor-17-43628201)

Although it is an interesting idea to scale access to compute inversely to how high the value of the accumulated reward is.

[18](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned#footnote-anchor-18-43628201)

What do we know works in addicts, but hasn’t been tried in AI? What works in AI, but hasn’t been tried in addicts?
