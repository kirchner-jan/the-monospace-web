# Inferring utility functions from locally non-transitive preferences

## TL;DR: Fanboying JvN, then a nuts-and-bolts description of the von-Neumann-Morgenstern theorem. A connection to reward modeling, some simulations, and pretty figures!

**Feb 10, 2022**

**Likes:** 2

# **Johnny did it.**

[Last week](https://universalprior.substack.com/p/task-decomposition-and-scientific) I offhandedly mentioned the unlikely possibility that my coworkers are [clones of John von Neumann](https://fantasticanachronism.com/2021/03/23/two-paths-to-the-future/). I need to explain that a bit more ——— It was a compliment, I swear! John von Neumann was... a "[genius](https://unherd.com/2021/11/the-genius-of-john-von-neumann/)" doesn't quite do it justice. The "[Last Great Polymath](https://www.sothebys.com/en/articles/john-von-neumann-the-last-great-polymath)"? The "[Man from the Future](https://www.amazon.co.uk/dp/B08X6QLFSC/ref=dp-kindle-redirect?_encoding=UTF8&btkr=1)"? The ["life of the party," "an occasional heavy drinker," and "reckless driver"](https://cs.stanford.edu/people/eroberts/courses/soco/projects/1998-99/game-theory/neumann.html)[1](https://universalprior.substack.com/p/inferring-utility-functions#footnote-1-48484774)? Okay, that last one again isn't very flattering. I'm trying to say that von Neumann was an interesting person who did many interesting things.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F6061293a-ebf0-48b2-9514-16cdc8e5c8b7_960x658.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F6061293a-ebf0-48b2-9514-16cdc8e5c8b7_960x658.png)John von Neumann, a young Richard Feynman, and Stanislaw Ulam. I'm as [grossed out by the flaws of the people of the past](https://twitter.com/stevenstrogatz/status/1446760034302562315) as the next person, but I still wouldn't say no to listening to those three talking.

Remember when [I claimed](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#:~:text=Claude%20Shannon%20at%20Bell%20Labs) that Claude Shannon came up with the minimax decision rule? I was wrong; Johnny[ did it](https://en.wikipedia.org/wiki/Minimax_theorem) 20 years earlier. The architecture of modern computers? [Johnny did it](https://en.wikipedia.org/wiki/Von_Neumann_architecture). A mathematical foundation of utilitarian ethics? Johnny did... what?

Well, [it's a bit complicated](http://fmwww.bc.edu/repec/esNASM04/up.25774.1075494883.pdf). Here’s my reasoning:

 **Preference utilitarianism and the Von-Neumann-Morgenstern theorem.** Ethics is the part of philosophy concerned with the question, "How should I act?" One possible answer to that question is [utilitarianism](https://www.utilitarianism.net/), prescribing that we should maximize happiness and well-being for all affected individuals. Achieving "happiness and well-being" is undoubtedly desirable ([or?](https://www.lesswrong.com/tag/wireheading)), but [kind of hard to operationalize](https://universalprior.substack.com/p/puberty-as-cause-x). Instead of asking people about what they want, we might also _observe_ what [people prefer](https://en.wikipedia.org/wiki/Revealed_preference) when given a choice. [Preference utilitarianism](https://www.utilitarianism.net/theories-of-wellbeing#:~:text=these%20rival%20accounts.-,Desire%20Theories,-We%20saw%20that) is a form of utilitarianism that focuses on satisfying everyone's _preferences_. And it [turns out that](https://en.wikipedia.org/wiki/Von_Neumann%E2%80%93Morgenstern_utility_theorem), if you are being reasonable about your preferences, we can represent your preferences succinctly in a "utility function," **u(A)**. This utility function has the neat property that for two possible options, **L** and **M** , you _prefer_ option **M** over option **L** iff[2](https://universalprior.substack.com/p/inferring-utility-functions#footnote-2-48484774) **u(M) > u(L)**.

This is one way to arrive at the "[von-Neumann-Morgenstern theorem](https://en.wikipedia.org/wiki/Von_Neumann%E2%80%93Morgenstern_utility_theorem)," but it's probably not the path von Neumann took when deriving it[3](https://universalprior.substack.com/p/inferring-utility-functions#footnote-3-48484774).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F918b0cdc-2f56-426e-bf59-effc0260e1d8_991x1469.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F918b0cdc-2f56-426e-bf59-effc0260e1d8_991x1469.png)[Oskar Morgenstern and John von Neumann](https://www.historyofinformation.com/detail.php?id=1803)

But I think it’s an interesting perspective. There is a seemingly straightforward way to use the theorem to solve some nasty technical problems related to “[making machines try to do what humans want them to do](https://ai-alignment.com/clarifying-ai-alignment-cec47cd69dd6).” Get everyone's utility functions, combine them, and then pick the actions that increase them the most. While you and I probably can't do that, perhaps a computer can help - they are very good at making numbers go up! And perhaps there is a case to be made that utility is effectively the best single number we can hope for.

Sounds good. Where is the catch?

#  **The futility of computing utility.**

Let's start by trying to write down a utility function. **The proof of the von-Neumann-Morgenstern is** _ **constructive**_ , i.e., it doesn't only guarantee the existence of a utility function, it also shows us the way to get there. Here is a step-by-step guide:

 _ **1\. Write down all the possible elementary outcomes that we might want to know the utility of.**_

Ah. Yeah. That's going to be a problem.

 **"All the things" is a lot of things.** We might (and will, in this post) limit ourselves to a toy domain to make some progress, but that will be a poor substitute for the thing we want: all the possible outcomes affecting all existing humans. We might not even think of some outcomes because they appear too good to be true. (Or too weird to be thinkable.) We might even want to include those outcomes _in particular,_ as they might be the best option that nobody realized was on the table. But if we can't think of them, we can't write them down.

(Perhaps there is a way out. An essential nuance in the first step is writing down "all the possible _elementary_ outcomes." We don't need to consider all the outcomes immediately. We only need to consider a set from which we can construct the more complicated outcomes. We need a [basis](https://en.wikipedia.org/wiki/Basis_%28linear_algebra%29) of the space of possibilities. That's already infinitely easier, and we're _always guaranteed_ to find a basis (if we're willing to [embrace chaos](https://www.youtube.com/watch?v=ec2-GZRYGd8)). The hope here might now be that we can find a basis of a system that is rich enough to describe all relevant outcomes and simple enough to allow for linear interpolation. Of course, a [semantic embedding of natural language](https://lena-voita.github.io/nlp_course/word_embeddings.html) comes to mind, but the imprecision of language is probably a deal-breaker. Perhaps the semantic embedding of a formal language/programming language is more appropriate[4](https://universalprior.substack.com/p/inferring-utility-functions#footnote-4-48484774)?)

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fab44e0f3-9397-45b7-bb1c-3ff566dfdc3e_9922x3438.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fab44e0f3-9397-45b7-bb1c-3ff566dfdc3e_9922x3438.png)A toy domain containing all the possible elementary outcomes one can think about.

Let's use a toy domain, call this an open problem, and move on.

 _ **2\. Order all the elementary outcomes from worst to best.**_

For some inexplicable reason, my intro to computer science course at uni has prepared me for [this exact task, and this task alone](https://en.wikipedia.org/wiki/Sorting_algorithm). We have a bunch of great algorithms for sorting the elements of a list by comparing them with each other. If we're not incredibly unlucky, **we can hope to sort N-many outcomes with**

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ff653c372-ffd6-4514-b42f-088a950f46e5_131x46.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ff653c372-ffd6-4514-b42f-088a950f46e5_131x46.png)

 **comparisons**. After sorting thousands of elementary outcomes, we pick the worst (bumping your toe against a chair[5](https://universalprior.substack.com/p/inferring-utility-functions#footnote-5-48484774)) and the best (ice cream sandwich) and assign them utility 0 and 1. For 1000 elementary outcomes, we could do with as little as 3000 comparisons which you could knock out in an afternoon. For 100000 elementary outcomes, we're talking 500000 comparisons which will keep you busy for a while. But it's for a good cause!

Unless... somebody screws up. Those 3000 comparisons have to be _spot on_. **If you accidentally mess up one comparison, the sorting algorithm might not be able to recover[6](https://universalprior.substack.com/p/inferring-utility-functions#footnote-6-48484774).** And since we're working with humans, some errors are guaranteed. Can you confidently say that you prefer a mushroom risotto over a new pair of shoes? Thought so.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F8523b1f1-38f2-4a18-9535-21f9e3140876_1600x230.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F8523b1f1-38f2-4a18-9535-21f9e3140876_1600x230.png)[New shoes](https://www.youtube.com/watch?v=LaecIn0iLfU) sound fantastic, but that mushroom risotto!

But now comes the real killer.

 _ **3\. Do a sequence of psychophysics experiments where humans indicate where the exact probabilistic combination of the worst- and the best possible outcome is equivalent to an intermediate outcome.**_

After sorting all outcomes from worst to best, we offer you a sequence of lotteries for each intermediate outcome (mushroom risotto): "Would you rather accept a 10% chance of stubbing your toe and a 90% chance of an ice cream sandwich, or a guaranteed mushroom risotto?" At some point (45% stubbing your toe), your answer will change from "Yes" to "No," and then we know we are very close to finding your utility for mushroom risotto (in this case, a utility of ~0.45).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fb963c330-81f7-4da0-b76c-3fb659faaa6b_1600x157.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fb963c330-81f7-4da0-b76c-3fb659faaa6b_1600x157.png)

I was halfway through setting up [MTurk](https://www.mturk.com/), but let's be realistic - this will not work. [Allais paradox](https://en.wikipedia.org/wiki/Allais_paradox) aside, I don't have the patience to set this up, so who will have the patience to go through this? Of course, we should have seen this coming. **Just because a proof is "constructive" doesn't mean that we can apply it in the messy real world.** Getting a utility function out of a human will require some elbow grease.

#  **Human fallibility and reward modeling.**

Let’s shuffle some symbols. How do we account for all the human messiness and the tendency to make mistakes? A standard trick is to call it "noise"[7](https://universalprior.substack.com/p/inferring-utility-functions#footnote-7-48484774). Given a _true_ estimate of utility, ū(A), we might write the perceived utility at any given time as a random variable, u(A), distributed around the true value,

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F4324cff1-d791-4e2c-86d9-d2407249fed2_310x46.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F4324cff1-d791-4e2c-86d9-d2407249fed2_310x46.png)

Given two outcomes, O₁ and O₂, the probability of assessing the utility of O₂ higher than the utility of O₁ is distributed as the difference of two Gaussians, which is again a Gaussian:

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fae4d1721-f40d-47bd-9e6d-b0987e203887_605x60.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fae4d1721-f40d-47bd-9e6d-b0987e203887_605x60.png)

(assuming independence of O₂ and O₁). The [error function](https://en.wikipedia.org/wiki/Error_function) (lovingly called **erf** ) is nasty because it doesn't have a closed-form solution. But it _does_ have a close relative that looks almost the same and is a lot nicer mathematically, and that has a much more pleasant-sounding name than " **erf** "... 

I'll replace the **erf** with a stereotypical [logistic function](https://en.wikipedia.org/wiki/Sigmoid_function), **S,**

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F02a39185-e966-4096-9499-b68f349efe23_958x53.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F02a39185-e966-4096-9499-b68f349efe23_958x53.png)

Much nicer. Even though the logistic function has largely [fallen out of favor as an activation function in machine learning](http://www.cs.toronto.edu/~fritz/absps/imagenet.pdf), its [grip on psychophysics is unbroken](https://en.wikipedia.org/wiki/Psychometric_function).

Now that we have the mathematical machinery in place, we need to calibrate it to reality. A natural choice is to take the cross-entropy between our machinery, **P(u(O₂) > u(O₁))**, and the _actual_ comparisons provided by humans, (O₂ > O₁) or (O₁ > O₂),

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc0553e38-3581-4da6-80d5-c1a6a8212a61_1196x52.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc0553e38-3581-4da6-80d5-c1a6a8212a61_1196x52.png)

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa2b09352-8766-49ee-8c27-9ad53b13c99c_385x61.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa2b09352-8766-49ee-8c27-9ad53b13c99c_385x61.png)

Surprise[8](https://universalprior.substack.com/p/inferring-utility-functions#footnote-8-48484774)! The resulting loss function is also used for the [reward modeling](https://arxiv.org/pdf/2112.00861.pdf) that I [briefly touched on in last week's post](https://universalprior.substack.com/p/task-decomposition-and-scientific)[9](https://universalprior.substack.com/p/inferring-utility-functions#footnote-9-48484774). The researchers who originally proposed this technique for learning human preferences say that it is similar to the [Elo rating system from chess](https://en.wikipedia.org/wiki/Elo_rating_system) and the ["Bradley & Terry model."](https://en.wikipedia.org/wiki/Bradley%E2%80%93Terry_model) I find the motivation of reward modeling as an approximation of the von-Neumann-Morgenstern theorem a lot more [Romantic](https://medium.com/age-of-awareness/how-to-be-a-romantic-with-a-capital-r-358566d6156b), though.

Having uncovered this connection, a natural strategy for inferring a utility function through training a neural network with comparisons of pairs of elements from the domain presents itself.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Feb6d641e-6acc-41a0-81f8-762c0bd63876_1600x323.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Feb6d641e-6acc-41a0-81f8-762c0bd63876_1600x323.png)Unordered elements from the domain of “things we might care about” ( **a** ) are translated into an orthonormal basis of a high dimensional vector space ( **b** ) and transformed into a scalar output through a multilayer perception ( **c** ).

Can this work? It doesn’t involve MTurk for now, so I am happy to try!

# A natural representation of utility functions.

I found that the neural network achieves near-zero loss on the comparisons after 20k steps (panel **a** ). Runtime appears to increase linearly with the number of elements[10](https://universalprior.substack.com/p/inferring-utility-functions#footnote-10-48484774). The resulting utility functions are monotonic and increase by an (approximately) equal amount from one item to another (panel **b** ). This demonstrates that given enough time, a multilayer perceptron can sort a list.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F1bb66e3e-ed8c-4ad3-9756-9885d9205b02_9922x2940.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F1bb66e3e-ed8c-4ad3-9756-9885d9205b02_9922x2940.png) **a.** Cross-entropy loss as a function of iterations for different sizes of the toy domain (indicated by color). **b.** Predicted utility of different items after 250k iterations of a “rational" (i.e., a total order) teaching signal. **c.** Predicted utility of items after 250k iterations of a “noisy rational” (i.e., 90% chance of total order, 10% chance of inverting preference) teaching signal. **d.** Predicted utility of items after 250k iterations of a “loopy rational” (i.e., total order, except for elements 3 and 4, or 3 and 7, which are connected in a loop) teaching signal. In **b** to **c** , the predicted utility is normalized between 0 and 1.

Some might say that I used several hours of compute time on a [Google Colab](https://research.google.com/colaboratory/) GPU _just_ to sort lists, but that would be rather uncharitable. My primary motivation for this approach (human tendency to make mistakes) bears fruits in the following experiment. When I add noise to the choice procedure (resulting in 10% “random” choices), the network is still able to recover the appropriate ordering (panel **c** ). And, even more remarkable, **when I make the choice procedure loopy (i.e.,[nontransitive](https://link.springer.com/article/10.1007/BF00056121)), the network can still recover a reasonable approximation of what the utility function looks like** (panel **d** )!

This last set of experiments is exciting because introducing loops leads to nonlinear utility functions that are squashed together in the vicinity of the loop. Intuitively, if outcomes #3 and #4 are impossible to distinguish reliably, this might indicate that their utility is indeed very similar. The exciting possibility is that step 3 of the procedure above (psychometric calibration of utilities) could automatically be satisfied when options are sufficiently similar and sometimes confused[11](https://universalprior.substack.com/p/inferring-utility-functions#footnote-11-48484774).

# Concluding thoughts and what’s next?

There are a lot more experiments I want to run on this toy domain to probe the limits to which preference orderings can be turned into utility functions:

  * What is the largest number of elements we can sort with a given architecture? How does training time change as a function of the number of elements?

  * How does the network architecture affect the resulting utility function? How do the maximum and minimum of the unnormalized utility function change?

  * Which portion of possible comparisons needs to be presented (on average) to infer the utility function?




But independent of those experiments, there are some fascinating directions that I plan to explore in a future post. Now that I have a natural way to induce utility functions, I think I can further explore the [utility monster](https://en.wikipedia.org/wiki/Utility_monster) and some of the classic literature on [(un-)comparability of utility functions](https://www.lesswrong.com/posts/cYsGrWEzjb324Zpjx/comparing-utilities). I also really want to write a proper treatment of [value handshakes](https://www.lesswrong.com/tag/values-handshakes), which is a topic in [dire need of exploration](https://www.lesswrong.com/posts/WuLxYmAQCigdR4spw/what-posts-do-you-want-written?commentId=HxG7aaaQKtCoRhHrY).

To stay up to date for when I write those, consider signing up for the newsletter. It’s free (and will stay free)!

Subscribe

[1](https://universalprior.substack.com/p/inferring-utility-functions#footnote-anchor-1-48484774)

What is it with intelligent people and self-medication? Also,[ He loved to eat, especially rich sauces and desserts, and in later years was forced to diet rigidly. To him exercise was “nonsense.](https://qualiacomputing.com/2018/06/21/john-von-neumann/)” A good reminder not to fall for the[ Halo effect](https://en.wikipedia.org/wiki/Halo_effect).

[2](https://universalprior.substack.com/p/inferring-utility-functions#footnote-anchor-2-48484774)

If and only if.

[3](https://universalprior.substack.com/p/inferring-utility-functions#footnote-anchor-3-48484774)

although - [who knows](http://idiomzero.blogspot.com/2010/07/8-anecdotes-about-john-von-neumann.html#:~:text=I%20did%20it!%22-,An,-MIT%20student%20cornered).

[4](https://universalprior.substack.com/p/inferring-utility-functions#footnote-anchor-4-48484774)

Has anybody ever looked at that? What happens when I subtract Fizzbuzz from the Fibonacci sequence?

[5](https://universalprior.substack.com/p/inferring-utility-functions#footnote-anchor-5-48484774)

A very close "win" over [S-risk scenarios](https://longtermrisk.org/s-risks-talk-eag-boston-2017/).

[6](https://universalprior.substack.com/p/inferring-utility-functions#footnote-anchor-6-48484774)

And the worst-case runtime shoots up to ∞ as soon as you have the probability of errors). In this situation, [Bogosort](https://en.wikipedia.org/wiki/Bogosort) might just be the most reliable solution - at least it won't terminate until it's done.

[7](https://universalprior.substack.com/p/inferring-utility-functions#footnote-anchor-7-48484774)

Joke aside, it’s an interesting question which factors need to come together to make something “noise.” I guess the central limit theorem can help if there are many independent factors, but that’s never really the case. The more general question is under which circumstances the [residual factors are random and when they are adversarial.](https://twitter.com/0xdoug/status/1456032851477028870)

[8](https://universalprior.substack.com/p/inferring-utility-functions#footnote-anchor-8-48484774)

Please ignore that it's already written in the section title.

[9](https://universalprior.substack.com/p/inferring-utility-functions#footnote-anchor-9-48484774)

The original [Leike paper](https://arxiv.org/pdf/1706.03741.pdf) has an equivalent expression that does not write out the logarithm applied to the sigmoid.

[10](https://universalprior.substack.com/p/inferring-utility-functions#footnote-anchor-10-48484774)

My money would be on O(n log n) or worse, of course.

[11](https://universalprior.substack.com/p/inferring-utility-functions#footnote-anchor-11-48484774)

I’d expect that the difference in utility, |ū(O₁) - ū(O₂)|, will be proportional to the probability of confusing the order, P(u(O₁) > u(O₂)).
