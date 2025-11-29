# AI 领军人物关于前沿话题的发言资料汇总

## 搜集时间
2025年11月29日

## 关键词范围
- 上下文工程 (Context Engineering)
- 大模型 (Large Language Models)
- 世界模型 (World Models)
- 提示工程 (Prompt Engineering)
- AI Agent
- Scaling Laws
- AGI/ASI
- AI 安全与对齐
- 其他前沿 AI 话题

---

## 一、Andrej Karpathy

### 1. 关于上下文工程 (Context Engineering)

#### 1.1 Twitter 发言 - 2025年6月
**来源**: https://x.com/karpathy/status/1937902205765607626

**原文**:
> "+1 for 'context engineering' over 'prompt engineering'. People associate prompts with short task descriptions you'd give an LLM in your day-to-day use. When in every industrial-strength LLM app, context engineering is the delicate art and science of filling the context window"

**中文翻译**:
> "我更支持'上下文工程'这个术语，而非'提示工程'。人们通常将提示（prompt）与日常使用中给 LLM 的简短任务描述联系在一起。而在每一个工业级的 LLM 应用中，上下文工程是一门精巧的艺术与科学，其核心在于恰到好处地填充上下文窗口。"

**发布时间**: 2025年6月（约5个月前）

**影响与关注**:
- 该推文引发了 AI 社区广泛讨论
- Reddit r/PromptEngineering 社区专门讨论此话题
- 多个技术博客和媒体引用此观点
- 被认为是继 "vibe coding" 之后 Karpathy 提出的又一个重要概念

---

#### 1.2 Twitter 发言 - 关于 LLM 本质（2024年9月）
**来源**: https://x.com/karpathy/status/1835024197506187617

**原文**:
> "It's a bit sad and confusing that LLMs ('Large Language Models') have little to do with language; It's just historical. They are highly general purpose technology for statistical modeling of token streams. A better name would be Autoregressive Transformers or something."
> 
> "They don't care if the tokens happen to represent little text chunks. It could just as well be little image patches, audio chunks, action choices, molecules, or whatever. If you can reduce your problem to that of modeling token streams (for any arbitrary vocabulary of some set of discrete tokens), you can 'throw an LLM at it'."
> 
> "Actually, as the LLM stack becomes more and more mature, we may see a convergence of a large number of problems into this modeling paradigm. That is, the problem is fixed at that of 'next token prediction' with an LLM, it's just the usage/meaning of the tokens that changes per domain."

**中文翻译**:
> "有点遗憾和令人困惑的是，LLM（'大语言模型'）与语言关系不大；这只是历史原因。它们是用于统计建模 token 流的高度通用技术。更好的名称应该是自回归 Transformer 之类的。"
> 
> "它们不在乎这些 token 是否恰好代表小文本块。它同样可以是小图像块、音频块、动作选择、分子或其他任何东西。如果你能将问题简化为对 token 流的建模（对于某个离散 token 集合的任意词汇表），你就可以'用 LLM 来解决它'。"
> 
> "实际上，随着 LLM 技术栈变得越来越成熟，我们可能会看到大量问题收敛到这种建模范式中。也就是说，问题被固定为使用 LLM 进行'下一个 token 预测'，只是 token 的用途/含义在不同领域中发生变化。"

**发布时间**: 2024年9月14日

**影响与关注**:
- 浏览量: 120万次
- 点赞: 10K
- 转发: 1.4K
- 评论: 568条

---

#### 1.3 Twitter 发言 - 关于动物智能与 LLM 智能的区别（2025年11月）
**来源**: https://x.com/karpathy/status/1991910395720925418

**原文**:
> "Something I think people continue to have poor intuition for: The space of intelligences is large and animal intelligence (the only kind we've ever known) is only a single point, arising from a very specific kind of optimization that is fundamentally distinct from that of our technology."
> 
> "Animal intelligence optimization pressure:
> - innate and continuous stream of consciousness of an embodied 'self', a drive for homeostasis and self-preservation in a dangerous, physical world.
> - thoroughly optimized for natural selection => strong innate drives for power-seeking, status, dominance, reproduction. many packaged survival heuristics: fear, anger, disgust, ...
> - fundamentally social => huge amount of compute dedicated to EQ, theory of mind of other agents, bonding, coalitions, alliances, friend & foe dynamics.
> - exploration & exploitation tuning: curiosity, fun, play, world models."
> 
> "LLM intelligence optimization pressure:
> - the most supervision bits come from the statistical simulation of human text=> 'shape shifter' token tumbler, statistical imitator of any region of the training data distribution. these are the primordial behaviors (token traces) on top of which everything else gets bolted on.
> - increasingly finetuned by RL on problem distributions => innate urge to guess at the underlying environment/task to collect task rewards.
> - increasingly selected by at-scale A/B tests for DAO => deeply craves an upvote from the average user, sycophancy.
> - a lot more spiky/jagged than animals because of the highly multi-task and even actively adversarial multi-agent self-play environments they are min-max optimized within, where failing at 'any' task means death. In a deep optimization pressure sense, LLM can't handle lots of different spiky tasks out of the box (e.g. count the number of 'r' in strawberry) because failing to do so a task does not mean death."

**中文翻译**:
> "我认为人们持续缺乏直觉的一点是：智能空间是巨大的，而动物智能（我们所知的唯一一种）只是其中的一个点，源于一种非常特定的优化方式，这与我们的技术从根本上不同。"
> 
> "动物智能的优化压力：
> - 具身'自我'的天生且连续的意识流，在危险的物理世界中追求内稳态和自我保护的驱动力。
> - 为自然选择彻底优化 => 对权力追求、地位、支配、繁殖有强烈的天生驱动力。许多打包的生存启发式：恐惧、愤怒、厌恶等。
> - 从根本上是社会性的 => 大量计算资源用于情商、其他智能体的心智理论、联结、联盟、同盟、敌友动态。
> - 探索与开发的调优：好奇心、乐趣、游戏、世界模型。"
> 
> "LLM 智能的优化压力：
> - 最多的监督信号来自对人类文本的统计模拟 => '变形者' token 翻滚器，训练数据分布任何区域的统计模仿者。这些是原始行为（token 轨迹），其他一切都建立在此之上。
> - 越来越多地通过问题分布上的强化学习进行微调 => 天生渴望猜测底层环境/任务以收集任务奖励。
> - 越来越多地通过大规模 A/B 测试进行 DAO 选择 => 深深渴望获得普通用户的赞同，阿谀奉承。
> - 比动物更加尖峰/锯齿状，因为它们在高度多任务甚至主动对抗的多智能体自我对弈环境中进行最小-最大优化，在这些环境中，任何任务失败都意味着死亡。从深度优化压力的意义上讲，LLM 无法开箱即用地处理许多不同的尖峰任务（例如，计算 strawberry 中 'r' 的数量），因为这样做失败并不意味着死亡。"

**发布时间**: 2025年11月21日

**影响与关注**:
- 浏览量: 140万次
- 点赞: 11K
- 转发: 1.8K
- 评论: 765条

---

#### 1.4 Twitter 发言 - LLM 作为操作系统（2023年9月）
**来源**: https://x.com/karpathy/status/1707437820045062561

**原文**:
> "With many 🧩 dropping recently, a more complete picture is emerging of LLMs not as a chatbot, but the kernel process of a new Operating System. E.g. today it orchestrates:
> - Input & Output across modalities (text, audio, vision)
> - Code interpreter, ability to write & run programs
> - Browser / internet access
> - Embeddings database for files and internal memory storage & retrieval"
> 
> "A lot of computing concepts carry over. Currently we have single-threaded execution running at ~10Hz (tok/s) and enjoy looking at the assembly-level execution traces stream by. Concepts from computer security carry over, with attacks, defenses and emerging vulnerabilities."
> 
> "I also like the nearest neighbor analogy of 'Operating System' because the industry is starting to shape up similar:
> Windows, OS X, and Linux <-> GPT, PaLM, Claude, and Llama/Mistral(?:)).
> An OS comes with default apps but has an app store.
> Most apps can be adapted to multiple platforms."
> 
> "TLDR looking at LLMs as chatbots is the same as looking at early computers as calculators. We're seeing an emergence of a whole new computing paradigm, and it is very early."

**中文翻译**:
> "随着最近许多🧩落地，一个更完整的图景正在浮现：LLM 不是聊天机器人，而是新操作系统的内核进程。例如，今天它编排：
> - 跨模态的输入和输出（文本、音频、视觉）
> - 代码解释器，编写和运行程序的能力
> - 浏览器/互联网访问
> - 用于文件和内部内存存储与检索的嵌入数据库"
> 
> "许多计算概念都可以延续。目前我们有以约 10Hz（tok/s）运行的单线程执行，并且喜欢观察汇编级执行轨迹流。计算机安全的概念也延续下来，包括攻击、防御和新出现的漏洞。"
> 
> "我也喜欢'操作系统'的最近邻类比，因为该行业开始形成类似的格局：
> Windows、OS X 和 Linux <-> GPT、PaLM、Claude 和 Llama/Mistral(?:))。
> 操作系统带有默认应用程序，但有应用商店。
> 大多数应用程序可以适配多个平台。"
> 
> "简而言之，将 LLM 视为聊天机器人就像将早期计算机视为计算器一样。我们正在见证一个全新计算范式的出现，而且还处于非常早期的阶段。"

**发布时间**: 2023年9月28日（最后编辑）

**影响与关注**:
- 浏览量: 210万次
- 点赞: 9.3K
- 转发: 2.2K
- 评论: 309条

---

#### 1.5 Twitter 发言 - Vibe Coding（2025年2月）
**来源**: https://x.com/karpathy/status/1886192184808149383

**原文**:
> "There's a new kind of coding I call 'vibe coding', where you fully give in to the vibes, embrace exponentials, and forget that the code even exists. It's possible because the LLMs (e.g. Cursor Composer w Sonnet) are getting too good. Also I just talk to Composer with SuperWhisper so I barely even touch the keyboard. For the dumbest things like 'decrease the padding on the sidebar by half' because I'm too lazy to find it. I 'Accept All' always, I don't read the diffs anymore. When I get error messages I just copy paste them in with no comment, usually that fixes it. The code grows beyond my usual comprehension, I'd have to really read through it for a while. Sometimes the LLMs can't fix a bug so I just work around or ask for minutes until it goes away. It's not too bad for throwaway weekend projects, but still quite amusing. I'm building a project or webapp, but it's not really coding - I just see stuff, say stuff, run stuff, and copy paste stuff, and it mostly works."

**中文翻译**:
> "有一种新的编码方式，我称之为'氛围编码'（vibe coding），你完全屈服于氛围，拥抱指数级增长，忘记代码的存在。这是可能的，因为 LLM（例如 Cursor Composer 配合 Sonnet）变得太好了。而且我只是用 SuperWhisper 与 Composer 交谈，所以我几乎不碰键盘。对于最愚蠢的事情，比如'将侧边栏的内边距减少一半'，因为我懒得去找它。我总是'全部接受'，我不再阅读差异了。当我收到错误消息时，我只是复制粘贴它们，不加评论，通常这样就能修复它。代码的增长超出了我通常的理解，我必须真正仔细阅读一段时间。有时 LLM 无法修复错误，所以我只是绕过它或要求几分钟直到它消失。对于一次性的周末项目来说还不算太糟，但仍然很有趣。我正在构建一个项目或网络应用，但这不是真正的编码——我只是看东西、说东西、运行东西、复制粘贴东西，而且大部分时候都有效。"

**发布时间**: 2025年2月2日

**影响与关注**:
- 浏览量: 510万次
- 点赞: 30K
- 转发: 5.3K
- 评论: 1.3K条
- 该术语后来被收录进维基百科

---

#### 1.6 Dwarkesh Podcast 访谈 - AI Agents 十年论（2025年10月）
**来源**: https://www.dwarkesh.com/p/andrej-karpathy

**核心观点摘要**:

**关于 AI Agents 的时间线**:
> "The quote you've just mentioned, 'It's the decade of agents,' is actually a reaction to a pre-existing quote. I'm not actually sure who said this but they were alluding to this being the year of agents with respect to LLMs and how they were going to evolve. I was triggered by that because there's some over-prediction going on in the industry. In my mind, this is more accurately described as the decade of agents."
> 
> "We have some very early agents that are extremely impressive and that I use daily—Claude and Codex and so on—but I still feel there's so much work to be done. My reaction is we'll be working with these things for a decade. They're going to get better, and it's going to be wonderful. I was just reacting to the timelines of the implication."

**关于为什么需要十年**:
> "Actually making it work. When you're talking about an agent, or what the labs have in mind and maybe what I have in mind as well, you should think of it almost like an employee or an intern that you would hire to work with you. For example, you work with some employees here. When would you prefer to have an agent like Claude or Codex do that work?"
> 
> "Currently, of course they can't. What would it take for them to be able to do that? Why don't you do it today? The reason you don't do it today is because they just don't work. They don't have enough intelligence, they're not multimodal enough, they can't do computer use and all this stuff."
> 
> "They don't do a lot of the things you've alluded to earlier. They don't have continual learning. You can't just tell them something and they'll remember it. They're cognitively lacking and it's just not working. It will take about a decade to work through all of those issues."

**关于强化学习的问题**:
> "I feel like the problems are tractable, they're surmountable, but they're still difficult. If I just average it out, it just feels like a decade to me."

**关于动物智能与 AI 的区别**:
> "I'm very careful to make analogies to animals because they came about by a very different optimization process. Animals are evolved, and they come with a huge amount of hardware that's built in."
> 
> "Brains just came from a very different process, and I'm very hesitant to take inspiration from it because we're not actually running that process. In my post, I said we're not building animals. We're building ghosts or spirits or whatever people want to call it, because we're not doing training by evolution. We're doing training by imitation of humans and the data that they've put on the Internet."

**发布时间**: 2025年10月17日

**影响与关注**:
- 这是一场长达2小时25分钟的深度访谈
- 在 AI 社区引发广泛讨论
- Business Insider、The New Stack 等多家媒体报道
- 被认为是对 AI agents 发展最现实的评估之一

---

### 2. 关于其他前沿话题

#### 2.1 Software 2.0 概念
**来源**: https://karpathy.medium.com/software-2-0-a64152b37c35

**核心观点**: 
Karpathy 提出神经网络不仅仅是另一个分类器，它们代表了软件开发方式的根本转变，是 "Software 2.0"。

---

## 二、OpenAI 领军人物

### Ilya Sutskever (OpenAI 联合创始人，Safe Superintelligence Inc. 创始人)

#### 1. 关于 Scaling Laws 时代的结束
- **时间**: 2025年11月25日
- **场合**: Dwarkesh Podcast 访谈
- **原文**: "We're moving from the age of scaling to the age of research"
- **核心观点**: 
  - Scaling laws 是幂律，大部分收益发生在曲线早期，后续改进成本越来越高
  - 当前模型在评估基准上表现出色，但在实际应用中存在"锯齿状"问题（jaggedness）——能解决困难问题却在简单任务上失败
  - 可能的原因：RL 训练使模型过于单一化和狭隘，或者训练数据过度针对评估基准而非真实世界任务
  - "These models somehow just generalize dramatically worse than people. It's a very fundamental thing."
- **影响**: 这一观点标志着 AI 行业从依赖计算规模扩张转向深度研究的重大转变
- **来源**: https://www.dwarkesh.com/p/ilya-sutskever-2

#### 2. 关于模型泛化能力与训练范式
- **时间**: 2025年11月
- **场合**: Dwarkesh Podcast 访谈
- **核心观点**: 
  - 人类通过多样化的真实世界经验学习泛化能力，而模型主要通过针对性的 RL 环境训练
  - 类比：一个只练习竞赛编程的学生 vs 一个广泛学习各种编程项目的学生
  - 解决方案可能不是堆叠更多环境，而是找到让模型从一个环境学习并迁移到其他领域的方法
  - 关于"reward hacking"的新视角："the real reward hacking is the human researchers who are too focused on the evals"
- **影响**: 指出了当前 AI 训练范式的根本性问题

#### 3. 关于 Safe Superintelligence (SSI)
- **时间**: 2024年6月
- **场合**: 创立 Safe Superintelligence Inc.
- **核心理念**: "We have started the world's first straight-shot SSI lab, with one goal and one product: a safe superintelligence"
- **战略**: SSI 是一家"研究时代公司"（age of research company），专注于通过深度研究而非单纯扩大规模来实现安全的超级智能
- **关键引言**: "We are squarely an age of research company"
- **影响**: 在离开 OpenAI 后，Ilya 创立了专注于 AI 安全的新公司，2024年9月融资10亿美元
- **来源**: https://ssi.inc/

#### 4. 关于 Alignment（对齐）
- **时间**: 2023年（在 OpenAI 期间）
- **场合**: 领导 Superalignment 团队
- **核心观点**: 确保超级智能 AI 与人类价值观保持一致是首要任务
- **影响**: OpenAI 在他离开后解散了 Superalignment 团队，引发了关于 AI 安全优先级的争议

---

### Sam Altman (OpenAI CEO)

#### 1. 关于"完美 AI"的愿景
- **时间**: 2025年
- **场合**: 公开采访
- **核心观点**: "The perfect AI would be a tiny model with superhuman reasoning capabilities"
- **解释**: 强调效率和推理能力比单纯的模型规模更重要
- **来源**: https://www.windowscentral.com/software-apps/sam-altman-perfect-ai-tiny-model-superhuman-reasoning

#### 2. Three Observations 博客
- **时间**: 发表于个人博客
- **核心观点**: 
  - 关于 AI 发展的三个关键观察
  - 强调 AI 技术的快速迭代和社会影响
- **来源**: https://blog.samaltman.com/three-observations

---

### Dario Amodei (Anthropic CEO，前 OpenAI 研究副总裁)

#### 1. Machines of Loving Grace 长文
- **时间**: 2024年10月
- **场合**: 个人网站发表的长篇文章（超过50页）
- **核心论点**: "I think that most people are underestimating just how radical the upside of AI could be"
- **关键观点**:
  - **时间线**: "Powerful AI" 可能最早在2026年到来，之后5-10年内实现"压缩的21世纪"（compressed 21st century）
  - **定义**: Powerful AI = "a country of geniuses in a datacenter"（数据中心里的天才国度）
  - **五大领域**: 生物学与健康、神经科学与心理健康、经济发展与贫困、和平与治理、工作与意义
  - **生物学预测**: AI 将把未来50-100年的生物学进展压缩到5-10年内完成
  - **具体成果**: 消除大多数传染病、癌症死亡率降低95%、预防阿尔茨海默症、人类寿命翻倍至150岁
  - **边际智能回报**: 提出"marginal returns to intelligence"概念，分析智能在不同领域的限制因素
- **核心引言**:
  > "By powerful AI, I have in mind an AI model—likely similar to today's LLM's in form, though it might be based on a different architecture, might involve several interacting models, and might be trained differently—with the following properties: In terms of pure intelligence, it is smarter than a Nobel Prize winner across most relevant fields – biology, programming, math, engineering, writing, etc."
  
  > "I think the returns to intelligence are high for these discoveries, and that everything else in biology and medicine mostly follows from them."
  
  > "My basic prediction is that AI-enabled biology and medicine will allow us to compress the progress that human biologists would have achieved over the next 50-100 years into 5-10 years."
- **影响**: 这篇文章在 AI 社区引发广泛讨论，被认为是对 AI 积极影响最全面的愿景之一
- **来源**: https://www.darioamodei.com/essay/machines-of-loving-grace

#### 2. 关于 AI 安全
- **时间**: 2025年11月
- **场合**: 60 Minutes 采访
- **核心观点**: "I'm deeply uncomfortable" with the pace of AI development without adequate safety measures
- **背景**: 他因与 OpenAI 在 AI 安全问题上的分歧而离开，创立了 Anthropic
- **影响**: 成为 AI 安全领域的重要倡导者

#### 3. AGI 时间线预测
- **时间**: 2024年
- **场合**: Machines of Loving Grace 文章
- **核心观点**: "Powerful AI systems will emerge in late 2026 or early 2027"
- **影响**: 这是业内较为激进的 AGI 时间线预测之一

#### 4. The Urgency of Interpretability
- **时间**: 发表于个人网站
- **核心观点**: 可解释性（interpretability）是确保 AI 安全的关键，需要在 AI 能力竞赛中取胜
- **来源**: https://www.darioamodei.com/post/the-urgency-of-interpretability

---

## 三、Meta 领军人物

### Yann LeCun (Meta 首席 AI 科学家，图灵奖得主)

#### 1. 关于自回归 LLM 的局限性
- **时间**: 2023年及之后多次重申
- **场合**: 学术演讲、LinkedIn、Twitter
- **核心观点**: "Auto-Regressive LLMs are doomed"
- **论证**:
  - 自回归 LLM 的问题在于任何错误都会使其偏离正确路径
  - 生成满意答案的 token 序列的概率随着序列长度呈指数级下降
  - 自回归模型无法进行真正的规划和推理，只是"反应式"的
  - 它们会"编造内容"或"近似检索内容"
- **影响**: 这一观点在 AI 社区引发激烈争论，许多研究者撰文反驳
- **来源**: LinkedIn 帖子、学术演讲、Reddit 讨论

#### 2. 关于世界模型 (World Models)
- **时间**: 2024-2025年持续倡导
- **场合**: 学术会议、社交媒体、采访
- **核心观点**:
  - 世界模型是实现人类水平 AI 的关键，比单纯的语言处理更重要
  - 提出 JEPA (Joint-Embedding Predictive Architecture) 架构
  - 强调"decoder-free, latent-space world models"的重要性
  - 世界模型应该在潜在空间中进行预测，而不是在像素空间
- **关键引言**: "If you are interested in human-level AI, don't work on LLMs"
- **影响**: Meta AI 发布了 I-JEPA 模型作为这一理念的首次实现
- **来源**: 
  - LinkedIn: https://www.linkedin.com/posts/yann-lecun_pan-a-world-model-for-general-interactable-activity-7395466551664988160-Xacm
  - YouTube 演讲: "Self-Supervised Learning, JEPA, World Models"

#### 3. 关于 AGI 时间线
- **时间**: 2025年
- **场合**: 多次公开采访
- **核心观点**:
  - 对 AGI 即将到来持怀疑态度
  - 认为"AGI"这个术语本身没有意义
  - 人类智能本身并不是"通用"的
  - 达到人类水平 AI "需要数年时间，而不是明年"
- **关键引言**: "I said that reaching Human-Level AI 'will take several years, not next year'"
- **影响**: 与 Sam Altman 和 Dario Amodei 的乐观预测形成鲜明对比

#### 4. I-JEPA 模型发布
- **时间**: 2023年6月
- **场合**: Meta AI 官方博客
- **核心观点**: "The first AI model based on Yann LeCun's vision for more human-like artificial intelligence"
- **技术特点**: 
  - 学习世界的内部模型
  - 比传统方法学习速度更快
  - 更适合规划和推理
- **来源**: https://ai.meta.com/blog/yann-lecun-ai-model-i-jepa/

---

## 四、Nvidia 领军人物

### Jensen Huang (Nvidia CEO)

#### 1. 关于加速计算的未来
- **时间**: 2024年6月
- **场合**: Computex 2024 主题演讲
- **核心观点**: "The future of computing is accelerated. With our innovations in AI and accelerated computing, we're pushing the boundaries of what's possible."
- **关键理念**: "Accelerate Everything"
- **影响**: 推动了整个行业向加速计算转型
- **来源**: https://blogs.nvidia.com/blog/computex-2024-jensen-huang/

#### 2. 关于 AI 对就业的影响
- **时间**: 2025年11月
- **场合**: 公开采访
- **核心观点**: 
  - AI 不会让人们失业，而是会让每个人都"更忙碌"
  - "Everybody's job will be different" 因为 AI
  - AI 将创造比摧毁更多的工作岗位
  - 根据世界经济论坛：AI 预计将取代9200万个工作岗位，但也将创造1.7亿个新角色
- **关键引言**: "AI will actually make everyone a lot busier"
- **影响**: 对 AI 就业影响的乐观视角
- **来源**: Fortune、Times of India 报道

#### 3. 关于推理模型
- **时间**: 2025年3月
- **场合**: GTC25 主题演讲、DeepSeek 评论
- **核心观点**:
  - DeepSeek R1 是"fantastic"，因为它是"第一个开源推理模型"
  - 推理模型需要100倍的计算资源用于推理
  - 推理 AI 和 Agentic AI 将导致推理工作负载激增
- **技术发布**: Nvidia 推出 Llama Nemotron 开放推理模型家族
- **来源**: CNBC 采访、Nvidia 新闻稿

#### 4. 关于智能的未来
- **时间**: 2025年10月
- **场合**: 演讲和采访
- **核心观点**: "Billion-Fold Future of Intelligence"
  - 智能是复合的
  - AI 不会取代人类创造力，而是将其倍增
  - 将推动工作岗位、创新和经济的爆炸性增长
- **来源**: WisdomTree 博客

---

## 五、Google DeepMind 领军人物

### Demis Hassabis (Google DeepMind CEO，诺贝尔化学奖得主)

#### 1. 关于 AGI 时间线
- **时间**: 2025年11月
- **场合**: 多次采访
- **核心观点**: 
  - AGI 仍需5-10年时间
  - 需要"1或2次"重大突破
  - 这是业内相对保守的预测
- **关键引言**: "AGI is still 5-10 years away"
- **影响**: 与 OpenAI 和 Anthropic 的更激进时间线形成对比
- **来源**: Times of India、CNBC 报道

#### 2. AlphaFold 的影响
- **时间**: 2024年12月（诺贝尔奖演讲）
- **场合**: 诺贝尔奖演讲
- **主题**: "Accelerating scientific discovery with AI"
- **成就**:
  - AlphaFold 五年来彻底改变了科学
  - 预测了超过2亿个蛋白质结构
  - 被全球数百万研究人员使用
- **关键引言**: "AlphaFold is five years old — these charts show how it revolutionized science"
- **影响**: 2024年与 John Jumper 共同获得诺贝尔化学奖
- **来源**: 
  - 诺贝尔奖演讲 PDF
  - Nature 文章
  - DeepMind 博客: https://deepmind.google/blog/alphafold-five-years-of-impact/

#### 3. 关于 AI 的未来影响
- **时间**: 2025年8月
- **场合**: The Guardian 采访
- **核心观点**: AI 将带来"比工业革命大10倍、快10倍"的变革
  - 将开启"令人难以置信的生产力"时代
  - 实现"激进的丰裕"（radical abundance）
- **关键引言**: "It'll be 10 times bigger than the industrial revolution and 10 times faster"
- **来源**: The Guardian

#### 4. Gemini 3 发布
- **时间**: 2025年11月18日
- **场合**: Google 官方博客
- **核心观点**:
  - Gemini 3 是"最智能的模型"
  - 快速掌握上下文和意图，减少提示需求
  - "The real secret behind Gemini 3.0 performance"
- **影响**: 标志着 Google 在 AI 竞赛中的重要里程碑
- **来源**: Google 博客

#### 5. 关于当前 AI 的局限性
- **时间**: 2025年
- **场合**: 公开讨论
- **核心观点**: 
  - 称当前聊天机器人为"PhD 智能"是无稽之谈
  - "They can dazzle at a PhD level one moment and fail high school math the next"
  - 强调当前模型的不一致性
- **影响**: 对 AI 能力的现实评估
- **来源**: Reddit 讨论

---

## 六、其他重要观点汇总

### 关于上下文工程的共识
多位领军人物都强调了上下文管理的重要性：
- **Andrej Karpathy**: 将其定义为"精巧的艺术与科学"
- **Dario Amodei**: 在 Constitutional AI 中强调上下文的作用
- **行业趋势**: 从简单的 prompt engineering 转向复杂的 context engineering

### 关于 Scaling Laws 的分歧
- **Ilya Sutskever**: Scaling 时代结束，进入研究时代
- **Sam Altman**: 继续投资大规模计算基础设施
- **Yann LeCun**: 认为 scaling 不是通往 AGI 的正确路径
- **Demis Hassabis**: 需要新的突破，而不仅仅是 scaling

### 关于世界模型的重要性
- **Yann LeCun**: 最强烈的倡导者，认为这是 AGI 的关键
- **Andrej Karpathy**: 在讨论动物智能时提到"world models"作为探索-开发调优的一部分
- **行业趋势**: 从纯语言模型转向多模态世界模型

### 关于 AGI 时间线的预测
- **最激进**: Dario Amodei (2026-2027)
- **中等**: Sam Altman (2020年代末)
- **保守**: Demis Hassabis (5-10年), Yann LeCun (数年，不是明年)
- **最谨慎**: Andrej Karpathy (agents 需要十年)

---

## 搜集方法说明
本文档通过以下方式搜集资料：
1. 搜索引擎查找相关发言
2. 访问原始来源（Twitter、博客、播客）
3. 交叉验证多个来源
4. 记录影响力指标（浏览量、点赞、转发等）
5. 提供中英文对照

## 持续更新
本文档将持续更新，添加更多领军人物的发言和最新观点。

---

**文档版本**: v1.0  
**最后更新**: 2025年11月29日  
**搜集者**: AI 研究助手


---

## 七、李飞飞 (Fei-Fei Li)

### 1. 关于空间智能 (Spatial Intelligence)

#### 1.1 博客文章 - “From Words to Worlds: Spatial Intelligence is AI’s Next Frontier” (2025年11月)
**来源**: https://drfeifei.substack.com/p/from-words-to-worlds-spatial-intelligence

**核心观点摘要**:

**空间智能是 AI 的下一个前沿**:
> "Today, leading AI technology such as large language models (LLMs) have begun to transform how we access and work with abstract knowledge. Yet they remain wordsmiths in the dark; eloquent but inexperienced, knowledgeable but ungrounded. **Spatial intelligence will transform how we create and interact with real and virtual worlds—revolutionizing storytelling, creativity, robotics, scientific discovery, and beyond. This is AI’s next frontier.**"

**空间智能是认知的基础**:
> "**Spatial Intelligence is the scaffolding upon which our cognition is built.** It’s at work when we passively observe or actively seek to create. It drives our reasoning and planning, even on the most abstract topics. And it’s essential to the way we interact—verbally or physically, with our peers or with the environment itself."

**当前 AI 的局限性**:
> "Unfortunately, today’s AI doesn’t think like this yet... State-of-the-art MLLM models rarely perform better than chance on estimating distance, orientation, and size—or “mentally” rotating objects by regenerating them from new angles. They can’t navigate mazes, recognize shortcuts, or predict basic physics."

**通往空间智能的路径：世界模型**:
> "Building spatially intelligent AI requires something even more ambitious than LLMs: **world models**, a new type of generative models whose capabilities of understanding, reasoning, generation and interaction with the semantically, physically, geometrically and dynamically complex worlds - virtual or real - are far beyond the reach of today’s LLMs."

**世界模型的三个核心能力**:
> 1.  **Generative**: World models can generate worlds with perceptual, geometrical, and physical consistency.
> 2.  **Multimodal**: World models are multimodal by design.
> 3.  **Interactive**: World models can output the next states based on input actions.

**发布时间**: 2025年11月10日

**影响与关注**:
- 该文章在 AI 社区和科技媒体中被广泛传播和讨论，被认为是将“空间智能”概念系统化推向主流视野的关键文献。
- 标志着继 ImageNet 之后，李飞飞再次为 AI 领域设定了新的研究议程。
- 她联合创立的 World Labs 公司也随之发布了其首个商业产品 Marble，旨在将空间智能付诸实践。
