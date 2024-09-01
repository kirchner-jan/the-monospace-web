# Serendipitous connections: applying explanations from AI to the brain

## TL;DR: A small shift in perspective (Elhage et al., 2021) helps interpret the ventral stream in the biological brain as the residual stream from ResNets. Experimental support, pre-, and post-dictions.

**Jan 04, 2022**

**Likes:** 2

I recently read the new [Transformers Circuit](https://transformer-circuits.pub/) work by [Elhage et al.](https://transformer-circuits.pub/2021/framework/index.html) at [Anthropic](https://www.anthropic.com/). While I am in no position to judge the importance of the paper for AI, (not that this has ever stopped me from sharing my opinion before) the paper made me connect some ideas from neuroscience that I couldn't connect before. This post is capturing those connections. I’m not sure if all of this is novel[1](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-1-46595289), but it was novel to me! 

If you just want to read the idea, feel free to skip to the section **“Put it together, it just makes sense”**. If you know a bit of neuroscience, but no machine learning, skip to the section **“The Residual”**. If you know a bit of machine learning, but no neuroscience, continue with the sections **“Visionary Hierarchy”** and **“Not the full story”**. If you want _everything_ , just keep reading.

#  **Visionary Hierarchy**

There is this idea floating around since at least [Hubel and Wiesel](https://braintour.harvard.edu/archives/portfolio-items/hubel-and-wiesel) that information processing in the brain is _hierarchical_ , in the sense that there are "lower" and "higher" levels of information processing. I will call this broad idea the “naive hierarchical brain theory” or **[NHBT](https://newhorizonsbandtoronto.ca/)** to indicate that probably very few people believe _exactly_ this. 

**Ventral stream.** One particularly well-studied example of the NHBT is the "[ventral stream](https://neuroscientificallychallenged.com/glossary/ventral-stream)":

> a pathway that carries visual information from the primary visual cortex to the temporal lobe.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F9b02ffb4-e1c2-46ba-9170-397bd0ececae_1280x451.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F9b02ffb4-e1c2-46ba-9170-397bd0ececae_1280x451.png)Hierarchical processing in the ventral stream. ([Manassi et al 2013](https://jov.arvojournals.org/article.aspx?articleid=2193828))

The ventral stream is concerned with extracting properties of objects from the "raw input" from the retina. The NHBT suggests that 

  1. after starting from roundish, simple representations in the lateral geniculate nucleus (LGN), 

  2. we get raw edges at the level of the primary visual cortex (V1), 

  3. we move to flat shapes in the secondary visual cortex (V2), 

  4. we skip V3[2](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-2-46595289), 

  5. and finally on to the quaternary visual cortex (V4) for three-dimensional objects. 




In animals that care about faces, we then move on to the inferior temporal cortex (IT) to represent faces and [Jennifer Aniston, in particular](https://en.wikipedia.org/wiki/Grandmother_cell). Once we've reached this very high-level representation, we might implement certain high-level behavioral strategies like
    
    
    see tiger -> run away

or
    
    
    see grandmother -> don't run away

 **Building neural representations.** A central idea of the NHBT is that higher-level representations are "assembled" from lower-level representations. In particular, the edges detected in the primary visual cortex are assembled from smaller, circular representations in the LGN.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F01ad4451-34eb-4160-ac2f-9bf0b27b47d2_1600x597.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F01ad4451-34eb-4160-ac2f-9bf0b27b47d2_1600x597.png)LGN receptive fields (orange blobs on the left) are pooled from multiple LGN cells to a V1 cell (right) and form a spatially-elongated, edge-selective receptive field (dashed line on the left).

This particular circuit has already been proposed by [Hubel and Wiesel in 1962](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1359523/) and has decent experimental evidence ([Reid and Alonso, 1995](https://pubmed.ncbi.nlm.nih.gov/7477347/);[ Sedigh-Sarvestani et al, 2017](https://www.jneurosci.org/content/37/21/5250)). We also understand a lot about the cortical dynamics of how this comes about from smart electrophysiology experiments ([Lampl et al., 2001](https://www.sciencedirect.com/science/article/pii/S0896627301002781#BIB32)), from looking at all the inputs of pyramidal neurons ([Rossi et al., 2020](https://www.nature.com/articles/s41586-020-2894-4)), and by modeling this to death ([Carandini and Ringach, 1997](https://pubmed.ncbi.nlm.nih.gov/9425519/)[3](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-3-46595289)).

After getting orientation selectivity in V1 there is less agreement about how to get shapes, objects, and faces in the higher-order cortices. My favorite work on this topic comes from [David Marr (1982)](https://homepages.inf.ed.ac.uk/rbf/CVonline/LOCAL_COPIES/GOMES1/marr.html), but I can’t find super strong experimental evidence that teases apart a circuit implementation[4](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-4-46595289).

 **Canonical circuits for assembling representations.** However, perhaps an exact implementation is also not necessary. There is a hand-wavy, standard circuit-level explanation referred to as the "canonical microcircuit" ([Shepherd, 2011](https://www.frontiersin.org/articles/10.3389/fnana.2011.00030/full)). In its simplest[5](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-5-46595289) form, the theory describes the information flow through the six layers of the cortex. Lower levels (f.e. LGN) project to neurons in layer 4, from where the information gets forwarded to layer 2/3[6](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-6-46595289), from there back to layer 5, and from there to the next level in the hierarchy.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F6eba8d0f-7886-47d7-bd5d-57f27398a384_2416x3234.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F6eba8d0f-7886-47d7-bd5d-57f27398a384_2416x3234.png)Schematic of the six layers of the cortex. Eight sample neurons are displayed that receive input from the previous level of the hierarchy (blue), perform recurrent processing (black), and output the result to the next level of the hierarchy (brown). Based on [Kast and Levitt, 2019](https://www.sciencedirect.com/science/article/pii/S0301008218301369).

We can therefore think of layer 4 as the "input" layer and layer 5 as the "output" layer. Cells in layer 2/3 are highly interconnected and form a type of [reservoir for performing computations](https://en.wikipedia.org/wiki/Reservoir_computing). Exactly what kind of computation this circuit performs is still under debate, but there are plenty of ideas floating around (see f.e. [Sadeh and Clopath, 2021](https://www.nature.com/articles/s41583-020-00390-z)). In the NHBT, layer 2/3 might be responsible for combining lower-level representations to form higher-level representations.

 **Strength of the NHBT.** There is also a lot of inspired work at the intersection between machine learning and neuroscience, where the representations that emerge in deep artificial neural networks are compared with those in the brain ([Yamins et al., 2014](https://www.pnas.org/content/111/23/8619.short)). And, almost fully in the land of AI, there is the Circuits work by [Olah et al. (2020)](https://distill.pub/2020/circuits/zoom-in/) that "zooms in" on different levels in a deep convolutional network to identify and interpret the motifs that give the network its umpf[7](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-7-46595289).

The whole story is very appealing for many reasons:

  * It's a simple theory with lots of experimentally-testable predictions.

  * It resonates nicely with the philosophy of [reductionism](https://www.lesswrong.com/posts/tPqQdLCuxanjhoaNs/reductionism).

  * It goes back to Hubel and Wiesel, which is a kind of magic incantation that [bestows credibility](http://jwilson.coe.uga.edu/EMT668/EMAT6680.F99/Challen/proof/proof.html#:~:text=which%20it%20is.-,Proof%20by%20authority,-%3A%20%22Well%2C%20Don%20Knuth).




#  **Not the full story**

I'm not saying that anybody is saying that the NHBT is the full story[8](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-8-46595289). But it's certainly an influential story that a lot of people take as a starting point for building more complicated models. _I'm_ certainly using the NHBT a lot when I need high-level intuitions for how sensory processing works. However, there are also a bunch of puzzle pieces that I've collected over the years that don't fit at all.

 **Redundancies.** I've laid out above how the representation of edges emerges in the primary visual cortex from combining simpler features from the LGN. Well, it turns out that 35% of retinal ganglion cells in the **eye** already encode edges ([Baden et al., 2016](https://www.nature.com/articles/nature16468)).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_lossy/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fb2b0a048-e3ce-4a21-bfec-8cd8664e888a_528x200.gif)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fb2b0a048-e3ce-4a21-bfec-8cd8664e888a_528x200.gif)A schematic of a retinal ganglion cell with bars moving across it to indicate visual flow. Black bars on the side indicate the generated action potentials of the cell. Note how only certain directions of the bars induce substantial action potential firing. Stolen from [Rivlin-Etzion et al., 2012](https://www.youtube.com/watch?v=AC9nSsFd-J4&ab_channel=CellPress).

In fact, researchers are constantly trying to one-up each other in the number of different things that are encoded already at the retina (spatial contrast, color, motion, flicker, fine and coarse textures, absolute light level, ... [Kim et al., 2021](https://www.frontiersin.org/articles/10.3389/fneur.2021.661938/full)). Note that this is _before_ the stimulus has even reached the LGN. In fact, the _same_ mechanism that computes the direction of moving edges in the cortex ([Rossi et al., 2020](https://www.nature.com/articles/s41586-020-2894-4)) has been identified a decade earlier in the retina ([Briggman et al., 2011](https://www.nature.com/articles/nature09818)).

From the NHBT perspective, this is just wasteful! Why would you compute a representation of edges already at the earliest stage of your hierarchy and then do the whole thing _again_ three steps later? Even worse, it turns out that at later stages in the ventral pathway, there are _still_ cells that only encode edges ([Olcese et al., 2013](https://www.sciencedirect.com/science/article/pii/S0896627313005266)). There are ways we can try to explain this away[9](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-9-46595289), but prima facie this is just inconsistent with the naive perspective.

 **Input, Output, all the same.** Also, get this: The supposed "output" layer 5 of the cortex _also_ receives the same input as the "input" layer 4 ([Constantinople and Bruno, 2013](https://www.science.org/doi/abs/10.1126/science.1236425))! If you carefully combine your lower-level representation to a higher-level representation through the layer 2/3 -> layer 4 -> layer 5 pathway, why would you slap on the original, lower-level representation in layer 5 again?

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F8b84ee41-aa4c-4ba9-a037-568c6b4c5f02_2416x3234.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F8b84ee41-aa4c-4ba9-a037-568c6b4c5f02_2416x3234.png)As the schematic before, but now with an additional “shortcut” connection that connects the input directly to the output unit.

There are a lot of other connections[10](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-10-46595289) that are not drawn into this diagram, but none of them are quite as strikingly inconsistent with the NHBT[11](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-11-46595289).

 **The problem with grandma.** Remember that thing about Jennifer Aniston and the grandmother from the previous section? Yeah, turns out that's super controversial to the point where some call it a failure and a myth ([Barwich, 2019](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6822296/)). Where the NHBT suggests that at the top of the hierarchy we find neurons coding for single, complex concepts, the reality in the brain looks different. Instead of a cell-to-concept correspondence, complex concepts are encoded combinatorially ([Quiroga et al., 2008](https://pubmed.ncbi.nlm.nih.gov/18262826/)):

> Neurons might fire selectively in response to highly specific stimuli, such as Halle Berry. But this is not the only stimulus to which they respond. Additionally, sparse coding does not show the encoding of particular stimuli as separate or isolated entities. Instead, it builds a _network of associations_ between familiar items: While a limited number of neurons responded to specific stimuli (say, pictures of Jennifer Aniston), these cells also responded selectively to specific stimuli known from the same context (namely, Lisa Kudrow, the actress starring next to Aniston in the sitcom _Friends_ ). ([Barwich, 2019](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6822296/))

This means, in particular, that it does not make a lot of sense to talk about one particular _stimulus_ that is encoded by a cell in the higher levels of the hierarchy. Cells need to be interpreted in the context of their local network.

While this is not fully inconsistent with the NHBT where representations in the visual cortex are assembled from simpler representations in the thalamus[12](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-12-46595289), it requires an additional component to explain why this scheme does not apply to the highest levels of the hierarchy.

#  **The Residual**

 **Degraded performance in deep networks.** We now dive briefly into the ancient history of machine learning, all the way back into the year 2016[13](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-13-46595289). Up to this point, steady progress in machine learning meant improving relatively "shallow"[14](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-14-46595289) networks (< 25 layers) to squeeze out more and more performance on the ImageNet classification dataset. Intuitively, we might expect deeper networks to perform better (more layers should allow more computation), but this didn't bear out in terms of performance. Making networks deeper actually _degraded_ performance.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F21c0bb17-2324-4a06-b24d-1aa6a946cdea_1600x1244.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F21c0bb17-2324-4a06-b24d-1aa6a946cdea_1600x1244.png)Schematic of the training error as a function of the total number of layers in the network. The blue line indicates what [deep learning theory would predict](https://proceedings.neurips.cc/paper/2017/hash/32cbf687880eb1674a07bf717761dd3a-Abstract.html), the red line indicates what was observed before the invention of ResNets.

The reason for this degradation problem, people [speculated](https://www.fatalerrors.org/a/explain-resnet-in-detail.html#:~:text=there%20is%20a%20problem%20of%20gradient%20vanishing%20or%20exploding%20in%20deep%20network), was that gradients tend to vanish or explode in deeper networks, which makes training unstable.

 **ResNet to the ResCue.** This changed when the ResNet architecture ([He et al., 2016](https://arxiv.org/abs/1512.03385)) was introduced:

> ResNet, short for Residual Networks is a classic neural network used as a backbone for many computer vision tasks. This model was the winner of ImageNet challenge in 2015. The fundamental breakthrough with ResNet was it allowed us to train extremely deep neural networks with 150+layers successfully. ([Dvivedi, 2019](https://towardsdatascience.com/understanding-and-coding-a-resnet-in-keras-446d7ff84d33))

The [central intuition](https://www.fatalerrors.org/a/explain-resnet-in-detail.html) for what they did is straightforward: If your shallow network achieves good performance, adding additional components _should_ just apply the identity transformation and forward that good solution to the output. Since they are not doing that, they must be struggling to "learn" the identity transformation. We can help them by adding a "skip connection" that, by default, implements the identity:

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F605372fa-2372-42dd-96c5-f2a9ddbe8610_1593x1304.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F605372fa-2372-42dd-96c5-f2a9ddbe8610_1593x1304.png)Strongly simplified schematic of the ResNet structure. Computations are typically nonlinear.

This worked pretty well, winning a lot of competitions, and enabling what Gwern calls the "blessing of scale":

> So, the larger the model, the better, if there is enough data & compute to push it past the easy convenient sub-models and into the sub-models which express desirable traits like generalizing, factorizing perception into meaningful latent dimensions, meta-learning tasks based on descriptions, learning causal reasoning & logic, and so on. If the ingredients are there, it’s going to happen. ([Gwern, 2020](https://www.gwern.net/Scaling-hypothesis))

These skip connections also happen to be one of the central components of the transformer architecture ([Vaswani et al., 2017](https://arxiv.org/abs/1706.03762)) that is currently [revolutionizing machine learning](https://threadreaderapp.com/thread/1468370605229547522.html).

 **Residual stream interpretation.** The "vanishing gradient" motivation for using a Resnet is _the_ go-to explanation for when and how skip-connections work. [There is, of course, another way of looking at this.](https://youtu.be/1bSPNboKCzM?t=966) Welcome to the stage, [Elhage et al., 2021](https://transformer-circuits.pub/2021/framework/index.html).

Rather than interpreting the skip connections as a solution to a problem, they evaluate them as an important component of the transformer in its own right. In particular, they observe that the chaining together of multiple skip connections (a "residual stream") opens the door to a range of interesting new computations. They say it much better than I could:

> One of the main features of the high level architecture of a transformer is that each layer adds its results into what we call the “residual stream.” The residual stream is simply the sum of the output of all the previous layers and the original embedding. We generally think of the residual stream as a communication channel, since it doesn't do any processing itself and all layers communicate through it. The residual stream has a deeply linear structure. Every layer performs an arbitrary linear transformation to "read in" information from the residual stream at the start, and performs another arbitrary linear transformation before adding to "write" its output back into the residual stream.[15](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-15-46595289)

Interpreted as a "residual stream", it is clear that later information computed early on is still accessible later in the stream[16](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-16-46595289).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ff950e58f-ba77-4d65-981e-d2b6e5c54bdc_1519x2429.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ff950e58f-ba77-4d65-981e-d2b6e5c54bdc_1519x2429.png)Schematic illustrating same situation as in the previous figure, but now with the skip connections chained together and labeled “residual stream”. The thick orange band indicates that the residual stream has a limited, but high-dimensional bandwidth.

In addition, there is a kind of "[memory management](https://en.wikipedia.org/wiki/Turing_machine)" that becomes possible through the residual stream: computational units later in the stream can "pick up and continue" the output of previous units, and then copy, modify, delete, or merge them. Presented like this, it is clear that the residual stream might be more than just a "solution to the problem of degrading performance", and that the residual stream is intimately involved in the complex calculations performed by deep networks.

#  **Put it together, it just makes sense**

If you've read the previous two sections back-to-back you can probably already predict where I'm going: Perhaps we shouldn't be thinking of the steps in the ventral stream as successive levels of a _hierarchy_ , but instead, we should think of them as reading from and writing into a _residual stream_. Instead of _levels_ in the hierarchy, we think of _stations_ in the stream. Instead of _merging_ representations, we _operate_ on portions of the stream. It’s just a small shift in perspective, but we can get a lot of mileage from it.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fe88944b8-be61-4316-8958-f8fc5129b31d_1600x1266.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fe88944b8-be61-4316-8958-f8fc5129b31d_1600x1266.png)Ventral stream illustrated with a residual stream.

 **Model[postdictions](https://en.wikipedia.org/wiki/Postdiction).** Under this model,

  1. the original input ought to be added to the computed output, consistent with what we know about the direct thalamocortical input onto layer 5 of the cortex ([Constantinople and Bruno, 2013](https://www.science.org/doi/abs/10.1126/science.1236425)). This also happens to be one of the hallmark features of the "Dendritic Gated Networks" recently proposed by [Sezener et al. (2020)](https://www.biorxiv.org/content/10.1101/2021.03.10.434756v1.full).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F37d0f407-3f9a-4b57-93db-30e934cf0199_2073x2778.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F37d0f407-3f9a-4b57-93db-30e934cf0199_2073x2778.png)As schematic before, but with input and output merged into a residual stream.

  2. representations would still _look_ somewhat hierarchical: as later processing steps of the stream receive the output of earlier steps as input, complexity[17](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-17-46595289) of the representation will increase at later stages in the stream. However, the hierarchy is a lot more flexible, and can dynamically route intermediate outputs from all levels to the end of the stream.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F8fa5d644-ca81-4490-878f-a336569d59e7_1625x1334.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F8fa5d644-ca81-4490-878f-a336569d59e7_1625x1334.png)Schematic illustrating that later stations in the stream might still have access to all previously computed intermediate results.

  3. computation is highly flexible. Depending on the input statistics, the same cell might be recruited in a wide range of roles.




 **From receptive fields to sparse coding.** Computations early in the stream mostly depend on the input. Computations later in the stream depend on both the input and on computations earlier in the stream. As a consequence, a cell early in the stream has a reliable "receptive field", while cells later in the stream do not strongly bind to the input and can only be interpreted as a sparse code ([Quiroga et al., 2008](https://pubmed.ncbi.nlm.nih.gov/18262826/)).

 **(Towards?) Turing-complete computations.** The content of the residual stream might represent a type of flexible memory with contents that can be read, modified, deleted, or merged at different stages in the stream. We might expect this to allow for pretty complex computations, probably bounded below by the expressive power of the transformer architecture.

 **Representation overloading.** This also happens to mesh extremely well with a recent proposal for biologically-plausible backpropagation from [Sezener et al. (2020)](https://www.biorxiv.org/content/10.1101/2021.03.10.434756v1.full):

> [External input to a neuron is] used for gating the weights: each neuron has a bank of weights at its disposal, and the external input determines which one is used. For example, a neuron might use one set of weights when the visual input contains motion cues predominantly to the right; another set of weights when it contains motion cues predominantly to the left; and yet another when there are no motion cues at all.

 **Model predictions.** There are also experimentally-testable predictions[18](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-18-46595289):

  * When task-relevant, robust representations of simple stimuli (f.e. edges) should be found all along layer 5 of the ventral stream.

  * Variability of neural activity should increase not only in proportion to variability in the _immediately_ preceding unit but in proportion to variability in _all_ preceding units.

  * We might expect some degree of dynamic deleting and/or editing in layer 5, where a portion of incoming thalamocortical inputs are partially or fully canceled out by computed inhibitory input.




These shouldn’t even be too difficult to test ([compared to, like, calcium imaging of dendrites in freely behaving animals](https://www.cell.com/neuron/pdf/S0896-6273\(19\)30889-X.pdf)).

 **Model limitations.** While I'd argue that the "residual stream" interpretation explains strictly more about biology than the NHBT interpretation, there are still a bunch more puzzle pieces[19](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-19-46595289).

But at least there are some interesting hints for how to continue:

  1. Which principles govern the computations within layer 2/3? I don't believe that the cortical microcircuit implements the transformer architecture. But it also doesn't have to - a "traditional" recurrent neural network should be able to do the same things as the transformer. It just cannot be trained as efficiently.

  2. How do we train the network to do "useful" computations? The specter of the "missing teaching signal" in the biological brain has prompted a lot of creative proposals from the neuroscience community over the decades[20](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-20-46595289). But the recent astonishing progress with "[self-supervised](https://en.wikipedia.org/wiki/Self-supervised_learning)" (i.e. autoregressive) learning shows that very capable networks can emerge without an external teaching signal. Instead of the backpropagation algorithm (which is not well-suited for biological networks), the brain might implement the next best approximation ([Sezener et al. 2020](https://www.biorxiv.org/content/10.1101/2021.03.10.434756v1.full); [Sacramento et al., 2018](https://proceedings.neurips.cc/paper/2018/hash/1dc3a89d0d440ba31729b0ba74b93a33-Abstract.html))

  3. What about inhibition? [Sezener et al. (2020)](https://www.biorxiv.org/content/10.1101/2021.03.10.434756v1.full) again have an answer[21](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-21-46595289): Inhibition might be responsible for gating on or off certain branches of the dendrites, effectively modulating the projection of the residual stream.




And what about [calcium waves in astrocytes](https://www.nature.com/articles/nn.4201)? And [axo-axonic synapses](https://en.wikipedia.org/wiki/Axo-axonic_synapse)? And the fact that mice are [basically blind](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5909038/)? And ...? Phew, great questions. I don't know man. One step at a time.

If you want to subscribe (it’s easy, free, and will stay free), click the button <3

Subscribe

[1](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-1-46595289)

I fully expect someone to tell me: Oh, that’s the “The-Brain-Is-A-Residual-Stream” theory from Smith et al. 1986.

[2](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-2-46595289)

Look, the[ guy who came up with these areas in 1909](https://en.wikipedia.org/wiki/Brodmann_area) didn't actually know what they were good for, so let’s cut him some slack.

[3](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-3-46595289)

And a lot more. Even your's truly has a model that can do this! ([Kirchner and Gjorgjieva, 2021](https://www.nature.com/articles/s41467-021-23557-3)).

[4](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-4-46595289)

This looks relevant however,[ Verhoef et al., 2012](https://www.cell.com/neuron/fulltext/S0896-6273%2811%2900995-0).

[5](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-5-46595289)

i.e. only reasonably useful,

[6](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-6-46595289)

If you wonder why there is no mention of layer 1 or layer 6, and why layers 2 and 3 are lumped together - that is _also_ the fault of[ that guy in 1909](https://en.wikipedia.org/wiki/Cerebral_cortex#:~:text=The%20work%20of%20Korbinian%20Brodmann%20%281909%29%20established%20that%20the%20mammalian%20neocortex%20is%20consistently%20divided%20into%20six%20layers)...

[7](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-7-46595289)

[This](https://www.urbandictionary.com/define.php?term=umpf#:~:text=Power%2C%20Strength%2C%20Energy%2C%20Might%2C%20Force%2C%20Potency%2C%20Ability%2C%20Excite) one, not[ this](https://www.urbandictionary.com/define.php?term=umpf#:~:text=A%20word%20that%20represents%20the%20sound%20made%20when%20one%20craves%20sexual%20intercourse.) one.

[8](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-8-46595289)

I'd perhaps argue that the situation is even worse and that people don't have a theory concrete enough to be wrong, but that would just bog us down at this point.

[9](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-9-46595289)

Maybe the cortex is just doing this _better_ than the retina? Perhaps the computation in the retina is for rapidly filtering out useless input that doesn't even need to be sent to the cortex? After all, there is a bottleneck (the LGN has much fewer neurons than the retina or the primary visual cortex) that the information needs to be passed through.

[10](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-10-46595289)

My favorite resource comes from the Allen Brain Institute[ here](https://portal.brain-map.org/explore/models/mv1-all-layers).

[11](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-11-46595289)

In particular, each transmission from one cell to another induces a temporal delay of a few milliseconds. This might be negligible for most macroscopic behavior, but for neural circuits [timing matters](http://www.scholarpedia.org/article/Spike-timing_dependent_plasticity). Directly feeding the input into the output messes this up, big time.

[12](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-12-46595289)

It could be that at lower levels in the hierarchy, the receptive field of a cell can still be defined, and only at higher levels, it falls apart.

[13](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-13-46595289)

The field is moving _fast_.

[14](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-14-46595289)

People at the time probably did not think these networks were "shallow".

[15](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-15-46595289)

Something interesting happened to my mind, where I now cannot un-see this interpretation anymore. I feel convinced that something about the old "vanishing gradient" explanation was unsatisfactory, but that I couldn't put my finger on it. Hindsight is, of course, 20/20.

[16](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-16-46595289)

As long as the information is not overwritten.

[17](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-17-46595289)

As measured by the degree of processing of the information.

[18](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-18-46595289)

Or perhaps post-dictions, those claims seem plausible enough that I might have read them before.

[19](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-19-46595289)

Of course, this is neuroscience after all.

[20](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-20-46595289)

Although most proposals I've encountered so far have been begging the question, just hiding the teaching signal in ever-more-clever places. Self-organizing networks are the notable exception ([Kaschube et al., 2010](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3138194/)).

[21](https://universalprior.substack.com/p/serendipitous-connections-applying#footnote-anchor-21-46595289)

The paper is not without flaws (the biological evidence is weak, the SARCOS dataset is contaminated to the point of non-usability, the results don't quite deliver what they promise), but it has _so many_ great ideas.
