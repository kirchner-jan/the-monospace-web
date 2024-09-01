# A Brief Excursion Into Molecular Neuroscience

## TL;DR: Poking fun at complicated nomenclature (p̴͓̂͘á̴̻͌s̶̻̗͋͑ṯ̸̹̈́̌à̶̳), identifying a pretty important signaling factor in the brain, and arbitrating (part of) the Guzey/Mendonça debate.

**Apr 10, 2022**

**Likes:** 2

_Previously in this series:[How to build a mind - neuroscience edition,](https://universalprior.substack.com/p/how-to-build-a-mind-neuroscience?s=w) [Serendipitous connections: applying explanations from AI to the brain](https://universalprior.substack.com/p/serendipitous-connections-applying?s=w)_, [The Unreasonable Feasibility Of Playing Chess Under The Influence.](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing?s=w)

#  **The Emperor's New Ǫ̵͎͊G̶̦̉̇l̶͉͇̝̽͆̚i̷͔̓̏͌c̷̱̙̍̂͜k̷̠͍͌l̷̢̍͗̃n̷̖͇̏̆å̴̤c̵̲̼̫͑̎̆**

 _(Ǫ̵͎͊G̶̦̉̇l̶͉͇̝̽͆̚i̷͔̓̏͌c̷̱̙̍̂͜k̷̠͍͌l̷̢̍͗̃n̷̖͇̏̆å̴̤c̵̲̼̫͑̎̆ is an intentionally[garbled](https://lingojam.com/GlitchTextGenerator) version of the word O-GlcNAc. The reasons for garbling it will hopefully become clear while reading this essay!)_

 _Flashback_ : It's June 7th, 2017. The transformer architecture [will drop on the arxiv](https://arxiv.org/abs/1706.03762) in 5 days, Hugh Hefner will die in less than 3 months[1](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-1-51607370), and the computational neuroscience community is having a field day on Twitter. It started with this tweet from [Michael Nitabach](https://medicine.yale.edu/lab/nitabach/) from Yale School of Medicine complaining about opaque jargon in theoretical papers:

[![Twitter avatar for @mnitabach](https://substackcdn.com/image/twitter_name/w_96/mnitabach.jpg)Dr Habanolide Nitters @mnitabachIs it really necessary to use mathematical jargon term "manifold" for this instead of plain English? ![Twitter avatar for @NeuroCellPress](https://substackcdn.com/image/twitter_name/w_40/NeuroCellPress.jpg)Neuron @NeuroCellPressGallego et al. discuss neural manifolds for the control of movement in the latest special issue @NeuroCellPress https://t.co/aKp5GsSxEn https://t.co/rDTIgjeinJ](https://twitter.com/mnitabach/status/873199689855795200?s=20&t=rbbyorUR899Wl-KM94vCTg)[3:26 PM ∙ Jun 9, 2017

* * *

33Likes6Retweets](https://twitter.com/mnitabach/status/873199689855795200?s=20&t=rbbyorUR899Wl-KM94vCTg)

(33 likes is a _lot_ on neurotwitter.)

There was a bit of goofy back and forth about the (un)importance of mathematical vocabulary in neuroscience, some attempts at explaining the term, and eventually the call for a workshop on "Manifold-splaining", which happened half a year later[2](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-2-51607370). 

There are some things to be said here about how we use terminology[3](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-3-51607370) or what manifolds _actually_ are[4](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-4-51607370), but I'm bringing this up because I distinctly[5](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-5-51607370) remember an offhand comment that someone made at that workshop. The comment was that it’s unfair that experimentalists get to write things like "[O-GlcNAc signaling entrains the circadian clock by inhibiting BMAL1/CLOCK ubiquitination,](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=Xxmiua8AAAAJ&citation_for_view=Xxmiua8AAAAJ:8k81kl-MbHgC)" and nobody gives _them_ hell for writing their papers in Klingon. Or at least [they are not getting](https://www.quora.com/Why-are-the-terms-in-biology-so-complicated-and-confusing) _enough_ hell for it.

When I was first confronted with the [alphabet soup](https://rupress.org/jcb/article/160/4/466/33255/Stories-of-Cells-The-American-Society-for-Cell#:~:text=supplied%20us%20with-,many%20gene%20names,-%28an%20%E2%80%9Calphabet%20soup) that calls itself molecular neuroscience, I was _awed_ by my colleagues, who appeared to be fluent in speaking p̴͓̂͘á̴̻͌s̶̻̗͋͑ṯ̸̹̈́̌à̶̳. It took me a year or two to figure out that they also do not know what most of the terms mean - and for most abbreviations, there are only a handful of people in the world who _can_ decode them. But nobody likes to [acknowledge that they don't know what things mean publicly](https://en.wikipedia.org/wiki/The_Emperor%27s_New_Clothes). Therefore everybody nods along when they read Ǫ̵͎͊G̶̦̉̇l̶͉͇̝̽͆̚i̷͔̓̏͌c̷̱̙̍̂͜k̷̠͍͌l̷̢̍͗̃n̷̖͇̏̆å̴̤c̵̲̼̫͑̎̆. So it's fine if you don't know what it means. Almost nobody does[6](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-6-51607370).

#  **Let’s talk about BDNF.**

Perhaps you are the kind of person that takes the preceding paragraphs as a challenge, and you’d like to learn to speak p̴͓̂͘á̴̻͌s̶̻̗͋͑ṯ̸̹̈́̌à̶̳ yourself. Or perhaps you like to read about different levels of abstraction, what we gain by using them, and how we can transition between them. Or perhaps you’re having a slow day and want to learn something funky. In all those cases, this essay is certainly for you. 

But perhaps you are a very busy person, and you tend to be very selective about how you spend your time. Perhaps you want to be sure that _if_ you’re going to dive into this mess of molecules, you’ll be able to get a [Pareto-sized chunk](https://en.wikipedia.org/wiki/Pareto_principle) of insight in return. Perhaps [you’ve been hurt before](https://slatestarcodex.com/2019/05/07/5-httlpr-a-pointed-review/) and have difficulties trusting _any_ molecule. In all those cases, this section is here to assuage you. Let me motivate why you might care about the protagonist of this essay, the "brain-derived neurotrophic factor" (BDNF[7](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-7-51607370)). 

**Argument from interestingness.**

BDNF has shown up repeatedly in the rationality-sphere over the last years:

  * Alexey Guzey's thesis about [why you ](https://guzey.com/theses-on-sleep/)_[shouldn't](https://guzey.com/theses-on-sleep/)_[ sleep](https://guzey.com/theses-on-sleep/) circles around BDNF. 

  * Natália Mendonça's counter-thesis that you _[should](https://www.lesswrong.com/posts/sbcmACvB6DqYXYidL/counter-theses-on-sleep)_[ sleep all the time](https://www.lesswrong.com/posts/sbcmACvB6DqYXYidL/counter-theses-on-sleep) attacks Guzey's claims about BDNF.

  * Scott Alexander [explained a few years ago](https://slatestarcodex.com/2017/06/13/what-is-depression-anyway-the-synapse-hypothesis/) how an increase in BDNF plays a central role in the function of antidepressants.

  * Then there was a [big Cell paper](https://www.cell.com/cell/fulltext/S0092-8674%2821%2900077-5) that argued for the importance of the canonical BDNF receptor (TrkB) rather than BDNF. Scott [didn't buy it](https://astralcodexten.substack.com/p/a-look-down-track-b?s=r).




But that is just the tip of the iceberg! Let’s check out what we can find on Spotify about BDNF.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc7cd97ea-585b-4605-8bea-4d53f16b0071_1774x849.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc7cd97ea-585b-4605-8bea-4d53f16b0071_1774x849.png)

Faster learning, better memory, neurogenesis, stopping Alzheimer’s. Also, some playlists that will boost your BDNF!

What about YouTube?

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fd0eca62a-535a-415b-ae83-3b78dab637cc_2177x646.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fd0eca62a-535a-415b-ae83-3b78dab637cc_2177x646.png)

More boosting brainpower, fighting anxiety, naturally increasing BDNF through workout…

Hopefully, all of your [alarm bells](https://universalprior.substack.com/p/via-productiva?s=w#:~:text=Don%27t%20listen%20to%20Cassandra.) are going off right now. This pattern-matches with scams and [irreplicability](https://slatestarcodex.com/2019/05/07/5-httlpr-a-pointed-review/). Cognitive enhancement would be a [huge deal](https://www.gwern.net/Nootropics), but it’s also super [difficult,](https://www.gwern.net/docs/algernon/2011-lynch.pdf) and apart from maybe coffee and modafinil, there don’t appear to be any easy hacks.

But why do (some) people _believe_ BDNF can do all these things? There are so many words in p̴͓̂͘á̴̻͌s̶̻̗͋͑ṯ̸̹̈́̌à̶̳; why pick BDNF in particular? Why are there no playlists about Ǫ̵͎͊G̶̦̉̇l̶͉͇̝̽͆̚i̷͔̓̏͌c̷̱̙̍̂͜k̷̠͍͌l̷̢̍͗̃n̷̖͇̏̆å̴̤c̵̲̼̫͑̎̆ improving your mental faculties?

 **Argument from academic street cred.**

A partial answer to that question comes directly when we open Google Scholar and search for BDNF.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F17bffc60-4c74-4817-98c1-bc77fabe486c_1212x852.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F17bffc60-4c74-4817-98c1-bc77fabe486c_1212x852.png)A semi-random selection of BDNF papers from the first page of Google Scholar.

If you happen to be doing neuroscience research in the 90s and you are looking for a hot topic to research - BDNF is your fast-track ticket to tenure[8](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-8-51607370). Considering that the "normal" citation count for a paper in a top journal like Nature is “[only” in the double digits](https://www.nature.com/nature-portfolio/about/journal-metrics), and a lot of papers [never get cited at all](https://blogs.lse.ac.uk/impactofsocialsciences/2014/04/23/academic-papers-citation-rates-remler), it is pretty insane that you have to go to page _14_ on Google Scholar after searching "BDNF" to find a paper with less than 100 citations[9](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-9-51607370).

Other signaling molecules pale in comparison: 

  * glutamate; first sub-100 citations paper on page 9 

  * GABA; first sub-100 citations paper on page 4 

  * dopamine; first sub-100 citations paper on page 3




Calling BDNF a "big deal" in neuroscience would be an understatement. In the literature, it’s called “[A convergence point for many signaling pathways](https://www.nature.com/articles/nrn1078)“, “[A Key Molecule for Memory in the Healthy and the Pathological Brain](https://www.frontiersin.org/articles/10.3389/fncel.2019.00363/full)“, and “[A Key Factor with Multipotent Impact on Brain Signaling and Synaptic Plasticity](https://link.springer.com/article/10.1007/s10571-017-0510-4)”. 

The fact that there is so much research on BDNF also hints at why there should be so much questionable content on Spotify and YouTube. We should expect the [noise to scale with the signal](https://universalprior.substack.com/p/via-productiva?s=w#:~:text=Don%27t%20listen%20to%20Cassandra.) \- the more research there is, the easier it is to pick out individual pieces and spin an arbitrary narrative. But this should not _a priori_ mean that the underlying science is bad! [Quantum healing](https://en.wikipedia.org/wiki/Quantum_healing) does not invalidate quantum physics.

Then again, [citations are not a good proxy for quality,](https://journals.sagepub.com/doi/10.1177/2158244019829575) and especially articles in [medicine-adjacent fields suffer from citation inflation](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0020885). And as a lot of literature on BDNF comes from those fields, they might have [replicability issues](https://slatestarcodex.com/2019/05/07/5-httlpr-a-pointed-review/). So, just because there are many highly-cited papers, we can’t necessarily conclude that the underlying research is solid.

 **Argument from ubiquity.**

So let us zoom out instead and (try to) take an unbiased look. From a [previous project,](https://universalprior.substack.com/p/on-context-and-people?s=w) I happen to have a 2D embedding of all the neuroscience papers published on biorxiv:

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F12d27039-8b04-484b-ae47-98394d85b7d5_301x305.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F12d27039-8b04-484b-ae47-98394d85b7d5_301x305.png)Zoom in on the neuroscience section of biorxiv (red) from a tSNE embedding of all papers on biorxiv. Superimposed are the projected embeddings of three famous neuroscientists and yours truly.

This embedding is useful for understanding _where/in which subcommunity_ certain topics are being researched. In particular, for any given keyword, we can compute the semantic similarity with all the papers:
    
    
    corpus_embeddings = get_papers('neuroscience')
    serotonin_embedding = model.encode("Serotonin or 5-hydroxytryptamine (5-HT)")
    util.cos_sim(corpus_embeddings, serotonin_embedding)

We can use the resulting similarity scores to color in a tSNE embedding of all the neuroscience papers.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fe27282bf-1881-4917-a05f-18c2f1265451_7093x2539.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fe27282bf-1881-4917-a05f-18c2f1265451_7093x2539.png)TSNE embedding of all preprints published in the neuroscience section of biorxiv. Embedding computed with the [Allen SPECTER model](https://github.com/allenai/specter). The color indicates semantic similarity with serotonin (left), glutamate (middle), or BDNF (right).

BDNF makes the neuroscience landscape [light up like a Christmas tree](https://getyarn.io/yarn-clip/dbc520a9-9a06-4eba-8c3b-c6c0ad1ea3a3)[10](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-10-51607370)! Almost all areas of neuroscience that are represented on biorxiv appear to have active research related to BDNF. Postulating that all the subfields of neuroscience conspire to do shoddy science on BDNF is probably a bit much. 

So I conclude that there is _some_ true signal in all the noise. That’s rather fortunate[11](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-11-51607370) for me since it means that the time I already spent [working on this](https://www.nature.com/articles/s41467-021-23557-3#:~:text=an%20activity%2Ddependent-,neurotrophin,-model) is not (completely) wasted. Let’s see if we can unpack this further and separate the fluff from the science.

# Exposition

It’s 1982[12](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-12-51607370), [and you are](https://en.wikipedia.org/wiki/Hans_Thoenen) a Swiss-born neurobiologist[13](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-13-51607370) who finds himself as the director of the Max-Planck Institute for Psychiatry[14](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-14-51607370) established only 5 years earlier. During your childhood in the Swiss mountainside, you would not have expected to find yourself in a laboratory, cooled down to 4°, containing several refrigerators filled with pig brains and a blender; but here you are. Together with [your colleague,](https://www.cardiff.ac.uk/people/view/81114-barde-yves) you are looking at a dark stripe localized in a single spot of the gel you just electrophorized. You can’t quite hide your satisfaction that the procedure worked. Indeed, it seems there _is_ a growth factor in the central nervous system that nobody has seen before.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa6d05815-9e42-468c-b568-f572e65d9e2c_387x695.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa6d05815-9e42-468c-b568-f572e65d9e2c_387x695.png)

Yves-Alain Barde and Hans Thoenen had searched for BDNF by purifying it from pig brains. It’s present in very low quantities, so it took them a while to find it. But they reasoned that there _should_ be an analog of the nerve growth factor (NGF) that was [critical for survival of peripheral neurons](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4530710/#:~:text=exhibited%20similar%20properties%20for%20other%20populations%20of%20neurons), so they kept searching until they found it[15](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-15-51607370). After this initial discovery, it [took seven years](https://www.nature.com/articles/341149a0) for them to deduce the amino acid sequence and produce BDNF in sufficient quantity to study its structure and effect[16](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-16-51607370).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F44b5b4d1-73ad-482a-a139-2fa156ed11b0_381x500.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F44b5b4d1-73ad-482a-a139-2fa156ed11b0_381x500.png)This is actually NGF, but all the neurotrophins are pretty similar. [source](https://pdb101.rcsb.org/motm/68)

People got excited about BDNF in the first place because it [keeps neurons alive](https://pubmed.ncbi.nlm.nih.gov/2697237/) and [makes synapses stronger](https://pubmed.ncbi.nlm.nih.gov/12441056/). Turns out neurons are little divas: when you put too many (or too few, or without [their cheerleaders](https://en.wikipedia.org/wiki/Glia)) of them in a dish, they [just die](https://www.researchgate.net/post/Why-are-my-primary-rat-neuronal-cultures-dying-at-around-14-days). A stroke (a reduction in blood supply to a part of the brain) really wouldn’t be so bad if it didn’t [kill a ton of neurons in the process](https://pubmed.ncbi.nlm.nih.gov/19182083/). And what Parkinson’s, Alzheimer’s, Huntington’s, etc., have in common is that their behavioral phenotype is [brought about mostly by neural death](https://en.wikipedia.org/wiki/Neurodegenerative_disease). Naturally, researchers hoped they could convince neurons not to do that if offered enough BDNF. (After tons of animal testing, the phase 1 trial of administering BDNF to people affected by Alzheimer’s disease [started in 2021](https://clinicaltrials.gov/ct2/show/NCT05040217).)

This is not the end of the story, though. If you’ve been living in this universe for a while, you will have realized that there can be no Sherlock without a Moriarty. [Seven years after BDNF could be cloned in sufficient quantity](https://pubmed.ncbi.nlm.nih.gov/8603699/), we finally got a solid understanding of how BDNF is produced in the brain: similar to other neurotrophins, it’s synthesized as a precursor (preproBDNF), which is then processed by an enzyme into an immature version of BDNF (proBDNF) and then finally into mature BDNF. 

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F6f521e1a-c42c-4986-8ab0-804297c05ba9_4519x1563.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F6f521e1a-c42c-4986-8ab0-804297c05ba9_4519x1563.png)**a** Schematic representation of preproBDNF, proBDNF, and mature BDNF. The scissor indicates cleaving by the appropriate enzyme. **b** Antagonistic relationship of proBDNF and BDNF. While proBDNF preferentially binds to a receptor that promotes synaptic depression and cell death, BDNF preferentially binds to a receptor that induces synaptic potentiation and cell growth.

Initially, people [were a bit doubtful](https://www.nature.com/articles/nn0209-105) of the biological relevance of proBDNF. But over time, [a](https://www.nature.com/articles/nn1510) [lot](https://www.nature.com/articles/nn.2244) [of](https://www.science.org/doi/full/10.1126/science.1100135) [evidence](https://www.jneurosci.org/content/25/22/5455.short) emerged that proBDNF is a true [darkest timeline](https://community-sitcom.fandom.com/wiki/Darkest_Timeline#:~:text=The%20Darkest%20Timeline%20is%20an,tragedy%20within%20the%20study%20group.) version of BDNF. Instead of making neurons survive, [it kills them](https://pubmed.ncbi.nlm.nih.gov/15930396/). Instead of making synapses stronger, it [makes them weaker](https://pubmed.ncbi.nlm.nih.gov/19451278/). And yet, as if stars of a sitcom, both proBDNF and BDNF have to live cramped together in synaptic vesicles. (Surprisingly, I could not find any phase 1 trial of administering proBDNF to people who are too healthy.)

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F115d0c05-9c85-41b8-86ad-3bb95716b1b0_706x365.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F115d0c05-9c85-41b8-86ad-3bb95716b1b0_706x365.png)Both proBDNF and BDNF are packed tightly into vesicles, ready to be released into the synaptic cleft. Alongside the neurotrophins, there are also cleaving proteases in the vesicle that can turn proBDNF into BDNF. Adapted from [source](https://www.pnas.org/doi/10.1073/pnas.1803645115).

While BDNF initially was only found in brain smoothies that are not doing much of anything anymore, it soon became clear that [neural activity can modulate neurotrophin concentration](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5479144/). The first hint came from the fact that mRNA for neurotrophins increases [after seizures,](https://www.science.org/doi/10.1126/science.2549634) but soon people were able to tease apart more closely that activity-dependent release of BDNF is [important for retaining memories](https://pubmed.ncbi.nlm.nih.gov/12553913/). And now we’re even getting to the point where we can stimulate individual synapses with a laser and [watch the amount of BDNF released in real-time](https://www.nature.com/articles/nature19766).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_lossy/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc6b1e2d1-f993-4529-bf39-e86ccb9deda6_204x234.gif)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc6b1e2d1-f993-4529-bf39-e86ccb9deda6_204x234.gif)Two-photon video demonstrating the increase in BDNF-SEP fluorescence in response to the induction of sLTP by two-photon glutamate uncaging. [source](https://www.nature.com/articles/nature19766)

Alright, so far[,](https://www.science.org/doi/10.1126/science.2549634) so good. Neurons contain BDNF, which brings about good things, and its evil twin, proBDNF, which brings about bad things. When a neuron fires, we get some additional BDNF. But _how_ does BDNF bring about good things? I’m glad you ask.

#  **Levels of abstraction**

Have you ever wondered what a synapse looks like up close[17](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-17-51607370)? Synapses are too small to see or even to image properly[18](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-18-51607370), but Dr. [David Goodsell](https://ccsb.scripps.edu/goodsell/) at the Scripps Research Institute has a great knack for illustrating what we would see if we were to look at a synapse in all its molecular glory:

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F86ed2040-9488-4564-8a0a-2ac4bce555b6_1190x1600.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F86ed2040-9488-4564-8a0a-2ac4bce555b6_1190x1600.png)This depicts a neuromuscular junction synapse at a magnification of x1,000,000. At this magnification, individual atoms are too small to resolve (about the size of a grain of salt). The axon terminal is at the top, and the muscle cell is at the bottom. A more detailed description is included with the [source](https://iubmb.onlinelibrary.wiley.com/doi/10.1002/bmb.20297).

This picture is pretty and gives you (maybe) a sense of awe at the mind-boggling complexity that lurks just a few levels below. It might help you understand [how small an acetylcholine molecule is](https://www.ncbi.nlm.nih.gov/books/NBK11143/#:~:text=About%2010%2C000%20molecules%20of%20ACh,by%20a%20vesicular%20ACh%20transporter.) compared to the vesicle that carries it. Or why neurotransmitters released into the synaptic cleft [might get lost on the way to the postsynapse](https://www.nature.com/articles/srep42022). Or just for [how incredibly ](https://www.youtube.com/watch?v=F37kuXObIBU&ab_channel=TEDxTalks)_[dense](https://www.youtube.com/watch?v=F37kuXObIBU&ab_channel=TEDxTalks)_[ the brain is](https://www.youtube.com/watch?v=F37kuXObIBU&ab_channel=TEDxTalks).

But beyond intuitions, the picture cannot carry you that much further. If we want to _understand_[19](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-19-51607370) what happens at a synapse, we need to abstract away details.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa288ca2d-485b-4f62-967d-b8d2b0bd9f4b_600x750.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa288ca2d-485b-4f62-967d-b8d2b0bd9f4b_600x750.png)In the words of Scott Alexander: “ _[People try to make this seem simple by displaying it as a system of billiard balls and tubes in a cute cartoon, but don’t be fooled – no human being has ever remembered any of it for more than two seconds.](https://slatestarcodex.com/2017/06/13/what-is-depression-anyway-the-synapse-hypothesis/#:~:text=People%20try%20to%20make%20this%20seem%20simple%20by%20displaying%20it%20as%20a%20system%20of%20billiard%20balls%20and%20tubes%20in%20a%20cute%20cartoon%2C%20but%20don%E2%80%99t%20be%20fooled%20%E2%80%93%20no%20human%20being%20has%20ever%20remembered%20any%20of%20it%20for%20more%20than%20two%20seconds.) ” _[source](https://www.hindawi.com/journals/ijpep/2011/654085/).

Now, this is… different. Certainly a lot less pretty. And importantly, we have exchanged the territory for a map[20](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-20-51607370). We lost information about spatial scales and how _dense_ everything is. But we have gained arrows! Suppose we trust the authors[21](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-21-51607370) to have done their literature research properly. In that case, we might now feel compelled to make statements like “ _Extracellular BDNF binds to the TrkB receptor and triggers the PLC-γ-mediated activation of IP3, which in turn contributes to intracellular calcium release. An increase in postsynaptic calcium triggers exocytosis of BDNF into the synaptic cleft, where it binds to pre-and postsynaptic TrkB receptors, kicking off further signaling cascades_ ”. And just like that, we find ourselves one step closer to speaking p̴͓̂͘á̴̻͌s̶̻̗͋͑ṯ̸̹̈́̌à̶̳ fluently ourselves. 

Don’t worry if you didn’t get that summary of BDNF action; I don’t get it either. A picture at this level might help us if we want to **roughly predict**[22](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-22-51607370) how a defect in one thing might affect other things - we can just follow the arrows. And it might inspire us to hunt for new connections between things that we didn’t know about - can we add an arrow somewhere?

But this level of abstraction still has severe limitations: Unless we have some _real_ expertise in molecular neuroscience, we are essentially operating at the level of [Ţ̷̣̙̖̠͊͑͌͌̈̚l̵̻̯̪͇͙̓̀̐d̶̖̊́t̶̰̄̎̌̈͛ͅs̵͎͇͍̮͑̎́̌̆i̶̱̙͕̰͎̍̅a̸̩͕̐͝ͅw̶̝̘̗͕̰̉̎̃s̵̹̀͘d̸̝͊̽́̎́i̴͇͈̝̭̝̝͋̍̿̐͝,](https://www.lesswrong.com/posts/f4txACqDWithRi7hs/occam-s-razor#:~:text=whole%20sentence%20as%20%E2%80%9C-,Tldtsiawsdi,-!%E2%80%9D%20so%20that%20the) recounting [magic password](https://www.lesswrong.com/posts/NMoLJuDJEms7Ku9XS/guessing-the-teacher-s-password) that lets us pass a test. What does any of it _mean_[23](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-23-51607370)? Taken in isolation, “PLC-γ-mediated activation of IP3” are prototypical “[words of false comprehension](https://www.hpmor.com/chapter/109#:~:text=%22-,The,-runes%20say%2C%20noitilov)”, disjoint from anything we can mentally operate on. If we want to understand more, we’ll have to zoom out further[24](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-24-51607370),[25](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-25-51607370).

# Less is More?

To simplify the tangle of arrows and boxes from the picture in the previous section, we can do: 1. **clustering** , 2. **summarizing** , and 3. **unrolling in time**. 

  1. **[Clustering](https://en.wikipedia.org/wiki/Cluster_analysis)** requires identifying components that are similar to each other and different from all the other things. For example, we might decide to lump together voltage-gated calcium channels and NMDA channels because they both lead to an influx of calcium[26](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-26-51607370).

  2.  **[Summarizing](https://en.wikipedia.org/wiki/Dimensionality_reduction) **requires lowering the system's dimensionality by [reducing](https://en.wikipedia.org/wiki/Summary_statistics) multiple items into a single item or identifying a [prototypical](https://en.wikipedia.org/wiki/Prototype_theory) stand-in for the cluster.

  3.  **[Unrolling in time](https://en.wikipedia.org/wiki/Backpropagation_through_time)** is a kind of clustering & reducing in _time_. Which processes happen (mostly) simultaneously and before/after others? How much temporal overlap can we ignore before the picture gets misleading[27](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-27-51607370)?




[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc36bd088-9c2d-4035-a435-f76b1196bc72_3621x1545.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc36bd088-9c2d-4035-a435-f76b1196bc72_3621x1545.png)Presynaptic activation leads to the release of glutamate into the synaptic cleft. Glutamate binds to postsynaptic receptors and triggers an influx of calcium. Calcium, in turn, brings about the release of BDNF into the synaptic cleft. BDNF binds to pre- and postsynaptic receptors, which prompts an increase in presynaptic glutamate stores and the insertion of additional postsynaptic glutamate receptors. Adapted from [source](https://link.springer.com/article/10.1007/s13295-014-0053-9).

While the story we can tell about the picture (see the caption) gets a lot more concise, abstraction also means losing information. If I’d only shown you this version of the picture, you wouldn’t know that PLC-γ is involved[28](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-28-51607370). But abstracting to this level of resolution gives us two powerful new actions:

  1. We can start to think about **[purpose](https://en.wiktionary.org/wiki/ulterior)**. When we follow the progression of steps, we realize that they culminate into more presynaptic glutamate and more postsynaptic receptors. Both of those things enable [more reliable signaling and stronger activation of the postsynapse](https://en.wikipedia.org/wiki/Long-term_potentiation). The BDNF signaling cascade depicted above leads to the [strengthening of a synapse](https://www.pnas.org/doi/10.1073/pnas.0711863105).

  2. We can start **[charting negative idea space](http://www.hpmor.com/chapter/8)**. The degrees of freedom in the picture are sufficiently reduced that we can look at the flow of information and wonder about “how things could be different”. And we can start to be [confused without being overwhelmed](https://www.lesswrong.com/posts/5JDkW4MYXit2CquLs/your-strength-as-a-rationalist).




Here are three examples of what I mean by “charting negative idea space”: 

  1. When I saw (a variation) of this picture for the first time, it made sense that there should be BDNF receptors in the _pre_ synapse. Diffusion of BDNF from the _post_ synapse back to the _pre_ synapse could be a kind of “read receipt”, indicating that signal transmission went fine[29](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-29-51607370). But why would there also be BDNF receptors in the _post_ synapse? The postsynapse already “ _knows_ ” that it just released BDNF. Why would you _build_ something like this?

  2. And, if BDNF is just overall awesome and stops your neurons from dying, why doesn’t your brain push the “more BDNF” button _all the time_? There must be trade-offs. Perhaps you don’t want _way_ _too_ _much_ BDNF. Still, if BDNF has all the magical abilities from the introduction (better hair, fantastic baritone voice, the ability to jump 3 meters high), then evolution ought to have figured out a way to crank up the natural production of BDNF.

  3. And finally: how does this relate to _everything else_? What about the [A̷͈̐̈́̆̍̋̃͑͘ṛ̸̨̨̻̹̖̙͖̺̱̋̇̈̈́̈́͆̈́̈̒̆̀̾̕͜c̴̢̢̢̜̪͖͇̥̲̟̱̪͓͚͊̅̈́̓́̒̑̑̌͐͂͗̚͘͠-signaling](https://www.science.org/doi/10.1126/science.aao0862#:~:text=OPEN%20IN%20VIEWER-,Arc,-%2C%20the%20protein%20encoded), [c̵̫̦̙̤͓̞̮̥͈̱̻͈̖͙̥̾͋͗́͛͆̇̏̏͘͝a̶̳̱̜̻̝̙̭̽̍͋̿̊̅͋͋̾̕͜͠ḷ̸̢̨̛̭̜͓̜͈̈̈́̋̏̀͑̅̇̈́̄̂̕͜ͅç̴̨̡̪͈͉̜̋̓̈́͌͘͝ͅḯ̶̫̬̝͑͐̌͑̓͐̓̋̈̓͆͘͠͝ͅn̸̥̬͉̯̙̻͍͙̪̲͚̭̮̎͌͝e̴̜̼̦̯̓̏̈́̾̐̃̄̇͝ù̶̮̹̺̤̫̰̰̝͕̣̘͉̜͌̾͜͝ȑ̶̪̣̙͇̣̻͔̪̘̙̎̉̂́̄̈́͌̋͑̽̈́̑̂͝í̵̫͆̇͋͑͘͝n̷̹̰͓̤̗̱̲̗͖̩̑̌-signaling,](https://www.cell.com/article/S2211-1247\(14\)01045-6/fulltext#:~:text=requires%20activation%20of-,calcineurin,-%2C%20IP3Rs%2C%20and%20mGluRs) [P̶̧̡͔̞͉̜̜̼̩͕̘̙̰͍͊̎̾̏̆͗́̕̕ͅR̶̛̛̯̍́̊̈̅̐̔̍͋̌͘P̸͖̗̹̩͂̂͌̌͒̃̎͆̉̓͊̈́̕͠͝-signaling,](https://www.nature.com/articles/nrn2963#:~:text=term%20memory%20if-,PRPs,-are%20made%20available) and of course [C̴͉͙̘̞̏͂̌́̅͊̇̄͌̂̿͐́ȁ̸̡̧̛̞͍̟̖̗͖̜͓͚̃́̑́͆̅̚͠M̴̡̩̙͛̈́̇̄̉̏͑̈̓̾̍̍̚̕͠K̷̢͔͇̭̘͈̼͚͉̭̦̖̥̩̅͌Į̶̼̼̫̀̐̂̅̊̇̈̈́̍̽͊̀̎̔͘I̴̡̼̠͍̹̭̦̓̆̈̅͊̄̓̊͆-signaling](https://pubmed.ncbi.nlm.nih.gov/24484698/#:~:text=the%20activation%20of-,CaMKII,-in%20dendritic%20spines)? Are all of those signaling cascades just _wrong_ or _irrelevant_?




Resolving this type of confusion is not straightforward. Here are some possible non-answers:

  1. Sometimes the error is in the map - perhaps the experiments that indicate BDNF receptors in the postsynapse are just bad[30](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-30-51607370)?

  2. Sometimes you don’t look at the map carefully enough, and the confusion comes from poor understanding.

  3. Sometimes there is no answer. Evolution is just [not always great at planning](https://en.wikipedia.org/wiki/Retina#Inverted_versus_non-inverted_retina). Things are complicated.




I’m still unsure what the answers to these questions are, and I have a good bit of probability mass on the three non-answers above[31](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-31-51607370). There is, however, [another way of looking at this](https://www.youtube.com/watch?t=966&v=1bSPNboKCzM&feature=youtu.be).

# Neurotrophin balance is all you need

In a shocking plot twist, the evil twin proBDNF reappears on the scene, resolving the dramatic tension rising throughout the preceding sections[32](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-32-51607370). Before we can witness the spectacle, here is an epistemic warning sign:

Text within this block will maintain its original spacing when published
    
    
     _The content of the preceding sections is perhaps simplified in some parts, but I’m pretty confident that none of it contradicts the consensus view on BDNF. But while the concentration of BDNF is low and experiments are difficult, the **[concentration of proBDNF is](https://www.nature.com/articles/nn0209-105#:~:text=by%20these%20cells.-,Thus,-%2C%20Matsumoto%20et%20al)**[ ](https://www.nature.com/articles/nn0209-105#:~:text=by%20these%20cells.-,Thus,-%2C%20Matsumoto%20et%20al)**[very low](https://www.nature.com/articles/nn0209-105#:~:text=by%20these%20cells.-,Thus,-%2C%20Matsumoto%20et%20al)**[and ](https://www.nature.com/articles/nn0209-105#:~:text=by%20these%20cells.-,Thus,-%2C%20Matsumoto%20et%20al)**[experiments are very difficult](https://www.nature.com/articles/nn0209-105#:~:text=by%20these%20cells.-,Thus,-%2C%20Matsumoto%20et%20al)**. While there haven’t been any papers arguing against the importance of proBDNF in the last decade, most of the recent supporting literature comes from a few research groups, and I’ve met some people at conferences who were skeptical of the whole story. So beware and mark this section with the appropriate amount of uncertainty._

As proBDNF and BDNF are packed together into the same vesicle, we might expect them to be released into the synaptic cleft together. And indeed, there is [some](https://www.pnas.org/doi/10.1073/pnas.1207767109) [evidence](https://pubmed.ncbi.nlm.nih.gov/19147841/) of proBDNF in the synaptic cleft following neural activity. So effectively, neural activity tells a synapse **both** to get stronger (BDNF signaling) and to get weaker (proBDNF signaling). It’s like [holding the gas and brake pedal at once.](https://youtu.be/K_DcOWDOETo?t=218)

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa54e00a7-3d62-41a8-b016-f48264d54a9a_320x136.gif)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa54e00a7-3d62-41a8-b016-f48264d54a9a_320x136.gif)

What is going on here? Has the brain lost its mind[33](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-33-51607370)? Well, maybe. But an alternative explanation comes from the fact that **[the processing of proBDNF into BDNF can also happen in extracellular space](https://pubmed.ncbi.nlm.nih.gov/19147841/)**. If we were to anthropomorphize the situation, we might say: The postsynapse makes a _best guess_ at whether it should become stronger or weaker and releases proBDNF and BDNF into the synaptic cleft in accordance. Then, the **presynapse** makes corrections to this best guess by **differentially processing some amount of proBDNF into BDNF**.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ffc3e6cb2-c94b-4032-acc3-f4de05d9b97e_763x355.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ffc3e6cb2-c94b-4032-acc3-f4de05d9b97e_763x355.png)Top: Interactions between neurotrophins (BDNF and proBDNF), neurotrophin receptors (TrkB and P75NTR), and cleaving protease (MMP9). Bottom: Outcome of synaptic stimulation where two synapses separated by a distance d innervate the same dendrite: I. The left synapse is stimulated with a burst of action potentials. II. Presynaptic activation causes the local release of MMP9 (yellow). III. Signal transduction into the postsynapse results in the spatially extended calcium influx (purple shading). Calcium triggers the exocytosis of proBDNF (orange) and BDNF (green) into extracellular space. IV. MMP9 differentially cleaves proBDNF into BDNF at the stimulated synapse. V. Repeating this pattern of stimulation potentiates the stimulated synapse and depresses the unstimulated synapse (arrows). [source](https://www.nature.com/articles/s41467-021-23557-3#Fig1)

MMP9 here is just a type of cleaving enzyme (represented by a scissor in the illustration in an earlier section). Notice how, even though **both** synapses initially released proBDNF and BDNF in an equal amount, only **one** synapse gets larger. The important difference is that only one of the two synapses has the cleaving enzyme.

This particular [framing of neurotrophin interaction](http://www.bio.brandeis.edu/classes/nbio143/Papers/Neurotrophins/Lu05.pdf) is fascinating to me, and I’ve spent some portion of my doctoral research thinking about how far we can push this interplay of activity and molecular balance to [establish structure in the developing brain](https://www.nature.com/articles/s41467-021-23557-3#Fig1)[34](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-34-51607370). In particular, this framing provides several elegant answers to the questions I have raised throughout this essay:

  1.  **Q** : Why would there also be BDNF receptors in the postsynapse? **A** : Because sending out proBDNF and BDNF into the synaptic cleft is not a “read receipt”, it’s a probe supposed to gather information about the status of the presynapse! Depending on how active the presynapse has been, the [more cleaving enzyme will be around](https://pubmed.ncbi.nlm.nih.gov/23019376/).

  2.  **Q** : If BDNF is overall awesome and makes your brain better, why doesn’t your brain push the “more BDNF” button _all the time_? **A** : Because what you want is not more BDNF _everywhere_ equally (unless you just had a [seizure](https://www.science.org/doi/10.1126/science.2549634) or have a neurodegenerative disease). The brain’s ability to process information comes from the _selective_ connectivity of different neurons. You want BDNF and proBDNF in an appropriate balance.

  3.  **Q** : And finally: how does this relate to _all the other signaling pathways_ we know? **A** : The interplay of proBDNF and BDNF is responsible for setting up the groundwork - making sure that the appropriate neurons and synapses survive. But once the groundwork is established, the pair fades into the background and leaves the stage for fancier actors to refine and tune. Indeed, expression of BDNF and proBDNF peaks in the second postnatal week and shifts into a BDNF dominated regime afterward.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fbc323ae3-091c-4dc4-840a-bde2ca935de2_274x302.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fbc323ae3-091c-4dc4-840a-bde2ca935de2_274x302.png)Hippocampal lysates from mice of the indicated genotype and ages were subjected to immunoprecipitation/western blot analysis for BDNF isoforms. [source](https://www.nature.com/articles/nn.2244/figures/2)




I’m pretty satisfied with these answers, but I want to stress again that a lot of stuff in this section is [conjecture](https://universalprior.substack.com/p/on-not-reading-papers?s=w#:~:text=a%20paper%20adds.-,Schematic,-of%20%E2%80%9Cthe%20delta). “Neurotrophin balance is all you need” has explanatory power and meshes well with [known themes in biology,](https://en.wikipedia.org/wiki/Homeostasis) but it’s important to keep in mind that:

> The ultimate arbiter of truth is experiment, not the comfort one derives from one's a priori beliefs, nor the beauty or elegance one ascribes to one's theoretical models. [Lawrence M. Krauss](https://www.azquotes.com/quote/702191)

So let’s wait and see what the universe says when we ask it.

# Closing thoughts

We’ve learned a bit about the beautiful language I call p̴͓̂͘á̴̻͌s̶̻̗͋͑ṯ̸̹̈́̌à̶̳, we’ve looked at pretty pictures, and we’ve closely observed what we do when we abstract away things. What more could we wish for on a slow Sunday afternoon?

We could inject ourselves into a debate that has raged in the LessWrong comment section for [the last few weeks](https://www.lesswrong.com/posts/sbcmACvB6DqYXYidL/counter-theses-on-sleep?commentId=Ehcng2LgeDuWmgQS3) about whether sleep deprivation might increase ([Alexey’s position](https://www.lesswrong.com/posts/HvcZmKS43SLCbJvRb/theses-on-sleep#:~:text=Sleep%20deprivation%20appears%20to%20increase%20BDNF)) or decrease ([Natália’s position](https://www.lesswrong.com/posts/sbcmACvB6DqYXYidL/counter-theses-on-sleep#:~:text=is%20not%20linear.-,Chronic%20sleep%20deprivation%20might%20be%20associated%20with%20*decreased*%20BDNF%20expression,-%2C%20as%20shown%20by)) the amount of BDNF in your brain. The two have been pushing back and forth on this point and are now stuck drawing causal arrows between depression ←→ more sleep ←→ more/less BDNF. What can we contribute to this?

  1. According to the “neurotrophin balance is all you need” perspective, the point is moot. Unless you have some reason to believe that you have too little BDNF by default, you probably don’t even _want_ more BDNF. Sleeping more or less doesn’t matter if you don’t know if either affects the balance in the right way.

  2. The papers that Alexey lists ([[1]](https://pubmed.ncbi.nlm.nih.gov/31782101/), [[2]](https://www.sciencedirect.com/science/article/abs/pii/S0924933817324033), [[3]](https://www.nature.com/articles/mp201310), [[4]](https://academic.oup.com/sleep/article/42/Supplement_1/A356/5451256)) are all kind of… “meh”. After reading them semi-carefully, I come out mostly confused. [[3]](https://www.nature.com/articles/mp201310) finds lower BDNF serum levels in people who are tired and fatigued, but they split their sample post-hoc between smokers and non-smokers. In the discussion, they hypothesize that acute sleep deprivation might _increase_ BDNF (they cite [this paper](https://www.nature.com/articles/4001897) which looks a bit more trustworthy) and that prolonged sleep deprivation _decreases_ it. So depending on how much BDNF you want in your brain, you might want to …

  3. … no, but really, those papers are all kind of “meh”. I don’t want to slight any of my fellow researchers (I’m sure they’ve worked hard on this), but the results are not solid enough to conclusively arbitrate _any_ high-level debate. Let’s wait five to ten years and [see if we can get a meta-analysis](https://slatestarcodex.com/2014/12/12/beware-the-man-of-one-study/). And then we can get back to the discussion.




Thus our excursion into the fascinating world of molecular neuroscience comes to an end. If you happen to be an expert in that field, please don’t be upset about the simplifications I made, and please let me know if I got anything wrong. If you are an excited amateur who would like to learn more, please talk to the expert. Anyone else who is ready to move on - consider signing up for my newsletter to get (free!) notifications about new posts I publish straight to your inbox. See you next time (:

Subscribe

[1](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-1-51607370)

Should we tell him? He'll probably find a way to make good use of his remaining time.

[2](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-2-51607370)

At the [Cosyne](https://www.cosyne.org/) 2018 [workshop](https://cosyne-2022.squarespace.com/s/Cosyne2018_workshops_program.pdf) with the title "Manifold-splaining: What the theorist said to the experimentalist".

[3](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-3-51607370)

I want to write a full post on that at some point, but for now, [this](https://slatestarcodex.com/2014/11/21/the-categories-were-made-for-man-not-man-for-the-categories/) and [this](https://www.lesswrong.com/s/SGB7Y5WERh4skwtnb) is great.

[4](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-4-51607370)

 _The answer may surprise you_. Hint: The average neuroscientist does _not_ know what "a topological space with the property that each point has a neighborhood that is homeomorphic to an open subset of n-dimensional Euclidean space" is.

[5](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-5-51607370)

i.e. 75% chance this actually happened

[6](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-6-51607370)

A colleague of mine points out that she reads this as: "[pathway I don't work on] is affected by [protein I don't work on]". I guess that's fine, and perhaps it even represents some optimal trade-off between conciseness and information content for some people. I'm just pointing out that most people don't know that there is no secret society of "initiated people" who can read all those titles and know what they mean.

[7](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-7-51607370)

Or, as I like to call it, bedumpf.

[8](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-8-51607370)

Also, consider telling Hugh Hefner about his death date. He'll probably find a way to make good use of his remaining time.

[9](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-9-51607370)

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F5f274fcf-46e7-42af-b249-cdfe623684d0_1210x268.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F5f274fcf-46e7-42af-b249-cdfe623684d0_1210x268.png)And this one was published only last… wait.. oh no. When did that happen?

[10](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-10-51607370)

I didn’t expect to see such a strong difference (glutamate and serotonin are also kind of important), so perhaps there is some bias in how the SPECTER model computes the embedding of the string “Brain-derived neurotrophic factor (BDNF)”. (Also, this is totally not how the SPECTER model is supposed to be used.) Or perhaps it’s because BDNF is comparatively “new”, i.e. only discovered 40 years ago?

As a “control” condition, I also compute the similarity with the word “socks”, thinking that there [should not be anything in neuroscience](https://neuro-socks.com/) that has a lot of semantic similarity with socks.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fb5c3b8dc-5a97-4db3-8f41-9bf370fdfc11_3407x2275.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fb5c3b8dc-5a97-4db3-8f41-9bf370fdfc11_3407x2275.png)The highest scoring paper is “[Estimating the sensorimotor components of cybersickness](https://www.biorxiv.org/content/10.1101/318758v1)”.

Well, that’s awkward. I forgot about cognitive neuroscience, and it turns out that the link “socks→feet→sensorimotor processing” is strong enough to make a portion of the field light up.

[11](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-11-51607370)

or overly convenient?

[12](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-12-51607370)

Hugh Hefner will have a minor stroke in three years and [reevaluate his lifestyle](https://en.wikipedia.org/wiki/Hugh_Hefner#:~:text=and%20he%20re%2Devaluated%20his%20lifestyle). Perhaps we should stop this time-traveling thing.

[13](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-13-51607370)

You can find an autobiography of Hans Thoenen focused on his scientific work [here](https://www.sfn.org/~/media/SfN/Documents/TheHistoryofNeuroscience/Volume%206/c14.asx).

[14](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-14-51607370)

Soon rebranded as the “Max-Planck Institute of Neurobiology” in 1998.

[15](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-15-51607370)

They wrote the [bottom line first](https://universalprior.substack.com/p/soldiers-scouts-and-albatrosses?s=w).

[16](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-16-51607370)

> “[BDNF was initially purified from pig brain (1), and was found to be expressed at low concentrations; 1.5 kg of starting material was required to purify 1 μg of BDNF.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4530710/#:~:text=BDNF%20was%20initially%20purified%20from%20pig%20brain%20\(1\)%2C%20and%20was%20found%20to%20be%20expressed%20at%20low%20concentrations%3B%201.5%20kg%20of%20starting%20material%20was%20required%20to%20purify%201%20%CE%BCg%20of%20BDNF.)”

[17](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-17-51607370)

Like, for example, right now when I just asked you that question?

[18](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-18-51607370)

Unless you [put them in a diaper and blow them up](https://www.sciencedirect.com/science/article/pii/S096999612100111X).

[19](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-19-51607370)

I mean, not “crappy”-crappy. Actually also kind of cool. But not with a satisfying amount of detail, anyway.

[![Synapsen Dr.Jastrows EM-Atlas](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F92e5fa7c-dc5c-4831-b0ea-82d6951e2b95_225x224.jpeg)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F92e5fa7c-dc5c-4831-b0ea-82d6951e2b95_225x224.jpeg)

[20](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-20-51607370)

Or rather, we have exchanged one map for a less detailed map.

[21](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-21-51607370)

A definition of “understanding” I like is “being able to predict the state at t+1 given the state at t”. Framed like this, understanding can be gradual (above chance performance), you can misunderstand (below chance performance), and you can grok something (near 100% performance).

[22](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-22-51607370)

We probably won’t be able to **predict** what happens **precisely**. The diagram is almost guaranteed to be missing some arrows, and removing an arrow will probably result in the addition of new arrows (the brain is [one big lump of homeostasis)](https://www.nature.com/articles/nrn1949). Any single component you knock out has a good chance of triggering a cascade of compensatory processes.

[23](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-23-51607370)

What _is_ PLC-γ? Uhm, one moment, let me goooooogle. [Ah](https://en.wikipedia.org/wiki/Phosphoinositide_phospholipase_C). It’s “Phosphoinositide phospholipase C,” an[ enzyme tha](https://slatestarcodex.com/2019/05/07/5-httlpr-a-pointed-review/)t plays an important role in signal transduction processes. You’re welcome.

[24](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-24-51607370)

Foolish!

[25](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-25-51607370)

[![Create meme "We need to go deeper \(We need to go deeper , meme DiCaprio ,  inception \)" - Pictures - Meme-arsenal.com](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ffeb43c1a-d8e2-4a51-8b9b-48802cb93c59_500x333.jpeg)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ffeb43c1a-d8e2-4a51-8b9b-48802cb93c59_500x333.jpeg)

[26](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-26-51607370)

(Similarly, PLC-γ, Shc, Grb2, Gab1, … share the property of being written in p̴͓̂͘á̴̻͌s̶̻̗͋͑ṯ̸̹̈́̌à̶̳).

[27](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-27-51607370)

Because effectively, all of those things might happen almost simultaneously.

[28](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-28-51607370)

There is the danger of starting to believe that the [picture is reality](https://en.wikipedia.org/wiki/The_Treachery_of_Images). That’s how you get [unknown unknowns](https://en.wikipedia.org/wiki/There_are_known_knowns).

[29](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-29-51607370)

I’m calling this move the “reversed Olah”.

[30](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-30-51607370)

That’s how [endocannabinoids](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3517813) work, I think.

[31](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-31-51607370)

One simple explanation for why there are receptors in the postsynapse would be that since there is also presynaptic release of BDNF (which I just left out of the simplified schematic), the postsynaptic receptors just detect that.

[32](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-32-51607370)

did you notice?

[33](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-33-51607370)

I wrote this essay mostly to make this one pun.

[34](https://universalprior.substack.com/p/a-brief-excursion-into-molecular#footnote-anchor-34-51607370)

As a good rationalist, I am of course not resting all of my research on this one (potentially shaky) assumption. After setting up a dynamical system of neurotrophin interactions, I immediately demonstrate how [we can reduce it](https://www.nature.com/articles/s41467-021-23557-3#:~:text=to%20each%20other.-,Generalized%20neurotrophin%2Dinspired%20model,-We%20reduced%20the) to a simpler system that is ubiquitous in computational neuroscience.
