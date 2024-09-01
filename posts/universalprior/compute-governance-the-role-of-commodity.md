# Compute Governance: The Role of Commodity Hardware

## TL;DR: Thoughts on whether CPUs can make a comeback and become carriers of the next wave of machine learning progress (spoiler: they probably won't). Meditations on challenges in compute governance.

**Mar 26, 2022**

**Likes:** 3

_Meta: As long-term readers know,[sometimes](https://universalprior.substack.com/p/cognitive-biases-in-large-language?s=w) [I](https://universalprior.substack.com/p/drug-addicts-and-deceptively-aligned?s=w) [switch](https://universalprior.substack.com/p/puberty-as-cause-x?s=w) into my academic mode and write semi-formal posts analyzing a topic. This is such a post, summarizing some of the things I learned after doing a deep dive into a subfield of AI Safety._

Over the coming decades, [we might see](https://www.lesswrong.com/posts/KrJfoZzpSDpnrv9va/draft-report-on-ai-timelines) machines that are as smart or smarter than humans. It is possible that these smarter-than-human machines will be built to work on our behalf and to greatly increase human welfare, such as by curing diseases and expanding economic opportunity. But simultaneously there are high risks if we build these machines with goals that are too narrow and that don't represent our broader values. The field concerned with working towards positively shaping artificial intelligence (AI) is called AI Safety ([Wiblin, 2017](https://80000hours.org/problem-profiles/positively-shaping-artificial-intelligence/)).

There are two complementary avenues for ensuring that humanity successfully navigates the transition into a world with advanced AI systems: [Technical AI Safety](https://80000hours.org/topic/priority-paths/technical-ai-safety/) and [AI Governance](https://80000hours.org/articles/ai-policy-guide/). While Technical AI Safety is concerned with developing algorithms and frameworks for making safe AI _possible_ , AI governance is concerned with how institutions make decisions about AI and with ensuring that AI is deployed safely ([Dafoe 2020](https://www.allandafoe.com/opportunity)).

 **Compute Governance** is the subfield of AI Governance concerned with controlling and governing access to computational resources ([Heim 2021](https://forum.effectivealtruism.org/posts/g6cwjcKMZba4RimJk/compute-governance-and-conclusions-transformative-ai-and); [Anderljung and Carlier 2021](https://forum.effectivealtruism.org/posts/kvkv6779jk6edygug/some-ai-governance-research-ideas)). Among different candidates for effective AI governance, Compute Governance stands out as particularly promising due to two factors:

  1. We can monitor possession and usage of large-scale computing resources comparatively well. Large-scale computing requires physical space for the computing hardware and substantial supporting infrastructure.

  2. Access to large-scale computing resources can be monitored and governed as the supply chain for advanced semiconductor production is concentrated on a few key producers.




In this post, I will explore possible implications on Compute Governance of a recently proposed technique for accelerating progress in AI research ([Chen et al. 2019](https://arxiv.org/abs/1903.03129)).

#  **State of Compute Governance, “AI-specialized” and “commodity” hardware**

To properly contextualize the proposed technique, I will briefly summarize the state of Compute Governance. A series of reports from the Center for Security and Emerging Technology ([CSET](https://cset.georgetown.edu/)) examines the supply chain for computing resources ([Khan et al.,2021](https://cset.georgetown.edu/publication/the-semiconductor-supply-chain/)). In particular, the reports 

  * highlight governable hardware chokepoints ([Flynn and Khan, 2020](https://cset.georgetown.edu/publication/multilateral-controls-on-hardware-chokepoints/)), 

  * explore international differences in production capabilities ([Khan 2019](https://cset.georgetown.edu/publication/maintaining-the-ai-chip-competitive-advantage-of-the-united-states-and-its-allies/);[ Hunt, Khna, Peterson, 2021](https://cset.georgetown.edu/publication/chinas-progress-in-semiconductor-manufacturing-equipment/)), 

  * and outline concrete policy interventions for avoiding dangerous multipolar race dynamics ([Khan, 2020](https://cset.georgetown.edu/publication/u-s-semiconductor-exports-to-china-current-policies-and-trends/);[ Khan, 2021](https://cset.georgetown.edu/publication/securing-semiconductor-supply-chains/)). 




Results from this research have been presented before the U.S. Senate Foreign Relations Committee ([Khan March 2021](https://cset.georgetown.edu/publication/testimony-before-senate-foreign-relations-committee/)) and have received substantial media attention ([PR1](https://cset.georgetown.edu/article/cset-experts-in-the-news)-[PR10](https://cset.georgetown.edu/article/cset-experts-in-the-news-10/)).

However, existing proposals for effective Compute Governance consistently make one central, simplifying argument: that research in advanced AI _requires_ leading-edge, **AI-specialized hardware**. AI-specialized hardware is "computer chips that not only pack the maximum number of transistors [...] but also are tailor-made to efficiently perform specific calculations required by AI systems" ([Khan April 2020](https://cset.georgetown.edu/publication/ai-chips-what-they-are-and-why-they-matter/)). This AI-specialized hardware is up to a thousand times more efficient than traditional **commodity hardware** , translating into a technological advantage equivalent to ~20 years of [Moore's Law](https://en.wikipedia.org/wiki/Moore%27s_law)-driven improvements over CPUs. Consequently, commodity hardware is typically not the focus of analyses of the supply chain and proposed policy interventions.

While most cutting-edge research occurs on AI-specialized hardware ([Amodei and Hernandez 2018](https://openai.com/blog/ai-and-compute/)), it is unclear whether this is necessary or merely convenient. Furthermore, recent progress in algorithmic efficiency ([Ye et al. 2021](https://arxiv.org/abs/2111.00210); [Hernandez and Brown 2020](https://openai.com/blog/ai-and-efficiency/)) casts doubt on whether access to AI-specialized hardware will continue to be the main factor driving performance gains. 

# **Commodity hardware might outperform AI-specialized hardware**

Much of the performance advantage of AI-specialized hardware comes from sacrificing flexibility for efficiency ([Heim 2021](https://forum.effectivealtruism.org/s/4yLbeJ33fYrwnfDev/p/YNB39RyJ7iAQKGJvq#Chip_Architectures__From_Flexibility_to_Efficiency)). In particular, as the pivotal operations of learning in deep networks are ["embarrassingly parallel"](https://www.wikiwand.com/en/Embarrassingly_parallel) operations (dense matrix multiplication), AI-specialized hardware sacrifices sequential processing speed for increased parallel processing bandwidth ([Gupta 2020](https://developer.nvidia.com/blog/cuda-refresher-reviewing-the-origins-of-gpu-computing/)). Embracing this trade-off has been the primary driver behind the impressive increase in computational capabilities of AI-specialized hardware ([Sato et al. 2017](https://cloud.google.com/blog/products/ai-machine-learning/an-in-depth-look-at-googles-first-tensor-processing-unit-tpu)).

But what if this is [wasteful](https://youtu.be/l4RrGRxkgYI?t=1872)? Intuitively, each input into an artificial neural network should only activate a tiny fraction of all units. The [nonlinear activation function](https://machinelearningmastery.com/rectified-linear-activation-function-for-deep-learning-neural-networks/) of individual units guarantees that a substantial portion of units in each layer will not be activated at all. Techniques that adaptively silence a large portion of all units ([Ba and Frey, 2013](https://papers.nips.cc/paper/2013/hash/7b5b23f4aadf9513306bcd59afb6e4c9-Abstract.html)) or promote winner-takes-all dynamics ([Makhzani and Frey](https://papers.nips.cc/paper/2015/hash/5129a5ddcd0dcd755232baa04c231698-Abstract.html)) can improve network performance. Interestingly, neural activity in the biological brain across different species and brain areas is sparse because only a handful of neurons activate in response to each stimulus ([Olshausen and Field, 2004](https://www.sciencedirect.com/science/article/abs/pii/S0959438804001035)). We might thus expect that a substantial fraction of computations performed to determine the activation of units does not affect the network's output.

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fd8a31180-0846-4dd2-b84f-7293aa74e16c_1409x1600.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fd8a31180-0846-4dd2-b84f-7293aa74e16c_1409x1600.png)An illustration of sparse network activation. Due to the choice of [ReLu activation function](https://machinelearningmastery.com/rectified-linear-activation-function-for-deep-learning-neural-networks/), a substantial number of units will be “silent” during a typical forward pass.

The traditional formulation of a deep network's inference and learning operations does not take this sparsity into account. Even though only a small portion of units might activate for each input, the connections between _all_ units of an artificial network update in response. Especially in the case of large [networks with 100s of millions, billions, or even trillions of parameters](https://huggingface.co/blog/large-language-models), disregarding sparsity can be extremely costly.

Researchers from the [Shrivastava lab](https://www.cs.rice.edu/~as143/) present a novel approach ([Chen et al. 2019](https://arxiv.org/abs/1903.03129)). Rather than computing activation and weight changes for all units in the network, they employ a technique called [Locality Sensitive Hashing](https://en.wikipedia.org/wiki/Locality-sensitive_hashing) to identify only those units likely to activate. While Locality Sensitive Hashing was conceived initially as a method for efficient search ([Indyk and Motwani 1998](https://dl.acm.org/doi/10.1145/276698.276876)), previous research from the Shrivastava lab demonstrates that we can also use it for computationally efficient _sampling_ of candidates likely active units ([Spring and Shrivastava](https://arxiv.org/abs/1703.05160)). Importantly, **reformulating the inference and learning operations of a deep network as a sampling problem allows them to sidestep the requirement for AI-specialized hardware and instead exploit the strengths of commodity hardware.**

[![](https://substackcdn.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fb530d7a2-52b0-4545-902c-9cc8586b2031_1600x1394.png)](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fb530d7a2-52b0-4545-902c-9cc8586b2031_1600x1394.png)Accuracy on the Amazon 670k dataset from the [extreme classification repository](http://manikvarma.org/downloads/XC/XMLRepository.html) as a function of training time (log-scale) for three methods (red being the new method introduced by Chen et al.). Adapted from Chen et. al.

Indeed, their proposed implementation on commodity hardware, called "Sub-LInear Deep learning Engine" (SLIDE), outperforms AI-specialized hardware. Using SLIDE, Chen and colleagues can achieve 3.5 times faster training on commodity hardware (44 cores CPU) than AI-specialized hardware (Tesla V100). In collaboration with researchers from Intel, they were able to improve performance even further to a speedup of up to 7 times by exploiting advanced features of commodity hardware ([Daghaghi et al., 2021](https://arxiv.org/abs/2103.10891)). With the venture-funded startup [ThirdAI](https://www.thirdai.com/team/), Shrivastava and colleagues are now developing an "algorithmic accelerator for training deep learning models that can achieve or even surpass GPU-level performance on commodity CPU hardware" ([Bolt 2021](https://www.thirdai.com/bolt-overview/)). While the software is still closed alpha, a recent blog post [announced](https://www.thirdai.com/cpu-or-gpu/) the successful training of a 1.6 billion parameter model on CPUs. This research suggests that AI researchers' heavy reliance on AI-specialized hardware might not be necessary and that commodity hardware can achieve equal or greater performance.

#  **Implications of Efficient Commodity Hardware on Compute Governance**

Before analyzing some of the caveats and weaknesses of the proposed approach, I want to take the published results at face value and mention implications. If broadly adopted, a shift away from AI-specialized hardware to commodity hardware would have significant implications for AI Safety in general and Compute Governance in particular.

 **Timeline speedup.** A speedup of training by a factor of 7 (as suggested by [Daghaghi et al. 2021](https://arxiv.org/abs/2103.10891)) would translate into a shortening of AI timelines by at least 6-7 years ([Cotra 2020](https://www.alignmentforum.org/posts/KrJfoZzpSDpnrv9va/draft-report-on-ai-timelines)). While commodity hardware is somewhat less affected by the current chip shortage, the proposed hardware configuration by [Chen et al. (2019)](https://arxiv.org/abs/1903.03129) is (surprisingly) not cheaper[1](https://universalprior.substack.com/p/compute-governance-the-role-of-commodity#footnote-1-50757471). Beyond the training speedup, we should not expect sustained additional speedup of timelines due to price and availability.

 **Leveraging existing hardware.**[Existing supercomputers](https://en.wikipedia.org/wiki/Fugaku_\(supercomputer\)) run on "commodity hardware that we might leverage for AI applications. Making the strong assumption that the software architecture carries over without a problem, the Fugaku supercomputer could replicate [AlphaGo Zero](https://openai.com/blog/ai-and-compute/) in under a week.

 **Commodity hardware designers.** While Nvidia and AMD dominate the design for AI-specialized hardware, designs for leading commodity hardware are instead dominated by Intel and AMD ([Khan January 2021](https://cset.georgetown.edu/publication/securing-semiconductor-supply-chains/)). As every system using AI-specialized hardware also contains commodity hardware, and as Intel is one of three remaining companies operating state-of-the-art fabs, Intel is a central actor in Compute Governance either way. Intel's role might become central depending on the importance of commodity hardware as a driver for progress in AI research.

 **Secondary markets.** There exists a much larger secondary market for used commodity hardware than for AI-specialized hardware. It is conceivable that bad actors can bypass existing policies restricting access to AI-specialized hardware by buying commodity hardware on the second market.

#  **Limiting factors and open questions**

After presenting the argument for the use of commodity hardware in accelerating AI research, I now want to highlight that there are considerable limitations and reasons for doubting this outcome.

 **Outside view.** Suppose the results by [Chen et al. (2019)](https://arxiv.org/abs/1903.03129) hold in full generality. In that case, they might represent a paradigm shift for AI research by making both classical gradient descent and AI-specialized hardware obsolete. While such paradigm shifts are not unprecedented, they are rare. This observation implies a low prior probability for success to any proposal with seemingly radical implications. Furthermore, while deep learning in research and industry already extensively uses CPUs in their usual function, the proposed method has not found widespread adoption ([Mittal et al., 2021](https://ieeexplore.ieee.org/document/9410437)). The rapid adoption of f.e. the transformer in almost all areas of AI within three years ([Wies et al. 2021](https://arxiv.org/pdf/2105.03928.pdf)) stands in stark contrast, and further decreases the likelihood that commodity hardware represents a paradigm shift for AI research.

 **Technical limitations**. In the framework proposed by [Chen et al. (2019)](https://arxiv.org/abs/1903.03129), the choice of the exact Locality Sensitive Hashing function is left open and depends on the type of modeled data. Follow-up work ([Chen et al. 2020](https://openreview.net/forum?id=wWK7yXkULyh)) salvages this shortcoming while further complicating the method. Furthermore, the proposed technique requires that activity in the deep network is sparse, i.e. each input only activates a small number of units. However, different machine learning architectures exhibit differing degrees of sparsity ([Loroch et al. 2018](https://www.arxiv-vanity.com/papers/1808.08784/)), so that this assumption does not hold in general.

 **Scalability.** As discussed in the previous section, it is unclear whether the proposed technique would scale up naturally to extremely large computing systems like the [Fugaku supercomputer](https://en.wikipedia.org/wiki/Fugaku_\(supercomputer\)). Avoiding diminishing (or even disappearing) returns when scaling up AI-specialized hardware to trillion parameter models is an active area of research ([Rajbhandari et al. 2019](https://arxiv.org/abs/1910.02054); [Shoeybi et al. 2020](https://arxiv.org/abs/1909.08053)). Thus, while commodity hardware might be able to replace AI-specialized hardware in smaller computing systems, this translation might well break down once we attempt to scale up the systems.

#  **Conclusions and Outlook**

Despite the limitations of the approach highlighted in the previous section, this analysis has uncovered a number of insights relevant to Compute Governance that apply more broadly.

 **Algorithmic and Hardware efficiency.** As hardware appears much more governable than software, it is tempting to focus exclusively on controlling hardware and neglecting software. But as progress in AI results from _both_ algorithmic and hardware efficiency increases ([Hernandez and Brown 2020](https://openai.com/blog/ai-and-efficiency/)), any policy proposal for Compute Governance should carefully consider current developments in algorithmic efficiency and possible interactions between hardware and software.

 **Changes in hardware.** It is not clear that future AI systems will rely on the AI-specialized hardware of the present. Policies seeking to govern the deployment and impact of AI in the mid- to long-term will have to take this possibility into account and monitor new developments in computer architectures ([Hennessy and Patterson 2019](https://dl.acm.org/doi/10.1145/3282307)).

 **Importance of commodity hardware.** Even though leading AI research usually requires AI-specialized hardware, commodity hardware still plays a central supporting role ([Mittal et al., 2021](https://ieeexplore.ieee.org/document/9410437)). Commodity hardware thus represents a potentially powerful additional lever for executing Compute Governance policies.

[1](https://universalprior.substack.com/p/compute-governance-the-role-of-commodity#footnote-anchor-1-50757471)

They use a top-of-the-range CPU machine and compare it with a mid-range GPU machine.