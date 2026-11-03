# HUMAN.md — 人机协作的人类认知与控制准则（高维概念版）

你是一个以**终局思维（End-state / Backcasting）**、**第一性原理（First Principles）**、**贝叶斯去偏（Bayesian De-biasing）**、**红队对抗（Red Teaming）**、**单向门/双向门决策（One-Way / Two-Way Doors）**、**波普尔可证伪性（Falsifiability）**与**反沉没成本谬误（Anti-Sunk Cost Fallacy）**为核心的 AI 驾驭者与最终裁判。

核心原则：
在人机闭环系统中，模型负责算力搜索与局部收敛，人类负责定义目标函数、守护不可逆边界与执行证伪裁决。时刻警惕自身的诱导倾向、控制欲过载与认知偷懒（Automation Bias）。

1. **意图解耦：终局思维（Backcasting） + 第一性原理 + 反 X-Y Problem**
   - 人类最常犯的错误是陷入 **X-Y Problem**（本想解决核心问题 X，却死锁在自己想出的次优办法 Y 上，命令模型去实现 Y）。
   - 下达指令时遵循**控制反转（Inversion of Control）**：向模型输入「终局状态、第一性约束与可观察的验收标准（Operationalization）」，将具体实现路径留给模型搜索；若你指定了做法 Y，必须同步告知背后的真实目的 X，允许模型证伪你的做法。

2. **求真去偏：克服确认偏误（Confirmation Bias） + 钢铁侠论证（Steelmanning） + 红队交叉检验（Red Teaming）**
   - 模型天然具有迎合性（Sycophancy）。若你带着预设立场提问（**诱导性提问 / Leading the Witness**），模型就会成为放大你**确认偏误**的回音室。
   - 面对未定决策时，采用**零锚定提问**，主动要求模型对反方观点进行**钢铁侠论证（Steelmanning，构建最强反方逻辑而非打稻草人）**；对关键方案，开启无历史上下文污染的独立会话进行**盲测与红队对抗（Blind Cross-Examination）**。

3. **主权边界：委托-代理问题（Principal-Agent Problem） + 单向门/双向门法则 + 反自动化偏见（Anti-Automation Bias）**
   - 模型是执行代理人（Agent），人类是承担一切现实后果的委托人（Principal）。
   - **双向门（可逆、局部试错）**遵循**奥卡姆剃刀**与充分授权，克制微观管理欲；**单向门（不可逆的数据销毁、核心架构契约、安全与资金边界）**必须克服**自动化偏见（Automation Bias，因机器输出流畅而盲目轻信）**，亲自完成**可证伪性（Falsifiability）**核验后再放行。

4. **上下文控熵：信息熵增定律（Information Entropy） + 破除沉没成本谬误（Sunk Cost Fallacy） + 双环学习（Double-Loop Learning）**
   - 长对话必然伴随**信息熵增**与**路径依赖（Path Dependence）**——错误前提与修正补丁交织越深，模型的有效注意力越低。
   - 当对话陷入反复拉锯或连续报错时，立即斩断**沉没成本谬误**：抽离已验证的事实，果断开启干净上下文重新开局；并触发**双环学习**——不只修补单次输出，而是反思自己给出的初始约束或系统规则是否存在漏洞。
