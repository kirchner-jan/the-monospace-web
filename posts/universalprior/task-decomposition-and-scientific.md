# Task Decomposition And Scientific Inquiry

## TL;DR: A curious asymmetry between making and criticizing, the scientific method as an approach to task decomposition, and a less-than-half-baked idea about syntax and semantics of task decomposition.

**Jan 31, 2022**

**Likes:** 2

_Meta: As this post is all about summarization (and since I value your time!), I’m experimenting with putting a_ **`one sentence`** **`summary`** _ **``** at the beginning of each paragraph. Let me know if you hate this in the comments._

#  **Astonishing Asymmetries**

 **`There is a curious asymmetry in how difficult it is to make something versus how easy it is to evaluate it.`** After working on an idea for a couple of days, I usually run my work by a friend or[1](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-1-47977244) colleague once I _think_ I have found a solution. More often than not, said colleagues manage to find a flaw in my argument in 5 minutes. While I can't deny that some of them are smarter than me, they are _not_ smart enough to do the same amount of mental work in 5 minutes that took me several days. They are no [clones of John von Neumann](https://fantasticanachronism.com/2021/03/23/two-paths-to-the-future/)[2](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-2-47977244).

 **`We might leverage that asymmetry for AI Alignment.`** This asymmetry pops up all over the place, sometimes making life [better](https://www.ijert.org/pvs-np-problem-and-its-application-in-public-key-cryptography), sometimes making it [worse](https://slatestarcodex.com/2017/03/24/guided-by-the-beauty-of-our-weapons/), and sometimes [driving computer scientists into madness](https://blog.codinghorror.com/the-girl-who-proved-p-np/). Nassim Taleb has written [several](https://en.wikipedia.org/wiki/Antifragile_%28book%29)[ books](https://en.wikipedia.org/wiki/Skin_in_the_Game_%28book%29) about it. And it also sits at the heart of a specific [family](https://openai.com/blog/debate/) of [proposals](https://ai-alignment.com/iterated-distillation-and-amplification-157debfd1616) for how we might control an artificial intelligence that is [smarter than us](https://arbital.greaterwrong.com/p/Vinge_principle?l=1c0): Perhaps we can set the AI up in a way that we have the asymmetry on our side? Then we might be able to steer the AI (even though it is a lot smarter than us) and use its smarts to achieve a positive outcome for all of humanity. That would be great.

 **`For this strategy to work we need to`** _ **`decompose`**_ **`complex tasks.`** [But it turns out that](https://www.lesswrong.com/s/xezt7HYfpWR6nwp7Z/p/vhfATmAoJcN8RqGg6) a critical property for these proposals to work out is that we can _decompose_ tasks into simpler subtasks. It is an empirical question whether this is possible in general, and some [initial results](https://ought.org/updates/2020-01-11-arguments) looked a bit discouraging[3](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-3-47977244). But there is also more recent research on "[Recursively Summarizing Books with Human Feedback](https://arxiv.org/abs/2109.10862)" that looks more encouraging[4](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-4-47977244). What is this proposal, and why is it encouraging? I'm glad you ask.

#  **Recursive Raillery**

 **`Summarizing books is an instructive test case.`** Reading an entire book and summarizing its content is [hard work and costs time](https://www.cold-takes.com/reading-books-vs-engaging-with-them/), so it would be fantastic if we could get someone else to do it for us. But how can we trust someone to do a good job at the summary? How do we know they are not leaving out important things or that the resulting summary is completely decoupled from the original text[5](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-5-47977244)?

 **`There is a natural, recursive strategy for summarization.`** Fortunately, summarizing text can be broken down into simpler subtasks. To generate a summary of a book, generate a summary of all the chapters and then combine those. To generate a summary of a chapter, generate a summary of all the paragraphs and then combine those. To generate a summary of a paragraph, take all the sentences and smush them together hard until they look summary-y[6](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-6-47977244).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fb299a97a-62de-46da-a733-46c787f49016_1600x597.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fb299a97a-62de-46da-a733-46c787f49016_1600x597.png) **Figure 1.** **(a)** The story “Alice in Wonderland” is split into six parts. The orange dots represent passages of approximately equal length from the source text. Illustration in the background from [John Tenniel](https://en.wikipedia.org/wiki/Illustrators_of_Alice%27s_Adventures_in_Wonderland#:~:text=The%20illustrator%20for%20the%20original,best%20known%20illustrations%20ever%20published.). **(b)**[Recursive summarization of Alice in Wonderland from OpenAI](https://openaipublic.blob.core.windows.net/recursive-book-summ/website/index.html?data_id=175b%2F4&dataset=gutenberg#/gutenberg).

 **`Once decomposed, each subtask is easier to verify.`** The aforementioned asymmetry shows up at each summarization step, which is cumbersome to do but relatively easy to _verify_ : it's not too much work to read a few sentences and to see if the summary is reasonably accurate. The hope is now that perhaps we can amplify the asymmetry and find some _scalable_ method for verifying one step of summarization. If we're able to verify (or steer) the steps at scale, then every sub-task will be solved accurately, and also the summary of the entire book ends up being accurate.

 **`Reward modeling is a scalable technique for verification.`** "[Recursively Summarizing Books with Human Feedback](https://arxiv.org/abs/2109.10862)" demonstrates that "[reward modeling](https://arxiv.org/abs/1811.07871)" can do the trick. We can capture human preferences for one summary over another in a reward model, serving as a target for the summarization process. The result is a collection of pretty good summaries of [hundreds of books](https://openaipublic.blob.core.windows.net/recursive-book-summ/website/index.html?data_id=175b%2F4&dataset=gutenberg#/gutenberg), produced by repeatedly breaking down the summarization task into simpler subtasks. Pretty nifty, right?

#  **Frenzied Factorization**

 **`Summarization is idempotent and books are highly structured.`** Well, of course there are caveats. As alluded to above, summarising books lends itself well to decomposition[7](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-7-47977244). This is due to two factors:

  1. The summarization operator is [idempotent](https://en.wikipedia.org/wiki/Idempotence): the summary of summaries is again a summary.

  2. Books have ([almost always](https://en.wikipedia.org/wiki/Choose_Your_Own_Adventure)) a neat linear and hierarchical structure.




As a consequence, we can solve each step of the process with the same operation, `summarize()`, and there is a _natural_ order in which we can decompose the book (`book -> chapters -> paragraphs -> sentences`).

 **`Decomposition might be difficult in general.`** Can we hope to find a decomposition in general? There is a [strong case](https://www.lesswrong.com/posts/tPqQdLCuxanjhoaNs/reductionism) that _nothing fundamentally complex exists_. Complexity is in the [map, not the territory](https://en.wikipedia.org/wiki/Map%E2%80%93territory_relation). Everything _can_ be neatly decomposed into disjoint pieces or dissolved whenever the [original thing is confused](https://www.lesswrong.com/posts/Mc6QcrsbH5NRXbCRX/dissolving-the-question). However, before we _know_ how to decompose something into its constituents correctly, we can get [very confused](https://en.wikipedia.org/wiki/Phlogiston_theory) about how it works[8](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-8-47977244).

 **`Debate as one proposal for automatic decomposition.`** Consequently, finding the correct lens for [zooming in](https://distill.pub/2020/circuits/zoom-in/), and uncovering the _correct_ way to decompose a problem, is non-trivial. One proposal for producing _correct_ problem decompositions is [debate](https://openai.com/blog/debate/), where the components of an argument are exposed through adversarial probing. It seems, however, that some [rather sticky issues](https://www.alignmentforum.org/posts/PJLABqQ962hZEqhdB/debate-update-obfuscated-arguments-problem) persist. Also, people [tend to be kind of bad](https://ought.org/updates/2020-01-11-arguments) at evaluating arguments. Decomposition through debate is not looking too promising right now.

 **`Debate in real-life cannot robustly decompose problems.`** In retrospect, perhaps we shouldn't be surprised. [Real debates kind of suck](https://www.youtube.com/watch?v=VcHPmVxtFw8&ab_channel=SarahZ). Something akin to debate led the ancient Greeks to believe that [everything is water](https://en.wikipedia.org/wiki/Thales_of_Miletus) and medieval scholars to think that fire is made from [phlogiston](https://en.wikipedia.org/wiki/Phlogiston_theory) and to ponder the [number of angels on the tip of a needle](https://en.wikipedia.org/wiki/How_many_angels_can_dance_on_the_head_of_a_pin%3F). A debate doesn't correctly leverage the asymmetry between building and criticizing. In particular, a [particularly convoluted argument](https://www.alignmentforum.org/posts/PJLABqQ962hZEqhdB/debate-update-obfuscated-arguments-problem) is too hard to disprove.

 **`Scientific inquiry as a robust technique for decomposition.`** [There is, of course, another way of looking at this.](https://youtu.be/1bSPNboKCzM?t=966) We _do_ have a much more robust method for decomposing problems: scientific inquiry. Half of the research process is about [finding the question](https://www.quora.com/How-long-does-it-take-for-a-PhD-scholar-to-decide-on-a-research-topic). Similarly, the hard part of proving a complicated mathematical theorem is _seeing_ why it has to be true; often, writing the proof can be almost mechanic. If we could automate scientific inquiry, we might get to a point where we can _reliably_ discover appropriate decompositions of problems.

#  **Dense Discoveries**

 **`Automating scientific inquiry is hard.`** Just saying “science!” is easy, of course. While we have [great tools](https://openai.com/blog/openai-api/) for automating debates, we [do not even have a clear idea](https://en.wikipedia.org/wiki/Philosophy_of_science) of what the scientific method _actually looks like_. Most knowledge about science is implicit, and an [unhealthy admiration of serendipity](http://philsci-archive.pitt.edu/14127/1/On%20Serendipity%20in%20Science%20FINAL_preprint.pdf) pervades academia. [I](https://universalprior.substack.com/p/making-of-ian) [have](https://universalprior.substack.com/p/on-scaling-academia) [some](https://universalprior.substack.com/p/on-not-reading-papers) [ideas](https://universalprior.substack.com/p/on-automatic-ideas) for automating parts of the research process, but the core of the problem eludes me[9](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-9-47977244).

 **`A decomposition has semantics and syntax.`** But I _do_ have a trace of an idea. The first observation is that there is something like [semantics and syntax](https://universalprior.substack.com/p/applied-mathematical-logic-for-the) of a decomposition. The semantics is the content of the decomposition, and the syntax is the structure that ties the content together. The second observation is that **for a successfully decomposed task, the semantic interplay of the individual components mirrors the structure in which they are arranged.**

Okay, I realize that probably makes almost no sense. Let’s look at an example.

 **`Semantic component of a decomposition.`** We take the decomposed story of Alice in Wonderland as a starting point. We want to ignore the decomposition structure for a second and just focus on the resulting text. In this Figure, I illustrate how I took the separate pieces of the source text and the summaries, embedded them in a high-dimensional vector space, and computed the similarity between all the components.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F7071ffb8-e370-4c75-8983-63e08869c91d_1600x471.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F7071ffb8-e370-4c75-8983-63e08869c91d_1600x471.png) **Figure 2: (a)** Passing the paragraphs of the original text and the intermediate and final summaries (left) through a sentence embedding model (middle; [all-mpnet-base-v2](https://www.sbert.net/docs/pretrained_models.html)) to obtain high-dimensional vector representations (right; 768 dimensions). **(b)** Correlation matrix of sentence embeddings of different parts of the recursive summarization process.

The resulting correlation matrix is clearly not random. For one, there are blocks of high correlation along the diagonal, which stem from the fact that paragraphs nearby in the text tend to share semantic features[10](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-10-47977244).

Another observation is that there are two highly correlated off-diagonals indicating the similarity of the depth two summary and the source text. There is also a much fainter set of four additional diagonals indicating the similarity between the depth one summary and multiple portions of the depth two summaries. The depth zero summaries should correlate with _everything_ , but it's tough to see because it is just a single row and column.

 **`Syntactic component of the decomposition.`** Now comes the kicker. Instead of focusing on the resulting text, we might also exclusively focus on the resulting _structure_ of the decomposition. In this Figure, I illustrate how I took the tree decoupled from the text, embedded the nodes in a high-dimensional vector space, and computed the similarity between all the components.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F2f4a9e78-ddf0-420d-89d0-02ec22dc2391_1600x483.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F2f4a9e78-ddf0-420d-89d0-02ec22dc2391_1600x483.png) **Figure 3: (a)** Passing the graph structure of the summarization process (left) through a graph embedding model (middle; [GGVec](https://github.com/VHRanger/nodevectors)) to obtain high-dimensional vector representations of the nodes (right; 30 dimensions). **(b)** Correlation matrix of node embeddings of different parts of the recursive summarization process.

I won't have to repeat the spiel of the previous paragraph. You can see that there is again clearly a pattern and that **this pattern looks a lot like the pattern from the previous figure**. This is what I mean when I say that semantic and syntactic structure match: The way that the tree's nodes relate to each other resembles how the different pieces of text relate to each other. This observation might be trivially true, but (I hope) it's trivially true [in an interesting way](https://en.wikipedia.org/wiki/Semantic_theory_of_truth)[11](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-11-47977244).

 **`And then, a cliffhanger…`** What does this buy us? I don’t have a great answer to that question yet[12](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-12-47977244). I’m running a bunch of experiments on this idea to see what it can do, but it’ll take a bit more time to process. But since my posts have been getting pretty long recently, and in the spirit of “[building in public](https://publiclab.co/building-in-public),” I’m putting this out there anyway. I’ll update you when I learn more!

Subscribe

[1](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-anchor-1-47977244)

Not an XOR!

[2](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-anchor-2-47977244)

Or, if they are, I would be shocked that the topic never came up during lunch before.

[3](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-anchor-3-47977244)

Some people also argue that we have to be even more thoughtful in leveraging the asymmetry because it's not enough to control the AI - we also have to control it [robustly](https://www.alignmentforum.org/tag/inner-alignment).

[4](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-anchor-4-47977244)

Yey humanity!

[5](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-anchor-5-47977244)

A while ago, I experimented with recursively summarizing a research paper of mine, and the resulting top-level summary was talking a _lot_ about owls. There is no mention of owls in my paper, except in one sentence towards the end.

[6](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-anchor-6-47977244)

I apologize for this abuse of language, but I could not resist.

[7](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-anchor-7-47977244)

I'm not sure if it is only evident in hindsight that summarization _should_ work well.

[8](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-anchor-8-47977244)

I am ~60% sure that Scott Garrabrant's work on [finite factored sets](https://www.lesswrong.com/posts/N5Jm6Nj4HkNKySA5Z/finite-factored-sets) is relevant here, but I am confused about how exactly. Okay, actually, make that ~30%.

[9](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-anchor-9-47977244)

It’s a hard problem.

[10](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-anchor-10-47977244)

I'm arranging the rows and columns of the correlation matrix to follow the story's sequential ordering.

[11](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-anchor-11-47977244)

I had a whole section on Wittgenstein's [picture theory of language](https://en.wikipedia.org/wiki/Picture_theory_of_language) and on the relationship between [syntax and semantics in mathematical logic](https://universalprior.substack.com/p/applied-mathematical-logic-for-the) sketched out, but it's late, and who am I kidding.

[12](https://universalprior.substack.com/p/task-decomposition-and-scientific#footnote-anchor-12-47977244)

Ideally, the distinction between semantics and syntax of decompositions will allow us to automate the process of decomposing. I’m thinking of a type of [EM algorithm](https://en.wikipedia.org/wiki/Expectation%E2%80%93maximization_algorithm) that iteratively proposes a hierarchical clustering of elements, attempts a decomposition, compares semantics and syntax, and proposes a new hierarchical clustering. But I’m pretty sure this is not how it’ll work.
