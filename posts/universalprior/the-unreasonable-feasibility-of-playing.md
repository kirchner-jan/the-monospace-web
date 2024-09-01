# The Unreasonable Feasibility Of Playing Chess Under The Influence

## TL;DR: The wonderful tradition of playing chess drunk, Marr's levels of analysis, AlphaZero, and Iterated Amplification and Distillation.

**Jan 12, 2022**

**Likes:** 3

# **A proud history of drinking and playing chess**

Please enjoy this clip of the reigning chess world champion Magnus Carlsen playing a game of [hyperbullet](https://en.wikipedia.org/wiki/Fast_chess#:~:text=controls%20are%20called%20%27-,hyperbullet,-%27%20and%20%27ultrabullet%27%20for) (30 sec total per player) while inebriated.

As the commenters are quick to point out, Magnus winning this game is partially due to his opponent blundering their Queen a couple of moves after Magnus takes over. But still. Even after a full night of sleep and being highly caffeinated I would struggle to _complete_ a game of chess in 30 seconds[1](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-1-46914010). Winning while chanting party bangers, and complaining about the state of one's own body, is kind of impressive.

Magnus is standing on the shoulders of giants in this game. Drinking and chess have been going hand in hand since at least [Paul Morphy](https://en.wikipedia.org/wiki/Paul_Morphy), whose family [started](https://www.chesshistory.com/winter/extra/alcohol.html#:~:text=Morphy%2C%20Murphy%20and%20beer) the [Murphy brewery](http://www.murphys.com/). Since Morphy, two former world champions stand out as particularly heavy drinkers, [Alexander Alekhine](https://en.wikipedia.org/wiki/Alexander_Alekhine) and [Mikhail Tal](https://en.wikipedia.org/wiki/Mikhail_Tal). The story of [Mikhail Tal](https://en.wikipedia.org/wiki/Mikhail_Tal), the Magician from Riga, is interesting as he was drinking and smoking _en masse_ while producing [more brilliancies](https://en.wikipedia.org/wiki/Mikhail_Tal#:~:text=more%20games%20by%20Tal%20than%20any%20other%20player)[2](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-2-46914010) than any other player.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F01812667-f146-4a62-90ee-6eaef84fc026_291x439.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F01812667-f146-4a62-90ee-6eaef84fc026_291x439.png)The Magician from Riga in his element.

His play under the influence might be the source of the common [urban myth](https://wegochess.com/does-alcohol-improve-chess-drunken-style/) that drinking might _improve_ one’s play. Tal's heavy drinking was likely not a character flaw, but [presumably](https://www.quora.com/Is-it-true-that-Mikhail-Tal-would-drink-heavily-even-on-nights-when-he-had-a-tournament-the-next-day-Would-he-have-been-an-even-better-player-without-this-way-of-living-or-did-it-add-to-his-wild-style-of-play) represented a type of [self-medication](https://en.wikipedia.org/wiki/Self-medication) for his congenital chronic illnesses. The same can not be said for another grandmaster, who triggered one of many[3](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-3-46914010) episodes of chess drama by drinking heavily and "[losing it](https://www.reddit.com/r/AnarchyChess/comments/gi6ysu/drunk_gm_hansen_losing_it_on_stream/)" live on Twitch during a chess streaming session. On the other hand, he was [awarded](https://www.youtube.com/watch?v=pCOiGL9--9I&ab_channel=CHESSMEMEX) the infamous title "best drunk chess player in the world" by world championship challenger [Fabiano Caruana](https://en.wikipedia.org/wiki/Fabiano_Caruana). Beyond the players, there is "[alcoholic chess](https://www.pinterest.de/pin/279786195576639442/)", the "[bongcloud opening](https://en.wikipedia.org/wiki/Bongcloud_Attack)", and of course, the recent Netflix hit show "[The Queen's Gambit](https://en.wikipedia.org/wiki/The_Queen%27s_Gambit_%28miniseries%29)" about a drug-addicted, female[ Bobby Fisher](https://en.wikipedia.org/wiki/Bobby_Fischer). Magnus Carlsen winning a game of hyperbullet after having a drink or two might appear impressive to an outsider - the aficionado just calls it "Tuesday".

#  **How do they do it?**

What's my point? I don't think we should be surprised that chess players drink alcohol. They are, visibly, human, which means the prior probability of them [having had a drink in the last year](https://ourworldindata.org/alcohol-consumption) is (based on location) somewhere between 60 and 100%. I couldn't find more specific numbers for Twitch streamers in their mid- or late-twenties, but you probably have a decent gut feeling for that demographic. Also, given the [stigma that chess is a game for four-eyes and dweebs,](https://www.reddit.com/r/chess/comments/a2ea2b/social_and_public_perception_of_chess_in_schools/) it's not surprising to find [countersignaling](https://en.wikipedia.org/wiki/Countersignaling) in the form of leather jackets and drug consumption. No mysteries there.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F556a6884-0273-435c-87ba-82418d0d9a49_1200x789.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F556a6884-0273-435c-87ba-82418d0d9a49_1200x789.png)Benny Watts, professional chess-playing “bad boy” from the [Queen's Gambit](https://en.wikipedia.org/wiki/The_Queen%27s_Gambit_\(miniseries\)).

The thing that boggles my mind is something else: _How_ can chess players get blackout drunk and still play decent chess? Chess was once [considered](https://twitter.com/martin_gorner/status/1199844865053347840) the [pinnacle](https://www.eapoe.org/works/essays/maelzel.htm) of human intellect. And while that perspective (perhaps rightfully) has [fallen out of favor](https://en.wikipedia.org/wiki/AI_effect), I'd like to circle back to the fact that the only way that I win against drunk Magnus Carlsen is when he literally [passes out during the game](https://www.quora.com/How-much-vodka-must-Magnus-Carlsen-drink-so-an-average-amateur-could-beat-him)[4](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-4-46914010).

In this post, I want to propose an analogy with the type of AI architecture that currently dominates computer chess, and which might give us some ideas for why grandmasters can play decent chess while drunk. Perhaps there is even something we can learn from inebriated humans that is interesting for AI.

#  **How to solve chess**

Which tool in our belt is best suited to understand complicated cognitive phenomena? [David Marr](https://en.wikipedia.org/wiki/David_Marr_%28neuroscientist%29)'s three[5](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-5-46914010) levels of analysis appear like a good match[6](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-6-46914010):

  1.  **computational level** : a formal description of what the system does.

  2.  **algorithmic level** : a step-by-step description of how a formal system can construct a solution.

  3.  **implementational level** : identification of a neural circuit that can implement the step-by-step description.




####  **Chess: the computational level.**

I find it very instructive to look back at the very early days of the computer[7](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-7-46914010) and to see what people came up with when confronted with this new toy. [After factoring a large number](https://en.wikipedia.org/wiki/History_of_software#:~:text=from%20the%20beginning.-,The%20very%20first%20time,-a%20stored%2Dprogram), researchers turned almost immediately to building a [theorem prover](https://en.wikipedia.org/wiki/Logic_Theorist), and then [in 1948: chess](http://billwall.phpwebhosting.com/articles/computer_chess_timeline.htm#:~:text=In%201948%20the%20UNIVAC). In the same year, Claude Shannon at Bell Labs published a [paper](https://vision.unipv.it/IA1/ProgrammingaComputerforPlayingChess.pdf) containing a strategy for, in theory, playing flawless chess on a computer. This strategy is now known as the [MiniMax decision rule](https://en.wikipedia.org/wiki/Minimax) and, informally, states that you should pick the chess move that gives you the best possible position (max), given that your opponent _afterward_ will choose the move that gives you the worst possible position (min).

What makes a position good or bad? If you care about winning, a position where you mate the opponent’s king is good, while a position where your own king is mated is bad[8](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-8-46914010).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F1fb07324-a2b5-4196-9dc7-5268ce8797dc_400x182.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F1fb07324-a2b5-4196-9dc7-5268ce8797dc_400x182.png)A schematic of a game tree, where some of the leaf nodes have a value of positive infinity (win) or negative infinity (lose). These values are propagated upwards in the tree, and at each level either the maximum or the minimum gets carried over.

In theory, determining if a move is good or bad requires only that the minimax decision rule is applied repeatedly. I pick a move that seems good for _me_ , then I put myself in my opponent’s shoes and pick a move that would be good for _them_ , at which I pick again a move that seems good for _me_ , etc. Eventually, we reach a position that is either a mate for _me_ or for _them_. Then I know that I won't go down that path in particular and I can go down a different path.

The problem with this becomes clear very quickly when we look at a portion of the tree with possible moves for a position late in the game:

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F7e0590ec-afa7-4074-9c69-31ac11d9a796_396x500.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F7e0590ec-afa7-4074-9c69-31ac11d9a796_396x500.png)A game tree from an endgame in chess based on the [analysis](https://www.amazon.com/Computers-Chess-Long-Range-Planning-Botvinnik/dp/B000QS7KLS) of former world champion Mikhail Botvinnik.

A moderate amount of possible moves at each level of the game tree results in [a combinatorial explosion](https://en.wikipedia.org/wiki/Combinatorial_explosion) and an [intimidating amount of possible chess positions](https://en.wikipedia.org/wiki/Shannon_number#:~:text=Shannon%27s%20calculation%5Bedit%5D-,Shannon,-showed%20a%20calculation). It's [not uncommon](https://www.quora.com/What-is-the-probability-that-at-a-given-point-of-time-a-particular-pattern-of-pieces-on-a-chess-board-during-a-game-is-unique-and-has-never-been-encountered-before-in-the-world#:~:text=The%20average%20length%20of%20a%20chess%20game%20is%20around%2040%20moves%3B%20given%20the%20distribution%20during%20the%20game%20I%20would%20estimate%20the%20overall%20percentage%20to%20be%20around%2050%25.) that within 20 to 30 moves the pieces on the board are in a position they have never been in before.

Claude Shannon's strategy was (and still is) impractical, but practicality is also not what we aim for at the computational level. Rather, **Shannon's MiniMax strategy provides us with a useful** _abstraction_ **through which we can analyze chess further with Marr's levels**.

####  **Chess: the algorithmic level.**

We will now brazenly skip half a century of chess history (including several [AI winters](https://en.wikipedia.org/wiki/AI_winter), the first computer to [beat the reigning world champion](https://en.wikipedia.org/wiki/Deep_Blue_%28chess_computer%29) in 1996, and [Centaur Chess](https://en.wikipedia.org/wiki/Advanced_chess)) and arrive almost in the present day. While humans have been completely outclassed on the chessboard for almost 30 years now, computer chess was characterized as "[solid and slow](https://www.theguardian.com/sport/2018/dec/11/creative-alphazero-leads-way-chess-computers-science)", taking no risks and grinding down their human opponents by accumulating tiny advantages. This changed with [AlphaZero](https://en.wikipedia.org/wiki/AlphaZero), a chess computer from the wonder factory that is Deepmind, with a playing style that is [a bit closer to the Romantics or Tal than most chess players would probably have expected](https://www.chess.com/article/view/7-games-that-transformed-chess). Grandmaster Peter Heine Nielsen [says](https://www.chess.com/article/view/7-games-that-transformed-chess#:~:text=the%20engine%27s%20games.%20%22-,After,-reading%20the%20%5BAlphaZero):

> After [...] seeing the games, I thought, 'well, I always wondered how it would be if a superior species landed on earth and showed us how they play chess. I feel now I know.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_lossy/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Faa144192-19f8-4136-8892-44320f056d27_720x720.gif)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Faa144192-19f8-4136-8892-44320f056d27_720x720.gif)Such a wild game. AlphaZero plays with white.

Why do people even still care about chess if no human has been able to compete with a computer for decades? On the one hand, chess has been called "[the drosophila of artificial intelligence](https://link.springer.com/chapter/10.1007/978-1-4613-9080-0_14)", i.e. a well-controlled model organism with, nonetheless, a rich repertoire of interesting behaviors. On the other hand, AlphaZero stood out for being trained exclusively through self-play (i.e. without access to human games), and still blazing past the best chess computer at the time [after just a few hours of training](https://www.theverge.com/2017/12/6/16741106/deepmind-ai-chess-alphazero-shogi-go).

And despite only playing with itself, there are some [striking parallels](https://arxiv.org/abs/2111.09259) in the concepts that emerge in the model compared to those that humans use to evaluate the game. Consistently, the play of AlphaZero has been described as [much more human-like](https://www.newyorker.com/science/elements/how-the-artificial-intelligence-program-alphazero-mastered-its-games#:~:text=that%20the%20engine%20%E2%80%9C-,plays%20like%20a%20human%20on%20fire,-.%E2%80%9D%20Quickly%2C%20Lc0%2C%20as) compared to previous chess computers. **On Marr's algorithmic level, AlphaZero appears like an interesting candidate to evaluate for our goal of understanding human chess playing**.

So how does AlphaZero work? It's in essence a product of a [recent revolution](https://universalprior.substack.com/p/serendipitous-connections-applying) in deep learning that allows the training of deeper and more capable neural networks. These networks are then used to bypass the problem of combinatorial explosion: instead of exploring _all_ the moves all the way to the end, the networks give reasonable suggestions for which moves appear particularly interesting, and which intermediate positions appear particularly favorable for which player. There are excellent explanations of the architecture [out](https://medium.com/applied-data-science/alphago-zero-explained-in-one-diagram-365f5abf67e0)[ there](https://nikcheerla.github.io/deeplearningschool/2018/01/01/AlphaZero-Explained/) from a machine learning engineering perspective, but for this post, I instead want to follow the lead of Paul Christiano.

####  **AlphaZero as an example of Iterated Amplification and Distillation.**

Paul Christiano [argues](https://ai-alignment.com/alphago-zero-and-capability-amplification-ede767bb8446) that the training procedure for AlphaZero can be interpreted as an instance of **Iterated Amplification and Distillation** (IAD)[9](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-9-46914010).

Conceptually, IAD requires three components:

  1. a prior distribution **p** over moves in a given position,

  2. an **amplification** procedure **A(p)** that can boost the performance of **p** (usually at the cost of runtime or storage),

  3. and a **distillation** procedure **p* = D(A(p))** that takes the boosted distribution **A(p)** as input and condenses it down to an updated prior distribution **p** * (usually at the cost of a bit of performance in exchange for a large speedup in runtime).




We can then **iterate** this procedure, and compute **p* =D(A(D(A(....D(A(p))))))**. If everything goes well, our prior **p** * will be getting better at every iteration, improving without bound or converging to a fixed point, **p*=D(A(p*))**.

For learning to play chess, we might start with a very poor prior distribution **p** , which suggests mostly terrible moves but still performs slightly above chance[10](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-10-46914010). In the previous section, we have already encountered a method to amplify the performance of this prior! Shannon's MiniMax strategy tells us that we can traverse the game tree, putting ourselves in the shoes of our opponent at every second level, to evaluate whether moves are good or bad for us. Doing this is costly (combinatorial explosion), but since our search is guided by our “slightly better than chance” prior, we have hope that some of the sequences of moves we explore end up relevant to the game. Using our prior **p** in conjunction with some amount of exploration of the game tree will, in effect, provide us with a slightly more accurate, or _amplified_ , distribution over moves in a position, **A(p)**.

Using **A(p)** to play chess was _de facto_ the way that all chess computers worked up until AlphaZero. People came up with ever cleverer prior distributions **p** and search strategies **A(p)** , and the superior speed and memory of modern computer systems were sufficient to leave human players in the dust. The novelty with AlphaZero[11](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-11-46914010) is the use of a **very deep neural network** to implement the prior **p**.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F70c63295-f521-4c6a-80c0-82f6291a45e8_1548x264.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F70c63295-f521-4c6a-80c0-82f6291a45e8_1548x264.png)The [ResNet](https://universalprior.substack.com/p/serendipitous-connections-applying) component of AlphaZero, [source](https://hackernoon.com/the-3-tricks-that-made-alphago-zero-work-f3d47b6686ef).

The big advantage of using this network is that there is a flexible operation for adopting the output of the network to a given target, the [backpropagation algorithm](https://en.wikipedia.org/wiki/Backpropagation). In the context of learning to play chess, the backpropagation algorithm allows us to perform the last step of IDA; given the move suggestions of the amplified prior **A(p)** , we can train an updated prior, **p*=D(A(p))** , which will reap some of the benefits of **A(p)** without having to perform the costly search!

And that's all the components we need to iterate the procedure, **p* =D(A(D(A(....D(A(p))))))** , and to see if we approach a fixed point[12](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-12-46914010).

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F4adb8f8b-ab2a-4fb2-939c-334fff67d783_600x262.gif)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F4adb8f8b-ab2a-4fb2-939c-334fff67d783_600x262.gif)Note that here AlphaZero is playing against a version of Stockfish that has already adopted the new trick of IAD.

Looks like it! The performance of AlphaZero against the leading chess computer StockFish increases monotonically over training and asymptotically reaches a level slightly above it[13](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-13-46914010).

We thus have a very powerful **algorithm-level** approximation to the ideal at the computational level. This implementation matches, and even outplays, Magnus Carlsen on his best day, while still playing in a distinctly human-like style. How might this algorithm be implemented in the brain? And, even more importantly, how can we make it drunk?

####  **Chess, the implementation level.**

The kicker of Marr's method is that once we have a particular algorithmic implementation, we can set out and try to find neural correlates. We have no guarantee of finding these correlates - in general, there are multiple possible algorithmic implementations, and there are no theoretical guarantees that we pick the one that evolution picked[14](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-14-46914010).

But I have a good feeling about this one. Let's see how far we can get.

 **Where's the prior?** First, which part of the brain might implement the neural network that computes the prior **p** for a given position? Given three decades of functional brain imaging, you'd expect that we have a pretty decent idea about which brain areas are active when chess experts evaluate a position?

Yeah, that would be nice, wouldn't it? [Studies](https://www.nature.com/articles/35088119)[ from the 90s](https://scite.ai/reports/non-dominant-dorsal-prefrontal-activation-during-chess-PKa4rm) highlight the importance of frontal and parietal areas.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F10821514-0537-4f7d-b80d-6809006a71c5_767x542.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F10821514-0537-4f7d-b80d-6809006a71c5_767x542.png)

Then, in the [2000s](https://jov.arvojournals.org/article.aspx?articleid=2131186) it was in vogue to attribute every kind of expert-level skill with a [recurring guest](https://universalprior.substack.com/p/serendipitous-connections-applying) on this Substack, the fusiform face area.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F0da2ee65-942c-44ab-a0ad-3173e5468c93_767x542.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F0da2ee65-942c-44ab-a0ad-3173e5468c93_767x542.png)The arrows are supposed to point to the _inside_ of the lobe.

The [2010s](https://www.sciencedirect.com/science/article/abs/pii/S0304394011006471) were marked by a shift of focus towards the posterior cingulate, orbitofrontal cortex, and right temporal cortex.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F559b4b51-f67b-443c-a7b9-84651cda2897_767x542.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F559b4b51-f67b-443c-a7b9-84651cda2897_767x542.png)Again, the arrows are supposed to point to the _inside_ of the lobe.

For [2019](https://www.sciencedirect.com/science/article/abs/pii/S0031938418309351?dgcid=api_sd_search-api-endpoint) I found a paper where researchers found that the parietal cortex tends to be more involved in chess games in the rapid format (10 minutes + 10 seconds increment) than in the lightning format (1 minute), p=0.045.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F1c571e03-331e-4e89-955f-19cab99d1584_767x542.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F1c571e03-331e-4e89-955f-19cab99d1584_767x542.png)

And then nothing too enlightening since then.

If I was [Scott Alexander](https://astralcodexten.substack.com/p/ivermectin-much-more-than-you-wanted) or [Zvi](https://thezvi.substack.com/p/omicron-post-13-outlook) I'd comb through those papers and wring out insight. Maybe I can take into account that something like the "[peak of the replication crisis in medicine](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4915619/)" hit in 2016, and discredit things before that strongly? Maybe I can go through the methodologies, evaluate each paper based on its merits, and assemble a coherent whole that explains discrepancies through differences in experimental design?

I can't bring myself to do that. And I also don't think I _have to_. In AlphaZero the prior **p** is computed from a deep neural network that receives the board position and a possible move as input and returns an estimate for how good this move appears. This type of pattern processing is pretty much what [the cortex overall is best at](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4141622/). In fact, it might [not be too much of a stretch](https://www.alignmentforum.org/posts/diruo47z32eprenTg/my-computational-framework-for-the-brain#:~:text=it%27s%20highly%20structured%20to%20remember%20particular%20kinds%20of%20patterns%20and%20their%20relationships) to characterize the cortex as one big prediction machine. So let's just say that the prior **p** might probably be computed _somewhere_ in the cortex.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F99529aa3-2018-4c03-a2c2-0ece0d5fdfa9_767x542.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F99529aa3-2018-4c03-a2c2-0ece0d5fdfa9_767x542.png)

This sounds vague, but it still excludes subcortical regions, the cerebellum, and the [extended mind thesis](https://en.wikipedia.org/wiki/Extended_mind_thesis). So it's better than nothing!

 **Where's the amplifier?** The second important IAD component of AlphaZero is the amplification mechanism that boosts the prior **p** through exploration of the game tree. To identify a neural correlate, I first need to fill you in on a detail that I glossed over earlier: AlphaZero needs to have the rules of chess explicitly encoded, which is a big discrepancy to how the brain does it (most people are not [Misha Osipov](https://www.google.com/search?q=misha+chess&oq=misha&aqs=chrome.1.69i57j69i59j0i512l2j46i512j0i512l2j46i512l2j0i512.2937j0j7&sourceid=chrome&ie=UTF-8#:~:text=PREVIEW,Jan%2024%2C%202017) and have to learn the rules first). But a new version, called [MuZero](https://deepmind.com/blog/article/muzero-mastering-go-chess-shogi-and-atari-without-rules), is also able to learn the rules of chess (and Shogi, Go, and Atari games), in addition to the prior **p** *, just from playing the game.

This type of learning is called _model-based_ learning, and it's totally [stolen from neuroscience](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3570165/). Neuroscientific theories of model-based learning originally emerged from [research on motor learning](https://pubmed.ncbi.nlm.nih.gov/12662535/), where an internal "forward" model of the body's movement can help master complex behaviors. Interestingly, [there is a very strong candidate](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3570165/#:~:text=most%20likely%20neural%20substrate%20of%20putative%20internal%20models) for implementing the forward model in the brain: the cerebellum.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fe79a7ef3-ef83-4fc0-bd4f-b907abf26d42_767x542.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fe79a7ef3-ef83-4fc0-bd4f-b907abf26d42_767x542.png)

Finally some answers! Could it be that the cerebellum is the neural correlate of the amplifier? Turns out, [people](https://www.sciencedirect.com/science/article/abs/pii/S1364661398012236) have been thinking about this for more than 20 years. [Ito (2008)](https://www.nature.com/articles/nrn2332) says:

> The intricate neuronal circuitry of the cerebellum is thought to encode internal models that reproduce the dynamic properties of body parts. [...] It is thought that the cerebellum might also encode internal models that reproduce the essential properties of mental representations in the cerebral cortex.

And here is [Steinlin (2007)](https://link.springer.com/article/10.1080/14734220701344507), who summarizes insights on the role of the cerebellum in development:

> The cerebrum might be like a glider, which needs the cerebellum as the motor aeroplane to bring it up in the air – once there, the glider is able to fly alone. But any troubles during this flight might bring it down again and the cerebellar motor aeroplane has to help once more to regain altitude!

Looking past the flowery language, this matches exactly what we would expect from a converged solution in IDA. Once the application of the amplification and distillation mechanism does not change the prior **p** * anymore, **p* =D(A(D(A(....D(A(p))))))** , their absence should not matter.

(There is even [a bit of evidence](https://pubmed.ncbi.nlm.nih.gov/16255391/) on the cerebellum being involved in chess playing but _only_ in novices. But, actually, this bit of evidence does not pass the bar that I put up in the previous section where I talked about fMRI. So let's scratch this last part.)

 **Getting a neural network drunk.**

Now we've moved all the pieces (no pun intended) in the right position to think about how Magnus Carlsen can still win at chess while intoxicated.

1\. **What does (acute) alcohol consumption do to the brain?**[ Bjork and Gilman (2014)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3971012/) have an answer:

> > [W]hile there are some discrepancies in specific regional effects of acute alcohol on the resting brain and on the brain at work, the preponderance of evidence indicates that **acute alcohol exerts region-specific suppression (e.g. cerebellum)** or enhancement (e.g. ventral striatum) of brain metabolic or hemodynamic activity, and by inference, neuronal activity.

This is, of course, no coincidence since if this wasn't the case I wouldn't have led you down this entire chain of logic.

2. **What happens to AlphaZero when we force it to only rely on its prior p for playing chess?** We don't know. But we know the next best thing, which is what happens to AlphaZero when we force it to only rely on its prior **p** for playing _Go_ :

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fe2f2867e-942a-400c-87e8-42daa11a8841_324x800.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fe2f2867e-942a-400c-87e8-42daa11a8841_324x800.png)Estimated difference in elo rating between the full AlphaZero model (blue) and the model restricted to the prior **p** (grey). Adapted from [Silver et al., 2017](https://www.nature.com/articles/nature24270).

About a 40% reduction in rating. Substantial, but still enough to put it [neck-at-neck with a human professional](https://www.lesswrong.com/posts/HAMsX36kCbbeju6M7/is-alphazero-any-good-without-the-tree-search?commentId=th3qptQoPFFYgqhR6).

3\. **How much worse does Magnus Carlsen play under the influence?** Carlsen recently set a new record for the[ highest bullet chess rating ever on Lichess](https://lichess.org/@/Kingscrusher-YouTube/blog/magnus-carlsen-creates-new-all-time-bullet-rating-record-11th-november-2021/kTiFcikR): 3379. Giving up 40% of rating points would knock him down to a rating of ~2000. His opponent from the beginning is rated 2500, making a win rather unlikely:[ only around 1%](https://wismuth.com/elo/calculator.html#rating1=2000&rating2=2500). But then again;[ anything is possible in bullet](https://en.wikipedia.org/wiki/Fast_chess#:~:text=%C2%A0Kazakhstan-,Criticism,-%5Bedit%5D), and this particular game has collected north of half a million views. Also, it's unlikely that alcohol knocks out the _entire_ amplification mechanism of the brain (not all of which will be located in the cerebellum).

It would be great to have more solid data on how alcohol affects play. Anecdotally, [Carlsen quit drinking](https://slate.com/culture/2020/02/magnus-carlsen-speed-chess-drdrunkenstein-pseudonyms-twitch-youtube.html#:~:text=Carlsen%20admits%20he%20quit) a while back for health reasons (and [after "sandbagging" the fifth Lichess Titled Arena](https://slate.com/culture/2020/02/magnus-carlsen-speed-chess-drdrunkenstein-pseudonyms-twitch-youtube.html#:~:text=I%20thought%20Carlsen%20was%20sandbagging%20these%20tournaments%20to%20make%20it%20interesting)). [This](https://wegochess.com/does-alcohol-improve-chess-drunken-style/) blog post talks at length about the detrimental effect of alcohol on chess play but does not list any sources. Opinions on the [Chess Forum](https://www.chess.com/forum/view/livechess/alcohol--chess--bad-or-good-idea) are divided.

#  **Concluding thoughts**

Should we feel less amazed at Carlsen’s intoxicated chess play, after all the above? Quite the contrary, thinking about _how_ something works can allow us to [appreciate at an even deeper level](https://www.lesswrong.com/posts/x4dG4GhpZH2hgz59x/joy-in-the-merely-real). And despite not really drinking too much myself, I _do_ have a few ideas for a couple of small experiments that really shouldn’t be too much effort…

Back to the point, is there anything we can say about artificial intelligence from these experiments? First, I find it interesting that performance deteriorates so much when relying only on the prior **p**. From one perspective this _does_ make a lot of intuitive sense, disabling a central component of the model _should_ affect performance. And it would be weird to play chess without _any_ consideration of what the opponent will likely do.

From another perspective, it is still a bit surprising. Performance deteriorating implies that the prior **p** is not yet a fixed point of **p*=D(A(p*))**. Possibly this is because the network that implements **p** is not able to distill any further amplification? Or is distillation impossible _in principle_ beyond a certain point? Or am I taking the IDA interpretation of AlphaZero too far? Who can tell? In any case, it is pretty amazing that computer chess continues to provide so many interesting questions, despite the match DeepBlue vs. Kasparov already being 25 years ago. As the great poet [#IAN](https://universalprior.substack.com/p/making-of-ian) used to say:

>  _There are two kinds of players: those who can play and those who can't. "Charles Darwin"_

* * *

A big thank you to Philipp Hummel for giving me the central insight of this post, and for very helpful proofreading.

If you enjoyed this post and want to receive a notification for my next post, consider subscribing (it’s free and will stay free!)

Subscribe

[1](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-anchor-1-46914010)

Much less _win_ against a 2400 opponent.

[2](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-anchor-2-46914010)

A term in chess that is not rigorously defined, but roughly equates to " **an extremely powerful move that is usually not obvious but that almost automatically wins** (or draws, if you are losing) the game. Some would call this move a “brilliant” one".[ source](https://www.quora.com/How-would-you-define-a-brilliancy-in-chess)

[3](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-anchor-3-46914010)

Who would have thought!

[4](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-anchor-4-46914010)

At which point I'd have decent drawing chances.

[5](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-anchor-5-46914010)

The[ original paper actually lists four](https://dspace.mit.edu/handle/1721.1/5782), but they are confusing.

[6](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-anchor-6-46914010)

Actually, it's the only tool I have. Send help. Or more tools.

[7](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-anchor-7-46914010)

Despite being so relatively recent, it is very hard to find a source that is reasonably complete and correct. Almost everyone ignores[ Konrad Zuse](https://en.wikipedia.org/wiki/Konrad_Zuse), or those who don't ignore him ignore everything else. I spent way too much time diving into this a few years ago, but it seems super relevant to me.

[8](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-anchor-8-46914010)

A draw is simply a disgrace and should be avoided whenever possible.

[9](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-anchor-9-46914010)

Or "Iterated capability amplification". Terminology is not quite set in stone yet.

[10](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-anchor-10-46914010)

To get this, we might instantiate the prior randomly and then make it perform slightly better than random by creating two copies of the system and adopting the prior through traditional reinforcement learning and self-play. This is where the _grounding_ of the prior comes from.

[11](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-anchor-11-46914010)

Am I being unfair to the people who came up with this using[ neural networks for chess in 1999](https://www.chessprogramming.org/Neural_Networks#:~:text=generalized%20AlphaZero%20algorithm.-,Move%20Ordering,-Concerning%20move%20ordering)? Possibly.

[12](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-anchor-12-46914010)

In case somebody who worked on the project ever reads this: Please don't be mad. I can't imagine the amount of blood, sweat, and tears that went into this.

[13](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-anchor-13-46914010)

[Stockfish](https://en.wikipedia.org/wiki/Stockfish_%28chess%29), the goliath of computer chess, has by now caught up and overtaken the record set by AlphaZero.

[14](https://universalprior.substack.com/p/the-unreasonable-feasibility-of-playing#footnote-anchor-14-46914010)

There are, however, weak hand-wavy arguments for why we might be lucky sometimes. In particular, the[ more general an algorithm, the more robust it tends to be to perturbations](https://deepmind.com/blog/article/generally-capable-agents-emerge-from-open-ended-play). Robustness is something that evolution "cares" a lot about. Generality is something that DeepMind cares a lot about (see also[ MuZero](https://deepmind.com/blog/article/muzero-mastering-go-chess-shogi-and-atari-without-rules)). Perhaps the number of totally general algorithm that can do all the things humans do is not _that_ large? Sounds plausible, right?
