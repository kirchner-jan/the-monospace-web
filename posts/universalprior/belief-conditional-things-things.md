# Belief-conditional things - things that only exist when you believe in them

## TL;DR: A little winter story about making beliefs come true. Epistemic status: this is >90% written to amuse. Not 100% though.

**Dec 25, 2021**

**Likes:** 0

# **🎵 Do you believe... 🎵**

It is the season, and I just finished watching the 2003 classic "[Elf](https://en.wikipedia.org/wiki/Elf_%28film%29)" with Will Ferrell as "Buddy", a human raised among elves at the North Pole who travels to New York to reunite with his biological father and to save Christmas. The movie got me thinking.

There is an interesting trope in the movie that's used as a story device: the magical powers of Santa are predicated on humans believing in Santa. Thus, Santa falls in the same category as some [magical creatures](https://en.wikipedia.org/wiki/Tinkerbell_effect), [the value of fiat money](https://www.investopedia.com/terms/f/fiatmoney.asp) and, arguably, god[1](https://universalprior.substack.com/p/belief-conditional-things-things#footnote-1-41815715). To spread some magical fuzzy winter feelings, I want to share some thoughts about what I call "belief-conditional things". I think I'm on to something here.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc25f2c85-95cf-469b-8251-36c97e0c571f_256x256.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc25f2c85-95cf-469b-8251-36c97e0c571f_256x256.png)Expect me to upgrade my [CGD](https://githubmemory.com/repo/crowsonkb/v-diffusion-pytorch) game even further in the new year! This looks a lot like Santa.

#  **🎵 ... in love after love 🎵**

What is the relationship between belief and reality? Some like to think in terms of "territory and map": the territory is everything _out there_. The map is a lossy _mental_ representation of the territory. We know that the [map is not the territory](https://www.lesswrong.com/posts/KJ9MFBPwXGwNpadf2/skill-the-map-is-not-the-territory); sometimes, we are [confused about how things work](https://universalprior.substack.com/p/frankfurt-declaration-on-the-cambridge), sometimes we [treat complex systems as black boxes](https://www.lesswrong.com/posts/tPqQdLCuxanjhoaNs/reductionism), and some things are [not represented in our map](https://xkcd.com/1053/).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F06741a49-d8e3-48eb-9ad2-f223b6e3adf9_256x256.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F06741a49-d8e3-48eb-9ad2-f223b6e3adf9_256x256.png)On the left there’s a map, on the right there’s… Middle earth?

The entire scientific endeavor might be summarized as reducing discrepancies between map and territory. Traditionally, you would update the map according to what you see in the environment.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fe3cfb969-51eb-458f-ba2b-ec551052b347_1600x496.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fe3cfb969-51eb-458f-ba2b-ec551052b347_1600x496.png)Broke: Seeing that there is no dragon in your garage and giving up on the belief.

But if your metric is symmetric (and why would you call it a [metric](https://en.wikipedia.org/wiki/Metric_mathematics) otherwise?) then it's equally effective to change the territory.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc0227e96-7572-42a6-9dcd-d2166212c7d6_1600x462.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc0227e96-7572-42a6-9dcd-d2166212c7d6_1600x462.png)Woke: Believing in the dragon so hard that reality changes to match your belief.

Indeed, I think this is what motivates a substantial part of moral philosophy[2](https://universalprior.substack.com/p/belief-conditional-things-things#footnote-2-41815715): Instead of accepting the world as it is, we conjure our ideas about how things ought to be into reality. Thus, it's not unheard of that reality is affected by our beliefs. This opens the door for...

#  **Gödel's trick**

When thinking about existence and belief, it is natural to think of [epistemic logic](https://plato.stanford.edu/entries/logic-epistemic) \- the subfield of the philosophy of knowledge that formalizes how we form and maintain beliefs. This approach allows us to derive, under reasonable axioms, that [belief and knowledge collapse](https://link.springer.com/chapter/10.1007/3-540-16761-7_68). Formally, this means that believing in the existence of Santa Claus,

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fb718bdbf-8854-4b9b-a835-f5bb35aeede9_502x80.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fb718bdbf-8854-4b9b-a835-f5bb35aeede9_502x80.png)

implies knowledge of the existence of Santa Claus,

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F1c87d227-397e-4d86-b37c-5d4b3e35b243_510x80.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F1c87d227-397e-4d86-b37c-5d4b3e35b243_510x80.png)

And then, by using [axiom T](https://en.wikipedia.org/wiki/Modal_logic#Axiomatic_systems), we immediately arrive at the existence of Santa Claus[3](https://universalprior.substack.com/p/belief-conditional-things-things#footnote-3-41815715),

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F3195e342-9f64-4a18-b41d-c57cefb38f75_432x80.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F3195e342-9f64-4a18-b41d-c57cefb38f75_432x80.png)

I presume that this must be essentially equivalent to [Gödel's ontological proof](https://en.wikipedia.org/wiki/G%C3%B6del%27s_ontological_proof), although I (same as everybody else) haven't checked the details. Therefore, I will call this “Gödel’s trick"[4](https://universalprior.substack.com/p/belief-conditional-things-things#footnote-4-41815715); and epistemic logic turns out to be extremely useful once again.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fe9c657b8-048a-4a42-9b68-0ebdf1276521_256x256.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fe9c657b8-048a-4a42-9b68-0ebdf1276521_256x256.png)I guess this is supposed to read “Gödel, Kurt”. Almost, CGD, almost.

#  **No, really, there** _ **is**_ **a dragon in my garage.**

Any good rationalist might now counter: "Well, yes, belief might imply existence. But you don't actually believe in **X**. You only [believe that you believe](https://www.lesswrong.com/posts/CqyJzDZWvGhhFJ7dY/belief-in-belief) in **X**." The classic example is the "[dragon in the garage](http://people.whitman.edu/~herbrawt/classes/110/Sagan.pdf)" of Carl Sagan:

> "A fire-breathing dragon lives in my garage"   
> Suppose I seriously make such an assertion to you. Surely you'd want to check it out, see for yourself. There have been innumerable stories of dragons over the centuries, but no real evidence. What an opportunity!   
> "Show me," you say.   
> I lead you to my garage. You look inside and see a ladder, empty paint cans, an old tricycle — but no dragon.   
> "Where's the dragon?" you ask.   
> "Oh, she's right here," I reply, waving vaguely.   
> "I neglected to mention that she's an invisible dragon."   
> You propose spreading flour on the floor of the garage to capture the dragon's footprints.   
> "Good idea," I say, "but this dragon floats in the air."   
> Then you'll use an infrared sensor to detect the invisible fire.   
> "Good idea, but the invisible fire is also heatless."   
> You'll spray-paint the dragon and make her visible.   
> "Good idea, but she's an incorporeal dragon and the paint won't stick."   
> And so on. I counter every physical test you propose with a special explanation of why it won't work.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Feff78aca-47f2-48b0-9e0a-a4313d7a0399_256x256.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Feff78aca-47f2-48b0-9e0a-a4313d7a0399_256x256.png)Such a cool dragon 🤩

Carl Sagan argues that the person claiming a dragon in their garage doesn't _actually_ believe this. Their ability to [explain away](http://strategicreasoning.org/wp-content/uploads/2010/03/pami93.pdf) (ahead of time) all contradicting experimental evidence reveals that they accurately model the territory. They know exactly what to expect, given that there is no dragon in the garage. They might claim to believe **X** , but they only believe that they believe **X**.

But for Gödel's trick to work, we _actually_ need to believe **X**. Thus we have to stick our necks out and make falsifiable predictions. Saying, "Come to my garage and see the dragon. She's really cool!" is not the hard part. The hard part is [paying rent](https://www.lesswrong.com/posts/a7n8GdKiAZRX86T5A/making-beliefs-pay-rent-in-anticipated-experiences).

#  **Trolling your landlord.**

"Paying rent" in this context comes from the rationalist strategy of "[making your beliefs pay rent](https://www.lesswrong.com/posts/a7n8GdKiAZRX86T5A/making-beliefs-pay-rent-in-anticipated-experiences)". Beliefs are only allowed to stay in your head if they "pay" by making predictions about the world. If those predictions cash out, the belief is allowed to stay. If not, they will be kicked out. If you continuously claim that there is a dragon in your garage, and you make predictions accordingly, eventually the belief won't be able to pay anymore. Then you won't be able to use Gödel's trick.

But what is the "money" here? What is used to pay the rent? And what determines how much "money" the belief has?

In a [Bayesian framework](https://en.wikipedia.org/wiki/Bayesian_probability),[ beliefs are akin to probabilities](https://www.sciencedirect.com/science/article/pii/S0888613X03001506) and have a number between zero and one [associated with them](https://en.wikipedia.org/wiki/Credence_%28statistics%29), indicating how strong the belief is. Changes these numbers in a systematic way (that incorporates all the evidence optimally) is called [Bayesian belief updates](https://www.lesswrong.com/posts/XTXWPQSEgoMkAupKt/an-intuitive-explanation-of-bayes-s-theorem). On the road to believing **X** into existence, you might suffer severe setbacks. If you naively follow Bayes, these setbacks will reduce your belief until you end up not believing in the _belief-conditional thing_ **X** \- thus creating a self-fulfilling prophecy.

Luckily, we are now in the territory of mathematics, a field known to be highly susceptible to shenanigans. Most [mathematicians are trollable](https://www.lesswrong.com/posts/5bd75cc58225bf067037518c/all-mathematicians-are-trollable-divergence-of-naturalistic-logical-updates)[5](https://universalprior.substack.com/p/belief-conditional-things-things#footnote-5-41815715). It turns out that any Bayesian hit to our belief in **X** through new evidence can be counteracted by thinking about ways that **X** might be true after all. In particular, any sentence **A - > X** that you can prove (like ["Santa Claus exists and used to be a reclusive toymaker in the Far North"](https://en.wikipedia.org/wiki/Klaus_film) therefore "Santa Claus exists"[6](https://universalprior.substack.com/p/belief-conditional-things-things#footnote-6-41815715)) eliminates probability mass of **not X**. Repeated sufficiently many times, this procedure should allow us to believe in **X** sufficiently strong to believe **X** into existence - again, a self-fulfilling prophecy. Dreaming about **X** and picturing it with as many details as possible is thus a necessary step for making it real.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F4efbda1a-2e16-4028-a9d8-0bb8cafc6653_256x256.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F4efbda1a-2e16-4028-a9d8-0bb8cafc6653_256x256.png)A very formal troll.

Thus, through several loops and twists, we arrive at what every child can already tell you: Making belief-conditional-things exists only requires us to believe strongly, picture the thing in as many details as possible, and act as if it really can exist. Easy as that.

#  **Closing thoughts.**

Through the examples I have listed in the first section, I might have deceived you into exclusively thinking about fantastic and mystical creatures. But those are (by far) not the only examples of things that can only exist when we believe in them. [Mars colonies](https://www.youtube.com/watch?v=0agVZwux1Hs), [curing cancer](https://www.nature.com/articles/nrd.2017.243), and peace on earth are additional examples - in fact, most good things in the future are belief-conditional. Following the argument outlined above, we can believe belief-conditional thing **X** into existence by doing the following things: By changing the territory rather than our map, by providing as many viable avenues to achieve **X** as possible, and by sticking our necks out to perform tests while actually believing in the possibility of **X**. There might be more things we can do, and most of the ones I list might not apply in all situations. But this is for you to find out.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F2fd3b6d2-9955-42ee-bff3-6dce2d4cebda_256x256.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F2fd3b6d2-9955-42ee-bff3-6dce2d4cebda_256x256.png)A winter wonderland.

Thank you, dear reader. Happy holidays.

Subscribe

[1](https://universalprior.substack.com/p/belief-conditional-things-things#footnote-anchor-1-41815715)

as explained in the [Book of Jezuboad](http://unsongbook.com/chapter-3-on-a-cloud-i-saw-a-child/) and discussed [here](https://brill.com/view/journals/jocc/8/1-2/article-p149_8.xml)

[2](https://universalprior.substack.com/p/belief-conditional-things-things#footnote-anchor-2-41815715)

and, for that matter,[ larping](https://en.wikipedia.org/wiki/Live_action_role-playing_game).

[3](https://universalprior.substack.com/p/belief-conditional-things-things#footnote-anchor-3-41815715)

Please don't send me messages about how this is wrong. I _want_ to believe.

[4](https://universalprior.substack.com/p/belief-conditional-things-things#footnote-anchor-4-41815715)

My Substack, my rules.

[5](https://universalprior.substack.com/p/belief-conditional-things-things#footnote-anchor-5-41815715)

Admittedly,[ not every prior is trollable in this way](https://www.lesswrong.com/posts/CvKnhXTu9BPcdKE4W/an-untrollable-mathematician-illustrated), but last time I checked, the choice of prior is personal. So the power to believe is ours.

[6](https://universalprior.substack.com/p/belief-conditional-things-things#footnote-anchor-6-41815715)

This _is_ a valid inference (the antecedent does, in fact, imply the succedent) and even a true statement (if the antecedent is false, the implication is always true)!
