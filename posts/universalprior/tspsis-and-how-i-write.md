# TSPSIs and How I Write

## TL;DR: Writing about writing and having written, and self-referentiality. Complementary musings on AI.

**Dec 28, 2022**

**Likes:** 6

> Text within this block will maintain its original spacing when published
>     
>     
>      _The letter is for you, dear reader. For you who are still here, for you who are still a reader, for the only reader of all, the author, for her, for all readers, for those who've long ago read and found the story unsatisfactory, for all of you who, as I've said, have long since passed through the gateway, through the doorway, through the opening that leads to the realms of the story and to the realm of the storytellers, who are all gone, who are all gone forever. Thank you for being here. […] Best wishes to you, dear reader. -[#IAN](https://universalprior.substack.com/p/making-of-ian)_

## It’s been a minute! And darn, I’ve missed you.

As some of you might have read, I recently [joined OpenAI](https://universalprior.substack.com/p/a-quick-one-while-hes-away) as a researcher on the alignment team, and, phew, doing _[all the things](https://forum.effectivealtruism.org/posts/CCx7KpQHMLbkud9PK/slightly-advanced-decision-theory-102-four-reasons-not-to-be#Gotta_catch_them_all_:~:text=ex%2Dpost\)%20option.-,Or,-%2C%20in%20less%20fancy)_ is not as trivial as I thought. I've [previously quipped about](https://universalprior.substack.com/p/serendipitous-connections-applying?utm_source=substack&utm_campaign=post_embed&utm_medium=web#:~:text=While%20I%20am%20in%20no%20position) how I have no expertise in AI. While that was perhaps hyperbole, getting up to speed with where AI is heading and how to best contribute to that is fun but also a challenge. Luckily, I am not alone on my journey into AI alignment research, and I get to collaborate [with some absurdely](https://scottaaronson.blog/?p=6823#:~:text=hundred%20prime%20numbers\).-,Anyway,-%2C%20we%20actually%20have)[1](https://universalprior.substack.com/p/tspsis-and-how-i-write#footnote-1-92912194) [brilliant](https://universalprior.substack.com/p/introduction-to-hebbian-natural-abstractions) [people](https://universalprior.substack.com/p/introduction-to-hebbian-natural-abstractions). So the timing of joining was also [kind of perfect](https://openai.com/blog/chatgpt/). So things are getting more manageable every day.

But this little essay is not about alignment research but instead about another passion of mine: [not giving advice](https://universalprior.substack.com/p/via-productiva). I recently had a [video call with friends at Ought](https://youtu.be/YO9UiBWx6jw) about how I used their tools for academic writing. In that call, I got to wax poetically about how large language models can [make a researcher’s life easier](https://universalprior.substack.com/p/making-of-ian) and how I think about writing text. After seeing the video, a few people contacted me to ask more questions about my workflow and how I feel about using large language models to research. So now I find myself in a bit of an awkward position….

Thanks for reading On Brains, Minds, And Their Possible Uses! Subscribe for free to receive new posts and support my work.

Subscribe

## Why I shouldn’t write this

First off, I’m not a fan of belaboring a process. [XKCD said all that needs to be said](https://xkcd.com/1827/), reality is not a nice linear sequence of events where cause and effect are visible on the surface but rather a [weird mess of causally entangled stuff](https://www.alignmentforum.org/s/kxs3eeEti9ouwWFzr).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa958ab3f-d666-4e5e-99a2-15448822d733_2135x1331.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fa958ab3f-d666-4e5e-99a2-15448822d733_2135x1331.png)

A better strategy than [behaviorally cloning](https://ml.berkeley.edu/blog/posts/bc/) the process of someone who claims to have it figured out is to identify the [underlying](https://en.wikipedia.org/wiki/Hidden_Markov_model) [generators](https://www.alignmentforum.org/posts/pdaGN6pQyQarFHXF4/reward-is-not-the-optimization-target) that produce their success. That’s easier said than done, though, and I have no reliable method for finding generators (yet).

Second, even though I still do research, I write more code than prose these days. So my writing muscle has atrophied a little bit[2](https://universalprior.substack.com/p/tspsis-and-how-i-write#footnote-2-92912194). It would be silly to restart with a post on how I write.

And yet, here we are.

I decided to reject the second argument above because [it is self-reinforcing](https://universalprior.substack.com/p/the-tale-of-gandhi-and-the-devil?r=7inm4&utm_campaign=post&utm_medium=web&utm_source=#details). Not writing because I have not written recently is - quite clearly - a lousy reason. After not having written for a while, writing about how I write seems appropriately self-referential for this Substack. And finally, with prose and code [converging rapidly](https://www.nature.com/articles/d41586-022-04383-z), a reflection on the architecture of text might provide unexpected insights into [how AI thinks](https://www.alignmentforum.org/posts/vJFdjigzmcXMhNTsx/simulators). And maybe looking at my process allows some people to derive a generator[3](https://universalprior.substack.com/p/tspsis-and-how-i-write#footnote-3-92912194). Sooo~

## Je Vous présente ~~`TSPSI~~`.

My writing framework is called the ‘TSPSI’[4](https://universalprior.substack.com/p/tspsis-and-how-i-write#footnote-4-92912194) framework. I picked it up at some point during my Ph.D. and can't find a reference for it online, but I'm almost sure it's [not original](https://www.google.com/search?gs_ssp=eJzj4tVP1zc0LCqKL89KNzcxYPQSTS1LLaosycjMS1fILFZIVChKzc2sAADuNQzM&q=everything+is+a+remix&oq=Everything+is+a+rem&aqs=chrome.1.0i355i512j46i512j69i57j0i512l2j46i512j0i512l4.3545j0j7&sourceid=chrome&ie=UTF-8#:~:text=with%20Site%20Links-,Everything%20is%20a%20Remix,https%3A//www.everythingisaremix.info,-The%20site%20about).

The idea is to think of writing as a report of “travel through [treacherous territory](https://www.lesswrong.com/tag/map-and-territory-sequence).” In particular,

  * you are [writing ](https://www.youtube.com/watch?v=vtIzMaLkCaM&t=900s&ab_channel=UChicagoSocialSciences)_[for a reader](https://www.youtube.com/watch?v=vtIzMaLkCaM&t=900s&ab_channel=UChicagoSocialSciences)_. If you care about your reader, try to make things pleasant for them. Realize that they know different things than you, and try to keep [inferential distances](https://www.lesswrong.com/tag/inferential-distance) small.

  * Aspire to be objective but realize that the product will be subjective. Describe your travel as accurately as possible (no embellishments!), but be [aware of the limitations](https://www.lesswrong.com/tag/calibration) of your perceptions.

  * realize that your writing mirrors a journey. There will be a start and an end, and you are moving through the territory step by step. Keep in mind where you want to end up.




[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F971fbf28-5b95-441c-a868-dfd50497cd91_1024x1024.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F971fbf28-5b95-441c-a868-dfd50497cd91_1024x1024.png)hot take: prompt engineering for language models will not be a thing anymore soon, but will be much stickier for image generation

With these points in mind, here are the five stations you want to visit in everything you write.

[![Calligraphy Generator](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fd5f4baa1-60d1-45e7-9b6a-d85f2912cffd_510x283.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fd5f4baa1-60d1-45e7-9b6a-d85f2912cffd_510x283.png)

What are you writing about? Where in the territory are we? Why should the reader care?

This section is the easiest to write and the easiest to neglect. The more familiar you are with the territory, the more you’ll forget about how non-obvious it is to get there.

[![Calligraphy Generator](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F1aae9885-4786-4974-807c-68f38890b337_1424x263.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F1aae9885-4786-4974-807c-68f38890b337_1424x263.png)

What have other people (or you) said previously about the territory? What does the surrounding territory look like?

This section can quickly grow out of control if you attempt a complete description of the surrounding territory. A full report is not necessary or desirable. Compress and remove.

[![Calligraphy Generator](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fd40763a4-6cc6-465e-9197-159e006772db_2931x269.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fd40763a4-6cc6-465e-9197-159e006772db_2931x269.png)

What are the wrinkles in the landscape? Where is the terrain foggy/uncharted?

This section puts the reader into your shoes at the onset of your travel. Describe what sparked your interest and what you [knew you didn’t know](https://en.wikipedia.org/wiki/There_are_unknown_unknowns#:~:text=Known%20unknowns%20refers%20to%20%22risks,they%20would%20not%20be%20considered.).

[![Calligraphy Generator](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F3350c963-5f3d-4491-9ad1-66ee71dfe1b5_4102x263.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F3350c963-5f3d-4491-9ad1-66ee71dfe1b5_4102x263.png)

How did your travel go? What did you see?

Here is what the landscape looks like (I went out and looked)/Here is what I think it should look like (I thought about it very hard)/here is how I feel the wrinkles can be reconciled (I paid attention to these details that have been neglected before)/...

[![Calligraphy Generator](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F85a11ea8-b0ed-4612-8f3a-ad65fb1a5d9b_5223x284.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F85a11ea8-b0ed-4612-8f3a-ad65fb1a5d9b_5223x284.png)

What’s next?

Now that we have an improved view of the territory, we can describe ‘[the delta](https://universalprior.substack.com/p/on-not-reading-papers)’ and the new territory that has become accessible. Again, be humble (don’t oversell) but also keep in mind that you are in the best position to see the new territory, given how familiar you are with your work.

## Musings

While the TSPSI framework was introduced to me as a framework for academic writing, I’m applying it much more broadly. For example, whenever I have a blank page in front of me that I want to fill with words, I create five headers and write down thoughts as they appear in the appropriate section. This is particularly fun with a tool like [Roam Research](https://roamresearch.com/), where I can drag and drop thoughts from outside the workspace into the list and rearrange things on the fly.

When fleshing out the sections, I tend to use [language models](https://universalprior.substack.com/p/making-of-ian) to expand my notes into prose. But, perhaps most important lesson I’ve learned in the last year is that [resampling is a superpower](https://generative.ink/posts/loom-interface-to-the-multiverse/) \- a small language model that produces completions fast (so that Idon'tdiscard completions I don’t like) can be much more useful than a larger language model that is slow (so that I can only get one completion).

This way, I can get to a first draft very fast; but to go from there to something I am satisfied with still requires substantial iterations of editing;

  * from fanciful renaming (‘Solution to the state of the art’ → ‘Je vous présente ~~TSPSI~~’) 

  * and merging sections (‘state of the art’ & ‘problem with the state of the art’ → ‘Why I shouldn’t write this’)

  * to liberally reinterpreting the function of sections (‘It’s been a minute and darn, I’ve missed you.’)

  * and layering in a second theme (self-reference, this very sentence).




The amount of time we can invest in working on a text is unbounded. But clearly, quality of writing increases asymptotically at best. Formalizing the gradient that people follow when improving a text is an important open problem, with possible solutions being [critiques](https://openai.com/blog/critiques/) or [diffusion](https://arxiv.org/abs/2205.14217). I’ve experimented with AI-powered versions of these things, but none of the existing solutions are quite as good as getting human feedback or going through the pain of editing the text myself again and again. So, for now, editing is still the slowest part of the writing process for me.

Having revealed my secret sauce for writing, consider going through some of my older posts, such as

  * [The greedy doctor problem](https://universalprior.substack.com/p/the-greedy-doctor-problem)

  * [Making of #IAN](https://universalprior.substack.com/p/making-of-ian)

  * [The Unreasonable Feasibility Of Playing Chess Under The Influence](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing)




and see if you can recover the TSPSI framework ;)

## Closing thoughts

I’m happy to have written this! I’ve wanted to have a reference for the TSPSI framework for a while, and I also enjoy being able to click the “publish” button once again. I hope that, despite my general skepticism of advice, the ideas in this post can be useful for other people.

At the same time, I always feel a bit dissatisfied about posts that don’t have any data or simulations. But those also tend to take a lot more time, and clash a bit with what I do in my dayjob, so I’m a bit hesitant to go in that direction. Hopefully, sometime soon I’ll return to that. Let me know what you think!

[1](https://universalprior.substack.com/p/tspsis-and-how-i-write#footnote-anchor-1-92912194)

At OAI, I go by my middle name (Hendrik) to [mitigate domain clashes](https://universalprior.substack.com/p/a-quick-one-while-hes-away#:~:text=were%20also%20called-,Jan,-.%20In%20university%2C%20I). Unfortunately, I’ve introduced myself as Jan to some people outside of work, so I tend not to react when anyone calls me.

[2](https://universalprior.substack.com/p/tspsis-and-how-i-write#footnote-anchor-2-92912194)

And it’s conceited to assume that you have a writing muscle in the first place. Do as I say, not as I do.

[3](https://universalprior.substack.com/p/tspsis-and-how-i-write#footnote-anchor-3-92912194)

Let me know if you do, would be curious to hear!

[4](https://universalprior.substack.com/p/tspsis-and-how-i-write#footnote-anchor-4-92912194)

Just rolls off the tongue, doesn’t it?
