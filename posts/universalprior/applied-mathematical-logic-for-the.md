# Applied Mathematical Logic For The Practicing Researcher

## TL;DR: Using the language of model theory to engineer a definition of "computational model".

**Oct 17, 2021**

**Likes:** 0

Asking for a friend[1](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-1-42721010): what happened to Richard Hamming's social status after he started asking [those pointed questions](https://www.cs.virginia.edu/~robins/YouAndYourResearch.html) about the importance of research questions and individual career decisions? Was he, like, _actually_ banished from the lunch table?

Subscribe

* * *

# Technically, I _am_ modeling for a living

A couple of months ago I've started asking my colleagues during lunch what their definition of a "model" is. This question is important: our job consists of building, evaluating, and comparing models. I am not hoping for an Aristotelean list of necessary & sufficient conditions, but it still appears like a good idea to "survey the land". Also, admittedly, lunch can get a bit boring without challenging questions.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ffe9ace6d-37fc-4099-b50d-68ba8d8b8ae3_256x256.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ffe9ace6d-37fc-4099-b50d-68ba8d8b8ae3_256x256.png)An abstract drawing of a computational model. [CGD generated](https://huggingface.co/spaces/akhaliq/clip-guided-diffusion).

I got a range of responses:

> " _a description of a phenomenon from which you can reason (= a description you can manipulate to tell more about the phenomenon than you would have been able to tell without it)_ "
> 
> " _It should be something like a representation of the modelled system without representing it completely. Perhaps most importantly that it preserves the causal relationships between the system elements without completely mapping these elements?_ "
> 
> " _an abstraction of reality_ "

I also ran into this adage again and again (attributed to a different person every time):

> " _All models are false, but some are useful._ "

Along similar lines, there is a [quote](https://pubmed.ncbi.nlm.nih.gov/18995824/) from the influential computational neuroscientist [Larry Abbott](https://en.wikipedia.org/wiki/Larry_Abbott):

> " _the term 'realistic' model is a sociological rather than a scientific term._ "

Alright, survey done, lunch is over. Back to...

* * *

# In search of tighter concepts

No! I'm not satisfied. What do you mean it's a _sociological_ term? What do you mean they are _false_? Can a model have a truth value? If a model is a "representation" / "abstraction" / "description" then what _exactly_ is a "representation" / "abstraction" / "description"? This is not some [idle philosophical nitpicking](https://www.lesswrong.com/posts/FwiPfF8Woe5JrzqEu/philosophy-a-diseased-discipline), this question is _immediately_ important. As a reviewer, I have to judge whether a model is _good_ (enough). As a researcher, I want to build a _good_ model. I'm not going to devote my career to building models if I don't have a _really good_ idea of what a model _is_.

I hope you can tell from my extensive use of italicized words that this is a topic I am rather passionate about. If the question of a good model is a sociological question then it's subject to trends and fads[2](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-2-42721010). And if the term "model" is broad enough to fit "[detailed biophysical models](https://neuron.yale.edu/neuron/)", "[abstract phenomenological models](https://www.nature.com/articles/s43586-020-00001-2)", "[linear regression](https://www.biorxiv.org/content/10.1101/2021.04.02.438248v1.full)" and "[a cartoon in Figure 8](https://www.jneurosci.org/content/37/21/5250#F8)" under its umbrella, then it's inevitable that our intuitive understanding of what constitutes a good model deviates. Heck, the term is so broad, technically even this should qualify:

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F66ddbc31-bfc0-4e83-8b07-a4d511bb563d_256x256.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F66ddbc31-bfc0-4e83-8b07-a4d511bb563d_256x256.png)An abstract painting of a very attractive [albatross](https://universalprior.substack.com/p/soldiers-scouts-and-albatrosses) that could totally be a fashion model. [CGD generated](https://huggingface.co/spaces/akhaliq/clip-guided-diffusion).

So in the spirit of [conceptual engineering](https://www.lesswrong.com/posts/9iA87EfNKnREgdTJN/conceptual-engineering-the-revolution-in-philosophy-you-ve) and [dissolving questions](https://www.lesswrong.com/posts/Mc6QcrsbH5NRXbCRX/dissolving-the-question), here goes my attempt of laying out what I think of when I think of models. This is obviously not authoritative and it's far from rigorous. This is just my "working definition" which I wrote down to force myself to tighten my terminology.

* * *

# Mathematical logic to the rescue

Since we mean so many different things by the term "model" it makes sense to start very general, i.e. mathematical. There is indeed a subfield of mathematics called "[model theory](https://en.wikipedia.org/wiki/Model_theory)" that makes some very useful distinctions! I'll trample over all subtleties to get to the core quickly, but consider checking out [this](https://www.lesswrong.com/posts/MG8Yhsxqu9JY4xRPr/mental-context-for-model-theory) or [this](https://www.lesswrong.com/s/SqFbMbtxGybdS2gRs/p/Z2CuyKtkCmWGQtAEh) for accessible introductory reading.

Here goes the central definition:

> A model is a (mathematical) object that satisfies all the sentences of a theory.

To make this useful, we have to further define the used terms. 

What is a _theory_? It's a set of sentences. What is a _sentence_? Well, it's pretty much what you would expect - it's a string of symbols constructed from an alphabet according to some fixed rules. A famous example of a theory is [Peano arithmetic](https://en.wikipedia.org/wiki/Peano_axioms#First-order_theory_of_arithmetic), but really the definition is much more general:

  1. A dynamical system, given as a set of differential equations[3](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-3-42721010), is a theory.

  2. A cellular automaton, given as a set of transition rules, is a theory.

  3. Any recursively enumerable set of sentences of a formal language, given as a set of production rules, is a theory.




[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Faf591ac5-2557-4ce0-853b-71bd19433f0c_256x256.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Faf591ac5-2557-4ce0-853b-71bd19433f0c_256x256.png)An abstract drawing of a cellular automaton. [CGD generated](https://huggingface.co/spaces/akhaliq/clip-guided-diffusion).

Now to the other part of the definition. What is a mathematical object? _Phew_ , you are opening a [can of worms](https://en.wikipedia.org/wiki/Philosophy_of_mathematics#Contemporary_schools_of_thought)... But I'm pretty sure you'll recognize a mathematical object when you see it. **[R](https://www.dcode.fr/number-sets)**[, ](https://www.dcode.fr/number-sets)**[Q](https://www.dcode.fr/number-sets)**[, ](https://www.dcode.fr/number-sets)**[Z,](https://www.dcode.fr/number-sets)**[ ](https://www.dcode.fr/number-sets)**[N](https://www.dcode.fr/number-sets)** , and all the cool stuff you can build from those sets, those are mathematical objects. **N** satisfies the theory of (and is, therefore, a model of) Peano arithmetic. For the three theories mentioned above, the mathematical objects that satisfy them are:

  1. A particular trajectory through state space, f.e. specified through initial conditions.

  2. A particular evolution of the cellular automaton, again specified through the initial conditions.

  3. A particular Turing machine that implements the production rules, specified through... (you get the idea).




If we are allowed to be even more hand-wavy, then we can also incorporate models à la [Tyler Cowen](https://marginalrevolution.com/marginalrevolution/2020/10/model-this-5.html): To "model this [headline]" we have to come up with a theory (a set of sentences) from which the headline follows.

One important thing to note here is that every model "inherits" every property that follows from the theory. But the inverse does not hold[4](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-4-42721010): just because a model has a certain property, this property does not necessarily follow from the theory. In general, there will always be multiple models that satisfy a theory, each with different "additional properties" that go beyond what is prescribed by the theory[5](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-5-42721010).

All fine and well. What does this added complexity buy us?

* * *

# Good models, bad models

Defining a model as an object satisfying a theory is broad enough to cover all the ways in which the term is used:

  * the entire spectrum of mathematical models, from detailed biophysical to normative Bayesian, is specified by a set of equations (a theory) and instantiated with parameter choices.

  * the "cartoon in Figure 8" is one particular (rather toothless) object that satisfies an implicit theory (consisting of a set of conjectured sentences).

  * the albatross fashion model... doesn't fit. But [you can't have everything, I'm told](https://open.spotify.com/track/5f5r2N4Lp9WoULWPH9zp2W?si=b2d7dec6f9da4884).




It also includes an interesting pathological case: to model a particular set of observations, we could just come up with a theory that contains all the observations as axioms, but no production rules. Then the observations themselves trivially satisfy the theory. This is clearly useless in some sense[6](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-6-42721010) (a dataset shouldn't be a model?) - but looking deeper into why it's useless reveals something about what constitutes a _good_ model - or, by extension, a _good_ theory.

Here is my definition:

> A _good_ model of a phenomenon is one that allows us to _understand_ something about the phenomenon. If all the models of a theory are good models, the theory is a _good_ theory.

Again, we need to define our terms for this to make sense. What is a _phenomenon_? A phenomenon is some (conjunction of) physical process(es). It's something [out there in the territory](https://www.lesswrong.com/posts/KJ9MFBPwXGwNpadf2/skill-the-map-is-not-the-territory). What does _understand_ mean? Understanding a phenomenon means predicting (better than chance level) the state of the phenomenon at time **t+1** given the state at time **t**.

Why does it make sense to set up things like this?

* * *

# Models with benefits

First, it establishes a neat hierarchy. Understanding is gradual: It goes from non-existing (chance level) to poor (consistently above chance[7](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-7-42721010)) to great (almost perfect prediction) to complete (100% prediction accuracy).

With this definition, a "black box" deep learning model that is able to [predict a percentage of brain activity](https://www.biorxiv.org/content/10.1101/133504v1.full) does provide _some_ understanding about a part of the brain. Similarly, a [mean-field model](https://en.wikipedia.org/wiki/Mean-field_theory) that has "lost" some conversion factor in its units can also still be a good model, as long as it is able to get the _direction_ of the evolution of the state correct.

Second, by making “predictions” the central criterion for the model quality we avoid unproductive [disputes resulting from mismatched terms](https://www.lesswrong.com/posts/7X2j8HAkWdmMoS8PE/disputing-definitions). The usual example here is "If a tree falls in the forest, does it make a sound?", which can lead to a highly unproductive discussion if asked at the lunch table. But when explanations are evaluated according to their predictive power, misunderstandings are resolved quickly: Either a tape recorder will or won't record airwaves. Either there is or there isn't activation in some auditory cortex.

Third, to have a good theory, you need to demonstrate that all its models are good (according to the definition above). This gets naturally easier if there are fewer models that satisfy the theory, thus incentivizing you to remove as many free parameters from the theory as possible[8](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-8-42721010). Ideally, you'll want a unique characterization of a good model from your theory.

Finally, this definition formalizes the "all models are wrong, but some are useful" adage. To get 100% prediction accuracy for a physical process you have to go down to the level of particles. F.e. having a fluid dynamics model of water motion will get you very far in terms of predictive power. In that sense, it's a very good model. But to get even close to 100%, you'll want an [atomic model of water](https://www.feynmanlectures.caltech.edu/I_01.html). And eventually, if you are pushing for ever more predictive power, you'll have to decompose your problem further and further, and eventually, you will get into very weird territory[9](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-9-42721010).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fe4ac78ed-528e-430f-87c7-3356749f79a0_256x256.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fe4ac78ed-528e-430f-87c7-3356749f79a0_256x256.png)An abstract drawing of the solar system. [CGD generated](https://huggingface.co/spaces/akhaliq/clip-guided-diffusion).

Thus, to determine whether a model is good or bad, you have to figure out which phenomenon it is trying to explain and then determine if the model allows you to predict the time-evolution of the phenomenon better than chance level. This is a relatively low bar, but in my experience, it's still not easy to clear. Actually demonstrating that your performance is different from chance requires explicit performance metrics, which are not usually adapted. But that's [a different story](https://universalprior.substack.com/p/on-scaling-academia).

* * *

# Cliffhanger!

This is almost all I wanted to say on the topic. But I glossed over an important point in that exposition: If a model is a mathematical object, why might we expect that it can predict physical processes _out there in the territory_? In fact, why should there be _any_ similarity between the [solar system and the atom](https://en.wikipedia.org/wiki/Bohr_model)[10](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-10-42721010)? Why does [analogical reasoning](https://plato.stanford.edu/entries/reasoning-analogy/) work?

I'm glad you ask. Stay tuned - I'll dig into that next time.

Subscribe

[1](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-anchor-1-42721010)

Okay, okay, I can't lie to you. That friend is me. I'm worried about getting banished from the lunch table.

[2](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-anchor-2-42721010)

And it's usually up to an influential "ingroup" to decide what fits in and what doesn't.

[3](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-anchor-3-42721010)

Plus [ZFC](https://en.wikipedia.org/wiki/Zermelo%E2%80%93Fraenkel_set_theory), I guess.

[4](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-anchor-4-42721010)

This inverse only holds when the model uniquely and completely specifies the model, which is pretty hard to achieve in principle. See [Logical Pinpointing](https://www.lesswrong.com/posts/3FoMuCLqZggTxoC3S/logical-pinpointing).

[5](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-anchor-5-42721010)

One might be tempted to argue that if many different models satisfy the same theory, this is evidence that the property actually does follow from the theory. This isn't guaranteed, but it might work in some cases. In Computational Neuroscience, this is the practice of demonstrating that the desired result holds even when the parameter is slightly perturbed.

[6](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-anchor-6-42721010)

This has some overlap with Chomsky's [levels of adequacy](https://en.wikipedia.org/wiki/Levels_of_adequacy): a theory that includes only the observations as axioms has observational adequacy, but neither descriptive nor explanatory adequacy.

[7](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-anchor-7-42721010)

Or below, of course! If you're consistently worse than chance that is very useful information.

[8](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-anchor-8-42721010)

Thus we arrive at an interesting version of Occam's razor.

[9](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-anchor-9-42721010)

Let's not talk about quantum stuff on this Substack, okay?

[10](https://universalprior.substack.com/p/applied-mathematical-logic-for-the#footnote-anchor-10-42721010)

Yes, I know that the Bohr model is not the end of the story. But it is still able to explain basically all of chemistry. And also " _let’s not talk about quantum physics on this Substack_ "!
