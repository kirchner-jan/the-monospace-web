# On Automatic Ideas

## TL;DR: As part of my "scaling academia" project, I tackle automated idea generation. Finetuned large language model, online machine learning, and semantic search. Poisson point processes!

**Dec 09, 2021**

**Likes:** 3

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F2b9f91e8-ef19-49fb-b934-70af62c41324_520x228.gif)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F2b9f91e8-ef19-49fb-b934-70af62c41324_520x228.gif)A prototype for automatic idea generation.

### Code first, ask questions later

In [On Scaling Academia](https://universalprior.substack.com/p/on-scaling-academia) I made the case that _automatic research_ , i.e. AI-supported & scalable application of the [scientific method](https://www.hpmor.com/chapter/8#:~:text=science%20investigation%20project%3A-,Step,-1%3A%20Form%20a), might be great. My argument went like this,

  1. automatic research is beneficial for academia (systematization and [objective metrics of progress](http://mason.gmu.edu/~rhanson/gamble.html) are woefully lacking in current academia),

  2. some degree of automation might be strictly necessary for continued scientific progress (note the ever-increasing [unwieldiness of humanity's collected knowledge](https://web.stanford.edu/~chadj/IdeaPF.pdf)).




However, many things "might be great"[1](https://universalprior.substack.com/p/on-automatic-ideas#footnote-1-45230438), but most aren't [tractable](https://forum.effectivealtruism.org/tag/itn-framework-1). Does _automatic research_ fall into that category? It's tempting to [tackle that question from the metaphorical ivory tower](https://www.nature.com/articles/s41599-020-0494-4) and to get lost in definitions and speculation. That's not my comparative advantage[2](https://universalprior.substack.com/p/on-automatic-ideas#footnote-2-45230438), I prefer getting excited and building things. In this spirit, I'll "code first, ask questions later". Instead of doing all of research at once, I focus on a central aspect of research, _idea generation_ , and present some of my initial experiments and experiences with automating idea generation.

###  **Using IAN to generate all the (proto-)ideas**

The first insight is that having ideas is _really easy_. The problem is having _good_ ideas[3](https://universalprior.substack.com/p/on-automatic-ideas#footnote-3-45230438). When you feel like you can't come up with any ideas, you probably can’t see the forest for the trees. Generating ideas is a combinatoric process: take two things (or more), combine them, and, voilà, [Clown Dentists, West Dakota, and Halloween in January](https://screenrant.com/bojack-horseman-todd-popular-dumb-ideas-reddit/)[4](https://universalprior.substack.com/p/on-automatic-ideas#footnote-4-45230438). People working on computational creativity [call this "pastiche"](https://www.creativitypost.com/article/systematizing-creativity-a-computational-view) and distinguish it from "real creativity". But let us not be deterred by that, we'll start philosophizing once we’re done coding. Perhaps we will see a path forward once we know how to generate pastiche at scale.

"Pastiche at scale" happens to be one of the many nicknames of [IAN](https://universalprior.substack.com/p/making-of-ian), a large language model fine-tuned of my personal notes and the papers that I read. Given a prompt, IAN will produce multiple possible continuations, kind of like the "autocomplete" feature on smartphones only more so. Prompting IAN with

> Text within this block will maintain its original spacing when published
>     
>     
>      _Here is a list of interesting project ideas:
>     1._

produces pastiche gems like

> Text within this block will maintain its original spacing when published
>     
>     
>      _I want to go to medical school_
> 
> Text within this block will maintain its original spacing when published
>     
>     
>      _Are there any ways in which the planning fallacy can be helpful?_
> 
> Text within this block will maintain its original spacing when published
>     
>     
>      _Build a service that delivers toilet paper to your home._
> 
> Text within this block will maintain its original spacing when published
>     
>     
>      _Investigate how neuromodulators affect the formation and function of dendritic spines._
> 
> Text within this block will maintain its original spacing when published
>     
>     
>      _Build a band name for your friends and make T-shirts._
> 
> Text within this block will maintain its original spacing when published
>     
>     
>      _A camera that takes a picture whenever it detects that someone is yawning._

And a _lot_ more. Making IAN generate pastiche for 24 hours results in ~10,000 "proto-ideas". I call them proto-ideas because quality varies a lot[5](https://universalprior.substack.com/p/on-automatic-ideas#footnote-5-45230438); sifting through all of them is more work than coming up with proper ideas myself. This leads us directly to the next step.

###  **Turning proto-ideas into ideas**

The second insight is that distinguishing nonsense from ideas is _easy_. I can tell if a proto-idea is nonsense in less than a second, which is [usually a good indicator](https://second.wiki/wiki/100-schritt-regel) that the process can be automated. The solution that I came up with is a logistic regression model on a [semantic embedding](https://www.sbert.net/) of the proto-idea, that is trained [online](https://github.com/online-ml/river) through an interface I [threw together](https://streamlit.io/):

This video shows the interface after I've trained it for a few hundred examples, and the "predicted usefulness" (0=nonsense, 1=idea) has already converged pretty well. In fact, when I map the proto-ideas [into a low-dimensional space](https://lvdmaaten.github.io/tsne/), we can see a bit of organization emerge.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F636dac22-5787-44da-9d2e-6d49c82a3261_1600x1370.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F636dac22-5787-44da-9d2e-6d49c82a3261_1600x1370.png)tSNE projection of semantic embedding of proto-ideas. Color indicates usefulness of proto-ideas as predicted by logistic regression model.

As you can see, the regression has learned that ideas from the neuroscience peninsula tend to be the most useful for me[6](https://universalprior.substack.com/p/on-automatic-ideas#footnote-6-45230438).

> Text within this block will maintain its original spacing when published
>     
>     
>      _A project on how the brain makes use of prior knowledge to guide decision-making._
> 
> Text within this block will maintain its original spacing when published
>     
>     
>      _Development of a new theory of cortical computation that incorporates topographic organization, feedback control and multi-sensory integration._
> 
> Text within this block will maintain its original spacing when published
>     
>     
>      _To understand how the brain stores ideas hierarchically, we could study how it works when it can't find an idea and how it works when it can._

But also in other regions of semantic space, there are ideas with high predicted usefulness. Here is a selection:

> Text within this block will maintain its original spacing when published
>     
>     
>      _Write a book in which each chapter is a different type of cinema, For example, the first chapter might be in the style of a documentary, the second chapter mainstream cinema, and the third chapter experimental cinema._
> 
> Text within this block will maintain its original spacing when published
>     
>     
>      _Have an online game night - This could be a game night that you host on Zoom and that people can join - You could do it every week and rotate hosts_
> 
> Text within this block will maintain its original spacing when published
>     
>     
>      _An AI system that plays the role of a creative director for an orchestra._
> 
> Text within this block will maintain its original spacing when published
>     
>     
>      _To make a game where you have to help a scientist find a cure for a disease._
> 
> Text within this block will maintain its original spacing when published
>     
>     
>      _[The Tale Of Gandhi](https://universalprior.substack.com/p/the-tale-of-gandhi-and-the-devil) And The Old Witch, The Tale Of Gandhi And The Two Giants, The Tale Of Gandhi And The Flying Mountain, The Tale Of Gandhi And The One Who Would Not Speak, The Tale Of Gandhi And The Loveless Kingdom, The Tale Of Gandhi And The Three Ghosts, The Tale Of Gandhi And The Two Dragons Who Were Best Friends_
> 
> [7](https://universalprior.substack.com/p/on-automatic-ideas#footnote-7-45230438) _, …_

### **Ideas and "great" ideas**

The third insight is that the quality of an idea is not an _intrinsic_ , but an _extrinsic_ property. The quality does not sit within the idea, it is determined by us from the outside. And these judgments are subjective[8](https://universalprior.substack.com/p/on-automatic-ideas#footnote-8-45230438), so there is no universal way to generate _great_ ideas.

However, once you _do_ know which criteria you care for, identifying a _great_ idea reduces to a [constraint satisfaction problem](https://en.wikipedia.org/wiki/Constraint_satisfaction_problem); and we have [great](https://en.wikipedia.org/wiki/Lagrange_multiplier) [tools](https://en.wikipedia.org/wiki/Pontryagin%27s_maximum_principle) for solving those. In the simplest form[9](https://universalprior.substack.com/p/on-automatic-ideas#footnote-9-45230438) we don't even have to resort to anything fancier than [search](https://universalprior.substack.com/p/soldiers-scouts-and-albatrosses). The algorithm looks something like this:
    
    
    while not found:
      idea = next_idea()
      if constraints(idea):
        return idea

I've implemented this with a [semantic search](https://www.sbert.net/examples/applications/semantic-search/README.html), followed by a ranking according to usefulness predicted by the regression[10](https://universalprior.substack.com/p/on-automatic-ideas#footnote-10-45230438).

The _actual_ constraints arising in a research project are substantially more complicated than just semantic similarity[11](https://universalprior.substack.com/p/on-automatic-ideas#footnote-11-45230438), but the central logic of this approach remains unchanged: generate a _lot_ of ideas and filter. The comparative advantage of computers is that they can do a simple thing much faster and much longer than a human can; generating a ginormous dataset of proto-ideas is not feasible for humans, but "easy"[12](https://universalprior.substack.com/p/on-automatic-ideas#footnote-12-45230438) for computers. This is essentially the same strategy that led to [superhuman chess performance](https://en.wikipedia.org/wiki/Deep_Blue_%28chess_computer%29) and that only now, after decades, is supplanted by [more data-efficient methods](https://www.youtube.com/watch?v=NJCLUzkn-sA&ab_channel=YannicKilcher).

###  **Going from great ideas to implementations**

The fourth insight is that while the greatness of ideas is subjective, the greatness of _implementations_ is more objective. You can argue whether some of the "great" ideas I listed above are actually great, but once there is an implementation the nature of an argument changes qualitatively. Once implemented, reality enters the discussion and adjudicates.

I want to write an entire post on how to automate going from idea to implementation, but here is the minimalist workflow that I'm using for now:

  1. Set a time frame based on previous experience from similar projects, [not based on particulars of the current project](https://www.lesswrong.com/posts/CPm5LTwHrvBJCa9h5/planning-fallacy).

  2. Divide the time **evenly**[13](https://universalprior.substack.com/p/on-automatic-ideas#footnote-13-45230438) into an "expansion" and a "contraction" phase[14](https://universalprior.substack.com/p/on-automatic-ideas#footnote-14-45230438).

    * In the expansion phase, iterate the following steps: Collect information (reading reviews and using [Elicit](https://roamresearch.com/elicit.org)), [chart](https://roamresearch.com/) people and beliefs (in my experience, authorship explains most variability), [implement prototypes](https://openai.com/blog/openai-codex/) ([build the smallest toy example that would invalidate an idea](https://threadreaderapp.com/thread/1441027241870118913.html)), explore implications and reject dead ends ([reductio ad absurdum](https://en.wikipedia.org/wiki/Reductio_ad_absurdum)).

    * In the contraction phase, do the following: Don't implement anything new ([feature freeze](https://en.wikipedia.org/wiki/Freeze_%28software_engineering%29)), identify the "solid core" (throw away _everything_ that is not fully cooked[15](https://universalprior.substack.com/p/on-automatic-ideas#footnote-15-45230438)), start writing early (writing forces you to put things in order), make illustrations (drawing things reveals how you _actually_ think about something), and collect feedback ([Grammarly](https://app.grammarly.com/) improves text beyond just fixing typos).

  3. Publish whatever you have at the end of your time frame.




There are [fantastic tools](https://roamresearch.com/) for some of these steps, and for the rest, I have ideas for how to build the necessary tools. I'll keep you posted on how this goes.

Subscribe

###  **Closing thoughts**

According to "code first, think later" we've now reached the "think" part. You can probably tell that I am skeptical of people who [declare](https://www.fastcompany.com/90339590/3-reasons-why-ai-will-never-match-human-creativity) that [creativity](https://thenextweb.com/news/ai-is-incredibly-smart-but-it-will-never-match-human-creativity) is [uniquely](https://www.aceyus.com/blog/why-ai-will-never-match-human-creativity/) human. These voices are less numerous now that AI-generated [poetry](https://www.gwern.net/GPT-3), [art-on-demand](https://www.wombo.art/), and [music](https://www.aisongcontest.com/) are actually enjoyable[16](https://universalprior.substack.com/p/on-automatic-ideas#footnote-16-45230438). Perhaps there is still a way of [drawing concept boundaries](https://www.lesswrong.com/s/SGB7Y5WERh4skwtnb/p/7X2j8HAkWdmMoS8PE) that make creativity uniquely human, but I'm skeptical that those concepts will end up being very useful.

I believe there is substantial confusion about where ideas come from. [WikiHow](https://www.wikihow.com/Main-Page) provides a representative answer to the question "[How to Come Up With Ideas](https://www.wikihow.com/Come-Up-With-Ideas)". They recommend the following three-step process:

  1.  _Getting Your Brain Moving_ , i.e. engage with the topic.

  2.  _Disengaging from Work_ , i.e. allow for gestation until an idea appears.

  3.  _Testing Your Ideas_ , i.e. reject bad ideas.




[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F7c8cb3f9-308a-4695-8efc-b838f80e3c40_1600x435.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F7c8cb3f9-308a-4695-8efc-b838f80e3c40_1600x435.png)I have a hard time putting my feelings about these illustrations into words.

Step two, the "gestation period" _appears_ magical. Mathematicians [have perfected the art of gestation](https://books.google.de/books?id=QdHBDwAAQBAJ&pg=PA236&lpg=PA236&dq=mathematics+creativity+take+a+walk&source=bl&ots=nxwB03USj1&sig=ACfU3U1cA9HiA6XmJ4551esBlD8qdpbuZQ&hl=en&sa=X&ved=2ahUKEwjp0uHuzL70AhWHC-wKHYOdBYgQ6AF6BAgUEAM#v=onepage&q=mathematics%20creativity%20take%20a%20walk&f=false):

>  _How does mathematical creativity take place? Where do good ideas come from? Of course there is no single answer, and as we all get older we wonder more and more why we don't have all the great ideas that we had thirty years ago.  
>   
>  There is general agreement, however, that one of the best ways to think about a problem is not to think about it. That is to say, you work hard and concentrate all your effort on the task for a protracted period of time; but then you let it go. Do something else: mow the lawn, go for a walk, take a shower, have a shave. The mind still percolates away, trying some things, discarding others. Often it happens that the solution to the problem will then just pop up unexpectedly.  
>   
> Ron Graham, late of Bell Labs and now a Distinguished Professor at U.C. San Diego, gets some of his best ideas while juggling or performing gymnastics. Persi Diaconis (1945- ) of Stanford lets his ideas gestate while he is creating and performing new magic tricks. Henri Poincare used to go on trips to the seashore. Isaac Newton worked in his garden. [...]_

I see the value of a healthy balance as much as the next person, [pain is not the unit of effort](https://www.lesswrong.com/posts/bx3gkHJehRCYZAF3r/pain-is-not-the-unit-of-effort). In fact, I believe that maintaining some balance between intense work and leisure is critical for sustained high research output. I still have a hard time believing that we will have to teach computers how to juggle as a _necessary_ component of the creative process. And also in humans, creativity does not _always_ require a gestation period. A good brainstorming session, or just thinking for [five minutes by the clock about a problem](https://www.lesswrong.com/posts/FHiM34PmrN224pqTz/on-creativity-the-joys-of-5-minute-timers), can solve a substantial portion of problems.

Instead of postulating [something magical that occurs through the interaction between the subconscious and the conscious](https://duncanwardle.com/how-to-open-the-door-to-your-creative-genius/)[17](https://universalprior.substack.com/p/on-automatic-ideas#footnote-17-45230438), I believe there is a much more parsimonious explanation: What if (as argued above) coming up with good ideas is simply a [search problem](https://universalprior.substack.com/p/soldiers-scouts-and-albatrosses) where possible ideas are proposed, evaluated and (most of the time) rejected? If each proposed idea only has a small probability of being a "hit", then the distribution of arrival times of ideas is a [Poisson process](https://en.wikipedia.org/wiki/Poisson_point_process), and the [distribution of waiting times in between ideas is an exponential distribution](https://gtribello.github.io/mathNET/resources/jim-chap20.pdf). As a consequence, finding a good idea simply takes a lot of time sometimes, especially when the probability of a hit is small. Having a "dry spell" of good ideas is just what we would (sometimes) expect under this model.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ffd3a7204-c9f3-45da-af5c-6535248a4113_1600x632.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ffd3a7204-c9f3-45da-af5c-6535248a4113_1600x632.png) **a** Example of a Poisson point process, blue circles indicate generated ideas as a function of time. Red bar highlights time period at beginning of simulation where no ideas were generated. **b** Distribution of waiting time lengths (red bar in **a** ) pooled across simulations. Notice the long tail.

Disengaging from the problem then is nothing else than pressing the "fast forward" button. The process of searching for a good idea continues to "[run in the background](https://en.wikipedia.org/wiki/Global_workspace_theory)", perhaps with reduced resources[18](https://universalprior.substack.com/p/on-automatic-ideas#footnote-18-45230438), and only rises to attention when a "hit" (or something looking a lot like a hit) was found. I suspect we can [explain away](https://martin-thoma.com/explaining-away/) the apparent "magical" component of the creative process this way. But doing that is a lot less exciting than "coding away" the confusion, so I’ll stick to that instead.

[1](https://universalprior.substack.com/p/on-automatic-ideas#footnote-anchor-1-45230438)

World peace, ending hunger, total equality (you pick which kind), infinite animal-suffering-free on-demand-ice cream, and all the wishes from the "[Open-Source Wish Project](https://web.archive.org/web/20080212074646/http://www.homeonthestrange.com/phpBB2/viewforum.php?f=4&sid=c33eee736cd053c05b21aede801f31a6)"

[2](https://universalprior.substack.com/p/on-automatic-ideas#footnote-anchor-2-45230438)

A previous, much more wordy version of this post was stuck in "draft" mode for a very long time.

[3](https://universalprior.substack.com/p/on-automatic-ideas#footnote-anchor-3-45230438)

I think this distinction is the easiest way to resolve the tension between Stephen Malina et al. [writing  
](https://guzey.com/ideas-not-mattering-is-a-psyop/#:~:text=don%E2%80%99t%20buy%20it.-,Empirically%2C%20all%20our%20aspiring%20founder%20friends%20are%20desperate%20for%20startup%20ideas%2C%20with%20few%20managing%20to%20land%20on%20something%20worthwhile%2C%20and%20all%20our%20scientist%20friends%20are%20desperate%20for%20research%20ideas.,-Good%20ideas%20are)" _Empirically, all our aspiring founder friends are desperate for startup ideas, with few managing to land on something worthwhile, and all our scientist friends are desperate for research ideas._ "  
and me [writing  
](https://universalprior.substack.com/p/on-scaling-academia#:~:text=I%20could%20come%20up%20with%20a%20research%20program%20that%20keeps%201000s%20of%20people%20busy)" _I could come up with a research program that keeps 1000s of people busy._ "  
I totally could keep them _busy_. I'm much less certain if I could get them to do anything _useful_.

[4](https://universalprior.substack.com/p/on-automatic-ideas#footnote-anchor-4-45230438)

Taking a list of ideas from some of the funniest writers is probably not the best way to make this point. However, the ideas that I come up with (combined keyboard & mouse, banana telephone, microphone shoes) are so lame, they are making my point _too_ well.

[5](https://universalprior.substack.com/p/on-automatic-ideas#footnote-anchor-5-45230438)

f.e. _"On Being Prepared" - by Impossible Things, Do a workout, Draw a picture of a religious situation from scratch._

[6](https://universalprior.substack.com/p/on-automatic-ideas#footnote-anchor-6-45230438)

Learning this is not too hard, a fuzzy keyword would probably also work.

[7](https://universalprior.substack.com/p/on-automatic-ideas#footnote-anchor-7-45230438)

The Tale Of Gandhi was _always_ supposed to be a series.

[8](https://universalprior.substack.com/p/on-automatic-ideas#footnote-anchor-8-45230438)

"Getting a tattoo", "Becoming an actor", "Starting a stamp collection", "Investing in cryptocurrency", are all either great or terrible ideas depending on what you value.

[9](https://universalprior.substack.com/p/on-automatic-ideas#footnote-anchor-9-45230438)

If all the constraints are just binary "satisfied" or "not satisfied" constraint.

[10](https://universalprior.substack.com/p/on-automatic-ideas#footnote-anchor-10-45230438)

I can imagine straightforward extensions of this where I layer [Boolean search](https://www.webopedia.com/definitions/boolean-search/) on top of the output of multiple semantic search queries, but probably there is a more elegant way to implement this directly on the semantic embedding.

[11](https://universalprior.substack.com/p/on-automatic-ideas#footnote-anchor-11-45230438)

You want your idea to be [novel](https://www.lesswrong.com/posts/KfMNFB3G7XNviHBPN/joy-in-discovery), fit into your [paradigm](https://plato.stanford.edu/entries/lakatos/), appeal to a [certain audience](https://www.nature.com/articles/d41586-020-02875-4), be [tractable, neglected, have a high impact-to-effort ratio](https://forum.effectivealtruism.org/tag/itn-framework-1), etc.

[12](https://universalprior.substack.com/p/on-automatic-ideas#footnote-anchor-12-45230438)

Given a [TPU machine](https://sites.research.google/trc/about/) from Google <3

[13](https://universalprior.substack.com/p/on-automatic-ideas#footnote-anchor-13-45230438)

This is super important. There will be a very strong pull to extend the expansion phase. Don't give in. This is the point where it's decided whether you hit your deadline or not.

[14](https://universalprior.substack.com/p/on-automatic-ideas#footnote-anchor-14-45230438)

These two phases are the ones I tried to characterize in "[Soldiers, Scouts, and Albatrosses](https://universalprior.substack.com/p/soldiers-scouts-and-albatrosses)", although I'm not sure if I hit the nail on the head there.

[15](https://universalprior.substack.com/p/on-automatic-ideas#footnote-anchor-15-45230438)

Be honest with yourself here. Again, the temptation is big to carry along that beautiful aspect of the project that you have sunken a ton of time into, but which simply doesn't mash with anything else. Throw it away. (Into your drawer of "future project ideas" that you will never open again).

[16](https://universalprior.substack.com/p/on-automatic-ideas#footnote-anchor-16-45230438)

With rather primitive technology, compared to what is possible.

[17](https://universalprior.substack.com/p/on-automatic-ideas#footnote-anchor-17-45230438)

Quote: _For most of any given day we only use our conscious brain, representing only a surprising 13% of the brain’s capacity. The other 87%, our subconscious brain goes unused because when we are stressed and hear ourselves say “I don’t have time to think,” the door between our conscious and subconscious brain closes completely. When this door is closed, access to all of that experiential and creative stimulus in the subconscious brain is denied, therefore, no big ideas. Every meal you’ve ever eaten, place you’ve ever visited, person you’ve ever met, book you’ve read, movie you’ve seen–they’re all back there in your subconscious brain waiting to make unrelated connections back to the challenge at hand and to support the creation of that big innovation._

[18](https://universalprior.substack.com/p/on-automatic-ideas#footnote-anchor-18-45230438)

As long as the time spent disengaged is much longer than the time actively working on the problem, reduced resources do not matter so much.
