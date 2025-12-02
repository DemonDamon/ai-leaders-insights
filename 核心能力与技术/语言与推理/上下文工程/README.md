# 上下文工程 (Context Engineering)

📍 位置：[核心能力与技术](../../README.md) > [语言与推理](../README.md) > 上下文工程

---

## 概述

**上下文工程**是在有限的上下文窗口内进行信息调度和记忆管理的系统化工程实践。正如 Andrej Karpathy 所描述的，这是"一门将恰到好处的信息填入上下文窗口，以进行下一步操作的微妙艺术与科学"。它是区分"玩具 demo"和"生产系统"的关键分水岭，涉及模型层面的窗口管理、记忆系统设计、多 Agent 协作、工具链管理等多个维度。

### 核心理念

> 上下文工程的成功不是靠"更好的模型"，而是靠**更好的架构设计和工程纪律**。

### 四大核心策略

1. **写入 (Write)**: 如何将信息写入上下文
2. **选择 (Select)**: 如何选择最相关的信息
3. **压缩 (Compress)**: 如何压缩冗余信息
4. **隔离 (Isolate)**: 如何隔离不同来源的上下文

---

## 📚 资料列表

本目录收集了 **18 份**相关资料，涵盖综述、记忆系统、知识图谱、成本优化、工具管理、深度调研报告和工程落地指南。

### 综述与基础

1. [A Survey of Context Engineering for Large Language Models](./01_A-Survey-of-Context-Engineering-for-Large-Language-Models.md)
   - 类型：学术论文 | 来源：arXiv
   - 简介：上下文工程的系统性综述

2. [Effective context engineering for AI agents](./02_Effective-context-engineering-for-AI-agents.md)
   - 类型：技术文章 | 来源：Anthropic
   - 简介：AI Agent 的上下文工程最佳实践

3. [Context Engineering: Enhancing Large Language Model Performance](./03_Context-Engineering-Enhancing-Large-Language-Model-Performance-Through-Comprehensive-Contextual-Mana.md)
   - 类型：学术论文 | 来源：arXiv
   - 简介：通过全面的上下文管理提升 LLM 性能

4. [Best practices for prompt engineering with the OpenAI API](./04_Best-practices-for-prompt-engineering-with-the-OpenAI-API.md)
   - 类型：官方文档 | 来源：OpenAI
   - 简介：OpenAI API 的提示工程最佳实践

### 记忆系统 (Memory Systems)

5. [MemGPT: Towards LLMs as Operating Systems (Paper)](./05_MemGPT-Paper.md)
   - 类型：学术论文 | 来源：arXiv (2310.08560)
   - 简介：将 LLM 视为操作系统，实现虚拟上下文管理
   - 核心概念：虚拟上下文管理、分层记忆、页换入换出

6. [MemGPT Documentation](./06_MemGPT-Documentation.md)
   - 类型：官方文档 | 来源：Letta (原 MemGPT)
   - 简介：MemGPT 的架构和使用文档

7. [What is MemGPT? Making Large Language Models Better](./07_MemGPT-Introduction.md)
   - 类型：技术博客 | 来源：Medium
   - 简介：MemGPT 的通俗介绍和实践案例

### 知识图谱增强检索 (GraphRAG)

8. [GraphRAG Official Documentation](./08_GraphRAG-Official-Docs.md)
   - 类型：官方文档 | 来源：Microsoft
   - 简介：GraphRAG 的官方文档和教程

9. [A Graph RAG Approach to Query-Focused Summarization (Paper)](./09_GraphRAG-Paper.md)
   - 类型：学术论文 | 来源：arXiv (2404.16130)
   - 简介：基于图的 RAG 方法用于查询聚焦摘要
   - 核心概念：社区层次结构、知识图谱提取

10. [GraphRAG Explained: Enhancing RAG with Knowledge Graphs](./10_GraphRAG-Explained.md)
    - 类型：技术博客 | 来源：Zilliz Medium
    - 简介：GraphRAG 与传统 RAG 的对比和优势

### 成本优化 (Cost Optimization)

11. [Anthropic Prompt Caching Blog](./11_Anthropic-Prompt-Caching-Blog.md)
    - 类型：官方博客 | 来源：Anthropic
    - 简介：Prompt Caching 技术介绍，可降低成本 90%
    - 核心概念：上下文缓存、TTL 管理

### 工具管理 (Tool Management)

12. [Model Context Protocol (MCP) Announcement](./12_MCP-Announcement.md)
    - 类型：官方公告 | 来源：Anthropic
    - 简介：MCP 协议的发布公告和核心理念

13. [MCP Official Site](./13_MCP-Official-Site.md)
    - 类型：官方网站 | 来源：modelcontextprotocol.io
    - 简介：MCP 的完整文档和规范

14. [Code Execution with MCP: Building More Efficient Agents](./14_Code-Execution-with-MCP.md)
    - 类型：工程博客 | 来源：Anthropic Engineering
    - 简介：使用 MCP 实现代码执行的高效 Agent

15. [Tool RAG: The Next Breakthrough in Scalable AI Agents](./15_Tool-RAG-Breakthrough.md)
    - 类型：技术文章 | 来源：Red Hat
    - 简介：Tool RAG 和 RAG-MCP 的突破性进展

### ⭐ 工程落地指南

16. [**上下文工程落地指南 - ima 问答**](./16_上下文工程落地指南-ima问答.md)

### 🔬 深度调研报告

17. [**RAG-MCP 深度调研报告**](./17_RAG-MCP深度调研报告.md)
    - 类型：深度调研 | 作者：Manus AI
    - 简介：**RAG-MCP 技术全面解析：原理、流程、场景与案例**
    - 核心内容：
      - ✅ 大规模工具选择的核心瓶颈分析
      - ✅ RAG-MCP 四步技术流程详解
      - ✅ 性能对比：准确率提升 3.17 倍，Token 减少 >50%
      - ✅ 企业级应用场景与实际案例
      - ✅ 与 Provence 的协同工作机制

18. [**Provence 深度调研报告**](./18_Provence深度调研报告.md)
    - 类型：深度调研 | 作者：Manus AI
    - 简介：**Provence 技术全面解析：原理、流程、场景与案例**
    - 核心内容：
      - ✅ RAG 中的上下文冗余问题分析
      - ✅ 三大关键技术：序列标注、统一剪枝重排序、多样化训练
      - ✅ 与其他方法的全面对比（唯一满足所有实用性要求）
      - ✅ 法律、医疗等领域的实际应用案例
      - ✅ 与 RAG-MCP 的协同工作流水线
    - 类型：实践指南 | 来源：用户提供
    - 简介：**从生产环境视角系统梳理上下文工程的核心挑战和解决方案**
    - 核心内容：
      - ✅ 10 大核心挑战（P0/P1/P2 优先级）
      - ✅ 三阶段落地路线图（起步期/成长期/成熟期）
      - ✅ 第一个月落地 Checklist
      - ✅ 工程师最容易踩的 5 个坑
      - ✅ 参考架构和系统对比

---

## 🔑 核心概念

### 主要挑战

| 优先级 | 挑战领域 | 典型问题 |
|--------|---------|---------|
| **P0** | 上下文窗口 | 有限窗口 + 成本爆炸 |
| **P0** | 记忆系统 | 长期记忆维护困难 |
| **P0** | 上下文管理 | 污染、干扰、混乱、冲突 |
| **P0** | 成本控制 | Token 消耗难以预测 |
| **P0** | 安全隔离 | 多租户数据泄露风险 |
| **P1** | 工具管理 | 工具爆炸与提示膨胀 |
| **P1** | 多 Agent | 协调复杂度指数增长 |
| **P1** | 评估调试 | 缺乏有效评估手段 |

### 技术方案

| 技术 | 用途 | 适用场景 |
|------|------|---------|
| **滑动窗口** | 基础上下文管理 | 短对话（<10 轮） |
| **分层记忆** | 长期记忆维护 | 个人助理、项目管理 |
| **混合检索** | 提升召回率 | 企业知识库 |
| **重排序** | 提升精确率 | 复杂查询场景 |
| **Prompt Cache** | 成本优化 | 重复上下文场景 |
| **RAG-MCP** | 动态工具选择 | 工具数量 >10 |
| **GraphRAG** | 结构化知识检索 | 多跳推理、关系查询 |
| **MemGPT** | 虚拟上下文管理 | 需要长期记忆的 Agent |

### 参考框架

- **MemGPT / Letta**: LLM as OS，虚拟上下文管理
- **Claude Code**: 文件系统作为上下文，子 Agent 隔离
- **RAG-MCP**: 动态工具选择，避免提示膨胀
- **GraphRAG**: 图结构增强检索
- **AgentScope / Swarm / AutoGen**: 多 Agent 编排框架
- **LangSmith / LangFuse**: 可观测性和 Trace 系统

---

## 🎯 快速开始

### 第一周 Checklist

- [ ] 选定主力 LLM（GPT-4/Claude/国产模型）
- [ ] 搭建调用链和基础日志
- [ ] 实现滑动窗口对话管理（最近 5 轮）
- [ ] 建立 Token 监控

### 第二周 Checklist

- [ ] 文档切分和向量化
- [ ] 选择向量数据库（Pinecone/Milvus/Faiss）
- [ ] 实现 Top-k 检索
- [ ] 测试 10 个典型问题的召回效果

### 第三周 Checklist

- [ ] 接入 2-3 个核心工具（如搜索、数据库查询）
- [ ] 实现工具调用的错误处理
- [ ] 限制重试次数和 Token 上限
- [ ] 测试工具调用的边界 case

### 第四周 Checklist

- [ ] 建立评估集（20-50 个 case）
- [ ] 跑一轮端到端测试
- [ ] 分析成本分布（哪个环节花费最多）
- [ ] 根据数据调整策略（检索数量、摘要频率等）

---

## 🖼️ 相关图片

本章节的相关图片资源存放在 `images/` 目录下。

---

## 📖 延伸阅读

- [推理模型](../推理模型/README.md) - 与上下文工程密切相关的推理能力
- [思维链技术](../思维链技术/README.md) - 上下文中的推理链构建
- [AI Agent](../../行动与规划/AI-Agent/README.md) - Agent 架构中的上下文管理

---

[⬆️ 返回上级](../README.md) | [🏠 返回首页](../../../README.md)
