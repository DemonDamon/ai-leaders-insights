# Safety-first AI for autonomous data center cooling and industrial control

**来源**: [https://blog.google/inside-google/infrastructure/safety-first-ai-autonomous-data-center-cooling-and-industrial-control/](https://blog.google/inside-google/infrastructure/safety-first-ai-autonomous-data-center-cooling-and-industrial-control/)

---

# Safety-first AI for autonomous data center cooling and industrial control

原文链接: https://blog.google/inside-google/infrastructure/safety-first-ai-autonomous-data-center-cooling-and-industrial-control/

# Safety-first AI for autonomous data center cooling and industrial control

Aug 17, 2018

·

Share

[Twitter](https://twitter.com/intent/tweet?text=Safety-first%20AI%20for%20autonomous%20data%20center%20cooling%20and%20industrial%20control%20%40google&url=https://blog.google/inside-google/infrastructure/safety-first-ai-autonomous-data-center-cooling-and-industrial-control/)
[Facebook](https://www.facebook.com/sharer/sharer.php?caption=Safety-first%20AI%20for%20autonomous%20data%20center%20cooling%20and%20industrial%20control&u=https://blog.google/inside-google/infrastructure/safety-first-ai-autonomous-data-center-cooling-and-industrial-control/)
[LinkedIn](https://www.linkedin.com/shareArticle?mini=true&url=https://blog.google/inside-google/infrastructure/safety-first-ai-autonomous-data-center-cooling-and-industrial-control/&title=Safety-first%20AI%20for%20autonomous%20data%20center%20cooling%20and%20industrial%20control)
[Mail](mailto:?subject=Safety-first%20AI%20for%20autonomous%20data%20center%20cooling%20and%20industrial%20control&body=Check out this article on the Keyword:%0A%0ASafety-first%20AI%20for%20autonomous%20data%20center%20cooling%20and%20industrial%20control%0A%0AA first-of-its-kind cloud-based AI control system is now safely delivering energy savings in multiple Google data centers.%0A%0Ahttps://blog.google/inside-google/infrastructure/safety-first-ai-autonomous-data-center-cooling-and-industrial-control/)

Copy link

![Amanda Gasparik](https://storage.googleapis.com/gweb-uniblog-publish-prod/images/res_1533733676446_1.max-244x184.format-webp.webp)

Amanda Gasparik

Google

![chris gamble](https://storage.googleapis.com/gweb-uniblog-publish-prod/images/chris_gamble.max-244x184.format-webp.webp)

Chris Gamble

DeepMind

![jim gao](https://storage.googleapis.com/gweb-uniblog-publish-prod/images/jim_gao_headshot.max-244x184.format-webp.webp)

Jim Gao

DeepMind

Share

[Twitter](https://twitter.com/intent/tweet?text=Safety-first%20AI%20for%20autonomous%20data%20center%20cooling%20and%20industrial%20control%20%40google&url=https://blog.google/inside-google/infrastructure/safety-first-ai-autonomous-data-center-cooling-and-industrial-control/)
[Facebook](https://www.facebook.com/sharer/sharer.php?caption=Safety-first%20AI%20for%20autonomous%20data%20center%20cooling%20and%20industrial%20control&u=https://blog.google/inside-google/infrastructure/safety-first-ai-autonomous-data-center-cooling-and-industrial-control/)
[LinkedIn](https://www.linkedin.com/shareArticle?mini=true&url=https://blog.google/inside-google/infrastructure/safety-first-ai-autonomous-data-center-cooling-and-industrial-control/&title=Safety-first%20AI%20for%20autonomous%20data%20center%20cooling%20and%20industrial%20control)
[Mail](mailto:?subject=Safety-first%20AI%20for%20autonomous%20data%20center%20cooling%20and%20industrial%20control&body=Check out this article on the Keyword:%0A%0ASafety-first%20AI%20for%20autonomous%20data%20center%20cooling%20and%20industrial%20control%0A%0AA first-of-its-kind cloud-based AI control system is now safely delivering energy savings in multiple Google data centers.%0A%0Ahttps://blog.google/inside-google/infrastructure/safety-first-ai-autonomous-data-center-cooling-and-industrial-control/)

Copy link

![Article's hero media](https://storage.googleapis.com/gweb-uniblog-publish-prod/images/GOOGLE_CBF_009_1.width-200.format-webp.webp)

Many of society’s most pressing problems have grown increasingly complex, so the search for solutions can feel overwhelming. At DeepMind and Google, we believe that if we can use AI as a tool to discover new knowledge, solutions will be easier to reach.

In 2016, we jointly developed an [AI-powered recommendation system](https://deepmind.com/blog/deepmind-ai-reduces-google-data-centre-cooling-bill-40/) to improve the energy efficiency of Google’s already highly-optimized data centers. Our thinking was simple: Even minor improvements would provide significant energy savings and reduce CO2 emissions to help combat climate change.

Now we’re taking this system to the next level: instead of human-implemented recommendations, our AI system is directly controlling data center cooling, while remaining under the expert supervision of our data center operators. This first-of-its-kind cloud-based control system is now safely delivering energy savings in multiple Google data centers.

## How it works

Every five minutes, our cloud-based AI pulls a snapshot of the data center cooling system from thousands of sensors and feeds it into our deep neural networks, which predict how different combinations of potential actions will affect future energy consumption. The AI system then identifies which actions will minimize the energy consumption while satisfying a robust set of safety constraints. Those actions are sent back to the data center, where the actions are verified by the local control system and then implemented.



The idea evolved out of feedback from our data center operators who had been using our AI recommendation system. They told us that although the system had taught them some new best practices—such as spreading the cooling load across more, rather than less, equipment—implementing the recommendations required too much operator effort and supervision. Naturally, they wanted to know whether we could achieve similar energy savings without manual implementation.

  

We’re pleased to say the answer was yes!



## Designed for safety and reliability

Google's data centers contain thousands of servers that power popular services including Google Search, Gmail and YouTube. Ensuring that they run reliably and efficiently is mission-critical. We've designed our AI agents and the underlying control infrastructure from the ground up with safety and reliability in mind, and use eight different mechanisms to ensure the system will behave as intended at all times.

One simple method we’ve implemented is to estimate uncertainty. For every potential action—and there are billions—our AI agent calculates its confidence that this is a good action. Actions with low confidence are eliminated from consideration.

Another method is two-layer verification. Optimal actions computed by the AI are vetted against an internal list of safety constraints defined by our data center operators. Once the instructions are sent from the cloud to the physical data center, the local control system verifies the instructions against its own set of constraints. This redundant check ensures that the system remains within local constraints and operators retain full control of the operating boundaries.

Most importantly, our data center operators are always in control and can choose to exit AI control mode at any time. In these scenarios, the control system will transfer seamlessly from AI control to the on-site rules and heuristics that define the automation industry today.

Find out about the other safety mechanisms we’ve developed below:

![DME_DCIQ_v08-05.png](https://storage.googleapis.com/gweb-uniblog-publish-prod/images/DME_DCIQ_v08-05.width-100.format-webp.webp)

## Increasing energy savings over time

Whereas our original recommendation system had operators vetting and implementing actions, our new AI control system directly implements the actions. We’ve purposefully constrained the system’s optimization boundaries to a narrower operating regime to prioritize safety and reliability, meaning there is a risk/reward trade off in terms of energy reductions.

Despite being in place for only a matter of months, the system is already delivering consistent energy savings of around 30 percent on average, with further expected improvements. That’s because these systems get better over time with more data, as the graph below demonstrates. Our optimization boundaries will also be expanded as the technology matures, for even greater reductions.

This graph plots AI performance over time relative to the historical baseline before AI control. Performance is measured by a common industry metric for cooling energy efficiency, kW/ton (or energy input per ton of cooling achieved). Over nine months, our AI control system performance increases from a 12 percent improvement (the initial launch of autonomous control) to around a 30 percent improvement.

![graph.gif](https://storage.googleapis.com/gweb-uniblog-publish-prod/original_images/graph.gif)

Our direct AI control system is finding yet more novel ways to manage cooling that have surprised even the data center operators. Dan Fuenffinger, one of Google’s data center operators who has worked extensively alongside the system, remarked: "It was amazing to see the AI learn to take advantage of winter conditions and produce colder than normal water, which reduces the energy required for cooling within the data center. Rules don’t get better over time, but AI does."

We’re excited that our direct AI control system is operating safely and dependably, while consistently delivering energy savings. However, data centers are just the beginning. In the long term, we think there's potential to apply this technology in other industrial settings, and help tackle climate change on an even grander scale.

POSTED IN:

---

*爬取时间: 2025-11-28 21:49:26*
