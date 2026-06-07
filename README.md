<div align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Microsoft+YaHei&weight=600&size=28&duration=3500&pause=500&color=FFFFFF&center=true&vCenter=true&width=700&lines=%F0%9F%93%96+Learning+Record;%E5%90%8E%E7%AB%AF%E6%9F%A5%E7%BC%BA%E8%A1%A5%E6%BC%8F+%C2%B7+Agent+%E4%BB%8E%E9%9B%B6%E6%9E%84%E5%BB%BA;%F0%9F%94%A5+Commit+to+Mastery" alt="Typing SVG" />
  <br>
  <img src="https://img.shields.io/badge/STATUS-LEARNING-00AAFF?style=for-the-badge&logo=apple&logoColor=white" />
  <img src="https://img.shields.io/badge/FOCUS-Backend%20%26%20Agent-999999?style=for-the-badge&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/TRACK-Progressive-30B0C0?style=for-the-badge&logo=target&logoColor=white" />
</div>

<div align="center">
  <br>
  <img src="https://img.shields.io/github/license/1480735780/Learning" />
  <img src="https://img.shields.io/github/last-commit/1480735780/Learning" />
  <img src="https://img.shields.io/github/repo-size/1480735780/Learning" />
  <img src="https://img.shields.io/badge/PRs-welcome-30B0C0?logo=github" />
</div>

---
## 🌟 项目简介

`Learning` 是一个个人后端与 AI Agent 技术学习仓库。

<div align="center">
  <table>
    <tr>
      <td width="50%" valign="top">
        <h3>🎯 后端能力查缺补漏</h3>
        整理 C++ 核心知识点，从虚函数表到内存模型，从网络编程到 RPC。
      </td>
      <td width="50%" valign="top">
        <h3>🤖 Agent Learning Hub</h3>
        基于 <a href="https://github.com/datawhalechina/Agent-Learning-Hub">Datawhale Agent-Learning-Hub</a> 分阶段学习路径，从零构建智能体。
      </td>
    </tr>
  </table>
</div>

---

## 📦 后端能力查缺补漏

> 以下为 C++ 后端知识点梳理，✅ 已掌握 / ⬜ 待加强 / 🟡 进行中。

### 一、C++ 基础

| 知识点 | 状态 |
|--------|------|
| 虚函数底层实现（vtable / vptr） | ✅ |
| 纯虚函数与抽象类 | ✅ |
| 虚析构函数的必要性与实现 | ✅ |
| override 与 final 关键字 | ✅ |

### 二、C++ 进阶

<details>
<summary><b>🔧 异常处理</b> — try/throw/catch · noexcept · RAII</summary>

| 知识点 | 状态 |
|--------|------|
| try / throw / catch 机制 | ⬜ |
| 异常规格（noexcept）与 move 语义 | ⬜ |
| 异常安全（RAII 保证） | ⬜ |
| 标准异常体系（std::exception） | ⬜ |
| 构造/析构函数中抛异常的注意事项 | ⬜ |

</details>

<details>
<summary><b>📐 泛型编程</b> — 函数模板/类模板 · 特化 · SFINAE · concepts</summary>

| 知识点 | 状态 |
|--------|------|
| 函数模板 vs 类模板 | ⬜ |
| 模板特化（全特化 / 偏特化） | ⬜ |
| SFINAE 与 concepts（C++20） | ⬜ |
| 模板元编程（TMP）基础 | ⬜ |

</details>

<details>
<summary><b>🧠 内存对象模型</b> — 内存对齐 · EBO · placement new</summary>

| 知识点 | 状态 |
|--------|------|
| C++ 对象布局（内存对齐、字节序） | ⬜ |
| 空类的大小（EBO） | ⬜ |
| 拷贝/移动构造语义 | ⬜ |
| placement new 与内存池 | ⬜ |

</details>

<details>
<summary><b>🏷️ RTTI</b> — typeid · dynamic_cast · type_traits</summary>

| 知识点 | 状态 |
|--------|------|
| typeid 与 type_info | ⬜ |
| dynamic_cast 原理与使用场景 | ⬜ |
| type_traits 与编译期类型判断 | ⬜ |

</details>

<details>
<summary><b>🔄 多态实现原理</b> — 静态多态 · 动态多态 · vtable</summary>

| 知识点 | 状态 |
|--------|------|
| 静态多态（重载、模板）vs 动态多态（虚函数） | ⬜ |
| 虚表（vtable）结构详解 | ⬜ |
| 菱形继承与虚继承的内存布局 | ⬜ |
| vptr 的构造与销毁时机 | ⬜ |

</details>

<details>
<summary><b>⚡ 四大类型转换</b> — static_cast · const_cast · dynamic_cast · reinterpret_cast</summary>

| 类型转换 | 作用 | 状态 |
|----------|------|------|
| static_cast | 编译期静态转换，父子类指针/引用转换 | ⬜ |
| const_cast | 移除或添加 const | ⬜ |
| dynamic_cast | 运行时安全转换，多态类型专用 | ⬜ |
| reinterpret_cast | 重新解释二进制位，风险极高 | ⬜ |

</details>

<details>
<summary><b>📱 C++11 核心特性</b> — 右值引用 · auto · unordered_map · thread · Lambda · 智能指针</summary>

| 知识点 | 状态 | 知识点 | 状态 |
|--------|------|--------|------|
| 左值 vs 右值 vs 将亡值 | ⬜ | 移动构造/赋值 | ⬜ |
| std::move / std::forward | ⬜ | auto / decltype | ⬜ |
| unordered_map 哈希原理 | ⬜ | 线程库（mutex/condition_variable） | ⬜ |
| atomic / async / future | ⬜ | Lambda 捕获模式 | ⬜ |
| 泛型 lambda（C++14） | ⬜ | 范围 for 循环 | ⬜ |
| unique_ptr / shared_ptr / weak_ptr | ⬜ | make_unique / make_shared | ⬜ |

</details>

### 三、调试技术

| 知识点 | 状态 |
|--------|------|
| GDB 基本命令（break/run/next/step/print/info） | ✅ |
| 条件断点与监视点（watch） | ✅ |
| 多线程调试（info threads / thread apply） | ✅ |
| core dump 分析 | ⬜ |
| GDB 脚本自动化调试 | ⬜ |

> **推荐学习资源**：经典 GDB 教程（B 站搜索“小神仙讲 GDB”）

### 四、网络编程

| 模型 | 核心特点 | 状态 |
|------|----------|------|
| select | fd_set 限制（默认 1024），线性扫描 O(n) | ⬜ |
| poll | 克服 fd 数量限制，线性扫描 O(n) | ⬜ |
| epoll | 事件驱动 O(1)，LT/ET 模式 | ⬜ |
| Reactor 模型 | — | ⬜ |
| one loop per thread 模式 | — | ⬜ |

### 五、RPC 与序列化技术

| 技术 | 知识点 | 状态 |
|------|--------|------|
| **gRPC + Protobuf** | .proto 编写、四种通信模式 | ⬜ |
| **Thrift** | IDL、多语言支持、传输/协议/服务端模型 | ⬜ |
| **RapidJSON** | SAX vs DOM 解析 | ⬜ |

> **推荐学习资源**：gRPC / Protobuf / Thrift 相关经典教程

### 六、计算机网络进阶

| 模块 | 知识点 | 状态 |
|------|--------|------|
| **TCP** | ISN、SYN Cookie、半连接/全连接队列、拥塞控制、TIME_WAIT | ⬜ |
| **HTTP** | HTTP 1.1/2.0/3.0 演进（多路复用、HPACK、QUIC） | ⬜ |
| **HTTPS** | TLS 1.2/1.3 握手、证书链验证 | ⬜ |
| **DNS 安全** | httpDNS、DNSSEC、DNS 污染与劫持 | ⬜ |

### 七、设计模式

<details>
<summary><b>🏗️ 创建型</b> — 单例 · 工厂 · 建造者 · 原型</summary>

| 知识点 | 状态 |
|--------|------|
| 单例（双检锁 / Meyers Singleton） | ⬜ |
| 工厂方法与抽象工厂 | ⬜ |
| 建造者模式（Builder） | ⬜ |
| 原型模式（Prototype / clone） | ⬜ |

</details>

<details>
<summary><b>🔗 结构型</b> — 适配器 · 装饰器 · 代理 · 组合</summary>

| 知识点 | 状态 |
|--------|------|
| 适配器模式（Adapter） | ⬜ |
| 装饰器模式（Decorator） | ⬜ |
| 代理模式（Proxy）与智能指针 | ⬜ |
| 组合模式（Composite） | ⬜ |

</details>

<details>
<summary><b>⚡ 行为型</b> — 观察者 · 策略 · 命令 · 模板方法 · 迭代器</summary>

| 知识点 | 状态 |
|--------|------|
| 观察者模式（Observer） | ⬜ |
| 策略模式（Strategy） | ⬜ |
| 命令模式（Command） | ⬜ |
| 模板方法（Template Method） | ⬜ |
| 迭代器模式（Iterator） | ⬜ |

</details>

### 八、第三方组件

| 组件 | 核心知识点 | 状态 |
|------|------------|------|
| **MySQL** | InnoDB、MVCC、索引原理、EXPLAIN、主从复制 | ⬜ |
| **PostgreSQL** | — | ⬜ |
| **Nginx** | 事件驱动、反向代理、负载均衡、限流 | ⬜ |
| **Redis** | 数据结构、RDB/AOF、哨兵、Cluster、缓存三兄弟 | ⬜ |
| **Docker** | 镜像、容器、Dockerfile、Compose、网络模式 | ⬜ |
| **Elasticsearch** | 倒排索引、分片/副本、DSL、聚合分析 | ⬜ |
| **消息队列（RabbitMQ/Kafka）** | Exchange 类型、分区/消费者组、持久化 | ⬜ |

> **推荐学习资源**：各组件官方文档、经典书籍及社区教程。

---

## 🤖 Agent Learning Hub

> 学习路径基于 [Datawhale Agent-Learning-Hub](https://github.com/datawhalechina/Agent-Learning-Hub) 整理。每个 Stage 完成后，产出对应的可运行项目或笔记。

**📌 学习理念**：Agent 领域的核心不是套框架，而是理解 **harness**——工具协议、权限、状态、评测等底层工程能力。

### 🗺️ Stage 0 — 理解 Agent 的本质

**目标**：区分 chatbot / workflow / agent / multi-agent，理解何时该用 agent。

| 任务 | 状态 |
|------|------|
| 读完《Anthropic: Building effective agents》 | ⬜ |
| 读完《OpenAI: A practical guide to building agents》 | ⬜ |
| 写一页笔记，回答「我的场景为什么需要 agent？」 | ⬜ |

📎 **产出**：一篇短笔记 📝

---

### 🛠️ Stage 1 — 构建最小 Agent Loop

**目标**：实现一个 50~150 行的最小 agent，能选择工具、执行工具、返回答案。

| 任务 | 状态 |
|------|------|
| 会用 LLM API 完成普通对话 | ⬜ |
| 会让模型输出结构化 JSON | ⬜ |
| 会定义一个工具函数（search / calculator） | ⬜ |
| 会解析 tool call / function call | ⬜ |
| 会执行工具并将结果喂回模型 | ⬜ |
| 会添加最大步数、超时和错误处理 | ⬜ |

📎 **产出**：一个可运行的最小 Agent ⚙️

---

### 📚 Stage 2 — 工具调用、RAG 与记忆

**目标**：构建一个能搜索、检索、引用资料的资料研究助手。

| 任务 | 状态 |
|------|------|
| 做 RAG：chunk → embed → retrieve → answer + citations | ⬜ |
| 接入搜索/数据库/浏览器/代码执行等工具 | ⬜ |
| 区分短期上下文、会话记忆、长期记忆 | ⬜ |
| 处理工具失败、空结果、幻觉引用 | ⬜ |

📎 **产出**：资料研究助手（输入主题 → 自动搜索/筛选/总结 → 输出引用链接）🔍

---

### 🚀 Stage 3 — 深入学习现代 Agent Harness

**目标**：选择一个现代 agent 系统深入理解，重点不是框架 API，而是工具组织、上下文、权限、状态、日志和反馈。

| 系统 | 特点 | 状态 |
|------|------|------|
| Claude Code Docs | 真实 coding agent 的 CLI、工具、权限、hooks、subagents、MCP | ⬜ |
| OpenClaw | 本地优先个人 agent，skills、消息入口、系统工具和安全边界 | ⬜ |
| hello-agents | 中文智能体教程，从零构建 Agent | ⬜ |
| LangGraph | 状态图和可控 agent 编排，工程基础 | ⬜ |

📎 **产出**：深入学习笔记 + 一个 Demo 实现 📘

---

### 🔧 Stage 4 — Skills / MCP / A2A / ACP

**目标**：理解现代 agent 生态中的连接协议和能力复用。

| 技术 | 作用 | 状态 |
|------|------|------|
| Skills | 能力复用 | ⬜ |
| MCP（Model Context Protocol） | 连接外部工具 | ⬜ |
| A2A | Agent 与 Agent 之间的连接协议 | ⬜ |

📎 **产出**：一个基于 MCP 或 Skills 的工具集成实践 🔌

---

### 🌐 Stage 5 — Browser Agent & Computer-Use Agent

**目标**：构建能操作网页的 browser agent，理解浏览器自动化与 API 调用的区别。

| 任务 | 状态 |
|------|------|
| 用 Playwright / browser-use 做网页观察和点击 | ⬜ |
| 给浏览器操作加安全限制（不登录敏感账号） | ⬜ |
| 处理页面变化、弹窗、加载失败 | ⬜ |

📎 **产出**：一个只操作公开网页的 browser agent 🌍

---

### 📊 Stage 6 — 评测、可观测性与安全

**目标**：为 agent 建立评测体系和 trace 能力，了解安全风险。

| 任务 | 状态 |
|------|------|
| 准备固定测试集，记录成功率和失败原因 | ⬜ |
| 会看 trace，定位失败环节（prompt/工具/检索/模型/状态） | ⬜ |
| 为危险工具加人工确认（发邮件/删文件/付款） | ⬜ |
| 了解 prompt injection、data exfiltration、tool abuse 等风险 | ⬜ |

📎 **产出**：一份 Agent Eval 表格（至少 20 个任务 + 失败分类）📋

---

### 🎯 Stage 7 — 上线一个真实的 Agent

**目标**：交付一个别人能 clone 下来跑的生产级 agent。

| 任务 | 状态 |
|------|------|
| 有明确用户、任务和成功标准 | ⬜ |
| 有日志、trace、错误重试、超时、成本上限 | ⬜ |
| 有权限边界和人工确认机制 | ⬜ |
| 有部署方式（CLI / Web app / Slack bot / GitHub Action） | ⬜ |
| 有完善的 README（运行方式/配置 key/扩展工具/限制） | ⬜ |

📎 **产出**：一个可运行的 Agent 生产项目 🚢

---

## 📁 项目阶梯

以下为可直接落地的项目实践清单，按难度递进：

| Level | 项目 | 说明 | 状态 |
|-------|------|------|------|
| 1 | Calculator Agent | 最小 tool call loop | ⬜ |
| 2 | Web Research Agent | 搜索、筛选、引用、总结 | ⬜ |
| 3 | PDF QA Agent | RAG、chunk、retrieval | ⬜ |
| 4 | Coding Review Agent | 读取 diff、风险排序、测试建议 | ⬜ |
| 5 | Browser Agent | 页面观察、点击、失败恢复 | ⬜ |
| 6 | Claude Code-style Nano Agent | shell、文件编辑、权限 | ⬜ |
| 7 | OpenClaw-style Gateway | channel、routing、session、memory | ⬜ |
| 8 | Reusable Skill Pack | SKILL.md、脚本、模板、触发条件 | ⬜ |
| 9 | Multi-Agent Writer | planner、writer、reviewer 协作 | ⬜ |
| 10 | Personal Agent | 记忆、skills、消息入口 | ⬜ |
| 11 | Production Harness | evals、trace、权限、CI | ⬜ |

---

## 📚 推荐资源

### 📖 官方指南（必读）
| 资源 | 说明 |
|------|------|
| [Anthropic: Building effective agents](https://www.anthropic.com/engineering/building-effective-agents) | Agent 设计入门必读 |
| [OpenAI: A practical guide to building agents](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/) | OpenAI 官方实践指南 |
| [Claude Code Docs](https://code.claude.com/docs/en/overview) | Coding Agent 产品文档入口 |

### 📄 经典论文
- [ReAct](https://arxiv.org/abs/2210.03629) — Reasoning + Acting 基础范式
- [Toolformer](https://arxiv.org/abs/2302.04761) — 模型学习何时调用工具
- [Generative Agents](https://arxiv.org/abs/2304.03442) — 记忆、反思、规划驱动的模拟 agent
- [Dive into Claude Code](https://arxiv.org/abs/2604.14228) — 从系统设计角度分析 coding agent 的 harness

---

## 🗺️ 学习路线建议

```mermaid
graph LR
    A[C++基础] --> B[C++进阶]
    B --> C[调试技术]
    C --> D[网络编程]
    D --> E[RPC/序列化]
    E --> F[计算机网络]
    F --> G[设计模式]
    G --> H[第三方组件]
    
    I[Stage 0-1: Agent入门] --> J[Stage 2: RAG与记忆]
    J --> K[Stage 3: Harness深入学习]
    K --> L[Stage 4-5: 工具协议与Browser Agent]
    L --> M[Stage 6-7: 评测与上线]
