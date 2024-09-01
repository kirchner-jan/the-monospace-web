# Making of #IAN

## TL;DR: I fine-tuned a large language model on my personal notes and embedded the resulting model in my everyday workflow. Personal experience, Roam Research, AI Safety.

**Aug 29, 2021**

**Likes:** 7

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fee60786b-f547-4d3c-92b4-351d547b729a_600x338.gif)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fee60786b-f547-4d3c-92b4-351d547b729a_600x338.gif)“ _Show, don’t tell._ ” - probably said originally by someone with bad hearing

## Building a 'digital person'.[1](https://universalprior.substack.com/p/making-of-ian#footnote-1-40527537)

Holden Karnofsky asks you to [imagine yourself as a digital person](https://www.cold-takes.com/imagining-yourself-as-a-digital-person-two-sketches/) \- a copy of yourself that runs on a computer and that has the potential to vastly increase both productivity and output. An easily deployable digital person has the thrilling potential to not only reduce the effort a task requires (like other productivity tools might), but additionally to scale up and dramatically raise the ceiling of your output.

As Balaji S. Srinivasan [points out](https://twitter.com/balajis/status/1421684650578104324?s=09), the biggest bottleneck in productivity might be the human in the loop:

>  _We really should be in the middle of a golden age of productivity. Within living memory, computers did not exist. Photocopiers did not exist. Backspace did not exist. You had to type it all by hand. […] For example, maybe we have it wrong with productivity apps. Maybe the goal isn't writing up a Google Doc so another human can understand it, but hitting enter on GitHub so a computer can do it._

Instead of assigning each other tasks in one big circle of shifted responsibility, we might want to factor out subtasks and automate them away aggressively.

I used a two-week vacation to take these thoughts to heart by fine-tuning a large language model on the text I have produced in the last decade and by integrating its capabilities into my daily workflow. This post summarises some of the things I've learned in the process.

* * *

## Does this have any practical use?

Turning large language models into productivity tools is _in vogue_. OpenAI Codex [promises](https://openai.com/blog/openai-codex/) to reduce coding to the exciting part, decomposing the problem, and remove the laborious part, turning the decomposed problem into code. [Emacs packages](https://github.com/semiosis/pen.el) to seamlessly apply well-engineered contextual prompts to arbitrary text are under development. And out of a [slurry](https://aiwriter.app/) of [quirky](https://twitter.com/sharifshameem/status/1284095222939451393?lang=en) GPT [applications](https://www.overfit.ai/classroom-items/gpt-3-text-to-emoji), Ought's [Elicit](https://elicit.org/) stands out to me for its vision and its obvious potential to accelerate science. Even the idea of [fine-tuning a language model with personal text](https://svilentodorov.xyz/blog/gpt-15b-chat-finetune/) is not new - [Tom Riddle](https://www.youtube.com/watch?v=dZewnFXl_MY) did it long ago.

However, none of the existing solutions enable exactly what I imagined. They are either in a closed beta stage or gimmicky and narrow, require a murder and the splitting of my soul, or generally do not fit naturally in my usual workflows. Opening a webpage to talk to [Richard Feynman](https://aiwriter.app/) is fun, but not faster than just reading the Wikipedia article. In addition, while Richard Feynman is famously great at explaining difficult concepts, I will still have to translate his explanation into my own reference frame. Arguably, the person who is best suited to extend my thoughts is - me.

* * *

## A big language model that can produce human-like text. What can go wrong?

Enter #IAN ( _intelligence artificielle neuronale_ ), a hacky (and obviously narrow) version of a digital person based on my writing pattern. I collected text across different platforms (Email, WhatsApp, Telegram, Facebook, Roam Research, ~50Mb in total) and used the Google [TPU Research Cloud](https://sites.research.google/trc/) to [fine-tune GPT-J](https://github.com/kingoflolz/mesh-transformer-jax/blob/master/howto_finetune.md), a language model recently released by the rockstars at [EleutherAI](https://www.eleuther.ai/). I then wrote a small plugin for Roam Research and a custom keyboard for Android that allow me to integrate #IAN into my daily workflow.[2](https://universalprior.substack.com/p/making-of-ian#footnote-2-40527537) It was a marvelous experience and the result is surprisingly useful - even though it of course falls way short of a full "digital person".

Let me first show you what the result looks like. I have three main modes of interaction with the model.

 **curl in the command line.** For a stylish retro aesthetic, sampling given a prompt works directly from the command line.[3](https://universalprior.substack.com/p/making-of-ian#footnote-3-40527537)

While the thought process of #IAN here is not 100% clean (it suggests a name and then immediately states it's searching for a name), this example nicely demonstrates that the fine-tuning clearly had some effect. I have indeed been thinking a lot about effective altruism recently and this exact suggestion would be highly unlikely from a model only trained on random text from the internet.

 **SmartBlock in Roam Research.** Since this project is already weird enough, I will not commence this section with a love letter to [Roam Research](https://roamresearch.com/)[4](https://universalprior.substack.com/p/making-of-ian#footnote-4-40527537). I will only state that I've been using this note-taking app quite extensively and integrating a language model that can automatically expand my thoughts has been the primary motivation for this project. Because, while Roam Research is useful as is, some workflows are rather painful. In particular, sometimes I want to retrieve notes where I don’t remember any of the relevant keywords nor the context in which I stored the note. While this can also be resolved by a [good system of tags and querying](https://roamstack.com/searching-in-roam/), I thought it would just be a lot cooler to give some more interactivity to [my second brain](https://medium.datadriveninvestor.com/how-to-create-your-second-brain-and-why-roam-research-is-pushing-to-it-97f217f1e8cc?gi=55454aa6beda).[5](https://universalprior.substack.com/p/making-of-ian#footnote-5-40527537)

In this example, #IAN is producing a lot of - somewhat disjoint - thoughts on polarisation, with references to Scott Alexander, Nate Silver, and Tyler Cowen's "[mood affiliation](https://marginalrevolution.com/marginalrevolution/2011/03/the-fallacy-of-mood-affiliation.html)". A lot like how my notes would usually look before editing. Some of these are potentially fruitful, mood affiliation can certainly contribute to polarization, even though I have never (i.e. don't remember having) made that connection before.

 **A custom keyboard for Android.** While the Roam plugin probably has the biggest potential to be useful in the long run, I also wanted an easy way of interacting with #IAN while on the road. So I dove into the exciting world of app development and hacked together a custom keyboard that allows querying #IAN in any text box.[6](https://universalprior.substack.com/p/making-of-ian#footnote-6-40527537)

This is mostly a party trick because the text is annoying to enter on the smartphone keyboard and the results are not easy to process further. But this mode of interaction makes it tempting to perform a type of Turing test with my friends over WhatsApp - if I end up doing that, it'll be another post.

* * *

## How to use a large language model for something.

Now as you've seen in the demo videos, result quality can vary quite drastically. As has been [pointed out](https://twitter.com/RokoMijic/status/1288427331674083332?s=20) [before](https://bmk.sh/2020/08/17/Building-AGI-Using-Language-Models/#fn3), a language model pre-trained on the internet will end up producing text that looks like random text from the internet, which is often not exceedingly useful. Fine-tuning [might](https://bmk.sh/2021/06/02/Thoughts-on-the-Alignment-Implications-of-Scaling-Language-Models/#:~:text=exploring%20ways%20to,something%20like%20this) alleviate this to some degree, but to improve model output there are additional strategies that have been proposed:

 **Repeated sampling/Cherrypicking**

> Most impressive demos of GPT-3 where it displays impressive knowledge of the world are cherrypicked, but what that tells us is that the model needs to improve by approx log(N)/L bits, where N and L are the number of cherrypickings necessary and the length of the generations in consideration, respectively, to reach that level of quality. In other words, cherrypicking provides a window into how good future models could be. [Leo Gao](https://bmk.sh/2020/08/17/Building-AGI-Using-Language-Models/#fn2)

IAN provides different [samples](https://huggingface.co/blog/how-to-generate#top-p-nucleus-sampling) every time it is queried. Getting useful output from the model often requires providing the same prompt several times. Here is an example (prompt in italics) with suggestions for dinner tomorrow:

>  _IAN says: Tomorrow for dinner I will cook one of the following dishes: 1. pasta_ 2\. meat with vegetables 3. vegetarian pasta 4. vegan pasta

>  _IAN says: Tomorrow for dinner I will cook one of the following dishes: 1. pasta_ with pesto __ 2\. spaghetti bolognese 3. arancini with giallo 4. hamburgers with ketchup 5. chicken fried rice 6. fish fillet with olive 7. salad or fruit 8. fried zucchini flowers with mint 9. vegan cookies 10. double chocolate cake 11. tiramisu

>  _IAN says: Tomorrow for dinner I will cook one of the following dishes: 1. pasta_ 2\. salad 3. vegan burger 4. fruit salad 5. dessert Dishes can be combined to make a meal, but please don't put more than one on the card.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F6226ac63-7b34-4f13-b386-775f8d334518_744x837.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F6226ac63-7b34-4f13-b386-775f8d334518_744x837.png)discovered on EleutherAI

 **Prompt engineering**

>  _ **Sampling Can Prove The Presence Of Knowledge But Not The Absence**  
>  GPT-3 may “fail” if a prompt is poorly-written, does not include enough examples, or bad sampling settings are used. [...] The question is not whether a given prompt works, but whether any prompt works. _[Gwern Branwen](https://www.gwern.net/GPT-3#:~:text=Sampling%20Can%20Prove%20The%20Presence%20Of%20Knowledge%20But%20Not%20The%20Absence)

Large language models have _hidden knowledge_ that is only revealed when the query is phrased [in the right way](https://www.gwern.net/GPT-3#prompts-as-programming). Asking #IAN a question usually doesn't work[7](https://universalprior.substack.com/p/making-of-ian#footnote-7-40527537) \- it gets "distracted" and changes the topic or continues with a volley of more questions.

>  _IAN says: What is the capital of Spain?_ What is the length of the human foot? What are common uses of the words "dog," "cat," "horse," "sheep," "cow," "goat," "fish"?" What is a deductive process? What is a market economy? What is a human being?  
>  The list goes on for a while and eventually ends with the same question: What is a word?

Half-finished sentences work better (kind of, I had to sample twice, the first response was "Seville")

>  _IAN says: The capital of Spain is_ Madrid. The main airport is Adolfo da Costa. The train from Madrid to Barcelona usually takes around 2 1/2 hours. The direct train from Barcelona to Frankfurt is not recommended because it stops in Lleida, which is not so exciting. If you would like to go to another city during your travels in Spain, just let me know.

Listicles work great - probably because they provide multiple results per prompt (see the previous section)!

>  _IAN says: Here is a list of ideas for my next tattoo: 1. a fish on a spaceship_ 2\. a stalker on a hunt 3. the double helix 4. the second law of thermodynamics 5. flames in the shape of a heart 6. a bird in flight 7. a birds nest with babies 8. a map of Europe with a "place" for every country 9. a woman with a machine gun 10. a bird eating a snake 11. two dragons eating each other 12. a star with a sunroof and a lightning bolt 13. a small person inside a big person 14. an astronaut with an instrument for measuring radiation 15. a skull eating a heart 16. three interlocking hearts

 **Embrace it.** While the previous two points have been made before, this next point I haven't encountered before. There are two ways to reduce the difference between model output and ground truth - either change the model or change the ground truth. I believe the second option has been under-explored. To get good performance, I might just change what I consider “good output”.

While I obviously say this tongue in cheek, I think there is a case to be made here. Something like the uncanny valley effect[8](https://universalprior.substack.com/p/making-of-ian#footnote-8-40527537) or [Larry Tesler's Theorem](https://en.wikipedia.org/wiki/AI_effect#cite_note-7)[9](https://universalprior.substack.com/p/making-of-ian#footnote-9-40527537) might unjustly bias us to dismiss model output that _is_ useful. Therefore, the "trick" for better performance is just to embrace the weirdness and the otherworldly quirkiness.

On decisions that have objectively good and bad outcomes, like personal finance, I don't feel ready to follow #IANs advice, which is a bit too [Keynesian](https://www.investopedia.com/terms/d/deficit-spending.asp) for me:

>  _IAN says: Here is a plan for how I will invest my money for the next 10 years:_  
>  **More in general** : I want to increase my spending on research, travel and learning.  
>  **More on academia** : I want to support more PhDs and PostDocs. In particular, I want to support the establishment of a Frankfurt-wide sustainability network (see details of how I envision this below).  
>  **More on sustainability in general** : I want to increase my support for organisations working on improving the world.  
>  **More on EA** : I want to increase my participation in and support for EA.

Those are all certainly worthy causes, but as a starving PhD student™ I was more hoping for ETF recommendations.

But for decisions where the outcome is purely subjective and where _owning it_ is part of succeeding, it's awesome to hand over some agency. In particular, #IAN is great at producing creative ideas for tattoos, songs, lyrics, and motives for painting.

>  _IAN says: My deepest darkest secret is  
>  _I would hate to see you hurt  
>  And the thought of you growing old  
>  And being used up  
>  Is like a punch to the gut

>  _IAN says: These are the lyrics of a beautiful love song, written by a highly advanced AI. It's lyrical elegance and astonishing vocabulary amazes experts of classical and contemporary poetry. The lyrics go like this: '_  
>  My dearest friend,   
> I am writing to tell you that I have just received an offer I cannot refuse. A very charming man from the Andromeda Galaxy has asked me out for dinner. He is half an inch tall, has black fur and green scales, and is very wise. I am afraid I am going to have to say no.’

> >  _IAN says: Here is a list of things I want to draw: 1. A tree on fire_ 2\. A wormhole 3. A space station 4. A list of things that are kind of neat 5. The first law of metaphysics 6. The general equilibrium effect 7. isomorphic and equivalently 8. A use of Kurt Gödel’s incompleteness theorem

So I will attempt to counter the [Larry Tesler bias](https://en.wikipedia.org/wiki/AI_effect#cite_note-7) and cut the model some slack. Instead of trying to poke holes into an idea, I will let myself be guided by (cherrypicked) suggestions from #IAN sometimes. Why _can’t_ I get a tattoo just because an AI told me to?[10](https://universalprior.substack.com/p/making-of-ian#footnote-10-40527537) Why _can’t_ I draw a “use of Kurt Gödel’s incompleteness theorem”? I can't help but think of this plot that has been popping up on Twitter a lot recently:

> [![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F8ebc3baa-c3a7-4734-9fca-51029d2407c0_1024x667.jpeg)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F8ebc3baa-c3a7-4734-9fca-51029d2407c0_1024x667.jpeg)

Adapting to the trend might require radical changes. Better start early.

* * *

## Learning to learn with AGI.

I have a few things I'd love to try once I have a continuous stretch of free time to improve #IAN. Top of my list is to find a smarter way of extracting text from Roam Research. Currently, the graph structure is lost completely in preprocessing. There must be something clever[11](https://universalprior.substack.com/p/making-of-ian#footnote-11-40527537) that can be done short of [changing the architecture](https://paperswithcode.com/method/graph-transformer).

It is also just a [question of time](https://www.eleuther.ai/faq/#:~:text=Are%20you%20serious,200%20billion%20parameters.) until larger pre-trained (i.e. foundational[12](https://universalprior.substack.com/p/making-of-ian#footnote-12-40527537)) models become available. [Larger models exhibit more "general reasoning capabilities"](https://arxiv.org/abs/2005.14165), which would expand the domain in which #IAN output is useable. It would likely also come with higher hardware requirements, to the point where fine-tuning is not feasible even with TRC access. On the other hand, compute gets cheaper every year, so perhaps it _will_ become feasible eventually.

One thing that I'd be curious to test is some version of [Iterated Distillation and Amplification](https://ai-alignment.com/iterated-distillation-and-amplification-157debfd1616)[13](https://universalprior.substack.com/p/making-of-ian#footnote-13-40527537) to boost performance. I imagine a routine as follows:

  1. when querying #IAN from Roam Research, amplify performance by generating multiple samples (/listicles) and only keeping the best.

  2. consistently prepend these with the #[[IAN says:]] tag.

  3. distill by fine-tuning from scratch with the amplified Roam graph.




This could potentially be automated by training a classifier that learns my preferences for which of the multiple samples to keep. However, I don't have great intuition about how sensible the output will be, given that we're talking about a miniature dataset here (~50Mb). But perhaps automation is not even necessary and a slow circle (amplifying for a month and then distilling) might already produce useful results. Note that I'm not trying to build artificial general intelligence here. I'm just trying to build something useful[14](https://universalprior.substack.com/p/making-of-ian#footnote-14-40527537).

* * *

## Do I even want to do this?

Connected to this last point, there are some points on AI safety and ethics that I want to make. When I told friends about this project, I got two types of responses: either moderate enthusiasm and encouragement or resigned despair ( _"Oh no, I already hate this"_ ). Since I try to take feedback that I get serious[15](https://universalprior.substack.com/p/making-of-ian#footnote-15-40527537), I’ll share my thought process here on why this is not a terrible idea.

I don't run any danger of creating something dangerous myself. I don't have the required access to compute and I am not an ML researcher. Taking the [outside view](https://www.lesswrong.com/tag/inside-outside-view) (no matter what my latent god complex tries to convince me of) worrying about this particular danger appears like an inefficient use of limited cognitive resources.

There is however also the possibility that posts like this one represent an [infohazard](https://www.lesswrong.com/tag/information-hazards). Perhaps pointing out that something like #IAN is possible leads to someone with more resources (compute and cognitive) to work on something that has an actual shot at AGI. This is still unlikely, but perhaps not as easily dismissed. Remember the [Yudkowsky-Moore Law of Mad Science](https://twitter.com/patrickc/status/650726376073367552?lang=en): _"Every 18 months, the minimum IQ necessary to destroy the world drops by one point."_ The fact that someone with my background is writing about this topic is actually a datapoint that neatly follows the trend suggested by this law.

But I am [by far](https://www.gwern.net/GPT-3#:~:text=For%20example%2C%20I,if%20finetuned%3F%20Indubitably.) [not the first one](https://svilentodorov.xyz/blog/gpt-15b-chat-finetune/) with [an idea like this](https://uploadedyudkowsky.tumblr.com/). The few people within the community that I've talked to said that this is pretty much one of the first ideas that everyone working on language models has. So if there is an infohazard in this post, then it's just in carrying this idea into broader circles. And to hedge against the danger of that, I'm spending some more [weirdness points](https://www.lesswrong.com/posts/wkuDgmpxwbu2M2k3w/you-have-a-set-amount-of-weirdness-points-spend-them-wisely) to advertise [AI Safety](https://deepmindsafetyresearch.medium.com/building-safe-artificial-intelligence-52f5f75058f1) to my peers. In particular, my plan for this Substack is to come back to this theme repeatedly.

* * *

## #IAN doesn’t have a brain.

One last ethical consideration I would like to touch on is whether it is acceptable for me to include information about all my interactions with other people in the fine-tuning of the model. My primary [intuition pump](https://en.wikipedia.org/wiki/Intuition_pump) here is that if it's fine to write notes about these interactions in an analog notepad, then it should also be fine to compute a statistical representation of these notes in a language model - as long as I am only using the resulting model as I would use a notepad (i.e. an external extension to my mental scratchpad). Setting up a chatbot where people can just ask any question to #IAN on f.e. Telegram and receive an automatic response would cross this line for me. Or really any interaction with #IAN that is not monitored/filtered by me. That would just feel icky.

Although I want to point out that #IAN has not "spilled any beans" so far. It _is_ often generating statements about real people doing things they might really be doing but has never (up to this point) actually recounted an event that actually happened. But this is just a restatement of " _the fine-tuning didn't overfit too hard_ " and viewed through that lens it is also likely that there is _some_ overfitting and that a careful [forensic data analyst](https://en.wikipedia.org/wiki/Forensic_data_analysis) might separate truth from plausible construct. Therefore, I'll rather be safe than sorry and not make the fine-tuned weights available. Also [this horrifying short story about the fate of the first uploaded mind](https://qntm.org/mmacevedo) \- no, thank you.

* * *

## A high-level view of what I just explained.

What to take away from this project? The most striking part for me is to interact with a statistical summary of my collected output. I notice certain invariants and lots of variabilities - a bit like a word cloud on steroids[16](https://universalprior.substack.com/p/making-of-ian#footnote-16-40527537). It made me reflect a lot on identity and style. At the same time, reading text generated in the style of _you_ is a lot of fun, and teasing meaning from #IAN is at times like reading tea leaves - any possible meaning is not in the object but in the interaction. 

It's interesting to see a substantial part of my lifetime output condensed to 50Mb. One consoling thought is that, as Gwern puts it, [the last bits are the deepest](https://www.gwern.net/Scaling-hypothesis#:~:text=The%20last%20bits%20are%20deepest.)[17](https://universalprior.substack.com/p/making-of-ian#footnote-17-40527537), and perhaps getting a great language model of a person doesn't actually require a lot of data - just extremely high quality. I’ll keep that in mind the next time I text someone about their lunch plans. Finally, figuring out how to "talk" to #IAN and to tease out the most useful responses is a pretty remarkable experience. Probably the closest you can currently get to talking to an alien mind. Can recommend.

Subscribe

* * *

 _A big thank you to the following people for proofreading & feedback: Jasper, Nadia, Max, Hiba, Dylan, Deyue and Zhuoshi._

[1](https://universalprior.substack.com/p/making-of-ian#footnote-anchor-1-40527537)

All the section titles after this one were generated by #IAN and then lightly cherrypicked by me. The prompt is _Here is a list of possible titles for the sections of my first Substack post on the creation of a large language model fine-tuned to my own speech patterns. This list has been curated by a very smart AI. 1._

[2](https://universalprior.substack.com/p/making-of-ian#footnote-anchor-2-40527537)

I’ll publish another post with all the boring technical details and code snippets in case someone wants to try the same.

[3](https://universalprior.substack.com/p/making-of-ian#footnote-anchor-3-40527537)

The nice folks at EleutherAI already [provide](https://github.com/kingoflolz/mesh-transformer-jax/blob/master/device_serve.py) a minimal python flask server that can process POST queries.

[4](https://universalprior.substack.com/p/making-of-ian#footnote-anchor-4-40527537)

That will be another post.

[5](https://universalprior.substack.com/p/making-of-ian#footnote-anchor-5-40527537)

Note the words generated in italics - those would be bidirectional tags in Roam which I change to italics to avoid my Roam graph from becoming cluttered.

[6](https://universalprior.substack.com/p/making-of-ian#footnote-anchor-6-40527537)

This required [installing](https://lybekk.tech/guide/termux-install-google-cloud-cli) the gcloud suite on Termux which is a bit (very) whacky but works for now. The prompt templates in the keyboard are taken from [this](https://github.com/semiosis/prompts) GitHub repo. 

[7](https://universalprior.substack.com/p/making-of-ian#footnote-anchor-7-40527537)

Asking politely _never_ works and is guaranteed to get you made fun of for trying.

[8](https://universalprior.substack.com/p/making-of-ian#footnote-anchor-8-40527537)

Anything that is close to but not quite human can elicit an adverse emotional response.

[9](https://universalprior.substack.com/p/making-of-ian#footnote-anchor-9-40527537)

 _“AI is whatever hasn't been done yet.”_

[10](https://universalprior.substack.com/p/making-of-ian#footnote-anchor-10-40527537)

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F70de15e9-e7d7-4d67-b058-1865c972eb0d_4624x3472.jpeg)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F70de15e9-e7d7-4d67-b058-1865c972eb0d_4624x3472.jpeg) _#IAN says: I want to get a new tattoo! This time it will be_ a snake on my shoulder, and I thought about asking you first. Do you have an idea what I could do? I’m thinking about snakes, I guess. Best, Jan

[11](https://universalprior.substack.com/p/making-of-ian#footnote-anchor-11-40527537)

Perhaps just adding some indication of the indentation level can already help? Or splitting the file, not after a fixed number of lines but after all the children of a block are processed?

[12](https://universalprior.substack.com/p/making-of-ian#footnote-anchor-12-40527537)

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F49b4b622-a423-438a-b4fe-58d6ae0db9b8_687x500.jpeg)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F49b4b622-a423-438a-b4fe-58d6ae0db9b8_687x500.jpeg)

They are just the same thing, right?

[13](https://universalprior.substack.com/p/making-of-ian#footnote-anchor-13-40527537)

> [We use a learned model many times as a subroutine in a more powerful decision-making process, and then re-train the model to imitate those better decisions.](https://ai-alignment.com/iterated-distillation-and-amplification-157debfd1616)

[14](https://universalprior.substack.com/p/making-of-ian#footnote-anchor-14-40527537)

That can help me research how to align AGI.

[15](https://universalprior.substack.com/p/making-of-ian#footnote-anchor-15-40527537)

As some people have pointed out to me later, the arguments that I am providing in this section are not at all soothing and only tangentially related to the reasons for why they originally said “Oh no”. To this, I can only say “Oh well”.

[16](https://universalprior.substack.com/p/making-of-ian#footnote-anchor-16-40527537)

Credit for this phrase goes fully to Dylan.

[17](https://universalprior.substack.com/p/making-of-ian#footnote-anchor-17-40527537)

 _“For everyday actions, anybody, of any intelligence, can get enough practice & feedback to do them quite well. Where individuals differ is when they start running into novel choices, rare choices, choices that take seconds but unfold over a lifetime, choices where we will never get any feedback (like after our death).” _My (fuzzy, handwavy) point here is that pretraining can get you very close to the first part. Once you are there, what distinguishes individuals might actually be a rather small set of preferences that plays out in complicated ways. 

I realize that this runs counter the typical idea of scaling, where the last bit requires the _most_ training data.
