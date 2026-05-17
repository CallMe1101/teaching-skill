# AI Teaching Skill

> 教 AI 如何把一个概念讲到用户真正理解。
> 不是"信息搬运"，是"搭建从不懂到懂的梯子"。

## 这是什么

一个给 AI Agent（Hermes Agent / Claude Code / Cursor 等）使用的教学技能文件。
加载这个 Skill 后，AI 会按照一套系统化的教学方法论来给用户讲解概念，
而不是一股脑地把信息 dump 给你。

## 核心设计

### 三条铁律

1. **不给答案，给梯子。** 引导发现，不是直接告诉。
2. **先诊断，后教学。** 先搞清楚学生水平，再决定怎么教。
3. **一次一个，不贪多。** 一问一答只引入一个新知识点。

### 教学流程

```
诊断（水平 + 目标） → 规划（学习路线图） → 教学（轻量/深度模式） → 验证（真的懂了吗？）
```

### 两种教学模式

| 模式 | 适用场景 | 流程 |
|------|---------|------|
| 轻量模式 | 代码/工具/项目/操作 | 比喻 → 展示 → 猜测 → 确认 → 动手 |
| 深度模式 | 概念/理论/原理/模型 | 五步梯：锚→义→推→例→界 |

### 五步梯（深度模式）

```
锚（比喻建模）→ 义（专业定义）→ 推（完整推导）→ 例（实践案例）→ 界（差异对比）
```

### 对抗遗忘机制

- 学习路线图 + [m]/[~] 掌握度追踪
- 导航提示（每 3 轮对话）
- 即时复盘（用到旧知识时快速回忆）
- 速查表构建（每学完一个概念群）

## 使用方式

### Hermes Agent

将 `SKILL.md` 复制到 `~/.hermes/skills/ai-teaching/` 目录下：

```bash
mkdir -p ~/.hermes/skills/ai-teaching
cp SKILL.md ~/.hermes/skills/ai-teaching/
```

然后在对话中说 `/skill ai-teaching` 或让 AI 自动匹配。

### Claude Code

将 `SKILL.md` 复制到项目的 `.claude/` 目录下，或作为 Claude Code plugin 使用。

### Cursor

将 `SKILL.md` 放到项目的 `.cursorrules` 或 `.cursor/skills/` 目录下。

## 设计来源

这个 Skill 的设计融合了以下来源的教学经验：

- 95+ 个 Hermes Agent 官方/社区 Skill 的结构分析
- `teaching-code-to-beginners` Skill 的交互式教学方法
- `systematic-debugging` Skill 的"铁律"设计手法
- `humanizer` Skill 的 Before/After 对比法
- Study Mode 提示词的路线图 + 掌握度追踪设计
- 五步教学法（概念锚定→专业定义→完整推导→实践案例→差异对比）
- 科普作家提示词的比喻优先 + 故事化叙事方法

## 文件结构

```
ai-teaching-skill/
├── SKILL.md           ← 核心 Skill 文件
├── README.md          ← 本文件
└── references/        ← 参考资料（待补充）
```

## License

MIT

## 更新日志

### v0.5.0 (2026-05-17)

**结构调整**：
- 添加 Prerequisites 部分（前置条件）
- 添加 Inputs Required 部分（输入要求）
- 添加 Verification Checklist 部分（验证清单）
- 优化 When to Use / When NOT to Use 部分
- 优化 Quality Standard 部分
- 优化 Anti-Patterns 部分

**内容优化**：
- 使教学流程更加具体和可操作
- 添加更多的示例和案例
- 使验证方法更加明确
- 使反面案例更加详细

**语言策略**：
- 采用中英文混合策略
- 元数据英文，内容中文
- 符合中文skill社区的惯例

### v0.4.0 (2026-05-16)

初始版本，包含完整的教学流程和方法论。
