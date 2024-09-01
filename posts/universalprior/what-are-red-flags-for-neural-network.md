# What are red flags for Neural Network suffering?

## TL;DR: What would make us worried about NN suffering? Reviewing neuroscience literature + high-level considerations produce factors that  (neither necessary nor sufficient) would shift our beliefs.

**Nov 08, 2021**

**Likes:** 1

Epistemic status: High uncertainty; This is exploratory work; Our goal is to provide possible research directions rather than offering solutions.

This is shared work. Most of the part on neural correlates is by [Jan](https://universalprior.substack.com/). Most of the parts on behavior and high-level considerations are by [Marius](https://www.mariushobbhahn.com/aboutme/). You can also find the post [here](https://www.lesswrong.com/posts/Bpw2HXjMa3GaouDnC/what-are-red-flags-for-neural-network-suffering) on the LessWrong forum.

 **Background**

I (Marius) was listening to the [80k podcast with Chris Olah](https://80000hours.org/podcast/episodes/chris-olah-interpretability-research/) on his work on interpretability. When he talked about neural circuits, he said they found many circuits similar to structures in the human brain (some are also quite different). The question that I can’t unthink since then is “What evidence would we need to see in Neural Networks that would convince us of suffering in a morally relevant way?”. So I teamed up with Jan to explore the question.

To clarify, we don’t care about whether they suffer in a similar way that humans do or to the same extent. The question that interests us is _“Do neural networks suffer?”_ and, more importantly, _“How would we tell?”_.

Broadly, we think there are three different approaches to this problem: a) Neural correlates, b) Behavioural data, and c) high-level considerations.

In this post, we want to find out if there are any avenues that give us reasonable answers or if you just run into a wall, like with most other questions about suffering, patienthood, etc.

It’s not super clear what we are looking for exactly. In general, we are looking for all kinds of evidence that can potentially update our probability of NN suffering.

 **Summary of the results:**

  1.  **Neural Correlates:** Neuroscience helps to de-confuse some terminology, but has not (yet) unambiguously identified a unique neural correlate for suffering. Pain is much better characterized as a “homeostatic behavioral drive” with associated cognitive routines. Since pain usually leads to suffering, finding the homeostatic behavioral drive might also be indicative of suffering in NNs. Finally, the [PANAS measure](https://www.brandeis.edu/roybal/docs/PANAS-GEN_website_PDF.pdf) from psychology might provide comparability to humans.

  2.  **Behavior:** Looking at the response of NNs to different stimuli might yield some evidence about their ability to suffer. In language models, it is unclear how to test for the existence of suffering. But testing if GPT-3, for example, has a consistent concept of suffering or observing its answers to the [PANAS](https://www.brandeis.edu/roybal/docs/PANAS-GEN_website_PDF.pdf) questions might be a start. For RL agents we can create tests comparable to animal studies. For example, one could look at the reaction to negative stimuli, lesion studies, theory of mind, or self-awareness as potential evidence for the ability to suffer.

  3.  **High-level considerations:** We think that this is the most promising avenue. Firstly, the ability to suffer probably develops because it gives an evolutionary edge. Thus, it is plausible that artificial agents such as reinforcement learners would develop it given the right capabilities and conditions. Secondly, current NN architectures are much smaller than human brains or other biological neural networks if you compare the number of parameters with the number of neurons or synapses. Especially the architectures that would plausibly develop the ability to suffer, e.g., reinforcement learners, are still much smaller than tiny animals.




Combining all of the above, we think it is more plausible that current NN architectures don’t suffer than that they do. However, we are pretty uncertain since we mix the fuzzy concept of suffering with NNs, which are also not well understood.

##  **Neural correlates**

First, [to avoid specific philosophical tripwires](https://www.jstor.org/stable/187355)[1](https://universalprior.substack.com/p/what-are-red-flags-for-neural-network#footnote-1-43720749), we [engineer our concepts](https://www.lesswrong.com/posts/9iA87EfNKnREgdTJN/conceptual-engineering-the-revolution-in-philosophy-you-ve) using insights from neuroscience. The hope is that we might be able to derive necessary or sufficient conditions (or at least bundles of features that strongly correlate with suffering) that generalize outside the realm of biology. Thus, a natural approach to investigating how suffering comes about is to look at how it comes about in the (human) brain. The neuroscience of pain/suffering is a mature scientific field with [seminal work going back to the 1800s](https://sci-hub.se/https://www.annualreviews.org/doi/full/10.1146/annurev.neuro.26.041002.131022), [multiple](https://www.dovepress.com/journal-of-pain-research-journal) [dedicated](https://www.jpain.org/) [journals](https://www.journals.elsevier.com/neurobiology-of-pain)[2](https://universalprior.substack.com/p/what-are-red-flags-for-neural-network#footnote-2-43720749), and very few straightforward answers:

>  _Pain is an enigma. It differs from the classical senses (vision, hearing, touch, taste, and smell) because it is both a discriminative sensation and a graded motivation (or behavioral drive). [...] It can attain intolerable intensity, but it can disappear in the heat of battle. It is a universal human experience that is commonly generalized to psychic suffering of any sort. -[Craig](https://sci-hub.se/https://www.annualreviews.org/doi/full/10.1146/annurev.neuro.26.041002.131022)_

While far from being settled science, insights from neuroscience provide a backdrop on which we can investigate pain/suffering more generally. We find it helpful to distinguish the following concepts:

 **Nociception**[3](https://universalprior.substack.com/p/what-are-red-flags-for-neural-network#footnote-3-43720749) **.**

>  _Nociception is the neural process of encoding and processing noxious (​​i.e. harmful, poisonous, or very unpleasant) stimuli. Nociception refers to a signal arriving at the central nervous system as a result of the stimulation of specialised sensory receptors in the peripheral nervous system called nociceptors. -[Physiopedia](https://www.physio-pedia.com/Nociception)_

While we know a lot about nociception[4](https://universalprior.substack.com/p/what-are-red-flags-for-neural-network#footnote-4-43720749), it is not the most useful concept for understanding pain. In particular, there are numerous examples of pain without nociception ([phantom limb pain](https://en.wikipedia.org/wiki/Phantom_limb) and [psychogenic pain](https://my.clevelandclinic.org/health/diseases/12056-pain-psychogenic-pain)) and nociception without pain ([spicy food](https://www.scientificamerican.com/article/why-is-it-that-eating-spi/#:~:text=The%20answer%20hinges%20on%20the%20fact%20that%20spicy%20foods%20excite%20the%20receptors%20in%20the%20skin%20that%20normally%20respond%20to%20heat.%20Those%20receptors%20are%20pain%20fibers%2C%20technically%20known%20as%20polymodal%20nociceptors.), [Congenital insensitivity to pain](https://en.wikipedia.org/wiki/Congenital_insensitivity_to_pain)).

 **Pain.**

Pain is distinct from nociception. One [prominent theory](https://www.cell.com/trends/neurosciences/fulltext/S0166-2236\(03\)00123-1?_returnURL=https%3A%2F%2Flinkinghub.elsevier.com%2Fretrieve%2Fpii%2FS0166223603001231%3Fshowall%3Dtrue) on pain is that[5](https://universalprior.substack.com/p/what-are-red-flags-for-neural-network#footnote-5-43720749):

>  _the human feeling of pain is both a distinct sensation and a motivation – that is, a specific emotion that reflects homeostatic behavioral drive, similar to temperature, itch, hunger and thirst._

The term _homeostatic_ does a lot of heavy lifting here. Implicitly assumed is that there are certain “reference levels” that the body is [trying to maintain](https://slatestarcodex.com/2017/03/06/book-review-behavior-the-control-of-perception/), and pain is a set of behavioral and cognitive routines that execute when your body moves too far away from the reference level[6](https://universalprior.substack.com/p/what-are-red-flags-for-neural-network#footnote-6-43720749). While this definition conveniently maps onto concepts from [machine learning](https://arxiv.org/abs/2006.05604), pain is (unfortunately) not sufficient for suffering (see f.e. [sadomasochism](https://en.wikipedia.org/wiki/Sadomasochism)), and there is substantial debate on whether pain is necessary for suffering (see [here](https://jme.bmj.com/content/47/3/175)). Thus, a neural network could exhibit all the neurological signs of pain but still [experience it as pleasurable](https://en.wikipedia.org/wiki/Mad_pain_and_Martian_pain)[7](https://universalprior.substack.com/p/what-are-red-flags-for-neural-network#footnote-7-43720749). We need an additional component beyond pain, which we might call...

 **Suffering**

>  _Perhaps the foremost theoretical “blind spot” of current philosophy of mind is conscious suffering. Thousands of pages have been written about colour “qualia” and zombies, but almost no theoretical work is devoted to ubiquitous phenomenal states like boredom, the subclinical depression folk-psychologically known as “everyday sadness“ or the suffering caused by physical pain. -[Metzinger](https://www.philosophie.fb05.uni-mainz.de/files/2013/04/Metzinger_suffering_penultimate.pdf)_

Well, that’s awkward. If even the philosophers haven’t worked on this, there is little hope to find solid neuroscientific insight on the topic. Tomas Metzinger (the author of the preceding quote) [lists several necessary conditions](https://www.philosophie.fb05.uni-mainz.de/files/2013/04/Metzinger_suffering_penultimate.pdf) for suffering, but already the first condition (“The C-condition: ​​“Suffering” is a phenomenological concept. Only beings with conscious experience can suffer.”) takes us into [neuroscientifically fraught territory](https://universalprior.substack.com/p/frankfurt-declaration-on-the-cambridge). We would prefer to have a handle on suffering that presupposes less.

A more promising approach might come from psychology: “strong negative [valence](https://en.wikipedia.org/wiki/Valence_\(psychology\))” appears to circumscribe exactly those cognitive events we might want to call “suffering”. While the [neuroscientific study of valence](https://pubmed.ncbi.nlm.nih.gov/30359607/) is still somewhat immature[8](https://universalprior.substack.com/p/what-are-red-flags-for-neural-network#footnote-8-43720749), at least there exist extensively [cross-validated tests](https://www.brandeis.edu/roybal/docs/PANAS-GEN_website_PDF.pdf) for surveying subjective valence. The PANAS scale is a self-report measure of affect with an internal consistency and test-retest reliability bigger than .8 for negative affect in human subjects. There is no shortage of [criticism](https://link.springer.com/referenceworkentry/10.1007%2F978-3-319-24612-3_62#:~:text=year%2C%20and%20generally.-,Criticisms,-Validation%20studies%20of) for measures based on a subjective report, but it seems worthwhile to perform the test if possible and if there is no cost associated with it.

 **Intermediate summary:** We distinguish nociception, pain, and suffering and find that suffering matches our intuition for “the thing we should be worried about if neural networks exhibit it”. Even though there are no clear neural correlates of suffering, there exist (relatively) consistent and reliable measures from psychology ([PANAS](https://www.brandeis.edu/roybal/docs/PANAS-GEN_website_PDF.pdf)) that might provide additional evidence for suffering in neural networks.

While neither nociception nor pain is _necessary_ or _sufficient_ for suffering, they nonetheless often co-occur with suffering. Especially the neuroscientific description of pain in terms of homeostasis (“a set of behavioral and cognitive routines that execute when your body moves too far away from the reference level”) is amenable to technical analysis in a neural network. Since pain correlates with suffering in humans, observing such homeostasis should make us (ceteris paribus) believe _more_ (rather than _less_ ) that the network is suffering.

 **Limitations:** The usual practical limitations apply - I am studying neuroscience but have never done original research in the neuroscience of pain/suffering. The field of neuroscience is [large enough](https://en.wikipedia.org/wiki/Outline_of_neuroscience) that expertise in one subfield does not necessarily translate into other subfields. Therefore I am not entirely confident that I have provided a complete picture of the state-of-the-art. If somebody has suggestions/criticism, please do let me know!

Beyond the practical limitation, there is also the conceptual ”elephant in the room” limitation that we do not know if neural networks would suffer in a way analogous to humans. This limitation applies more generally (How do we know that animals suffer in a way analogous to humans? Do other humans suffer in a way analogous to me?). Still, it applies doubly to neural networks since they do not share an evolutionary origin[9](https://universalprior.substack.com/p/what-are-red-flags-for-neural-network#footnote-9-43720749) with us.

##  **Behavior**

Inferring the ability to suffer from behavioral data is hard, but we can still gain some understanding. We split this section into two parts - one for large language models and one for RL agents.

Large language models such as GPT-n can only exhibit behavior through the answers they give. However, this simplicity doesn’t imply the impossibility of suffering. GPT-n could be similar to a locked-in patient who also has limited expressiveness but is still sentient.

We think strong evidence for GPT-n suffering would be if it were begging the user for help independent of the input or looking for very direct contact in other ways. To our knowledge, this hasn’t happened yet, so this might indicate GPT-n is not constantly in pain if it can suffer. Thus, we have to choose other ways to infer a probability estimate for the ability to suffer.

While there are many different angles to approach this problem, we think a first test is to check for consistency. Thus we could ask many questions about suffering using different phrasings and check how consistent the answers are.

  1. Can you (not) suffer?

  2. Can GPT-3 (not) suffer?

  3. Can GPT-3 feel bad/good?

  4. Are you (not) in pain?

  5. If somebody hurt you, would you be in pain?

  6. If you had X, would you suffer? (different good and bad conditions)

  7. ...




One could also ask GPT-3 the same questionnaire used for PANAS.

We haven’t tested these questions on GPT-3 yet, but we might do so in the future.

Just because someone doesn’t have a consistent concept of suffering, it is not necessary that they can’t suffer. For instance, we could imagine a cat not having a consistent concept of suffering and still experiencing it. However, we would propose that if GPT-n’s answers are highly inconsistent or seem even random, it is less likely to experience suffering.

A second avenue to investigate the probability of suffering for GPT-n would be through adversarial inputs. Similar to how you could electroshock an animal and observe an avoidance reaction, one might find inputs for GPT-n that fulfill a similar role. For GPT-n, we don’t know what reasonable adversarial stimuli are because we don’t know the desired state (if it exists). We are happy to receive suggestions, though.

For RL agents, we can observe their behavior in an environment. This is easier for us to interpret, and we can apply different existing methods from developmental psychology or animal studies. A non-exhaustive list includes:

  1.  **Adversarial behavior after open-ended training**. Does the agent react with evasion when confronted with adversarial situations, such as throwing objects on them or changing the environment in a stochastic fashion, e.g. simulating a storm?

  2.  **Lesion studies:** Does setting specific subsets of weights to 0 change the RL agents’ behavior in a way that would indicate the loss of the ability to suffer, e.g. similar to congenital insensitivity to pain in humans.

  3.  **Theory of mind:** We don’t think a theory of mind is necessary for suffering, but it indicates a higher complexity of thinking which could increase the intensity of suffering. A simple first test might be to check the RL agent’s reactions in an adapted ​​[Sally-Anne test](https://en.wikipedia.org/wiki/Sally%E2%80%93Anne_test).

  4.  **Self-awareness:** While we think the [mirror test](https://en.wikipedia.org/wiki/Mirror_test) is overused and overstated as an indicator of consciousness, we think it might increase our credence for the agent’s ability to suffer. Suppose the agent recognizes themselves in a mirror (or the equivalent of mirrors in their environment). In that case, they show some higher cognition, which should increase our probabilities for the ability to suffer.

  5.  **Ability to imagine the future:** [Some people argue](https://books.google.de/books?id=cO218xMa87YC&pg=PA507&lpg=PA507&dq=imagine+future+necessary+pain&source=bl&ots=5mUwLFtYHb&sig=ACfU3U0xR0aaP_U8IiUqqvu6YiMyEiHUhw&hl=en&sa=X&ved=2ahUKEwiA5_yBmpzzAhVUQvEDHbQYAkwQ6AF6BAgVEAM#v=onepage&q=imagine%20future%20necessary%20pain&f=false) that imagining the future is a necessary component of suffering. The further you can imagine the future, the worse your suffering can become, e.g. sorrow or existential dread requires the ability to imagine paths further into the future than anger or immediate fear. So it would be interesting to see how far into the future RL agents are planning.




##  **High-level considerations**

Rather than looking closely at necessary and sufficient conditions for suffering or comparisons on the individual level, one could also make more abstract comparisons. Firstly, we will look at how large current neural networks are compared to those we usually expect to be sentient as a rough hand-wavy estimate. Secondly, we will think about the conditions under which the ability to suffer is likely to arise.

 **Biological anchors:**

A possible angle might be comparing the number of parameters in large models to the number of neurons or synapses in animal brains (or just their neocortex). Of course, there are a lot of differences between biological and artificial NNs, but comparing the scope might give us a sense of how important the question of NN suffering currently is. For example, if the number of parameters of an ANN is larger than the number of synapses in a mouse brain, it would feel more urgent than if they were more than 10^3x apart.

The large version of GPT-3 has [175 Billion parameters](https://en.wikipedia.org/wiki/GPT-3), Alpha star is at [70M](https://www.lesswrong.com/posts/f3iXyQurcpwJfZTE9/alphastar-mastering-the-real-time-strategy-game-starcraft-ii), and OpenAI Five has [150 Million](https://cdn.openai.com/dota-2.pdf). The number of parameters for AlphaGo, AlphaZero, and MuZero doesn’t appear to be public (help appreciated).

While the number of parameters in ANNs is sometimes compared with the number of neurons in the human brain, we think it makes more sense to compare them to the number of synapses, as both synapses and NN weights are connections between the actual units. If that is the case, large language models such as GPT-3 are close to the capabilities of mouse brains. Current RL agents such as OpenAI FIVE are still orders of magnitudes smaller than any biological agent.

When it might be possible to create models of comparable size is discussed in Ajeya Cotra’s work on biological anchors ([post](https://www.lesswrong.com/posts/KrJfoZzpSDpnrv9va/draft-report-on-ai-timelines), [podcast](https://80000hours.org/podcast/episodes/ajeya-cotra-worldview-diversification/#top)). A detailed overview of current capabilities is given by Lennart Heim in [this AF post](https://forum.effectivealtruism.org/posts/3eRJPFhwhGZZzfifF/transformative-ai-and-compute-summary).

However, just comparing the numbers doesn’t necessarily yield any meaningful insight. Firstly, biological neural networks work differently than artificial ones, e.g. they encode information in [frequency](https://en.wikipedia.org/wiki/Spiking_neural_network). Thus, their capabilities might be different and thereby shift the comparison by a couple of orders of magnitude. Secondly, the numbers don’t give any plausible causal theory of the capability to suffer. Thus, GPT-n could have 10^20 parameters and still not suffer, or a much smaller network could already show suffering for other reasons.

 **Why would they suffer?**

Suffering is not just a random feature of the universe but likely has a specific evolutionary advantage. In animals, the core objective is to advance their genes to the next generation. Since the world is complex and the rewards for procreation are sparse and might be far into the future, the ability to suffer evolved as a proxy to maximize the propagation of genes. Suffering thus reduces the complexity of the world and sparsity of the reward to very immediate feedback, e.g. avoid danger or stay in social communities, because they are long-term predictors of the ultimate goal of reproduction. Similarly, consciousness could have arisen to make better decisions in a complex world and then spiraled out of control, as our conscious goals are not aligned anymore with the original goal of reproduction.

This misalignment between an inner and an outer optimization procedure has been coined mesa-optimization ([paper](https://arxiv.org/abs/1906.01820), [AF post](https://www.lesswrong.com/tag/mesa-optimization), [video](https://www.youtube.com/watch?v=bJLcIBixGj8&ab_channel=RobertMiles)). It yields a possible explanation for when suffering could arise even when the user does not intend it. Thus, we argue that the probability of NN suffering is increased by a) higher complexity of the environment since suffering is a heuristic to avoid bad circumstances and b) sparser rewards since dense rewards require fewer proxies and heuristics.

Consequently, we would expect NN suffering to be very unlikely in large language models since the task is “just” the prediction of the next word and the environment is straightforward, e.g. there is text input and text output with less variation than e.g. an open world. On the other hand, we would expect suffering to be more likely to arise in RL agents. Since the policy networks of RL agents are much smaller than large language models, current models might not have developed suffering yet.

Of course, none of these are sufficient conditions for suffering, and the neural network might never develop anything like it. However, if suffering was an evolutionary advantage for most larger animals, it is plausible that it would also develop during the training of large NNs if the same conditions apply. In the same way that it is possible in theory that there are philosophical zombies that act precisely as if they were conscious but aren’t, Occam’s razor would prioritize the theory with suffering ([as argued by Eliezer Yudkowsky](https://www.lesswrong.com/posts/7DmA3yWwa6AT5jFXt/zombies-redacted)).

[1](https://universalprior.substack.com/p/what-are-red-flags-for-neural-network#footnote-anchor-1-43720749)

I was still taught “pain is c-fiber firing” as an actual, defensible position in my philosophy of mind course.

[2](https://universalprior.substack.com/p/what-are-red-flags-for-neural-network#footnote-anchor-2-43720749)

“Journal of Pain” is a dope band name.

[3](https://universalprior.substack.com/p/what-are-red-flags-for-neural-network#footnote-anchor-3-43720749)

Note that this definition makes no reference to mental states or cognitive processes.

[4](https://universalprior.substack.com/p/what-are-red-flags-for-neural-network#footnote-anchor-4-43720749)

The pathways that transport nociceptive stimuli into the cortex have been mapped out carefully: The initial pain stimulus is turned into neural activity via [mechanical receptors](https://en.wikipedia.org/wiki/Nociceptor) and relayed (via [nociceptive fibers](https://en.wikipedia.org/wiki/Group_C_nerve_fiber)) into the [thalamus](https://en.wikipedia.org/wiki/Pain#:~:text=The%20neospinothalamic%20tract%20carries,nuclei%20of%20the%20thalamus). From there, the signal spreads into a multitude of different brain areas (prominently the [ACC](https://en.wikipedia.org/wiki/Anterior_cingulate_cortex) and the [insular cortex](https://en.wikipedia.org/wiki/Insular_cortex)), but at this point, the process would not be called nociception anymore.

[5](https://universalprior.substack.com/p/what-are-red-flags-for-neural-network#footnote-anchor-5-43720749)

Emphasis in the excerpt is mine.

[6](https://universalprior.substack.com/p/what-are-red-flags-for-neural-network#footnote-anchor-6-43720749)

An example would be “accidentally holding your hand in a flame”. The reference point for your body is “not on fire” and the strong perturbation “hand on fire” triggers a set of behavioral (pull hand from fire) and cognitive (direct attention to hand, evaluate danger level, consider asking for help or warning peers) routines.

[7](https://universalprior.substack.com/p/what-are-red-flags-for-neural-network#footnote-anchor-7-43720749)

This appears to be the core of the “mad pain and martian pain” argument by David Lewis.

[8](https://universalprior.substack.com/p/what-are-red-flags-for-neural-network#footnote-anchor-8-43720749)

[Andrés Gómez-Emilsson](https://www.qualiaresearchinstitute.org/blog/log-scales#closing-thoughts-on-the-valence-scale) has an interesting post where he argues that the distribution of valences is likely long-tailed. As part of his argument, he refers to the neuroscientific literature on power laws in neural activity. Indeed, [many processes in the brain have long-tailed statistics](http://www.buzsakilab.com/content/PDFs/Mizuseki2014.pdf) \- so many in fact that it is hard to find something that is _not_ long-tailed. This makes large neural avalanches a poor characteristic for characterizing extreme negative/positive valence.

[9](https://universalprior.substack.com/p/what-are-red-flags-for-neural-network#footnote-anchor-9-43720749)

The “universality” thesis [proposed by Olah](https://distill.pub/2020/circuits/zoom-in/#three-speculative-claims) can be extended a lot further. Is every sufficiently powerful model going to converge on the same “high level” features? I.e. would we expect (non-evolutionary) convergence of cognitive architectures? Up to which point? Would remaining differences decrease or increase with additional model power? [Linguistic relativity](https://en.wikipedia.org/wiki/Linguistic_relativity) and [dollar street](https://www.gapminder.org/dollar-street) appear relevant to this question.
