# human.md

> Everyone writes `AGENTS.md` for AI. We wrote `HUMAN.md` for the human in the loop.

你可以从遇到的麻烦说起，即使还不知道该怎么问。这套约定帮助 AI 理解你想改变什么，给出它推荐的做法，并在确实需要你取舍时，把问题问清楚。

## 从哪里开始

| 文档 | 适合什么时候读 |
| --- | --- |
| [HUMAN-simplified.md](human/HUMAN-simplified.md) | 第一次读，用装修的例子理解怎样提需求、交给对方拿主意、解决分歧 |
| [HUMAN.md](human/HUMAN.md) | 想仔细了解如何判断建议、授权、处理暂停与反复试错 |
| [Codex](agents/codex/AGENTS.md) · [Claude Code](agents/claude-code/CLAUDE.md) · [Gemini](agents/gemini/GEMINI.md) | 为你使用的编程助手配置同一套工作原则 |
| [CHATBOT.md](chatbots/CHATBOT.md) | 为对话式助手配置独立指令 |

## 双方怎样协作

比如你说“客户总找不到以前提交的申请，给首页加个搜索框吧”。AI 可以先沿着客户的操作找一次申请。如果首页上“我的申请”很难发现，它可以建议把入口放到显眼的位置。如果客户已经找到了列表，却翻不到某一笔申请，搜索才更可能解决问题。缺少这段信息时，值得问的是“客户通常卡在哪一步？”

你熟悉自己的处境，可以把具体做法交给 AI。已有偏好和项目惯例足以决定的细节，由它直接处理。遇到影响结果的取舍，它应先给出首选方案，用日常语言讲清好处和代价。

出现具体冲突时，AI 暂停相关步骤，说明原因，继续能独立完成的工作。恢复的条件取决于停下来的原因。缺授权就取得相应授权，方案违背要求就改方案或重新商定要求，剩下的取舍由有权决定的人作出。连续失败时，先弄清下一次尝试能验证什么。

## 工程原则

先看用户能否完成任务，再判断方案是否足够。新增机制要能指出简单做法满足不了哪项实际需要。交付前从实际入口验证关键行为。旧功能何时停用，依据现有使用者、兼容承诺和迁移安排决定。

三份编程助手文档保持正文一致。机器专属工具和路径保留在个人配置中。

## 使用方式

先阅读人类侧文档，再按所用工具选择对应 Agent 文件。合并到已有个人配置前，检查并保留仍然需要的本地设置；不要直接覆盖未备份的配置。

在仓库根目录下，可以将对应文档复制到本地配置位置。以下命令使用交互确认，目标已存在时会询问是否覆盖：

```bash
# 按使用的工具选择执行
mkdir -p ~/.codex
cp -i agents/codex/AGENTS.md ~/.codex/AGENTS.md

mkdir -p ~/.claude
cp -i agents/claude-code/CLAUDE.md ~/.claude/CLAUDE.md

mkdir -p ~/.gemini
cp -i agents/gemini/GEMINI.md ~/.gemini/GEMINI.md
```

复制后的配置不会随仓库自动更新。也可以自行使用软链接，但仓库修改会直接影响本地配置，且应另行安排机器专属设置。指令的加载和优先级以各工具实际行为为准。

## License

[MIT](LICENSE) © Rael LIANG
