# human.md

> Everyone writes `AGENTS.md` for AI. We wrote `HUMAN.md` for the human in the loop.

一套给人类与 AI 共同使用的工作约定。人类决定目标与取舍，AI 负责提出方案和执行；双方的事实判断都需要证据，错误指令和错误建议都应被挑战。

## 从哪里开始

| 文档 | 用途 |
| --- | --- |
| [HUMAN.md](human/HUMAN.md) | 人类侧：说明目标、判断证据、处理暂停、明确取舍与停止盲目试错 |
| [HUMAN-simplified.md](human/HUMAN-simplified.md) | 用装修的例子解释同一套协作约定 |
| [Codex · AGENTS.md](agents/codex/AGENTS.md) | 判断与表达、需求与产品判断、工程原则、协作与决策 |
| [Claude Code · CLAUDE.md](agents/claude-code/CLAUDE.md) | 与 Codex、Gemini 保持相同的通用原则 |
| [Gemini · GEMINI.md](agents/gemini/GEMINI.md) | 与 Codex、Claude Code 保持相同的通用原则 |
| [CHATBOT.md](chatbots/CHATBOT.md) | 对话式助手的独立指令；本次协作规则更新未同步此文件 |

## 双方怎样协作

1. **明确目标。** 人类说明希望改善的结果、约束与偏好；AI 检查做法是否服务于目标，提出有依据的替代，不自行替换目标。
2. **依据证据判断。** 双方区分事实、假设和推断，考虑会推翻结论的证据。独立审查用于暴露分歧，不能用模型票数代替核验。
3. **必要时暂停。** 执行将实质违背明确目标或约束、依赖被证伪的关键前提，或缺少必要授权、存在可能造成难以挽回后果的重大未决取舍时，AI 暂停受影响的步骤，说明依据和替代，继续不受影响的工作。
4. **解决后继续。** 人类纠正前提、调整目标或约束，或知情接受具体剩余风险。催促不能消除冲突；取舍明确后，AI 没有新的重要证据就不反复阻拦，也不要求固定的确认措辞。
5. **让试错产生信息。** 重复失败时检查假设和证据，下一次尝试应有信息目的或改变依据。讨论混乱时先整理事实和未决问题，再决定继续、独立审查或换会话，不默认推倒重来。

这些约定约束人类的盲目指挥，也约束 AI 的迎合、擅自扩张和过度阻拦。自然语言指令不能保证实际行为，需在任务中观察效果，并根据真实问题修订。

## 工程原则

三份 Coding Agent 文档使用相同正文：从实际需求与已有契约出发，明确职责、数据与业务规则归属，按实际场景处理故障，避免投机抽象、重复校验和掩盖错误的兜底。新增机制应有当前需求或失效路径的依据，并值得其复杂度成本。

共同原则直接保留在各 Agent 的入口文件中，修改时同步三份正文。机器专属工具和路径按本地环境另行适配，不写入公共版本。

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
