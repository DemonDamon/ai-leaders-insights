# How Do We Fix and Update Large Language Models?

**来源**: [https://hai.stanford.edu/news/how-do-we-fix-and-update-large-language-models](https://hai.stanford.edu/news/how-do-we-fix-and-update-large-language-models)

---

# How Do We Fix and Update Large Language Models? | Stanford HAI

原文链接: https://hai.stanford.edu/news/how-do-we-fix-and-update-large-language-models

[news](/news)

# How Do We Fix and Update Large Language Models?

Date

February 13, 2023

Topics

[Machine Learning](/topics/machine-learning)

![](ai-leaders-insights/核心能力与技术/记忆与学习/知识更新/images/8470dc73440748bb8a230b52eae51fbc.jpg)

iStock/imaginima

These three approaches to editing large language models could make them more accurate, consistent, and up-to-date.

When OpenAI released [ChatGPT](https://openai.com/blog/chatgpt/) to the public in November of 2022, it was widely acknowledged as the best AI chatbot to date. Nevertheless, like other systems that rely on large language models, ChatGPT is not always factual or logically consistent, may generate hate speech or other harmful content, and has no knowledge of events that occurred after it was trained. So, for example, ChatGPT doesn’t know that the prime minister of the United Kingdom is now Rishi Sunak or that Argentina won the World Cup in soccer.

“Even when we train very capable models, it’s still not clear how to keep them up to date or revise them when they make errors,” says Eric Anthony Mitchell, a 4th-year computer science PhD student in the [Stanford Artificial Intelligence Lab](https://ai.stanford.edu/), led by HAI associate director and Stanford professor [Chris Manning](https://profiles.stanford.edu/chris-manning).

When faced with a bug in traditional software systems, developers can fix the problem directly in the source code. But developers of a large language model don’t know which of its billions of parameters need tweaking when the model makes a mistake, Mitchell says. And although these models could be retrained to fix their errors, retraining is expensive and time consuming.

“Ideally, when the state of the world changes, we would be able to update models in a way that’s not as computationally expensive as training a new model,” Mitchell says.

In pursuit of that ideal, the last few years have seen an explosion of approaches for updating models to extend their useful life. Some aim to edit the model itself using various fine-tuning strategies, while others behave more like a list of facts in the model’s back pocket, readily at hand when the model is about to make a mistake, Mitchell says. Eventually, some combination of these approaches might emerge. Or perhaps models will learn new information in an automated way – as if they are reading the daily news, Mitchell says.

Here, Mitchell describes the challenge of model editing, some of the promising approaches he and his colleagues have pursued, and some ideas for the path forward.

**Why is it so difficult to directly fix errors in a large language model?**

These models use neural networks, which means they learn the way a brain does – almost.

When a student believes that “two plus two equals five,” we hope that a high-level instruction – “two plus two equals four” – should be enough to correct the student’s mistake. The teacher does not need to specify how to adjust the strength of the connections between every axon in the student’s brain.

But when we train models, in addition to providing the information “two plus two equals four,” we compute a gradient, which essentially specifies how we should update every connection between every neuron in the model based on this new information. And in these large language models, that’s billions of connections.

But when we just want to edit a model to learn a single new fact – for example, that the prime minister of the UK is now Rishi Sunak – adjusting all of the model’s billions of parameters would also be overkill. But failing to tweak enough parameters could lead to underfitting, meaning the model might only say Rishi Sunak when it’s prompted with a specific sequence of words. Excessive tweaking, on the other hand, might lead to overfitting, where the model will say Rishi Sunak for unrelated inputs, such as “Who is the prime minister of India?”

So instead, we take the raw gradient signal that’s giving us some rough idea of how to change every parameter, and we figure out which parameters need changing and which we can ignore. But it’s quite hard to do that sort of filtering or processing operation on top of the enormous raw gradient that we get for these large language models.

To make that problem tractable, our team has worked on a project called MEND that uses gradient decomposition to represent large language models’ gradients in a more compact way. We can then filter the neural connections to identify which need to get updated and which don't. Making the gradient more compact so we can do this processing efficiently is the key. And we showed that MEND can make reliable edits to a model with more than 10 billion parameters, with less over- or underfitting than existing approaches. One limitation of this approach is that when we start to cram a lot of these updates into a model’s parameters, they can start to conflict with each other, making it hard for the model to keep them straight. Also, the model doesn’t necessarily learn the downstream implications of a new fact. For example: If Sunak is the new UK prime minister, who is the prime minister’s wife?

**Can a model’s outputs be corrected or updated in a way other than directly editing the model?**

Our lab has developed two frameworks – SERAC and ConCoRD – that leave the pre-trained model alone and instead figure out when to override the predictions of the underlying model.

With MEND, it’s as if we’re fixing the student’s beliefs and releasing the student into the world assuming its false beliefs have been corrected. But with SERAC and ConCoRD, instead of stuffing new information into the student’s head, we give him or her a notebook of corrections to keep in a back pocket. And then when a particular topic of conversation comes up, the student can pull out the notebook and say “the prime minister of the UK is Rishi Sunak” or whatever new fact is called for.

In the case of SERAC, the back-pocket notebook is a list of facts that someone has realized the model needs to correct or update. ConCoRD uses a similar approach but seeks to enforce consistency in the things the model says. It’s like having a notebook in your back pocket that itemizes things you’ve said before, and it uses an off-the-shelf natural language inference model to check them for consistency with what the model is about to say. And we showed that ConCoRD can rather dramatically reduce the amount of inconsistency in a model.

One benefit of the notebook-based approach is that if I make 10,000 updates to my model and they’re all separately written down in this notebook, they’re not going to start getting mixed up as much as they would if we tried to cram them directly into the model. Another benefit: These models are better at reasoning about the downstream effects of a correction.

**At some point will the “back-pocket notebook” get so full of edits that it will be time to train a new model and start the editing process anew?**

One thing we’ve been thinking about is whether you might periodically distill the stuff that’s in your notebook back into your brain, so you can basically get a new notebook. And so, for methods like SERAC or ConCoRD, you’d have your original model that maybe makes some mistakes, and you have your notebook. And you could make a new copy of the problematic model and train it to imitate the behavior of the aggregate system that consists of the problematic model plus the notebook. And by imitating this sort of aggregate behavior, the information that’s in the model and the information that’s in the notebook would be combined into a single model with a brand-new empty notebook for writing down new facts. Periodically you would do this sort of flushing process that would prevent the notebook from getting infinitely long.

**How do model editors know when a model needs an update?**

So far, most model editors have focused on methods for updating models, but as you’re alluding to, there’s a second issue which is how to detect the need for an update.

Typically, either the maintainer of the model decides what to update or, if the model is deployed, they receive a stream of user reports and, with a human in the loop, decide when an update is needed. For a large model serving a lot of people, this could be a relatively involved process, with hundreds to thousands of updates every single day.

But our team is contemplating how to automate that process by training the model to detect when a data stream contains new knowledge or new information that conflicts with the model’s current beliefs. The grand challenge here is how to take an extremely capable model like GPT3 and set up an automated system so that it can read the news every day and incorporate whatever new information is in that data stream without losing any of its existing abilities or knowledge. And to do that, you need a way to detect new information and a way to incorporate it. It’s the detection side of things that we’re just breaking into now.

**What’s the future of model editing?**

We’ve seen a lot of improvement in the raw ability to cram a lot of updates into our model in a computationally efficient way, which is great. But there are still several shortcomings. For example, to make sure these approaches are ready for real world use, we need to know that they can reason about the downstream effects of an edit. So, for example, if we’ve made an edit signaling that Rishi Sunak is now the prime minister of the UK, a prompt asking for the names of the UK prime minister’s children should list Sunak’s offspring, not Boris Johnson’s. MEND does not do this very well, and although SERAC can do it to some extent, it’s far from perfect. Our team has some ideas about how to do this better and we’re actively working on that right now, and there are others working on related approaches as well, including [David Bau’s group](http://rome.baulab.info) at Northeastern University.

We’d also like to think about editing not only facts but other types of model behaviors such as sentiment. For example, when an open source, publicly available dialogue model was recently asked what it thinks about vaccines, its responses were consistently quite negative. And so it would be appropriate to edit the model not necessarily to say new facts about vaccines, but to say: For this particular topic, we want you to be a little more positive. That’s a very different and useful way to edit a model but it’s not as clear-cut as a factual update.

On a related note, we need to think about making model editing straightforward for the user. For example, it would be nice to specify an edit by describing it in natural language (“be more positive about vaccines”) rather than by collecting a dataset of examples (e.g., a series of positive statements about vaccines) with which to retrain the model.

We should also be thinking about editing not only large language models but other types of large models whose beliefs can become outdated, such as vision models and robotics controllers.

The big picture here is that we invest a ton of resources into these large models, and we want to extend their useful life in terms of not just their accuracy, but also how well they reflect the values of the people they’re serving. So when the values of people change, ideally we would be able to update the models in a way that’s easier and not as computationally expensive as training a new model. Model editing is one way of doing this.

*Stanford HAI’s mission is to advance AI research, education, policy and practice to improve the human condition. [Learn more](https://hai.stanford.edu/).*

iStock/imaginima

Share

Link copied to clipboard!

Contributor(s)

###### Katharine Miller

### Related News

##### [Fei-Fei Li Wins Queen Elizabeth Prize for Engineering](/news/fei-fei-li-wins-queen-elizabeth-prize-for-engineering)

[Shana Lynch](/people/shana-lynch)

Nov 07, 2025

News

![](ai-leaders-insights/核心能力与技术/记忆与学习/知识更新/images/e655c002d3052b1cdc6da710bad0113e.jpg)

The Stanford HAI co-founder is recognized for breakthroughs that propelled computer vision and deep learning, and for championing human-centered AI and industry innovation.

News

![](ai-leaders-insights/核心能力与技术/记忆与学习/知识更新/images/081586c4867d635354494d37e43c57e3.jpg)

#### [Fei-Fei Li Wins Queen Elizabeth Prize for Engineering](/news/fei-fei-li-wins-queen-elizabeth-prize-for-engineering)

[Shana Lynch](/people/shana-lynch)

[Computer Vision](/topics/computer-vision)[Machine Learning](/topics/machine-learning)Nov 07

The Stanford HAI co-founder is recognized for breakthroughs that propelled computer vision and deep learning, and for championing human-centered AI and industry innovation.

##### [Offline “Studying” Shrinks the Cost of Contextually Aware AI](/news/offline-studying-shrinks-the-cost-of-contextually-aware-ai)

Andrew Myers

Sep 29, 2025

News

![Blue abstract background with light traveling through abstract flat cable illustrating data flow (3D render)](ai-leaders-insights/核心能力与技术/记忆与学习/知识更新/images/52e75806e3bb7ca8e619730af9483f59.jpg)

By having AI study a user’s context offline, researchers dramatically reduce the memory and cost required to make AI contextually aware.

News

![Blue abstract background with light traveling through abstract flat cable illustrating data flow (3D render)](ai-leaders-insights/核心能力与技术/记忆与学习/知识更新/images/89180e12c50a9e07635f6753ce4315e9.jpg)

#### [Offline “Studying” Shrinks the Cost of Contextually Aware AI](/news/offline-studying-shrinks-the-cost-of-contextually-aware-ai)

Andrew Myers

[Foundation Models](/topics/foundation-models)[Machine Learning](/topics/machine-learning)Sep 29

By having AI study a user’s context offline, researchers dramatically reduce the memory and cost required to make AI contextually aware.

##### [BEHAVIOR Challenge Charts the Way Forward for Domestic Robotics](/news/behavior-challenge-charts-the-way-forward-for-domestic-robotics)

Andrew Myers

Sep 22, 2025

News

![](ai-leaders-insights/核心能力与技术/记忆与学习/知识更新/images/39c01cea3f776f9c22881b655d3cc3bf.jpg)

With a first-of-its-kind competition for roboticists everywhere, researchers at Stanford are hoping to push domestic robotics into a new age of autonomy and capability.

News

![](ai-leaders-insights/核心能力与技术/记忆与学习/知识更新/images/e8b1b6ce04d94766d7bdb50d1c485aec.jpg)

#### [BEHAVIOR Challenge Charts the Way Forward for Domestic Robotics](/news/behavior-challenge-charts-the-way-forward-for-domestic-robotics)

Andrew Myers

[Robotics](/topics/robotics)[Machine Learning](/topics/machine-learning)Sep 22

With a first-of-its-kind competition for roboticists everywhere, researchers at Stanford are hoping to push domestic robotics into a new age of autonomy and capability.

---

*爬取时间: 2025-11-28 21:51:36*
