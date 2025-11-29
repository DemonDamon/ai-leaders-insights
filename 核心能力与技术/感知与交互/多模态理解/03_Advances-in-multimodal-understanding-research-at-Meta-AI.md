# Advances in multimodal understanding research at Meta AI

**来源**: [https://ai.meta.com/blog/advances-in-multimodal-understanding-research-at-meta-ai/](https://ai.meta.com/blog/advances-in-multimodal-understanding-research-at-meta-ai/)

---

# Advances in multimodal understanding research at Meta AI

原文链接: https://ai.meta.com/blog/advances-in-multimodal-understanding-research-at-meta-ai/

[![Meta](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/252294889_575082167077436_6034106545912333281_n.svg/meta-logo-primary_standardsize.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=FDEypt5jWQIQ7kNvwG3dVx9&_nc_oc=AdkwxxGDUh2ezBuBKitHZ8hdishoEOGr-6ZtxuPBiaxhaYrImko1LZPRpNJSamjOHGY&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_Afhit94Z0IqLuXaLU8GcJDBQnMvZac2sHFIOSHQk110CSw&oe=693031B9)](#)

- [Meta AI](#)
- [AI Research](#)
- [The Latest](/blog/)
- [About](#)
- [Get Llama](https://www.llama.com/?utm_source=ai_meta_site&utm_medium=web&utm_content=AI_nav&utm_campaign=09252025_moment)
- [Try Meta AI](https://www.meta.ai/?utm_source=ai_meta_site&utm_medium=web&utm_content=AI_nav&utm_campaign=09252025_moment)

#### Research

# Advances in multimodal understanding research at Meta AI

March 16, 2022

[Share on Facebook](http://www.ai.meta.com/sharer/sharer.php?u=https%3A%2F%2Fai.meta.com%2Fblog%2Fadvances-in-multimodal-understanding-research-at-meta-ai%2F)[Share on Twitter](https://twitter.com/intent/tweet?text=Advances+in+multimodal+understanding+research+at+Meta+AI+https%3A%2F%2Fai.meta.com%2Fblog%2Fadvances-in-multimodal-understanding-research-at-meta-ai%2F)

In order for AI to become a more useful tool, it has to learn how to accurately interpret content more holistically. This means working in multiple modalities (such as text, speech, and images) at once. For example, recognizing whether a meme is hateful requires considering  [both the image and the text](https://ai.facebook.com/blog/hateful-memes-challenge-and-data-set/) content of the meme. Similarly, building the [metaverse will require integrating multimodal models](https://ai.facebook.com/blog/project-cairaoke/) with augmented and virtual reality devices, so they can recognize the sound of a siren, for example, and display an alert showing which direction the sound is coming from.

Historically, analyzing such different formats of data together — text, images, speech waveforms, and video, each with a distinct architecture — has been extremely challenging for ​​machines.

Over the last couple of years, Meta AI has produced a slew of research projects, each addressing an important challenge of multimodal perception — from solving a shortage of publicly available data for training [(Hateful Memes)](https://ai.facebook.com/blog/hateful-memes-challenge-and-data-set/) , to a creating single algorithm for vision, speech, and text [(Data2vec)](https://ai.facebook.com/blog/the-first-high-performance-self-supervised-algorithm-that-works-for-speech-vision-and-text/) , to building foundational models that work across many tasks [(FLAVA)](https://arxiv.org/abs/2112.04482) , to finding the right model parameters [(Omnivore)](https://arxiv.org/abs/2201.08377) , and many others. Taken together, they represent a clear trend: Multimodal understanding will be crucial to smarter AI systems in the near future.

Today, we’re sharing a roundup of Meta AI’s recent cutting-edge multimodal research, which we believe will collectively lead to more interactive, immersive, and smarter AI systems.

## Omnivore: A single model for images, videos, and 3D data

Our new Omnivore model can operate on image, video, and 3D data using the same parameters — without degrading performance on modality-specific tasks. For example, it can recognize 3D models of pumpkins or videos of yachts even though at training time it observed images only of pumpkins and yachts, respectively. This enables radically new capabilities, such as AI systems that can search and detect content in both images and videos. Omnivore has achieved state-of-the-art results on popular recognition tasks from all three modalities, with particularly strong performance on video recognition. [Read the paper here.](https://arxiv.org/abs/2201.08377)

## FLAVA: A foundational model spanning dozens of multimodal tasks

FLAVA represents a new class of “foundational model” that’s jointly trained to do over 35 tasks across domains, including image recognition, text recognition, and joint text-image tasks. For instance, the FLAVA model can single-handedly describe the content of an image, reason about its text entailment, and answer questions about the image. FLAVA also leads to impressive zero-shot text and image understanding abilities over a range of tasks, such as image classification, image retrieval, and text retrieval.

FLAVA not only improves over prior work that is typically only good at one task, but, unlike prior work, it also uses a shared trunk that was pretrained on openly available public pairs — which we hope will help further advance research. [Read the paper here.](https://arxiv.org/abs/2112.04482)

## CM3: Generalizing to new multimodal tasks

CM3 is one of the most general open source multimodal models available today. By training on a large corpus of structured multimodal documents, it can generate completely new images and captions for those images. It can also be used in our setting to infill complete images or larger structured text sections, conditioned on the rest of the document. Using prompts generated in an HTML-like syntax, the exact same CM3 model can generate new images or text, caption images, and disambiguate entities in text.

Traditional approaches to pretraining have focused on mixing the architectural choices (e.g., encoder-decoder) with objective choices (e.g., masking). Our novel approach of “causally masked objective” gets the best of both worlds by introducing a hybrid of causal and masked language models. [Read the paper here.](https://arxiv.org/abs/2201.07520)

## Data2vec: The first self-supervised model that achieves SOTA for speech, vision, and text

Research in self-supervised learning today is almost always focused on one particular modality. In our recent breakthrough data2vec research, we show that the exact same model architecture and self-supervised training procedure can be used to develop state-of-the-art models for recognition of images, speech, and text. The illustration below shows how data2vec is used with images, but the same procedure can also be used to train models for speech or natural languages. Data2vec demonstrates that the same self-supervised algorithm can work well in different modalities — and it often outperforms the best existing algorithms. [Read more about Data2vec here.](https://ai.facebook.com/blog/the-first-high-performance-self-supervised-algorithm-that-works-for-speech-vision-and-text/)

## What’s next for multimodal understanding?

Our data2vec models are currently trained separately for each of the various modalities. But our results from Omnivore, FLAVA, and CM3 suggest that, over the horizon, we may be able to train a single AI model that solves challenging tasks across all the modalities. Such a multimodal model would unlock many new opportunities. For example, it would further enhance our ability to comprehensively understand the content of social media posts in order to recognize hate speech or other harmful content. It could also help us build AR glasses that have a more comprehensive understanding of the world around them, unlocking exciting new applications in the metaverse.

As interest in multimodality has grown, we want researchers to have great tools for quickly building and experimenting with multimodal, multitask models at scale. We are open-sourcing TorchMultimodal — a library of multimodal primitives (models, fusion layers, loss functions, data sets, and utilities) and a repository of examples that bring together components and common infrastructure from across the PyTorch ecosystem. As a first open source example, researchers will be able to train and extend FLAVA using this new library. Keep a look out for more details on this soon.

As part of our continued commitment to open science, we are excited to share our most recent research results and are looking forward to building the multimodal AI future together with the wider AI community.

## Written By

#### Laurens van der Maaten

Research Director

#### Ishan Misra

Research Scientist

#### Rohit Girdhar

Research Scientist

#### Amanpreet Singh

Software Engineer

#### Armen Aghajanyan

Research Scientist

#### Alexei Baevski

Research Engineer

[Share on Facebook](http://www.ai.meta.com/sharer/sharer.php?u=https%3A%2F%2Fai.meta.com%2Fblog%2Fadvances-in-multimodal-understanding-research-at-meta-ai%2F)[Share on Twitter](https://twitter.com/intent/tweet?text=Advances+in+multimodal+understanding+research+at+Meta+AI+https%3A%2F%2Fai.meta.com%2Fblog%2Fadvances-in-multimodal-understanding-research-at-meta-ai%2F)

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

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.2365-6/87524316_2677189655726266_6338721200264445952_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=df33cwwvHMEQ7kNvwGYPnZt&_nc_oc=Adkfam2Xd8oEV8hS8C8WJW8xKSbSLROsKBCUUVo_sNU9TPuIFkaAnMv8kcr8BIrfU_U&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfhDbPO5dyq0EIrlESybCnx9CmSklhlLypOKWO7S5QlXjA&oe=69449B78)

[![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/335682312_964107378293184_3093631164486164913_n.svg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=K-H1ELUclsAQ7kNvwFPhyJ0&_nc_oc=AdnfwYsgeNO726apW4DXzJqIbM-ILOdsJX9N91NwWLnPQp7T9KheKftfMYyxTiog7gk&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_Afi2e7tpYmUGj7FWrr4WcCecgQ3pi8QIgkbxQ5a1SVk5IA&oe=693021E7)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/335682312_964107378293184_3093631164486164913_n.svg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=K-H1ELUclsAQ7kNvwFPhyJ0&_nc_oc=AdnfwYsgeNO726apW4DXzJqIbM-ILOdsJX9N91NwWLnPQp7T9KheKftfMYyxTiog7gk&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_Afi2e7tpYmUGj7FWrr4WcCecgQ3pi8QIgkbxQ5a1SVk5IA&oe=693021E7)](https://www.facebook.com/aiatmeta/)

[![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/336009607_1870102080040414_6753977241281150924_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=LeGtn766Rm4Q7kNvwGKpFvd&_nc_oc=AdlLFSC-f6x2BlA-z1U0oyrQhunJPuPx6laHKQUcPkhj745xUQEtRQK1vq-dXCoEycE&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfjYWwZQTxIaGeR6DbF4Ajbpq9_G3JZvHYn3tbO5D8275w&oe=69301A22)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/336009607_1870102080040414_6753977241281150924_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=LeGtn766Rm4Q7kNvwGKpFvd&_nc_oc=AdlLFSC-f6x2BlA-z1U0oyrQhunJPuPx6laHKQUcPkhj745xUQEtRQK1vq-dXCoEycE&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfjYWwZQTxIaGeR6DbF4Ajbpq9_G3JZvHYn3tbO5D8275w&oe=69301A22)](https://twitter.com/aiatmeta/)

[![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/336289415_1541032296405649_2165099305308791297_n.svg?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yr3zuUlwW8oQ7kNvwEUorPv&_nc_oc=AdnV68NHAsQjQjpEcvJ-8IRKSKPAzUDDNNbTOebK1LZ74_z6ZlZQzs2Jct8bk4lX1xI&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfhK6QwcESj1YUkUVnR8yv0PYDXfI6jjdjtTJmmgNmqBuQ&oe=693045FB)

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/336289415_1541032296405649_2165099305308791297_n.svg?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yr3zuUlwW8oQ7kNvwEUorPv&_nc_oc=AdnV68NHAsQjQjpEcvJ-8IRKSKPAzUDDNNbTOebK1LZ74_z6ZlZQzs2Jct8bk4lX1xI&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfhK6QwcESj1YUkUVnR8yv0PYDXfI6jjdjtTJmmgNmqBuQ&oe=693045FB)](https://www.linkedin.com/showcase/aiatmeta)

[![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/335648731_142576991793348_7786819189843639239_n.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=WjfuuM_g9RsQ7kNvwFUAdLJ&_nc_oc=AdlX0_S2fd7rTRM5Sx8A5Nm1QJl4lfQpDRfkEIM8MyeTSPDGQYn8hCiPKlJMDz1Iqmc&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfhArc43AVLlKtOkW5eBI0tk4Nr4WQEInvWhJceBX_3GDg&oe=6930272E)

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/335648731_142576991793348_7786819189843639239_n.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=WjfuuM_g9RsQ7kNvwFUAdLJ&_nc_oc=AdlX0_S2fd7rTRM5Sx8A5Nm1QJl4lfQpDRfkEIM8MyeTSPDGQYn8hCiPKlJMDz1Iqmc&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfhArc43AVLlKtOkW5eBI0tk4Nr4WQEInvWhJceBX_3GDg&oe=6930272E)](https://www.youtube.com/@aiatmeta)

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

[![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/335682312_964107378293184_3093631164486164913_n.svg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=K-H1ELUclsAQ7kNvwFPhyJ0&_nc_oc=AdnfwYsgeNO726apW4DXzJqIbM-ILOdsJX9N91NwWLnPQp7T9KheKftfMYyxTiog7gk&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_Afi2e7tpYmUGj7FWrr4WcCecgQ3pi8QIgkbxQ5a1SVk5IA&oe=693021E7)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/335682312_964107378293184_3093631164486164913_n.svg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=K-H1ELUclsAQ7kNvwFPhyJ0&_nc_oc=AdnfwYsgeNO726apW4DXzJqIbM-ILOdsJX9N91NwWLnPQp7T9KheKftfMYyxTiog7gk&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_Afi2e7tpYmUGj7FWrr4WcCecgQ3pi8QIgkbxQ5a1SVk5IA&oe=693021E7)](https://www.facebook.com/aiatmeta/)

[![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/336009607_1870102080040414_6753977241281150924_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=LeGtn766Rm4Q7kNvwGKpFvd&_nc_oc=AdlLFSC-f6x2BlA-z1U0oyrQhunJPuPx6laHKQUcPkhj745xUQEtRQK1vq-dXCoEycE&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfjYWwZQTxIaGeR6DbF4Ajbpq9_G3JZvHYn3tbO5D8275w&oe=69301A22)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/336009607_1870102080040414_6753977241281150924_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=LeGtn766Rm4Q7kNvwGKpFvd&_nc_oc=AdlLFSC-f6x2BlA-z1U0oyrQhunJPuPx6laHKQUcPkhj745xUQEtRQK1vq-dXCoEycE&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfjYWwZQTxIaGeR6DbF4Ajbpq9_G3JZvHYn3tbO5D8275w&oe=69301A22)](https://twitter.com/aiatmeta/)

[![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/336289415_1541032296405649_2165099305308791297_n.svg?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yr3zuUlwW8oQ7kNvwEUorPv&_nc_oc=AdnV68NHAsQjQjpEcvJ-8IRKSKPAzUDDNNbTOebK1LZ74_z6ZlZQzs2Jct8bk4lX1xI&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfhK6QwcESj1YUkUVnR8yv0PYDXfI6jjdjtTJmmgNmqBuQ&oe=693045FB)

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/336289415_1541032296405649_2165099305308791297_n.svg?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yr3zuUlwW8oQ7kNvwEUorPv&_nc_oc=AdnV68NHAsQjQjpEcvJ-8IRKSKPAzUDDNNbTOebK1LZ74_z6ZlZQzs2Jct8bk4lX1xI&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfhK6QwcESj1YUkUVnR8yv0PYDXfI6jjdjtTJmmgNmqBuQ&oe=693045FB)](https://www.linkedin.com/showcase/aiatmeta)

[![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/335648731_142576991793348_7786819189843639239_n.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=WjfuuM_g9RsQ7kNvwFUAdLJ&_nc_oc=AdlX0_S2fd7rTRM5Sx8A5Nm1QJl4lfQpDRfkEIM8MyeTSPDGQYn8hCiPKlJMDz1Iqmc&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfhArc43AVLlKtOkW5eBI0tk4Nr4WQEInvWhJceBX_3GDg&oe=6930272E)

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/335648731_142576991793348_7786819189843639239_n.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=WjfuuM_g9RsQ7kNvwFUAdLJ&_nc_oc=AdlX0_S2fd7rTRM5Sx8A5Nm1QJl4lfQpDRfkEIM8MyeTSPDGQYn8hCiPKlJMDz1Iqmc&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfhArc43AVLlKtOkW5eBI0tk4Nr4WQEInvWhJceBX_3GDg&oe=6930272E)](https://www.youtube.com/@aiatmeta)

[Privacy Policy](https://www.facebook.com/about/privacy/)

[Terms](https://www.facebook.com/policies/)

[Cookies](https://www.facebook.com/policies/cookies/)

Meta © 2025

[![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/335682312_964107378293184_3093631164486164913_n.svg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=K-H1ELUclsAQ7kNvwFPhyJ0&_nc_oc=AdnfwYsgeNO726apW4DXzJqIbM-ILOdsJX9N91NwWLnPQp7T9KheKftfMYyxTiog7gk&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_Afi2e7tpYmUGj7FWrr4WcCecgQ3pi8QIgkbxQ5a1SVk5IA&oe=693021E7)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/335682312_964107378293184_3093631164486164913_n.svg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=K-H1ELUclsAQ7kNvwFPhyJ0&_nc_oc=AdnfwYsgeNO726apW4DXzJqIbM-ILOdsJX9N91NwWLnPQp7T9KheKftfMYyxTiog7gk&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_Afi2e7tpYmUGj7FWrr4WcCecgQ3pi8QIgkbxQ5a1SVk5IA&oe=693021E7)](https://www.facebook.com/aiatmeta/)

[![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/336009607_1870102080040414_6753977241281150924_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=LeGtn766Rm4Q7kNvwGKpFvd&_nc_oc=AdlLFSC-f6x2BlA-z1U0oyrQhunJPuPx6laHKQUcPkhj745xUQEtRQK1vq-dXCoEycE&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfjYWwZQTxIaGeR6DbF4Ajbpq9_G3JZvHYn3tbO5D8275w&oe=69301A22)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/336009607_1870102080040414_6753977241281150924_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=LeGtn766Rm4Q7kNvwGKpFvd&_nc_oc=AdlLFSC-f6x2BlA-z1U0oyrQhunJPuPx6laHKQUcPkhj745xUQEtRQK1vq-dXCoEycE&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfjYWwZQTxIaGeR6DbF4Ajbpq9_G3JZvHYn3tbO5D8275w&oe=69301A22)](https://twitter.com/aiatmeta/)

[![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/336289415_1541032296405649_2165099305308791297_n.svg?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yr3zuUlwW8oQ7kNvwEUorPv&_nc_oc=AdnV68NHAsQjQjpEcvJ-8IRKSKPAzUDDNNbTOebK1LZ74_z6ZlZQzs2Jct8bk4lX1xI&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfhK6QwcESj1YUkUVnR8yv0PYDXfI6jjdjtTJmmgNmqBuQ&oe=693045FB)

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/336289415_1541032296405649_2165099305308791297_n.svg?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yr3zuUlwW8oQ7kNvwEUorPv&_nc_oc=AdnV68NHAsQjQjpEcvJ-8IRKSKPAzUDDNNbTOebK1LZ74_z6ZlZQzs2Jct8bk4lX1xI&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfhK6QwcESj1YUkUVnR8yv0PYDXfI6jjdjtTJmmgNmqBuQ&oe=693045FB)](https://www.linkedin.com/showcase/aiatmeta)

[![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/335648731_142576991793348_7786819189843639239_n.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=WjfuuM_g9RsQ7kNvwFUAdLJ&_nc_oc=AdlX0_S2fd7rTRM5Sx8A5Nm1QJl4lfQpDRfkEIM8MyeTSPDGQYn8hCiPKlJMDz1Iqmc&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfhArc43AVLlKtOkW5eBI0tk4Nr4WQEInvWhJceBX_3GDg&oe=6930272E)

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/335648731_142576991793348_7786819189843639239_n.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=WjfuuM_g9RsQ7kNvwFUAdLJ&_nc_oc=AdlX0_S2fd7rTRM5Sx8A5Nm1QJl4lfQpDRfkEIM8MyeTSPDGQYn8hCiPKlJMDz1Iqmc&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=OmRF3jDtfmC01P66aoVGSQ&oh=00_AfhArc43AVLlKtOkW5eBI0tk4Nr4WQEInvWhJceBX_3GDg&oe=6930272E)](https://www.youtube.com/@aiatmeta)

---

*爬取时间: 2025-11-28 21:51:05*
