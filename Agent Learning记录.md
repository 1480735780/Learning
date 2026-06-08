# Agent Learning记录

> 来源：datawhalechina/Agent Learning Hub \| 整理：思州（Datawhale）
> 
> 

# Stage 0：理解 Agent 是什么

* [x] 区分 chatbot、workflow、agent、multi\-agent

* [x] 理解 agent 的基本循环：observe → think → act → observe

* [ ] 明白什么时候不该用 agent：任务可预测、流程稳定、普通脚本能解决时，agent 反而增加不确定性

* [ ] 读完 [Anthropic: Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)

* [ ] 读完 [OpenAI: A practical guide to building agents](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/)

**产出：** 写一页短笔记，回答「我的场景为什么需要 agent，而不是普通 workflow？」

## 一、区分chatbot、workflow、agent、multi\-agent

### 1\.chatbot和workflow，agent和multi\-agent的概述



> 资料来源：
> 
> 1\.Chatbot：https://blog\.csdn\.net/zp357252539/article/details/147294987
> 
> 2\.Workflow:
> 
> \[1\]https://hub\.baai\.ac\.cn/view/45109
> 
> \[2\]https://www\.anthropic\.com/engineering/building\-effective\-agents?ref=blog\.langchain\.dev
> 
> 3\.multiagent：https://developer\.aliyun\.com/article/1707462
> 
> 

Workflow\(工作流\)就像是一条**流水线**，把复杂的任务拆分成多个简单的步骤，**每一步都有明确的目标和流程**。

通俗定义：工作流指的是一系列步骤或任务，通过预定义的顺序和规则，完成特定目标的一种方法。可以把它想象成你每天早晨的例行程序：起床、洗漱、吃早餐、出门上班。每个步骤都有固定的顺序，如果打乱了顺序，可能会影响整个流程的效率。在工作流的框架下，步骤和规则的关系可以概括为：

> 工作流 = 步骤1 \+ 步骤 2 \+ … \+ 步骤 3
> 
> 其中，每个步骤都是一个独立的任务，工作流决定了任务的执行顺序和条件、
> 
> 

当然，我个人更喜欢Anthropic在《building\-effective\-agents》中一文的解释。

Chatbot在我们当中体会最深的莫过于你日常最频繁使用的豆包，千问，deepseek等。你通过告诉它一个Query，它进行推理，告诉你答案。

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=YjRiYzNmNzIwMmU3MzQ0Mzk3MzdjMmZhNzhjNDE4ZjVfYjE5N2QxZmQ0NWIyMDY0YmY4NDhjYWNjNDdhMDAxMTFfSUQ6NzY0NzgyODMxMTc0NjAyMjM0Ml8xNzgwOTA4MTgwOjE3ODA5OTQ1ODBfVjM)

重点在于：

> Workflows 是通过预先写好的代码路径来协调 LLMs 和工具工作的系统。
> 
> 而 Agents 则是由 LLMs 自己动态地决定流程和工具使用，它们掌控着任务完成的方式。
> 
> 

Agent 是一个能够自主感知环境、规划决策、调用工具并执行任务的智能系统，其核心是从“被动响应”到“主动执行”的范式转变。

它通过ReAct模式：感知（接收指令/环境反馈）→ 规划（拆解任务、制定计划）→ 行动（调用工具执行）→ 观察（评估结果，循环直至目标达成）进行一个agent loop。

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=YzhjMTY5NjdhMTFlNjI2MGQzZWQwMDQ5MTQxZWM0NDRfNmMzNjRjZTJlYmI0ZjUyODUxYmY0NzZhYWE2OWNlYmVfSUQ6NzY0NzgzMjgxMzk5MTU5NTIxMV8xNzgwOTA4MTgwOjE3ODA5OTQ1ODBfVjM)

Multi‑Agent System（MAS，多智能体系统） 是由多个具备独立决策能力的自治智能体通过通信协议构成的分布式协作系统，旨在解决单一 Agent 难以应对的复杂长链路任务；

此外，正因为单一Agent 还易出现上下文偏移、逻辑纠缠、鲁棒性缺失 等问题。所以Multi‑Agent 的本质也是利用到分治思想 “分而治之，合而谋之” ——将复杂商业逻辑拆解为多个专业化角色，通过协议进行信息交互。

### 2\.四者的使用场景和区别

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=N2ExMDA2Y2EzMzBjZjZlZGExOGEwYmM1ZGNiNGE2NmRfY2ViYTllZDRhMDFlMGNiYjM0YzQxYTJlMGI4ZTc5MDZfSUQ6NzY0NzkxNDAyMjg2NzgxNTM1Ml8xNzgwOTA4MTgwOjE3ODA5OTQ1ODBfVjM)

## 二、理解 agent 的基本循环：observe → think → act → observe

Agent = LLM \+ tools\+memory

Agent 本质上是在大模型基础上增加了工具调用、记忆管理和循环执行能力。其核心遵循 Observe → Think → Act → Observe 的闭环。

首先感知用户输入或环境状态，然后由大模型进行推理和任务规划，判断是否需要调用外部工具。如果需要，则执行工具调用，并将工具返回结果作为新的 Observation 再次输入给大模型继续推理。这个过程会不断迭代，直到达到任务目标并输出最终结果。因此 Agent 不再是一次性的 Prompt→Answer，而是具备自主决策和多步执行能力的智能体。

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=YzNkNmI2MDM0YzFhN2FkYjZlMzhmY2UxOGRhMDI5NGJfNmI1NDNkYjBiM2RmNmYyZGVhYjVlOWM4YjhlZDYxYTBfSUQ6NzY0NzkyNDE4MTM2NzA4MjIyN18xNzgwOTA4MTgwOjE3ODA5OTQ1ODBfVjM)

## 三、明白什么时候不该用agent：任务可预测、流程稳定、普通脚本能解决时，agent 反而增加不确定性

对于什么时候不该用agent，什么时候该用agent，我们先按下不表。先分析为什么 LLM 会出错？主要有两个原因：一是模型本身能力还不够；二是传递给模型的上下文信息不对或者不完整。

根据我们的经验，第二种情况非常常见。那又是什么导致上下文信息传递出问题呢？

- System Message 不完整或写得太短

- 用户的输入太模糊

- 没有给 LLM 提供正确的工具

- 工具的描述写得不好

- 没有传入恰当的上下文信息

- 工具返回的响应格式不对

> 💡 要构建一套可靠的 Agentic 系统，真正的挑战在于如何确保 LLM 在每一步都能拿到最合适的上下文信息。这包含了两方面：一是精准控制到底把哪些具体内容喂给 LLM，二是执行正确的步骤来生成那些有用的内容。
> 
> 

Workflows 之所以有用，部分原因就在于它们能够将正确的上下文传递给给 LLMs ，可以精确地决定数据如何流动。所以当任务可预测、流程稳定、普通脚本能解决时，使用workflows也许效果比使用agent要好。这样你也就目标，什么时候该使用agent，什么时候该使用workflow。

```Python
import re
import time

# 模拟输入数据（格式高度固定）
raw_text = "客户姓名: 张三, 订单编号: 2026060899"

# ================= 1. 传统脚本方法（正则表达式） =================
def extract_by_script(text):
    # 稳定、可预测的规则
    name_match = re.search(r"客户姓名:\s*([^,]+)", text)
    order_match = re.search(r"订单编号:\s*(\d+)", text)
    
    if name_match and order_match:
        return {
            "name": name_match.group(1).strip(),
            "order_id": order_match.group(1).strip()
        }
    return None

# ================= 2. Agent / LLM 方法（模拟网络与推理延迟） =================
def extract_by_agent(text):
    # 模拟大模型思考、Token 生成以及网络 IO 延迟（通常在 0.5秒 - 3秒不等）
    # 在实际应用中，这里会是 client.chat.completions.create(...)
    time.sleep(1.2) 
    
    # 假设 Agent 正确解析了数据（但实际上面临不确定性，比如偶尔返回 Markdown）
    return {
        "name": "张三",
        "order_id": "2026060899"
    }

# ================= 性能测试与对比 =================
def run_comparison():
    print("--- 开始测试 ---")
    
    # 测试传统脚本
    start_time = time.perf_counter()
    script_result = extract_by_script(raw_text)
    end_time = time.perf_counter()
    script_duration = (end_time - start_time) * 1000 # 转换为毫秒
    
    print(f"[传统脚本] 结果: {script_result}")
    print(f"[传统脚本] 耗时: {script_duration:.4f} 毫秒")
    
    print("-" * 30)
    
    # 测试 Agent 方法
    start_time = time.perf_counter()
    agent_result = extract_by_agent(raw_text)
    end_time = time.perf_counter()
    agent_duration = (end_time - start_time) * 1000 # 转换为毫秒
    
    print(f"[Agent模型] 结果: {agent_result}")
    print(f"[Agent模型] 耗时: {agent_duration:.4f} 毫秒")
    
    print("-" * 30)
    
    # 计算倍数差距
    ratio = agent_duration / max(script_duration, 0.0001)
    print(f"结果分析：Agent 比传统脚本慢了约 {ratio:.1f} 倍！")

if __name__ == "__main__":
    run_comparison()
```

![Image](https://internal-api-drive-stream.feishu.cn/space/api/box/stream/download/authcode/?code=YTUwNjYxYjcwNWUxMDY4MDFjNzFmMjYwY2EyMGRjNWFfMGIwMDI4ZDE1MTRlMGM2NzcwNjY0YWE2MWJmMWM2Y2ZfSUQ6NzY0ODkzMzI2OTE0NDYxOTk5M18xNzgwOTA4MTgwOjE3ODA5OTQ1ODBfVjM)

## 四、[Anthropic: Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)读后感

1\.What are agents？



## 五、[OpenAI: A practical guide to building agents](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/)读后感

## 六、阶段0的产出总结

