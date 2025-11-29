# I-JEPA: The first AI model based on Yann LeCun’s vision for more human-like AI

**来源**: [https://ai.meta.com/blog/yann-lecun-ai-model-i-jepa/](https://ai.meta.com/blog/yann-lecun-ai-model-i-jepa/)

---

# The first AI model based on Yann LeCun’s vision for more human-like AI

原文链接: https://ai.meta.com/blog/yann-lecun-ai-model-i-jepa/

[![Meta](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/252294889_575082167077436_6034106545912333281_n.svg/meta-logo-primary_standardsize.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=FDEypt5jWQIQ7kNvwG3dVx9&_nc_oc=AdkwxxGDUh2ezBuBKitHZ8hdishoEOGr-6ZtxuPBiaxhaYrImko1LZPRpNJSamjOHGY&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_AfjuQi29slC3ibK0jwn6EJU-nDCMo9aTKpuJYcXlz5L27g&oe=693031B9)](#)

- [Meta AI](#)
- [AI Research](#)
- [The Latest](/blog/)
- [About](#)
- [Get Llama](https://www.llama.com/?utm_source=ai_meta_site&utm_medium=web&utm_content=AI_nav&utm_campaign=09252025_moment)
- [Try Meta AI](https://www.meta.ai/?utm_source=ai_meta_site&utm_medium=web&utm_content=AI_nav&utm_campaign=09252025_moment)

Research

# I-JEPA: The first AI model based on Yann LeCun’s vision for more human-like AI

June 13, 2023•

7 minute read

![](ai-leaders-insights/技术路径与方法论/世界模型流派/JEPA架构/images/425e3b9090abb0e0bcd1b4d798304dbe.png)

Last year, Meta’s Chief AI Scientist Yann LeCun proposed a new architecture intended to overcome key limitations of even the most advanced AI systems today. His vision is to create machines that can learn internal models of how the world works so that they can learn much more quickly, plan how to accomplish complex tasks, and readily adapt to unfamiliar situations.

We’re excited to introduce the first AI model based on a key component of LeCun’s vision. This model, the Image Joint Embedding Predictive Architecture (I-JEPA), learns by creating an internal model of the outside world, which compares abstract representations of images (rather than comparing the pixels themselves). I-JEPA delivers strong performance on multiple computer vision tasks, and it’s much more computationally efficient than other widely used computer vision models. The representations learned by I-JEPA can also be used for many different applications without needing extensive fine tuning. For example, we train a 632M parameter visual transformer model using 16 A100 GPUs in under 72 hours, and it achieves state-of-the-art performance for low-shot classification on ImageNet, with only 12 labeled examples per class. Other methods typically take two to 10 times more GPU-hours and achieve worse error rates when trained with the same amount of data.

Our [paper on I-JEPA](https://arxiv.org/abs/2301.08243) will be presented at CVPR 2023 next week, and we’re also open-sourcing the training code and model checkpoints today.

## Capturing common-sense knowledge with self-supervised learning

RECOMMENDED READS

* [Yann LeCun on a vision to make AI systems learn and reason like animals and humans](https://ai.facebook.com/blog/yann-lecun-advances-in-ai-research/)
* [Studying the brain to build AI that processes language as people do](https://ai.facebook.com/blog/studying-the-brain-to-build-ai-that-processes-language-as-people-do/)
* [Teaching AI to be more collaborative with humans without learning directly from them](https://ai.facebook.com/blog/teaching-ai-to-be-more-collaborative-with-humans-without-learning-directly-from-them/)

Our work on I-JEPA (and Joint Embedding Predictive Architecture (JEPA) models more generally) is grounded in the fact that humans learn an enormous amount of background knowledge about the world just by passively observing it. It has been hypothesized that this common sense information is key to enable intelligent behavior such as [sample-efficient acquisition of new concepts](https://www.pnas.org/doi/abs/10.1073/pnas.2200800119), [grounding](https://openreview.net/pdf?id=BZ5a1r-kVsf), and [planning](https://openreview.net/pdf?id=BZ5a1r-kVsf).

AI researchers have tried to devise learning algorithms that capture common sense background knowledge about the world and then encode it into a digital representation the algorithm can access later. To be effective, the system must learn these representations in a self-supervised manner – that is to say, directly from unlabeled data such as images or sounds, rather than from manually assembled labeled datasets.

At a high level, the JEPA aims to predict the representation of part of an input (such as an image or piece of text) from the representation of other parts of the same input. Because it does not involve collapsing representations from multiple views/augmentations of an image to a single point, the hope is for the JEPA to avoid the [biases and issues](https://arxiv.org/abs/2210.07277) associated with another widely used method called invariance-based pretraining.

At the same time, by predicting representations at a high level of abstraction rather than predicting pixel values directly, the hope is to learn directly useful representations that also avoid the limitations of generative approaches, which underlie the large language models that have generated so much recent excitement.

In contrast, generative architectures learn by removing or distorting portions of the input to the model – for example, erasing part of a photo or hiding some of the words in a text passage. They then try to predict the corrupted or missing pixels or words. One significant shortcoming of generative methods, however, is that the model tries to fill-in every bit of missing information, even though the world is inherently unpredictable. As a result, generative methods may be prone to mistakes a person would never make because they focus too much on irrelevant details instead of capturing high-level predictable concepts. For example, it is notoriously difficult for generative models to generate human hands accurately. (They often add extra digits or make other glaring errors.)

![](ai-leaders-insights/技术路径与方法论/世界模型流派/JEPA架构/images/8b0e7c7c6a4b9b98952764cb71dac90e.png)

Common architectures for self-supervised learning, in which the system learns to capture the relationships between its inputs. The objective is to assign a high energy to incompatible inputs, and to assign a low energy to compatible inputs. (a) Joint-Embedding (invariant) Architectures learn to output similar embeddings for compatible inputs x, y and dissimilar embeddings for incompatible inputs. (b) Generative Architectures learn to directly reconstruct a signal y from a compatible signal x, using a decoder network that is conditioned on additional (possibly latent) variables z to facilitate reconstruction. (c) Joint-Embedding Predictive Architectures learn to predict the embeddings of a signal y from a compatible signal x, using a predictor network that is conditioned on additional (possibly latent) variables z to facilitate prediction.

## A first step toward a broadly capable joint-embedding predictive architecture

The idea behind I-JEPA is to predict missing information in an abstract representation that’s more akin to the general understanding people have. Compared to generative methods that predict in pixel/token space, I-JEPA uses abstract prediction targets for which unnecessary pixel-level details are potentially eliminated, thereby leading the model to learn more semantic features. Another core design choice to guide I-JEPA towards producing semantic representations is the proposed multi-block masking strategy. Specifically, we demonstrate the importance of predicting large blocks containing semantic information (with sufficiently large scale), using an informative (spatially distributed) context.

![](ai-leaders-insights/技术路径与方法论/世界模型流派/JEPA架构/images/88f447bc8698cd7b8dba356ef4f518a4.png)

The Image-based Joint-Embedding Predictive Architecture (I-JEPA) uses a single context block to predict the representations of various target blocks originating from the same image. The context encoder is a Vision Transformer (ViT) that only processes the visible context patches. The predictor is a narrow ViT that takes the context encoder output and predicts the representations of a target block at a specific location, conditioned on positional tokens of the target (shown in color). The target representations correspond to the outputs of the target-encoder, the weights of which are updated at each iteration via an exponential moving average of the context encoder weights.

The predictor in I-JEPA can be seen as a primitive (and restricted) world-model that’s able to model spatial uncertainty in a static image from a partially observable context. What’s more, this world model is semantic in the sense that it predicts high-level information about unseen regions in the image, rather than pixel-level details.

![](ai-leaders-insights/技术路径与方法论/世界模型流派/JEPA架构/images/9af7265c518b942e1703ffab2bf73ce0.png)![](ai-leaders-insights/技术路径与方法论/世界模型流派/JEPA架构/images/c75b5843100ec2821c668775e87c1978.pdf)

Illustrating how the predictor learns to model the semantics of the world. For each image, the portion outside of the blue box is encoded and given to the predictor as context. The predictor outputs a representation for what it expects to be in the region within the blue box. To visualize the prediction, we train a generative model that produces a sketch of the contents represented by the predictor output, and we show a sample output within the blue box. Clearly the predictor recognizes the semantics of what parts should be filled in (the top of the dog’s head, the bird’s leg, the wolf’s legs, the other side of the building).

To understand what the model is capturing, we trained a stochastic decoder that maps the I-JEPA predicted representations back in pixel space, which shows the model’s outputs when probed to make predictions inside the blue box. This qualitative evaluation shows that the model correctly captures positional uncertainty and produces high-level object parts with the correct pose (e.g., dog’s head, wolf’s front legs). In short, I-JEPA is able to learn high-level representations of object parts without discarding their localized positional information in the image.

## Greater efficiency and strong performance

I-JEPA pretraining is also computationally efficient. It doesn’t involve any overhead associated with applying more computationally intensive data augmentations to produce multiple views. Only one view of the image needs to be processed by the target encoder, and only the context blocks need to be processed by the context encoder.

Empirically, we find that I-JEPA learns strong off-the-shelf semantic representations without the use of hand-crafted view augmentations - see the figure below. It also outperforms pixel and token-reconstruction methods on ImageNet-1K linear probing and semi-supervised evaluation.

![](ai-leaders-insights/技术路径与方法论/世界模型流派/JEPA架构/images/7d93024f1e434b154a8d15936bb60572.png)

Linear evaluation performance on ImageNet-1k as a function of GPU hours for pretraining.

I-JEPA is also competitive with previous pretraining approaches that rely on hand-crafted data augmentations on semantic tasks. Compared to these methods, I-JEPA achieves better performance on low-level vision tasks such as object counting and depth prediction. By using a simpler model with less rigid inductive bias, I-JEPA is applicable to a wider set of tasks.

![](ai-leaders-insights/技术路径与方法论/世界模型流派/JEPA架构/images/b11bf9c976e48e00dbcb02b0c0cc07a5.png)

Low Shot Classification Accuracy: Semi-supervised evaluation on ImageNet-1k with 1% of the labels (approximately 12 labeled images per class).

## A step closer to human-level intelligence in AI

I-JEPA demonstrates the potential of architectures for learning competitive off-the-shelf image representations without the need for extra knowledge encoded through hand-crafted image transformations. It would be particularly interesting to advance JEPAs to learn more general world-models from richer modalities, e.g., enabling one to make long-range spatial and temporal predictions about future events in a video from a short context, and conditioning these predictions on audio or textual prompts.

We look forward to working to extend the JEPA approach to other domains, like image-text paired data and video data. In the future, JEPA models could have exciting applications for tasks like video understanding. This is an important step towards applying and scaling self-supervised methods for learning a general model of the world.

[Read the I-JEPA paper](https://arxiv.org/abs/2301.08243)

[Access the code and model checkpoints](https://github.com/facebookresearch/ijepa)

---

Share:

---

Our latest updates delivered to your inbox

[Subscribe](https://ai.facebook.com/subscribe/) to our newsletter to keep up with Meta AI news, events, research breakthroughs, and more.

Join us in the pursuit of what’s possible with AI.

[See all open positions](https://www.metacareers.com/jobs/?is_leadership=0&sub_teams%5B0%5D=Artificial+Intelligence&is_in_page=0&fbclid=IwAR0O8BF7opOj5gASJmwYVGalPPXTLu-6xrl9w00eC7Rarp2HQ9uEH8tERFw)

Related Posts

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.2365-6/338318848_238475658638014_6444534044370711549_n.gif?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=sVwBs67VZNkQ7kNvwFYAR3U&_nc_oc=AdlzTocN7bFQLvbdDr7Sccwok1l4aIERhSIRzZ2ySGKS0jAt9OnpcgjIwzs83-cj4Y4&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afjt8qMWEi_mcHOhelQgVF0rbz95ajNbcTTzf0Mc2aI4Jg&oe=6944A929)

Computer Vision

Introducing Segment Anything: Working toward the first foundation model for image segmentation

April 5, 2023

[Read post](https://ai.meta.com/blog/segment-anything-foundation-model-image-segmentation/)

FEATURED

![](ai-leaders-insights/技术路径与方法论/世界模型流派/JEPA架构/images/6f10f81934e7df4900127dcc932dfc11.jpg)

Research

MultiRay: Optimizing efficiency for large-scale AI models

November 18, 2022

[Read post](https://ai.meta.com/blog/multiray-large-scale-AI-models/)

FEATURED

![](ai-leaders-insights/技术路径与方法论/世界模型流派/JEPA架构/images/5681a600e9a0812c648cccc2fcc8f780.png)

ML Applications

MuAViC: The first audio-video speech translation benchmark

March 8, 2023

[Read post](https://ai.meta.com/blog/muavic-audio-visual-speech-translation-benchmark/)

[Our approach](/about)

[About AI at Meta](/about)

[People](/results/?content_types%5B0%5D=person&sort_by=random)

[Careers](https://www.metacareers.com/jobs/?is_leadership=0&sub_teams[0]=Artificial%20Intelligence&is_in_page=0)

[Research](/research)

[Infrastructure](/infrastructure)

[Resources](/resources)

[Demos](https://aidemos.meta.com/)

[Meta AI](/meta-ai/)

[Explore Meta AI](/meta-ai/)

[Get Meta AI](/get-meta-ai/)

[AI Studio](/ai-studio/)

[Latest news](/blog)

[Blog](/blog)

[Newsletter](/subscribe)

Foundational models

[Llama](https://www.llama.com/)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.2365-6/87524316_2677189655726266_6338721200264445952_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=df33cwwvHMEQ7kNvwGYPnZt&_nc_oc=Adkfam2Xd8oEV8hS8C8WJW8xKSbSLROsKBCUUVo_sNU9TPuIFkaAnMv8kcr8BIrfU_U&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_AfiXAo9qsfzpUJJVAkRp4E381q2v7Jd-Xfd9qT7eVrLE1g&oe=69449B78)

[![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/335682312_964107378293184_3093631164486164913_n.svg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=K-H1ELUclsAQ7kNvwFPhyJ0&_nc_oc=AdnfwYsgeNO726apW4DXzJqIbM-ILOdsJX9N91NwWLnPQp7T9KheKftfMYyxTiog7gk&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afi-avvOdoomYCMvn--XPtdpNRL_ZWss2PeTrPIs7FVDJw&oe=693021E7)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/335682312_964107378293184_3093631164486164913_n.svg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=K-H1ELUclsAQ7kNvwFPhyJ0&_nc_oc=AdnfwYsgeNO726apW4DXzJqIbM-ILOdsJX9N91NwWLnPQp7T9KheKftfMYyxTiog7gk&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afi-avvOdoomYCMvn--XPtdpNRL_ZWss2PeTrPIs7FVDJw&oe=693021E7)](https://www.facebook.com/aiatmeta/)

[![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/336009607_1870102080040414_6753977241281150924_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=LeGtn766Rm4Q7kNvwGKpFvd&_nc_oc=AdlLFSC-f6x2BlA-z1U0oyrQhunJPuPx6laHKQUcPkhj745xUQEtRQK1vq-dXCoEycE&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afj28SgRPHJ0Dp-eT5ZYE26cWnTIpimiYnZHyQbvT_eBQw&oe=69301A22)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/336009607_1870102080040414_6753977241281150924_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=LeGtn766Rm4Q7kNvwGKpFvd&_nc_oc=AdlLFSC-f6x2BlA-z1U0oyrQhunJPuPx6laHKQUcPkhj745xUQEtRQK1vq-dXCoEycE&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afj28SgRPHJ0Dp-eT5ZYE26cWnTIpimiYnZHyQbvT_eBQw&oe=69301A22)](https://twitter.com/aiatmeta/)

[![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/336289415_1541032296405649_2165099305308791297_n.svg?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yr3zuUlwW8oQ7kNvwEUorPv&_nc_oc=AdnV68NHAsQjQjpEcvJ-8IRKSKPAzUDDNNbTOebK1LZ74_z6ZlZQzs2Jct8bk4lX1xI&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afik8QMB1fsfk5L6KrzfdDlxxhin-r_3VU2jW3Q-fGzuCA&oe=693045FB)

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/336289415_1541032296405649_2165099305308791297_n.svg?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yr3zuUlwW8oQ7kNvwEUorPv&_nc_oc=AdnV68NHAsQjQjpEcvJ-8IRKSKPAzUDDNNbTOebK1LZ74_z6ZlZQzs2Jct8bk4lX1xI&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afik8QMB1fsfk5L6KrzfdDlxxhin-r_3VU2jW3Q-fGzuCA&oe=693045FB)](https://www.linkedin.com/showcase/aiatmeta)

[![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/335648731_142576991793348_7786819189843639239_n.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=WjfuuM_g9RsQ7kNvwFUAdLJ&_nc_oc=AdlX0_S2fd7rTRM5Sx8A5Nm1QJl4lfQpDRfkEIM8MyeTSPDGQYn8hCiPKlJMDz1Iqmc&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_AfhwdaH_idE-KU-h0LBN76zZwK7SPkKH1lBAUJMoam6UHw&oe=6930272E)

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/335648731_142576991793348_7786819189843639239_n.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=WjfuuM_g9RsQ7kNvwFUAdLJ&_nc_oc=AdlX0_S2fd7rTRM5Sx8A5Nm1QJl4lfQpDRfkEIM8MyeTSPDGQYn8hCiPKlJMDz1Iqmc&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_AfhwdaH_idE-KU-h0LBN76zZwK7SPkKH1lBAUJMoam6UHw&oe=6930272E)](https://www.youtube.com/@aiatmeta)

Our approach

[Our approach](/about)[About AI at Meta](/about)[People](/results/?content_types%5B0%5D=person&sort_by=random)[Careers](https://www.metacareers.com/jobs/?is_leadership=0&sub_teams[0]=Artificial%20Intelligence&is_in_page=0)

Research

[Research](/research)[Infrastructure](/infrastructure)[Resources](/resources)[Demos](https://aidemos.meta.com/)

Meta AI

[Meta AI](/meta-ai/)[Explore Meta AI](/meta-ai/)[Get Meta AI](/get-meta-ai/)[AI Studio](/ai-studio/)

Latest news

[Latest news](/blog)[Blog](/blog)[Newsletter](/subscribe)

Foundational models

[Llama](https://www.llama.com/)

[![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/335682312_964107378293184_3093631164486164913_n.svg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=K-H1ELUclsAQ7kNvwFPhyJ0&_nc_oc=AdnfwYsgeNO726apW4DXzJqIbM-ILOdsJX9N91NwWLnPQp7T9KheKftfMYyxTiog7gk&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afi-avvOdoomYCMvn--XPtdpNRL_ZWss2PeTrPIs7FVDJw&oe=693021E7)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/335682312_964107378293184_3093631164486164913_n.svg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=K-H1ELUclsAQ7kNvwFPhyJ0&_nc_oc=AdnfwYsgeNO726apW4DXzJqIbM-ILOdsJX9N91NwWLnPQp7T9KheKftfMYyxTiog7gk&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afi-avvOdoomYCMvn--XPtdpNRL_ZWss2PeTrPIs7FVDJw&oe=693021E7)](https://www.facebook.com/aiatmeta/)

[![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/336009607_1870102080040414_6753977241281150924_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=LeGtn766Rm4Q7kNvwGKpFvd&_nc_oc=AdlLFSC-f6x2BlA-z1U0oyrQhunJPuPx6laHKQUcPkhj745xUQEtRQK1vq-dXCoEycE&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afj28SgRPHJ0Dp-eT5ZYE26cWnTIpimiYnZHyQbvT_eBQw&oe=69301A22)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/336009607_1870102080040414_6753977241281150924_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=LeGtn766Rm4Q7kNvwGKpFvd&_nc_oc=AdlLFSC-f6x2BlA-z1U0oyrQhunJPuPx6laHKQUcPkhj745xUQEtRQK1vq-dXCoEycE&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afj28SgRPHJ0Dp-eT5ZYE26cWnTIpimiYnZHyQbvT_eBQw&oe=69301A22)](https://twitter.com/aiatmeta/)

[![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/336289415_1541032296405649_2165099305308791297_n.svg?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yr3zuUlwW8oQ7kNvwEUorPv&_nc_oc=AdnV68NHAsQjQjpEcvJ-8IRKSKPAzUDDNNbTOebK1LZ74_z6ZlZQzs2Jct8bk4lX1xI&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afik8QMB1fsfk5L6KrzfdDlxxhin-r_3VU2jW3Q-fGzuCA&oe=693045FB)

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/336289415_1541032296405649_2165099305308791297_n.svg?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yr3zuUlwW8oQ7kNvwEUorPv&_nc_oc=AdnV68NHAsQjQjpEcvJ-8IRKSKPAzUDDNNbTOebK1LZ74_z6ZlZQzs2Jct8bk4lX1xI&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afik8QMB1fsfk5L6KrzfdDlxxhin-r_3VU2jW3Q-fGzuCA&oe=693045FB)](https://www.linkedin.com/showcase/aiatmeta)

[![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/335648731_142576991793348_7786819189843639239_n.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=WjfuuM_g9RsQ7kNvwFUAdLJ&_nc_oc=AdlX0_S2fd7rTRM5Sx8A5Nm1QJl4lfQpDRfkEIM8MyeTSPDGQYn8hCiPKlJMDz1Iqmc&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_AfhwdaH_idE-KU-h0LBN76zZwK7SPkKH1lBAUJMoam6UHw&oe=6930272E)

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/335648731_142576991793348_7786819189843639239_n.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=WjfuuM_g9RsQ7kNvwFUAdLJ&_nc_oc=AdlX0_S2fd7rTRM5Sx8A5Nm1QJl4lfQpDRfkEIM8MyeTSPDGQYn8hCiPKlJMDz1Iqmc&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_AfhwdaH_idE-KU-h0LBN76zZwK7SPkKH1lBAUJMoam6UHw&oe=6930272E)](https://www.youtube.com/@aiatmeta)

[Privacy Policy](https://www.facebook.com/about/privacy/)

[Terms](https://www.facebook.com/policies/)

[Cookies](https://www.facebook.com/policies/cookies/)

Meta © 2025

[![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/335682312_964107378293184_3093631164486164913_n.svg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=K-H1ELUclsAQ7kNvwFPhyJ0&_nc_oc=AdnfwYsgeNO726apW4DXzJqIbM-ILOdsJX9N91NwWLnPQp7T9KheKftfMYyxTiog7gk&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afi-avvOdoomYCMvn--XPtdpNRL_ZWss2PeTrPIs7FVDJw&oe=693021E7)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/335682312_964107378293184_3093631164486164913_n.svg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=K-H1ELUclsAQ7kNvwFPhyJ0&_nc_oc=AdnfwYsgeNO726apW4DXzJqIbM-ILOdsJX9N91NwWLnPQp7T9KheKftfMYyxTiog7gk&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afi-avvOdoomYCMvn--XPtdpNRL_ZWss2PeTrPIs7FVDJw&oe=693021E7)](https://www.facebook.com/aiatmeta/)

[![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/336009607_1870102080040414_6753977241281150924_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=LeGtn766Rm4Q7kNvwGKpFvd&_nc_oc=AdlLFSC-f6x2BlA-z1U0oyrQhunJPuPx6laHKQUcPkhj745xUQEtRQK1vq-dXCoEycE&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afj28SgRPHJ0Dp-eT5ZYE26cWnTIpimiYnZHyQbvT_eBQw&oe=69301A22)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/336009607_1870102080040414_6753977241281150924_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=LeGtn766Rm4Q7kNvwGKpFvd&_nc_oc=AdlLFSC-f6x2BlA-z1U0oyrQhunJPuPx6laHKQUcPkhj745xUQEtRQK1vq-dXCoEycE&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afj28SgRPHJ0Dp-eT5ZYE26cWnTIpimiYnZHyQbvT_eBQw&oe=69301A22)](https://twitter.com/aiatmeta/)

[![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/336289415_1541032296405649_2165099305308791297_n.svg?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yr3zuUlwW8oQ7kNvwEUorPv&_nc_oc=AdnV68NHAsQjQjpEcvJ-8IRKSKPAzUDDNNbTOebK1LZ74_z6ZlZQzs2Jct8bk4lX1xI&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afik8QMB1fsfk5L6KrzfdDlxxhin-r_3VU2jW3Q-fGzuCA&oe=693045FB)

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/336289415_1541032296405649_2165099305308791297_n.svg?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yr3zuUlwW8oQ7kNvwEUorPv&_nc_oc=AdnV68NHAsQjQjpEcvJ-8IRKSKPAzUDDNNbTOebK1LZ74_z6ZlZQzs2Jct8bk4lX1xI&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_Afik8QMB1fsfk5L6KrzfdDlxxhin-r_3VU2jW3Q-fGzuCA&oe=693045FB)](https://www.linkedin.com/showcase/aiatmeta)

[![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/335648731_142576991793348_7786819189843639239_n.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=WjfuuM_g9RsQ7kNvwFUAdLJ&_nc_oc=AdlX0_S2fd7rTRM5Sx8A5Nm1QJl4lfQpDRfkEIM8MyeTSPDGQYn8hCiPKlJMDz1Iqmc&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_AfhwdaH_idE-KU-h0LBN76zZwK7SPkKH1lBAUJMoam6UHw&oe=6930272E)

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/335648731_142576991793348_7786819189843639239_n.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=WjfuuM_g9RsQ7kNvwFUAdLJ&_nc_oc=AdlX0_S2fd7rTRM5Sx8A5Nm1QJl4lfQpDRfkEIM8MyeTSPDGQYn8hCiPKlJMDz1Iqmc&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=2XGSCcN1ZkYPaDTHhp456A&oh=00_AfhwdaH_idE-KU-h0LBN76zZwK7SPkKH1lBAUJMoam6UHw&oe=6930272E)](https://www.youtube.com/@aiatmeta)

---

*爬取时间: 2025-11-28 21:49:38*
