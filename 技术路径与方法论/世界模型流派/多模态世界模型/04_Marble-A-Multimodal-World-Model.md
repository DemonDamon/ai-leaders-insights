# Marble: A Multimodal World Model

**来源**: [https://www.worldlabs.ai/blog/marble-world-model](https://www.worldlabs.ai/blog/marble-world-model)

---

# Marble: A Multimodal World Model | World Labs

原文链接: https://www.worldlabs.ai/blog/marble-world-model

November 12, 2025Marble, our frontier multimodal world model, is available to everyone starting today

# Marble: A Multimodal World Model

[](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/hero.mp4)

Spatial intelligence is the next frontier in AI,
demanding powerful world models to realize its full potential.
World models should reconstruct, generate, and simulate 3D worlds;
and allow both humans and agents to interact with them.
Spatially intelligent world models will
transform a wide variety of industries over the coming years.

Two months ago we shared a [preview of Marble](bigger-better-worlds),
our World Model that creates 3D worlds from image or text prompts.
Since then, Marble has been available to an early set of beta users
to create 3D worlds for themselves.

Today we are making Marble,
a first-in-class generative multimodal world model,
generally available for anyone to use.
We have also drastically expanded Marble's capabilities,
and are excited to highlight them here:

**Multimodal Marble**:
Marble is now massively multimodal.
Marble can create 3D worlds from text, images, video, or coarse 3D layouts;
Marble also lets you interactively edit, expand, and combine worlds.
Once generated, 3D worlds can be exported as Gaussian splats, meshes, or videos.
These new capabilities let users create and edit worlds with fine-grained control;
and makes those worlds more useful than ever before.

**Marble Labs**:
We are launching [Marble Labs](/labs),
a creative hub where imagination meets experimentation.
It is where artists, engineers, and designers push the boundaries of world models,
showcasing bold ideas, real-world workflows,
and new possibilities across gaming, VFX, design, robotics, and beyond.
Marble Labs is also home to in-depth case studies, tutorials, and documentation
that give anyone the tools to learn, build, and share their own 3D worlds.

Sign up at [marble.worldlabs.ai](https://marble.worldlabs.ai/) and start creating worlds for yourself!

## The Marble World Model

Our human experience of the world is inherently multimodal:
we use all of our senses to make sense of the world around us.
We integrate sight, sound, touch, and language to build up a mental model of the outside world;
these different representations work together, enriching and reinforcing each other to
let us reason about the world and act within it.

World models should work similarly.
They should be massively multimodal, able to lift whatever input signals are available
into a full 3D world, and they should be able to iteratively update their understanding
of the world as new information becomes available.

Marble is the first of its kind - a next-generation world model making strides toward this vision.
It can now create 3D worlds from a wide variety of input types,
and lets users iteratively edit or expand worlds.

Marble's new capabilities let you dive as deep as you want in controlling your generated worlds.
You can quickly create full 3D worlds from a simple image or text prompt
or interactively edit worlds in both 2D and 3D,
bringing to life a precise vision of a world in your mind.

![](/images/MarbleWorldModelV4.svg)

## Text and Image to World

To start, Marble can create a full 3D world from a single image or a short text prompt.
This is the simplest and easiest way to create worlds.
Marble can generate worlds with a wide variety of scene types and artistic styles.

Image prompts make it easy to combine Marble with other AI tools.
You can generate images with your favorite image generation model,
then bring it to Marble to lift it to a full 3D world.

Text Prompt

A detailed, lived-in hobbit kitchen filled with woven baskets and copper kettles,
awash in calm pale-blue daylight and soft ambient shadow

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/t2w-hobbit-kitchen.mp4)

Image Prompt

![](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/4aa69fb321ca5469fd8d77cc88e53ed7.jpg)

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/i2w-living-room.mp4)

Text Prompt

A station kitchen blending mid-century diner aesthetics with orbital tech,
featuring checkered floors and stainless fixtures under soft aqua illumination.

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/t2w-blue-diner.mp4)

Image Prompt

![](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/e6fba471e56d53b2a9bef081e95178a7.jpg)

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/i2w-victorian-foyer.mp4)

Text Prompt

A sunlit stone castle courtyard with ivy-covered walls,
bathed in warm golden morning light and soft drifting shadows.

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/t2w-castle-courtyard.mp4)

Image Prompt

![](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/fd8a0cbf980db4b1697d67652098f3a6.jpg)

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/i2w-mushroom-forest.mp4)

Text Prompt

A whimsical anime library painted in pastel pinks and mint greens,
with cloud-shaped pillows in cozy cubby reading corners.

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/t2w-anime-library.mp4)

Text-to-world generation

Text-to-world generation

Text and image prompts are intuitive and powerful,
but limited in creative control:
Marble must invent all the details of the world that are not present in the input text or image prompt.
This is often magical;
but sometimes you may want to steer Marble more directly toward a desired world.

## Multi-Image and Video to World

An easy way to create worlds with more creative control is **multi-image prompting**.
Marble can accept different prompt images for different parts of the world,
stitching them together into a unified 3D world.

Multi-image prompts let you create worlds with more precision.
Unlike text or single-image prompts where Marble must invent all parts of the world not
present in the prompt, with multi-image prompts you can control what the generated
world will look like from different angles.

This leads to a brand-new workflow for generating worlds.
You can use your favorite image generation tool to iterate separately on the
input views, and Marble will lift them into full 3D worlds while also adding
seamless transitions between the input views.

Multi-Image Prompt

![Front](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/71d4e3a7184cadca397e52573d6422b3.jpg)

Front

![Back](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/24122b5055d17b4bb94ad2117ac9af7c.jpg)

Back

![Front](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/71d4e3a7184cadca397e52573d6422b3.jpg)

Front

![Back](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/24122b5055d17b4bb94ad2117ac9af7c.jpg)

Back

![Front](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/71d4e3a7184cadca397e52573d6422b3.jpg)

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/mim2w-blue-pink-room.mp4)

Multi-Image Prompt

![Front](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/5b054aa51e2430b41fc759187688b24a.jpg)

Front

![Back](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/5e4f7bc216f01aa3f8e96e00269a5633.jpg)

Back

![Right](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/221a129856ec992356bb8f65bfac4efd.jpg)

Right

![Front](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/5b054aa51e2430b41fc759187688b24a.jpg)

Front

![Back](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/5e4f7bc216f01aa3f8e96e00269a5633.jpg)

Back

![Right](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/221a129856ec992356bb8f65bfac4efd.jpg)

Right

![Front](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/5b054aa51e2430b41fc759187688b24a.jpg)

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/mim2w-overgrown-courtyard.mp4)

Multi-Image Prompt

![Front](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/f6c52bd678959b3162446d83dc4c320b.jpg)

Front

![Back](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/543bfbc11efe1a00a7e004f569d9a2a9.jpg)

Back

![Front](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/f6c52bd678959b3162446d83dc4c320b.jpg)

Front

![Back](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/543bfbc11efe1a00a7e004f569d9a2a9.jpg)

Back

![Front](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/f6c52bd678959b3162446d83dc4c320b.jpg)

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/mim2w-monkey-rainbow.mp4)

Multi-Image Prompt

![Front](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/71aab0f4addfe26d588516f01ac2013b.jpg)

Front

![Back](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/44e6810be72dba4f970d1ae6ab62290a.jpg)

Back

![Front](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/71aab0f4addfe26d588516f01ac2013b.jpg)

Front

![Back](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/44e6810be72dba4f970d1ae6ab62290a.jpg)

Back

![Front](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/71aab0f4addfe26d588516f01ac2013b.jpg)

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/mim2w-desert-diner.mp4)

Multiple Images to World

Multiple Images to World

Multi-image prompts can also be used to create worlds inspired by real-world spaces.
Marble can input a few photos or a short video depicting a real-world location from
different angles, and it will combine them to generate a 3D world with elements of
the real-world space.

Multi-Image Prompt

![Image 1](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/5a055540423f5416e9b9fec1772225f6.jpg)

![Image 2](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/0186b427f968a96a6a9582928062da37.jpg)

![Image 3](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/08a335751ed983b53bcdd5842bd7a9bb.jpg)

![Image 4](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/6f87ccb55d56667795ab61c63f138a06.jpg)

![Image 1](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/5a055540423f5416e9b9fec1772225f6.jpg)

![Image 2](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/0186b427f968a96a6a9582928062da37.jpg)

![Image 3](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/08a335751ed983b53bcdd5842bd7a9bb.jpg)

![Image 4](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/6f87ccb55d56667795ab61c63f138a06.jpg)

![Selected image 1](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/5a055540423f5416e9b9fec1772225f6.jpg)

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/mia2w-everest.mp4)

Multi-Image Prompt

![Image 1](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/1d8fdfcf534a94bb2a67f3bb714bda22.jpg)

![Image 2](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/0136548764775dfa69a93ee1b265399f.jpg)

![Image 3](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/79d960a9eef9d9359e232d3dc2f20d48.jpg)

![Image 4](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/c66c7f32c5c7fa373eb177de28139f4f.jpg)

![Image 5](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/6c751f4208df6eec5824366b907c1c8d.jpg)

![Image 1](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/1d8fdfcf534a94bb2a67f3bb714bda22.jpg)

![Image 2](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/0136548764775dfa69a93ee1b265399f.jpg)

![Image 3](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/79d960a9eef9d9359e232d3dc2f20d48.jpg)

![Image 4](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/c66c7f32c5c7fa373eb177de28139f4f.jpg)

![Image 5](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/6c751f4208df6eec5824366b907c1c8d.jpg)

![Selected image 1](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/1d8fdfcf534a94bb2a67f3bb714bda22.jpg)

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/mia2w-pingpong.mp4)

Multi-image prompts can generate worlds from real-world photos

Multi-image prompts can generate worlds from real-world photos

## World Editing

The creative process is highly iterative for many users.
Often, generating a world is only the start of a creative journey.
Seeing a generated 3D world often kicks off a dozen more ideas for
changing it or improving it.

Marble includes AI-native world editing tools.
Edits can be small and local: remove an object, touch up an area.
They can also be more drastic: swap objects, change the visual style,
or re-structure large parts of the world.
This gives a new level of fine-grained control to the world creation process.

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/edit-cozy-tavern-post.mp4)

Edited

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/edit-cozy-tavern-pre.mp4)

Original

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/edit-turtles-post.mp4)

Edited

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/edit-turtles-pre.mp4)

Original

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/edit-alley-post.mp4)

Edited

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/edit-alley-pre.mp4)

Original

Edit: Turn the entire back wall into a stage, and replace the tables with low benches facing the stage

Edit: Turn the entire back wall into a stage, and replace the tables with low benches facing the stage

World editing lets you re-imagine the same space in endless different ways.

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/edit-kitchen-counters.mp4)

Edited

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/edit-kitchen-orig.mp4)

Original

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/edit-kitchen-floor.mp4)

Edited

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/edit-kitchen-orig.mp4)

Original

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/edit-kitchen-cabinets.mp4)

Edited

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/edit-kitchen-orig.mp4)

Original

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/edit-kitchen-conversation.mp4)

Edited

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/edit-kitchen-orig.mp4)

Original

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/edit-kitchen-pit.mp4)

Edited

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/edit-kitchen-orig.mp4)

Original

Edit: Change all the kitchen counters to black granite

Edit: Change all the kitchen counters to black granite

## Chisel: Sculpting Worlds in 3D

Marble's multimodal inputs and editing features give a lot of control over your generated 3D worlds.
But sometimes, creating the world exactly as you see it in your mind's eye requires finer-grained control
over the scene layout or exact sizes and positions of objects.

For these situations we are introducing **Chisel**, an AI-native tool to sculpt Marble worlds directly in 3D.

Chisel is a new experimental editing mode for advanced users to create 3D worlds.
It lets you lay out the coarse structure of your world in 3D
using coarse 3D shapes like boxes or planes,
or importing existing 3D assets into the scene.

After laying out the coarse 3D scene, you can add a text prompt to describe the visual style of the scene,
or additional elements not present in the coarse layout.
Marble will combine these inputs to give you a fully detailed 3D world.

Chisel decouples **structure** from **style**.
The coarse 3D scene determines the world's structure,
while the text prompt controls its overall style.
The two can be mixed in any combination, adding a whole new dimension of control to world generation.

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/chisel-gallery-v2-a-scene.mp4)

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/chisel-gallery-v2-a-3d.mp4)

Coarse 3D

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/chisel-gallery-v2-b-3d.mp4)

Coarse 3D After

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/chisel-gallery-v2-a-3d.mp4)

Coarse 3D Before

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/chisel-gallery-v2-b-scene.mp4)

Generated World After

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/chisel-gallery-v2-a-scene.mp4)

Generated World Before

Text prompt: A beautiful modern art museum with wooden flooring, filled with colorful paintings and curving sculptures

Text prompt: A beautiful modern art museum with wooden flooring, filled with colorful paintings and curving sculptures

The coarse 3D scene can be as simple or complex as you want.
In addition to building the coarse 3D scene out of basic blocks and walls,
you can import existing 3D assets of objects.
Objects will be restyled based on the text prompt to give a cohesive 3D world.

Varying the text prompt can give rise to 3D worlds with drastically different
visual styles and appearances that all share a common structure determined
by the coarse 3D scene.

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/chisel-bedroom2-scandinavian.mp4)

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/chisel-bedroom2-3d.mp4)

Coarse 3D

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/chisel-bedroom2-japanese.mp4)

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/chisel-bedroom2-3d.mp4)

Coarse 3D

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/chisel-bedroom2-mediterranean.mp4)

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/chisel-bedroom2-3d.mp4)

Coarse 3D

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/chisel-bedroom2-fantasy.mp4)

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/chisel-bedroom2-3d.mp4)

Coarse 3D

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/chisel-bedroom2-tuscany.mp4)

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/chisel-bedroom2-3d.mp4)

Coarse 3D

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/chisel-bedroom2-stone.mp4)

Generated World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/chisel-bedroom2-3d.mp4)

Coarse 3D

Text Prompt: A serene scandinavian guesthouse bedroom with stunning views of glaciers

Text Prompt: A serene scandinavian guesthouse bedroom with stunning views of glaciers

## Building Large Worlds by Expanding and Composing

Sometimes bigger really is better.
Larger worlds give more possibilities, more space, more room for your creativity to shine.
Marble offers two ways to make bigger worlds than ever before.

After a world has been generated, Marble allows one-step **expansion** to make it larger.
You are in control of this process: you can select a region of the world to
be expanded, and Marble will create more content to fill the selected region.

Expansion can make worlds larger. Regions of the world that previously broke
down into artifacts can become crisp and clean after expansion.
Expansion can also be used to add detail to targeted regions of a world.
Sometimes the back of a table or the far corner of a room is not a crisp
as the room's center; expanding the world in that region can improve it.

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/expand-interior-post.mp4)

Expanded World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/expand-interior-pre.mp4)

Initial World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/expand-room-post.mp4)

Expanded World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/expand-room-pre.mp4)

Initial World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/expand-garden-post.mp4)

Expanded World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/expand-garden-pre.mp4)

Initial World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/expand-library-post.mp4)

Expanded World

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/expand-library-pre.mp4)

Initial World

Marble can expand scenes to create larger traversable areas

Marble can expand scenes to create larger traversable areas

In addition to generating individual worlds, you can **compose** any number of
worlds to build out extremely large spaces with Marble's composer mode.
This composition is entirely under your control: you can choose exactly which worlds
to compose, and exactly how to lay them out relative to each other.
Composing is yet another way to build worlds that follow your creative vision.

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/stitched-train.mp4)

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/stitched-spaceship.mp4)

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/stitched-house.mp4)

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/stitched-haunted.mp4)

A large train composed with Marble

A large train composed with Marble

## Exporting Worlds to 3D and Video

After creating a world with Marble you have many options to export it
for incorporation into downstream projects.

**Gaussian splats** are the highest-fidelity representation for Marble worlds.
They represent 3D scenes as a large set of semitransparent particles.
You can render Gaussian splats in the browser using [Spark](https://sparkjs.dev/),
our open-source cross-platform renderer integrated with THREE.js.

Marble worlds can also be exported as triangle meshes.
Marble can generate both **collider meshes**, which are low-fidelity meshes intended for
coarse physics simulation; and **high-quality meshes** which are intended to match the
visual fidelity of Gaussian splats as closely as possible.
Exporting worlds as meshes lets them interoperate with many industry-standard tools.

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/mesh-v2-grey.mp4)

Mesh

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/mesh-v2-splats.mp4)

Splats

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/mesh-v2-shaded-lights.mp4)

Mesh with lighting

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/mesh-v2-grey-lights.mp4)

Mesh with lighting

Marble can export generated worlds as Gaussian splats or triangle meshes

Marble can export generated worlds as Gaussian splats or triangle meshes

Marble worlds exist in full 3D, but sometimes a video is the best way to share a world.
You can use Marble to render generated worlds to videos with pixel-accurate camera control,
letting you frame every shot just as you imagine it.
In fact, **nearly all the videos in this post were generated directly from Marble**.

Marble can also **enhance** exported videos.
Enhanced videos can add detail, remove artifacts, and add dynamic elements to the scene,
while maintaining pixel-perfect camera control and adhering to the structure of the
generated 3D world.

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/video-cabin-post.mp4)

Enhanced Video

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/video-cabin-pre.mp4)

Original Video

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/video-ocean-post.mp4)

Enhanced Video

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/video-ocean-pre.mp4)

Original Video

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/video-mushroom-forest-post.mp4)

Enhanced Video

[Your browser does not support video playback.](https://wlt-ai-cdn.art/videos/2025-11-12-clean-720p-24crf/video-mushroom-forest-pre.mp4)

Original Video

Enhanced videos clean up artifacts and introduce motion in the scene. Notice the smoke above the chimney, the dancing flames, and the flowing water.

Enhanced videos clean up artifacts and introduce motion in the scene. Notice the smoke above the chimney, the dancing flames, and the flowing water.

## Marble Labs: A Glimpse of Future Possibilities

While flexing your creativity in Marble, Marble Labs may further inspire your imagination.
This is where artists, engineers, and designers are already shaping what comes next.
From cinematic filmmaking and interactive worlds to robotics simulations and therapeutic environments,
these projects show how Marble is transforming imagination into reality.
Each one reflects a new way of building with world models, both creative and technical.
Explore Marble Labs to see what others are creating and discover how you can start building your own worlds today.

[

Your browser does not support video playback.

](https://wlt-ai-cdn.art/videos/marble_labs/marble-highlight.mp4)

## From Marble to Spatial Intelligence

Marble is a state-of-the-art generative world model.
Today it lets you create worlds from diverse input types, edit them, expand them, and export them.
These capabilities give you unprecedented levels of control when creating worlds,
and are already enabling a wide variety of creative use cases across industries.

But Marble is just a step on our journey toward spatial intelligence.
Going forward, a key opportunity is **interactivity**.
Future world models will let humans and agents alike interact with generated worlds in new ways,
unlocking even more use cases in simulation, robotics, and beyond.

## Try Marble Today

Marble is available today at
[marble.worldlabs.ai](https://marble.worldlabs.ai/).
Sign up now and start creating worlds!

If you are excited about this vision and want to help us build it,
[join us](https://jobs.ashbyhq.com/worldlabs)!

## Read More

[November 10, 2025

### From Words to Worlds: Spatial Intelligence is AI’s Next Frontier

A manifesto piece explaining what spatial intelligence is, why it matters, and how we’re building the world models that will unlock it—with impact that will reshape creativity, embodied intelligence, and human progress.

![From Words to Worlds: Spatial Intelligence is AI’s Next Frontier](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/078e73a494b4ef531fed614aedb2c836.jpg)](/blog/from-words-to-worlds)[October 16, 2025

### RTFM: A Real-Time Frame Model

A research preview of RTFM, a new generative world model that generates video in real-time as you interact with it.

![RTFM: A Real-Time Frame Model](ai-leaders-insights/技术路径与方法论/世界模型流派/多模态世界模型/images/d85722abce1c35ea8007c310e7f68a86.jpg)](/blog/rtfm)

---

*爬取时间: 2025-11-28 21:50:17*
