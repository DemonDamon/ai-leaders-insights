# V-JEPA: The next step toward advanced machine intelligence

**来源**: [https://ai.meta.com/blog/v-jepa-yann-lecun-ai-model-video-joint-embedding-predictive-architecture/](https://ai.meta.com/blog/v-jepa-yann-lecun-ai-model-video-joint-embedding-predictive-architecture/)

---

# V-JEPA: The next step toward advanced machine intelligence

原文链接: https://ai.meta.com/blog/v-jepa-yann-lecun-ai-model-video-joint-embedding-predictive-architecture/

[![Meta](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/252294889_575082167077436_6034106545912333281_n.svg/meta-logo-primary_standardsize.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=FDEypt5jWQIQ7kNvwG3dVx9&_nc_oc=AdkwxxGDUh2ezBuBKitHZ8hdishoEOGr-6ZtxuPBiaxhaYrImko1LZPRpNJSamjOHGY&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_Afg9F83-PbWL0J5LU0o3HsbvnFI_MBum5kx1tJ3-vGOKUw&oe=693031B9)](#)

- [Meta AI](#)
- [AI Research](#)
- [The Latest](/blog/)
- [About](#)
- [Get Llama](https://www.llama.com/?utm_source=ai_meta_site&utm_medium=web&utm_content=AI_nav&utm_campaign=09252025_moment)
- [Try Meta AI](https://www.meta.ai/?utm_source=ai_meta_site&utm_medium=web&utm_content=AI_nav&utm_campaign=09252025_moment)

Research

# V-JEPA: The next step toward Yann LeCun’s vision of advanced machine intelligence (AMI)

February 15, 2024•

3 minute read

[![](ai-leaders-insights/技术路径与方法论/世界模型流派/JEPA架构/images/ad9df8b2f59abea5da95be73c637b27c.jpg)](https://video-iad3-2.xx.fbcdn.net/o1/v/t2/f2/m266/AQMVvq9F9Vc_IcQs8hGrh_Eeg5L_2fUjJMV3ZYG5dW2tIwAN9lqtL8au31WwTRb7w9exwBiBlSqKyMlWudmf3FibpufHUEmSXXY.mp4?strext=1&_nc_cat=103&_nc_sid=8bf8fe&_nc_ht=video-iad3-2.xx.fbcdn.net&_nc_ohc=vB7z5PddplQQ7kNvwE6QYV0&efg=eyJ2ZW5jb2RlX3RhZyI6Inhwdl9wcm9ncmVzc2l2ZS5GQUNFQk9PSy4uQzMuMTkyMC5jb21wcmVzc2VkX3NvdXJjZSIsInhwdl9hc3NldF9pZCI6NzE3NzY1NjgwNDk2ODYwLCJhc3NldF9hZ2VfZGF5cyI6NjUyLCJ2aV91c2VjYXNlX2lkIjoxMDEyOCwiZHVyYXRpb25fcyI6NjcsInVybGdlbl9zb3VyY2UiOiJ3d3cifQ%3D%3D&ccb=17-1&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&_nc_zt=28&oh=00_Afh-Rc2Om-b4QsWanky6gDwLw4qLUuIT_-3-ekbjodlzJQ&oe=692C2FFB&bitrate=1332226&tag=compressed_source)

## Takeaways:

* Today, we’re publicly releasing the Video Joint Embedding Predictive Architecture (V-JEPA) model, a crucial step in [advancing machine intelligence](https://openreview.net/pdf?id=BZ5a1r-kVsf) with a more grounded understanding of the world.
* This early example of a physical world model excels at detecting and understanding highly detailed interactions between objects.
* In the spirit of responsible open science, we’re releasing this model under a Creative Commons NonCommercial license for researchers to further explore.

  

As humans, much of what we learn about the world around us—particularly in our early stages of life—is gleaned through observation. Take Newton’s third law of motion: Even an infant (or a cat) can intuit, after knocking several items off a table and observing the results, that what goes up must come down. You don’t need hours of instruction or to read thousands of books to arrive at that result. Your internal world model—a contextual understanding based on a mental model of the world—predicts these consequences for you, and it’s highly efficient.

“V-JEPA is a step toward a more grounded understanding of the world so machines can achieve more generalized reasoning and planning,” says Meta’s VP & Chief AI Scientist Yann LeCun, who proposed the original Joint Embedding Predictive Architectures (JEPA) in 2022. “Our goal is to build advanced machine intelligence that can learn more like humans do, forming internal models of the world around them to learn, adapt, and forge plans efficiently in the service of completing complex tasks.”

## Video JEPA in focus

V-JEPA is a non-generative model that learns by predicting missing or masked parts of a video in an abstract representation space. This is similar to how our [Image Joint Embedding Predictive Architecture (I-JEPA)](https://ai.meta.com/blog/yann-lecun-ai-model-i-jepa/) compares abstract representations of images (rather than comparing the pixels themselves). Unlike generative approaches that try to fill in every missing pixel, V-JEPA has the flexibility to discard unpredictable information, which leads to improved training and sample efficiency by a factor between 1.5x and 6x.

Because it takes a self-supervised learning approach, V-JEPA is pre-trained entirely with unlabeled data. Labels are only used to adapt the model to a particular task after pre-training. This type of architecture proves more efficient than previous models, both in terms of the number of labeled examples needed and the total amount of effort put into learning even the unlabeled data. With V-JEPA, we’ve seen efficiency boosts on both of these fronts.

With V-JEPA, we mask out a large portion of a video so the model is only shown a little bit of the context. We then ask the predictor to fill in the blanks of what’s missing—not in terms of the actual pixels, but rather as a more abstract description in this representation space.

![](ai-leaders-insights/技术路径与方法论/世界模型流派/JEPA架构/images/f91fd91a991ef3fd0efc3525053645da.png)

V-JEPA trains a visual encoder by predicting masked spatio-temporal regions in a learned latent space.

## Masking methodology

V-JEPA wasn’t trained to understand one specific type of action. Instead it used self-supervised training on a range of videos and learned a number of things about how the world works. The team also carefully considered the masking strategy—if you don’t block out large regions of the video and instead randomly sample patches here and there, it makes the task too easy and your model doesn’t learn anything particularly complicated about the world.

It’s also important to note that, in most videos, things evolve somewhat slowly over time. If you mask a portion of the video but only for a specific instant in time and the model can see what came immediately before and/or immediately after, it also makes things too easy and the model almost certainly won’t learn anything interesting. As such, the team used an approach where it masked portions of the video in both space and time, which forces the model to learn and develop an understanding of the scene.

## Efficient predictions

Making these predictions in the abstract representation space is important because it allows the model to focus on the higher-level conceptual information of what the video contains without worrying about the kind of details that are most often unimportant for downstream tasks. After all, if a video shows a tree, you’re likely not concerned about the minute movements of each individual leaf.

One of the reasons why we’re excited about this direction is that V-JEPA is the first model for video that’s good at “frozen evaluations,” which means we do all of our self-supervised pre-training on the encoder and the predictor, and then we don’t touch those parts of the model anymore. When we want to adapt them to learn a new skill, we just train a small lightweight specialized layer or a small network on top of that, which is very efficient and quick.

![](ai-leaders-insights/技术路径与方法论/世界模型流派/JEPA架构/images/a3fbdb474fc30c0d667da65b327651be.png)

Low-shot frozen evaluation: Comparing V-JEPA to other video models in frozen evaluation on Kinetics-400 and Something-Something-v2 as we vary the percentage of labeled examples from each dataset available for training the attentive probe. We train the probes in several low-shot settings: using either 5%, 10%, or 50% of the train set, and take three random splits in each setting to obtain more robust metrics, resulting in nine different evaluation experiments for each model. We report the mean and standard deviation on the official validation K400 and SSv2 validation sets. V-JEPA is more label-efficient than other models—specifically, decreasing the available number of labeled examples from each class increases the performance gap between V-JEPA and the baselines.

Previous work had to do full fine-tuning, which means that after pre-training your model, when you want the model to get really good at fine-grained action recognition while you’re adapting your model to take on that task, you have to update the parameters or the weights in all of your model. And then that model overall becomes specialized at doing that one task and it’s not going to be good for anything else anymore. If you want to teach the model a different task, you have to use different data, and you have to specialize the entire model for this other task. With V-JEPA, as we’ve demonstrated in this work, we can pre-train the model once without any labeled data, fix that, and then reuse those same parts of the model for several different tasks, like action classification, recognition of fine-grained object interactions, and activity localization.

![](ai-leaders-insights/技术路径与方法论/世界模型流派/JEPA架构/images/5a2babdec7356eef71a4968378509a07.png)

A self-supervised approach for learning representations from video, V-JEPA can be applied to various downstream image and video tasks without adaption of the model parameters. V-JEPA outperforms previous video representation learning approaches in frozen evaluation on image classification, action classification, and spatio-temporal action detection tasks.

## Avenues for future research...

While the “V” in V-JEPA stands for “video,” it only accounts for the visual content of videos thus far. A more multimodal approach is an obvious next step, so we’re thinking carefully about incorporating audio along with the visuals.

As a proof of concept, the current V-JEPA model excels at fine-grained object interactions and distinguishing detailed object-to-object interactions that happen over time. For example, if the model needs to be able to distinguish between someone putting down a pen, picking up a pen, and pretending to put down a pen but not actually doing it, V-JEPA is quite good compared to previous methods for that high-grade action recognition task. However, those things work on relatively short time scales. If you show V-JEPA a video clip of a few seconds, maybe up to 10 seconds, it’s great for that. So another important step for us is thinking about planning and the model’s ability to make predictions over a longer time horizon.

## ...and the path toward AMI

To date, our work with V-JEPA has been primarily about perception—understanding the contents of various video streams in order to obtain some context about the world immediately surrounding us. The predictor in this Joint Embedding Predictive Architecture serves as an early physical world model: You don’t have to see everything that’s happening in the frame, and it can tell you conceptually what’s happening there. As a next step, we want to show how we can use this kind of a predictor or world model for planning or sequential decision-making.

We know that it’s possible to train JEPA models on video data without requiring strong supervision and that they can watch videos in the way an infant might—just observing the world passively, learning a lot of interesting things about how to understand the context of those videos in such a way that, with a small amount of labeled data, you can quickly acquire a new task and ability to recognize different actions.

V-JEPA is a research model, and we’re exploring a number of future applications. For example, we expect that the context V-JEPA provides could be useful for our embodied AI work as well as our work to build a contextual AI assistant for future AR glasses. We firmly believe in the value of responsible open science, and that’s why we’re releasing the V-JEPA model under the CC BY-NC license so other researchers can extend this work.

[Read the paper](https://ai.meta.com/research/publications/revisiting-feature-prediction-for-learning-visual-representations-from-video/)  
  
[Get the code](https://github.com/facebookresearch/jepa)

---

Share:

---

Our latest updates delivered to your inbox

[Subscribe](https://ai.facebook.com/subscribe/) to our newsletter to keep up with Meta AI news, events, research breakthroughs, and more.

Join us in the pursuit of what’s possible with AI.

[See all open positions](https://www.metacareers.com/jobs/?is_leadership=0&sub_teams%5B0%5D=Artificial+Intelligence&is_in_page=0&fbclid=IwAR0O8BF7opOj5gASJmwYVGalPPXTLu-6xrl9w00eC7Rarp2HQ9uEH8tERFw)

Related Posts

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.2365-6/338318848_238475658638014_6444534044370711549_n.gif?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=sVwBs67VZNkQ7kNvwFYAR3U&_nc_oc=AdlzTocN7bFQLvbdDr7Sccwok1l4aIERhSIRzZ2ySGKS0jAt9OnpcgjIwzs83-cj4Y4&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_Afjnm7iJl1nPfOBvmuvgWVzmk89qQuMdtvk-Qyg_A2H18g&oe=6944A929)

Computer Vision

Introducing Segment Anything: Working toward the first foundation model for image segmentation

April 5, 2023

[Read post](https://ai.meta.com/blog/segment-anything-foundation-model-image-segmentation/)

FEATURED

![](ai-leaders-insights/技术路径与方法论/世界模型流派/JEPA架构/images/7911be9e2b062f8e8e8876239649c01f.jpg)

Research

MultiRay: Optimizing efficiency for large-scale AI models

November 18, 2022

[Read post](https://ai.meta.com/blog/multiray-large-scale-AI-models/)

FEATURED

![](ai-leaders-insights/技术路径与方法论/世界模型流派/JEPA架构/images/a58582392aacb1c47bec5d13504e412f.png)

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

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.2365-6/87524316_2677189655726266_6338721200264445952_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=df33cwwvHMEQ7kNvwGYPnZt&_nc_oc=Adkfam2Xd8oEV8hS8C8WJW8xKSbSLROsKBCUUVo_sNU9TPuIFkaAnMv8kcr8BIrfU_U&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfiG8Po-SEtSZe8C9A6hIqg_6E-ftHZl1TZTMm4fx7E3UA&oe=69449B78)

[![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/335682312_964107378293184_3093631164486164913_n.svg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=K-H1ELUclsAQ7kNvwFPhyJ0&_nc_oc=AdnfwYsgeNO726apW4DXzJqIbM-ILOdsJX9N91NwWLnPQp7T9KheKftfMYyxTiog7gk&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfjYaDImI2CLlTupzCE6CGUxRd7pTzYXjp47A5a-ItZfkA&oe=693021E7)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/335682312_964107378293184_3093631164486164913_n.svg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=K-H1ELUclsAQ7kNvwFPhyJ0&_nc_oc=AdnfwYsgeNO726apW4DXzJqIbM-ILOdsJX9N91NwWLnPQp7T9KheKftfMYyxTiog7gk&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfjYaDImI2CLlTupzCE6CGUxRd7pTzYXjp47A5a-ItZfkA&oe=693021E7)](https://www.facebook.com/aiatmeta/)

[![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/336009607_1870102080040414_6753977241281150924_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=LeGtn766Rm4Q7kNvwGKpFvd&_nc_oc=AdlLFSC-f6x2BlA-z1U0oyrQhunJPuPx6laHKQUcPkhj745xUQEtRQK1vq-dXCoEycE&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfiYXisLg_QRHc8WrDYOLHOKB5r-Vsf5m5-_eoUvIdz-0A&oe=69301A22)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/336009607_1870102080040414_6753977241281150924_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=LeGtn766Rm4Q7kNvwGKpFvd&_nc_oc=AdlLFSC-f6x2BlA-z1U0oyrQhunJPuPx6laHKQUcPkhj745xUQEtRQK1vq-dXCoEycE&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfiYXisLg_QRHc8WrDYOLHOKB5r-Vsf5m5-_eoUvIdz-0A&oe=69301A22)](https://twitter.com/aiatmeta/)

[![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/336289415_1541032296405649_2165099305308791297_n.svg?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yr3zuUlwW8oQ7kNvwEUorPv&_nc_oc=AdnV68NHAsQjQjpEcvJ-8IRKSKPAzUDDNNbTOebK1LZ74_z6ZlZQzs2Jct8bk4lX1xI&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfhsTrbmQJxsQb4xzt7qoFzopIOV0TGJcJKXOmdX7F4lUA&oe=693045FB)

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/336289415_1541032296405649_2165099305308791297_n.svg?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yr3zuUlwW8oQ7kNvwEUorPv&_nc_oc=AdnV68NHAsQjQjpEcvJ-8IRKSKPAzUDDNNbTOebK1LZ74_z6ZlZQzs2Jct8bk4lX1xI&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfhsTrbmQJxsQb4xzt7qoFzopIOV0TGJcJKXOmdX7F4lUA&oe=693045FB)](https://www.linkedin.com/showcase/aiatmeta)

[![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/335648731_142576991793348_7786819189843639239_n.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=WjfuuM_g9RsQ7kNvwFUAdLJ&_nc_oc=AdlX0_S2fd7rTRM5Sx8A5Nm1QJl4lfQpDRfkEIM8MyeTSPDGQYn8hCiPKlJMDz1Iqmc&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfjOp79EQMc0uYNwBrCKhXwI41ZdRe63ZHoMPkAXeQV0AA&oe=6930272E)

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/335648731_142576991793348_7786819189843639239_n.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=WjfuuM_g9RsQ7kNvwFUAdLJ&_nc_oc=AdlX0_S2fd7rTRM5Sx8A5Nm1QJl4lfQpDRfkEIM8MyeTSPDGQYn8hCiPKlJMDz1Iqmc&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfjOp79EQMc0uYNwBrCKhXwI41ZdRe63ZHoMPkAXeQV0AA&oe=6930272E)](https://www.youtube.com/@aiatmeta)

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

[![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/335682312_964107378293184_3093631164486164913_n.svg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=K-H1ELUclsAQ7kNvwFPhyJ0&_nc_oc=AdnfwYsgeNO726apW4DXzJqIbM-ILOdsJX9N91NwWLnPQp7T9KheKftfMYyxTiog7gk&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfjYaDImI2CLlTupzCE6CGUxRd7pTzYXjp47A5a-ItZfkA&oe=693021E7)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/335682312_964107378293184_3093631164486164913_n.svg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=K-H1ELUclsAQ7kNvwFPhyJ0&_nc_oc=AdnfwYsgeNO726apW4DXzJqIbM-ILOdsJX9N91NwWLnPQp7T9KheKftfMYyxTiog7gk&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfjYaDImI2CLlTupzCE6CGUxRd7pTzYXjp47A5a-ItZfkA&oe=693021E7)](https://www.facebook.com/aiatmeta/)

[![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/336009607_1870102080040414_6753977241281150924_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=LeGtn766Rm4Q7kNvwGKpFvd&_nc_oc=AdlLFSC-f6x2BlA-z1U0oyrQhunJPuPx6laHKQUcPkhj745xUQEtRQK1vq-dXCoEycE&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfiYXisLg_QRHc8WrDYOLHOKB5r-Vsf5m5-_eoUvIdz-0A&oe=69301A22)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/336009607_1870102080040414_6753977241281150924_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=LeGtn766Rm4Q7kNvwGKpFvd&_nc_oc=AdlLFSC-f6x2BlA-z1U0oyrQhunJPuPx6laHKQUcPkhj745xUQEtRQK1vq-dXCoEycE&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfiYXisLg_QRHc8WrDYOLHOKB5r-Vsf5m5-_eoUvIdz-0A&oe=69301A22)](https://twitter.com/aiatmeta/)

[![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/336289415_1541032296405649_2165099305308791297_n.svg?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yr3zuUlwW8oQ7kNvwEUorPv&_nc_oc=AdnV68NHAsQjQjpEcvJ-8IRKSKPAzUDDNNbTOebK1LZ74_z6ZlZQzs2Jct8bk4lX1xI&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfhsTrbmQJxsQb4xzt7qoFzopIOV0TGJcJKXOmdX7F4lUA&oe=693045FB)

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/336289415_1541032296405649_2165099305308791297_n.svg?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yr3zuUlwW8oQ7kNvwEUorPv&_nc_oc=AdnV68NHAsQjQjpEcvJ-8IRKSKPAzUDDNNbTOebK1LZ74_z6ZlZQzs2Jct8bk4lX1xI&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfhsTrbmQJxsQb4xzt7qoFzopIOV0TGJcJKXOmdX7F4lUA&oe=693045FB)](https://www.linkedin.com/showcase/aiatmeta)

[![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/335648731_142576991793348_7786819189843639239_n.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=WjfuuM_g9RsQ7kNvwFUAdLJ&_nc_oc=AdlX0_S2fd7rTRM5Sx8A5Nm1QJl4lfQpDRfkEIM8MyeTSPDGQYn8hCiPKlJMDz1Iqmc&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfjOp79EQMc0uYNwBrCKhXwI41ZdRe63ZHoMPkAXeQV0AA&oe=6930272E)

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/335648731_142576991793348_7786819189843639239_n.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=WjfuuM_g9RsQ7kNvwFUAdLJ&_nc_oc=AdlX0_S2fd7rTRM5Sx8A5Nm1QJl4lfQpDRfkEIM8MyeTSPDGQYn8hCiPKlJMDz1Iqmc&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfjOp79EQMc0uYNwBrCKhXwI41ZdRe63ZHoMPkAXeQV0AA&oe=6930272E)](https://www.youtube.com/@aiatmeta)

[Privacy Policy](https://www.facebook.com/about/privacy/)

[Terms](https://www.facebook.com/policies/)

[Cookies](https://www.facebook.com/policies/cookies/)

Meta © 2025

[![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/335682312_964107378293184_3093631164486164913_n.svg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=K-H1ELUclsAQ7kNvwFPhyJ0&_nc_oc=AdnfwYsgeNO726apW4DXzJqIbM-ILOdsJX9N91NwWLnPQp7T9KheKftfMYyxTiog7gk&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfjYaDImI2CLlTupzCE6CGUxRd7pTzYXjp47A5a-ItZfkA&oe=693021E7)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/335682312_964107378293184_3093631164486164913_n.svg?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=K-H1ELUclsAQ7kNvwFPhyJ0&_nc_oc=AdnfwYsgeNO726apW4DXzJqIbM-ILOdsJX9N91NwWLnPQp7T9KheKftfMYyxTiog7gk&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfjYaDImI2CLlTupzCE6CGUxRd7pTzYXjp47A5a-ItZfkA&oe=693021E7)](https://www.facebook.com/aiatmeta/)

[![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/336009607_1870102080040414_6753977241281150924_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=LeGtn766Rm4Q7kNvwGKpFvd&_nc_oc=AdlLFSC-f6x2BlA-z1U0oyrQhunJPuPx6laHKQUcPkhj745xUQEtRQK1vq-dXCoEycE&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfiYXisLg_QRHc8WrDYOLHOKB5r-Vsf5m5-_eoUvIdz-0A&oe=69301A22)

![](https://scontent-iad3-2.xx.fbcdn.net/v/t39.8562-6/336009607_1870102080040414_6753977241281150924_n.svg?_nc_cat=103&ccb=1-7&_nc_sid=e280be&_nc_ohc=LeGtn766Rm4Q7kNvwGKpFvd&_nc_oc=AdlLFSC-f6x2BlA-z1U0oyrQhunJPuPx6laHKQUcPkhj745xUQEtRQK1vq-dXCoEycE&_nc_zt=14&_nc_ht=scontent-iad3-2.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfiYXisLg_QRHc8WrDYOLHOKB5r-Vsf5m5-_eoUvIdz-0A&oe=69301A22)](https://twitter.com/aiatmeta/)

[![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/336289415_1541032296405649_2165099305308791297_n.svg?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yr3zuUlwW8oQ7kNvwEUorPv&_nc_oc=AdnV68NHAsQjQjpEcvJ-8IRKSKPAzUDDNNbTOebK1LZ74_z6ZlZQzs2Jct8bk4lX1xI&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfhsTrbmQJxsQb4xzt7qoFzopIOV0TGJcJKXOmdX7F4lUA&oe=693045FB)

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/336289415_1541032296405649_2165099305308791297_n.svg?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=Yr3zuUlwW8oQ7kNvwEUorPv&_nc_oc=AdnV68NHAsQjQjpEcvJ-8IRKSKPAzUDDNNbTOebK1LZ74_z6ZlZQzs2Jct8bk4lX1xI&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfhsTrbmQJxsQb4xzt7qoFzopIOV0TGJcJKXOmdX7F4lUA&oe=693045FB)](https://www.linkedin.com/showcase/aiatmeta)

[![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/335648731_142576991793348_7786819189843639239_n.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=WjfuuM_g9RsQ7kNvwFUAdLJ&_nc_oc=AdlX0_S2fd7rTRM5Sx8A5Nm1QJl4lfQpDRfkEIM8MyeTSPDGQYn8hCiPKlJMDz1Iqmc&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfjOp79EQMc0uYNwBrCKhXwI41ZdRe63ZHoMPkAXeQV0AA&oe=6930272E)

![](https://scontent-iad3-1.xx.fbcdn.net/v/t39.8562-6/335648731_142576991793348_7786819189843639239_n.svg?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=WjfuuM_g9RsQ7kNvwFUAdLJ&_nc_oc=AdlX0_S2fd7rTRM5Sx8A5Nm1QJl4lfQpDRfkEIM8MyeTSPDGQYn8hCiPKlJMDz1Iqmc&_nc_zt=14&_nc_ht=scontent-iad3-1.xx&_nc_gid=7dY7QXHrXKARmSO8GunS9Q&oh=00_AfjOp79EQMc0uYNwBrCKhXwI41ZdRe63ZHoMPkAXeQV0AA&oe=6930272E)](https://www.youtube.com/@aiatmeta)

---

*爬取时间: 2025-11-28 21:49:42*
