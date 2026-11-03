# human.md

> **"Everyone writes `AGENTS.md` for AI. We wrote `HUMAN.md` for the human in the loop."**  
> 全网都在给 AI 写 `AGENTS.md` / `CLAUDE.md` / `GEMINI.md`，但人机回路（Human-in-the-Loop）里最大的瓶颈，往往是没有一份给人类自己的 `HUMAN.md`。

一套面向新一代原生推理模型（GPT-6 / Claude 5.5 / Gemini 4 / Grok 4.7 / DeepSeek-V4）与人类协作者的**双向认知与执行协议**。

---

## 为什么需要 `HUMAN.md`？（机器与人类的镜像非对称）

在人机协作闭环中，**模型的上下文窗口**与**人类的生物大脑**遵循完全相反的唤醒机制：

1. **给 AI 的协议（`agents/` & `chatbots/`）—— 去图腾化的高精度动作契约**
   - 模型每轮对话都会机械重读 System Prompt。若在提示词中堆砌抽象哲学口号，会引发原生推理模型的“词汇泄漏（掉书袋）”与自适应推理算力空转。
   - 因此，给模型的文档剥离了一切修辞图腾，仅保留模型无法自行推断的**工具时序（先检索后落笔）、自治与不可逆边界、反作弊验证与快慢算力分流**。
2. **给自己的协议（`human/`）—— 唤醒隐性知识的元概念与单主线类比**
   - 人类不会在每次敲回车前背诵操作手册。机械的条文看一遍就会忘；真正能在关键决策瞬间唤醒人类直觉的，只有两种载体：
     - **[`HUMAN.md`](./human/HUMAN.md)（主文档 · 跨学科高维概念版）**：通过 `X-Y Problem`、`确认偏误`、`钢铁侠论证`、`委托-代理问题`、`单向门/双向门`、`沉没成本谬误` 等真实存在的跨学科概念锚点，一键点亮大脑中已有的隐性知识库。
     - **[`HUMAN-simplified.md`](./human/HUMAN-simplified.md)（简化版 · “西瓜书”式单主线类比）**：全篇仅用**“房东请超级包工头装修新房”**这一个生活场景从头串到尾（开工交底 → 审设计图 → 现场施工 → 返工止损），零专业术语，任何无技术背景的人都能一秒读懂并形成肌肉记忆。

---

## 目录结构

```text
.
├── human/                          # 面向人类协作者（Human-in-the-Loop）
│   ├── HUMAN.md                    # 主文档：跨学科高维概念版（唤醒隐性认知）
│   └── HUMAN-simplified.md         # 简化版：“西瓜书”式装修房子单主线通俗版
├── agents/                         # 面向本地 Coding Agents 的全局执行契约
│   ├── gemini/
│   │   └── GEMINI.md               # Google Antigravity / Gemini 4 专用契约
│   ├── codex/                      # [WIP] OpenAI Codex 专用契约
│   ├── claude-code/                # [WIP] Anthropic Claude Code 专用契约
│   ├── cursor/                     # [WIP] Cursor 专用契约
│   ├── windsurf/                   # [WIP] Windsurf 专用契约
│   └── opencode/                   # [WIP] OpenCode 专用契约
├── chatbots/                       # 面向网页端/对话式大模型的全局参谋契约
│   └── CHATBOT.md                  # ChatGPT / Claude / Gemini Web 通用自定义指令
└── LICENSE                         # MIT License
```

---

## 人机四阶对偶闭环

| 协作阶段 | 人类侧职责 ([`human/HUMAN.md`](./human/HUMAN.md)) | 模型侧职责 ([`agents/`](./agents/) & [`chatbots/`](./chatbots/)) |
| :--- | :--- | :--- |
| **1. 破题与求真** | **反 X-Y Problem**：给出真实终局目标与约束底线，不微操具体步骤。 | **先检索后落笔 & 动态核验**：查证本地上下文与一手官方信源，发现前提缺陷直陈更优解。 |
| **2. 推演与去偏** | **零锚定提问 & 红队交叉审查**：隐去个人倾向，用独立会话对冲确认偏误。 | **严守归因红线**：拒绝迎合与事后合理化，主动构建最强反方论点与反证条件。 |
| **3. 决策与边界** | **守住单向门裁判权**：可逆细节充分放权，不可逆边界亲自核验，克服自动化偏见。 | **默认端到端闭环**：可逆任务直接落地，触及删数、破契约、核心依赖与安全/计费边界硬拦截。 |
| **4. 控熵与止损** | **破除沉没成本谬误**：长会话信噪比劣化时果断清空重开，触发双环学习修补规则。 | **最小侵袭 & 精准验证**：禁投机抽象与静默吞错，局部验证防过度测试，简单任务跳过冗余推理。 |

---

## License

[MIT](./LICENSE) © Rael LIANG
