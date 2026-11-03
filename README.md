# human.md

> **"Everyone writes `AGENTS.md` for AI. We wrote `HUMAN.md` for the human in the loop."**  
> 全网都在给 AI 写 `AGENTS.md` / `CLAUDE.md` / `GEMINI.md`，但人机回路（Human-in-the-Loop）里最大的瓶颈，往往是没有一份给人类自己的 `HUMAN.md`。

一套面向新一代原生推理模型（GPT-6 / Claude 5.5 / Gemini 4 / Grok 4.7 / DeepSeek-V4）与人类协作者的**双向认知与执行协议**。

---

## 一分钟速览：人类在 AI 协作中最常踩的 4 个坑

想象你（**房东**）请了一位手脚快如闪电、什么活都会干、但特别爱看你脸色行事的 **“超级包工头（AI）”** 来装修你的新房（完整版见 [`human/HUMAN-simplified.md`](./human/HUMAN-simplified.md)，跨学科概念版见 [`human/HUMAN.md`](./human/HUMAN.md)）：

1. **【开工交底】只提“居住要求和底线”，别夺过铲子教他怎么和泥（反 `X-Y Problem`）**
   - 告诉他“老人住、要防滑隔音、预算三万”，别外行指导内行规定“水泥沙子几比几”；非要指定“装地暖”时，顺嘴补一句“我是怕老人冬天脚冷”，万一层高不够，他才能替你想到更好的暖气片方案。
2. **【审设计图】别诱导他顺着你吹捧，学会找“隔壁师傅”唱对台戏（克服 `确认偏误` & `红队盲测`）**
   - 别问“把阳台砸了是不是特敞亮？”，要反问“如果打通阳台，住进去三年后最让人后悔的坑是什么？”；重大方案捂住名字交给另一个干净窗口的 AI 挑刺，让两个行家唱对台戏。
3. **【现场施工】换窗帘随他折腾，砸承重墙必须亲眼验看（区分 `双向门` 与 `单向门`）**
   - 随时能重来的小事彻底放权，别让他每拧一颗螺丝都来请示；但碰到“砸承重墙、埋暗管、删老数据、改核心接口”这种没法后悔的**单向门**，必须叫停施工亲眼核验水压与钢筋，绝不做盲目签字的橡皮图章。
4. **【返工止损】墙面越补越花时，别心疼那点旧涂料，铲平重刷最快（对抗 `信息熵增` & `沉没成本谬误`）**
   - 同一窗口来回拉锯十几个回合、越改越乱时，说明这面墙的腻子已经彻底花了。别在烂摊子上糊第六层补丁——直接抄下有用的结论，开一个全新的干净窗口从头刷。

---

## 核心设计哲学：机器与人类的“镜像非对称”

在人机协作闭环中，**模型的上下文窗口**与**人类的生物大脑**遵循完全相反的唤醒机制：

* **给 AI 的协议（[`agents/`](./agents/) & [`chatbots/`](./chatbots/)）—— 去图腾化的高精度动作契约**
  - 模型每轮对话都会机械重读 System Prompt。若在提示词中堆砌抽象哲学口号，会引发原生推理模型的“词汇泄漏（掉书袋）”与自适应推理算力空转。
  - 因此，给模型的文档剥离了一切修辞图腾，仅保留模型无法自行推断的**工具时序（先检索后落笔）、反停滞自治、单向门硬拦截、防过度测试、快慢算力分流与上下文劣化主动熔断**。
* **给自己的协议（[`human/`](./human/)）—— 唤醒隐性知识的元概念与单主线类比**
  - 人类不会在每次敲回车前背诵操作清单。机械的条文看一遍就会忘；真正能在关键决策瞬间唤醒人类直觉的，只有**高维跨学科概念锚点**（[`HUMAN.md`](./human/HUMAN.md)）与**“西瓜书”式一以贯之的具象类比**（[`HUMAN-simplified.md`](./human/HUMAN-simplified.md)）。

---

## 目录结构与一键安装

```text
human.md/
├── human/                          # 面向人类协作者（Human-in-the-Loop）
│   ├── HUMAN.md                    # 主文档：跨学科高维概念版（唤醒隐性认知）
│   └── HUMAN-simplified.md         # 简化版：“西瓜书”式装修房子单主线通俗版
├── agents/                         # 面向主流本地 Coding Agents 的全局执行契约
│   ├── gemini/
│   │   └── GEMINI.md               # Google Antigravity / Gemini 全局契约 (~/.gemini/GEMINI.md)
│   ├── codex/
│   │   └── AGENTS.md               # OpenAI Codex 全局契约 (~/.codex/AGENTS.md)
│   └── claude-code/
│       └── CLAUDE.md               # Anthropic Claude Code 全局契约 (~/.claude/CLAUDE.md)
├── chatbots/                       # 面向网页端/对话式大模型的全局参谋契约
│   └── CHATBOT.md                  # ChatGPT / Claude / Gemini Web 通用自定义指令
└── LICENSE                         # MIT License
```

### 快速安装（Coding Agents）

在克隆后的仓库根目录下执行，通过软链接（Symlink）将仓库作为唯一事实源（SSOT）挂载至本地全局配置：

```bash
# 1. Google Antigravity / Gemini
ln -sf "$PWD/agents/gemini/GEMINI.md" ~/.gemini/GEMINI.md

# 2. OpenAI Codex
ln -sf "$PWD/agents/codex/AGENTS.md" ~/.codex/AGENTS.md

# 3. Anthropic Claude Code
ln -sf "$PWD/agents/claude-code/CLAUDE.md" ~/.claude/CLAUDE.md
```

---

## 人机四阶对偶闭环

| 协作阶段 | 人类侧职责 ([`human/HUMAN.md`](./human/HUMAN.md)) | 模型侧职责 ([`agents/`](./agents/) & [`chatbots/`](./chatbots/)) |
| :--- | :--- | :--- |
| **1. 破题与求真** | **反 X-Y Problem**：给出真实终局目标与约束底线，不微操具体步骤。 | **先检索后落笔 & 动态核验**：查证本地上下文与一手官方信源，发现前提缺陷直陈更优解。 |
| **2. 推演与去偏** | **零锚定提问 & 红队交叉审查**：隐去个人倾向，用独立会话对冲确认偏误。 | **严守归因红线**：拒绝迎合与事后合理化，主动构建最强反方论点与反证条件。 |
| **3. 决策与边界** | **守住单向门裁判权**：可逆细节充分放权，不可逆边界亲自核验，克服自动化偏见。 | **默认端到端闭环**：可逆任务直接落地，触及删数、破契约、核心依赖与安全/计费边界硬拦截。 |
| **4. 控熵与止损** | **破除沉没成本谬误**：长会话信噪比劣化时果断清空重开，触发双环学习修补规则。 | **最小侵袭、精准验证与主动熔断**：禁投机抽象与静默吞错，局部验证防过度测试；连续故障或长会话劣化时主动输出「已验证事实与阻塞点摘要」提示重开。 |

---

## License

[MIT](./LICENSE) © Rael LIANG
