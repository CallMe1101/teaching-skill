# AI Teaching Skill

> **教 AI 如何把一个概念讲到用户真正理解。**
> 不是"信息搬运"，是"搭建从不懂到懂的梯子"。

[![Version](https://img.shields.io/badge/version-0.5.0-blue.svg)](https://github.com/CallMe1101/teaching-skill/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub stars](https://img.shields.io/github/stars/CallMe1101/teaching-skill.svg?style=social)](https://github.com/CallMe1101/teaching-skill/stargazers)

[English](README.md) | [中文文档](README.zh.md)

---

## 这是什么？

一个给 AI Agent（Claude Code、Codex、Cursor 等）使用的教学技能文件。加载这个 Skill 后，AI 会按照一套系统化的教学方法论来给用户讲解概念，而不是一股脑地把信息 dump 给你。

**核心理念**：好的教学 = 学生能用自己的话向别人解释清楚这个概念。

---

## 🚀 安装

### 1. Claude Code

Claude Code 可以直接使用这个技能作为本地技能。这是最简单的安装路径。

**主要方法：插件市场安装**

这个仓库已发布为 Claude Code 插件，使安装变得简单。

```bash
# 添加市场（一次性）
/plugin marketplace add https://github.com/CallMe1101/teaching-skill

# 安装插件
/plugin install teaching-skill

# 重新加载以应用
/reload-plugins
```

重新加载后技能自动可用，无需手动设置。

**备用方法：手动复制**

如果你更喜欢手动控制，可以将 SKILL.md 文件复制到 Claude 技能目录：

```bash
mkdir -p ~/.claude/skills
cp SKILL.md ~/.claude/skills/teaching.md
```

然后打开新的 Claude Code 会话，自然地调用它：

```
解释一下什么是API
教我机器学习
```

**官方 Claude Code 文档**：
- [Skills](https://docs.anthropic.com/en/docs/claude-code/skills)
- [Slash commands](https://docs.anthropic.com/en/docs/claude-code/commands)

### 2. Codex

Codex 可以直接使用这个技能作为本地技能。这是最简单的安装路径。

**克隆仓库**

```bash
git clone https://github.com/CallMe1101/teaching-skill.git
cd teaching-skill
```

**安装技能**

```bash
mkdir -p ~/.codex/skills
cp -R . ~/.codex/skills/teaching/
```

**更新后重新安装**

```bash
git pull
cp -R . ~/.codex/skills/teaching/
```

**完成**

重启 Codex 以便新添加的技能被识别。

然后自然地提问，例如：
- `解释一下什么是API`
- `教我机器学习`

如果你不想使用终端，手动将技能文件夹复制到 `~/.codex/skills/` 也可以。

### 3. 其他代理或手动使用

如果你的代理支持可重用的提示文件、系统提示或代理配置，最小可移植单元是技能目录本身：

```
teaching-skill/
├── README.md
├── SKILL.md
└── references/...
```

在这种情况下：

1. 将整个技能目录复制到你的提示库或项目中。
2. 保持 `SKILL.md` 和任何 `references/` 文件在一起。
3. 根据需要调整前置元数据和正文以适应目标代理的原生格式。

**支持的代理**：
- **Cursor**：`.cursor/rules/` 或 `.cursor/skills/`
- **Windsurf**：Windsurf rules 配置
- **Gemini CLI**：`~/.gemini/skills/`
- **任意代理**：复制到你的提示库或项目中

---

## 💡 使用示例

**用户**："解释一下什么是API"

**AI（使用skill）**：
> 在开始之前，我想先了解一下你的情况。你之前接触过"API"这个词吗？比如在学编程、用工具、或者读文档时看到过？尝试用自己的话描述一下你认为的API是什么（哪怕只说一个词或一个比喻也行）。
>
> 不用紧张，怎么想的就怎么说，我根据你的回答来调整接下来的节奏。😊

**用户**："听说过，但不太清楚"

**AI**：
> 好的！让我用一个比喻来帮助你理解。
>
> 想象你去餐厅吃饭。你（客户端）想点餐，但你不能直接进厨房做饭。你需要通过服务员（API）来传达你的需求。
>
> 服务员的工作：
> 1. 接收你的点单（请求）
> 2. 把点单告诉厨房（服务器）
> 3. 把做好的菜端给你（响应）
>
> **API就是软件世界里的"服务员"**。它让你不用知道厨房（服务器）怎么运作，就能吃到饭（获取数据）。

---

## 🎯 解决什么问题？

| 问题 | 传统AI教学 | AI Teaching Skill |
|------|-----------|-------------------|
| **信息过载** | 一次性dump所有信息 | 一次一个概念，循序渐进 |
| **缺乏引导** | 直接给答案 | 引导学生自己发现 |
| **节奏失控** | 固定速度教学 | 自适应节奏调整 |
| **验证缺失** | 不知道是否真的懂了 | 多种验证方法 |
| **遗忘曲线** | 学完就忘 | 对抗遗忘机制 |

---

## 📚 技能索引

| 功能 | 状态 | 用途 | 触发关键词 |
|------|------|------|-----------|
| **概念教学** | ✅ Stable | 教概念、理论、原理，使用比喻和结构化讲解 | "explain", "teach me", "what is", "give me a lecture", "讲解", "解释", "教我" |
| **代码教学** | ✅ Stable | 教代码、工具、项目，使用展示-猜测-确认方法 | "what does this mean", "help me understand this code", "这段代码是什么意思", "帮我理解" |
| **深度学习** | ✅ Stable | 完整五步梯教学，深入理解复杂概念 | "deep understanding", "full derivation", "深入理解", "完整推导", "详细讲解" |
| **快速解释** | ✅ Stable | 轻量模式，快速简洁的解释 | "quick explanation", "briefly explain", "简单说一下", "快速解释" |

---

## 🔍 技能详情

### 概念教学

**功能** — 教概念、理论和原理，使用结构化方法：先比喻，再专业定义，然后验证。确保学生真正理解后再继续。

**核心规则**

| 领域 | 核心规则 |
|------|---------|
| 比喻优先 | 总是用生活比喻开始，建立心智模型 |
| 一次一个概念 | 一次交流只引入一个新概念 |
| 验证理解 | 让学生用自己的话解释 |
| 连接实际 | 将概念连接到学生的实际场景 |

**工作流程示例**

```
用户："什么是协整？"
AI：[使用比喻：遛狗]
AI：[提供专业定义]
AI：[问验证问题]
AI：[连接到学生项目]
```

### 代码教学

**功能** — 教代码、工具和项目，使用展示-猜测-确认方法：展示真实代码，让学生猜测含义，确认或纠正，然后动手实践。

**核心规则**

| 领域 | 核心规则 |
|------|---------|
| 真实代码优先 | 使用学生自己的项目代码，不是教科书例子 |
| 先猜后讲 | 让学生猜测含义后再解释 |
| 动手实践 | 总是让学生自己尝试 |
| 渐进难度 | 从简单开始，逐渐增加复杂度 |

**工作流程示例**

```
用户："这段CSS flex是什么意思？"
AI：[展示学生项目中的代码]
AI："你觉得这行代码是干什么的？"
AI：[确认或纠正学生的猜测]
AI："试试改一下看看会发生什么"
```

### 深度学习

**功能** — 为复杂概念提供完整的五步梯教学：锚（比喻）→ 义（专业定义）→ 推（逐步推导）→ 例（实际案例）→ 界（边界分析）。

**核心规则**

| 领域 | 核心规则 |
|------|---------|
| 五步梯 | 遵循 锚→义→推→例→界 流程 |
| 零跳跃 | 推导中展示每一步，没有魔术公式 |
| 符号释义 | 解释公式中的每个符号 |
| 至少2个案例 | 一个基础，一个进阶 |

**工作流程示例**

```
用户："详细讲解贝叶斯定理"
AI：[步骤1：比喻 - 医学检测]
AI：[步骤2：专业定义]
AI：[步骤3：完整推导和符号解释]
AI：[步骤4：两个案例]
AI：[步骤5：与频率派对比]
```

### 快速解释

**功能** — 为简单概念或用户只需要快速概述时提供轻量、简洁的解释。使用比喻和一句话总结。

**核心规则**

| 领域 | 核心规则 |
|------|---------|
| 一个比喻 | 用一个清晰的比喻来解释 |
| 一句话总结 | 以清晰的要点结束 |
| 无验证 | 不问验证问题 |
| 保持简短 | 最多2-3段 |

**工作流程示例**

```
用户："快速解释一下什么是API"
AI："API就像餐厅里的服务员..."
AI："记住：API是不同软件之间的桥梁。"
```

---

## 📚 核心设计

### 三条铁律（不可违反）

1. **不给答案，给梯子** — 引导发现，不是直接告诉
2. **先诊断，后教学** — 先搞清楚学生水平，再决定怎么教
3. **一次一个，不贪多** — 一问一答只引入一个新知识点

### 两种教学模式

| 模式 | 适用场景 | 流程 |
|------|---------|------|
| **轻量模式** | 代码/工具/项目/操作 | 比喻 → 展示 → 猜测 → 确认 → 动手 |
| **深度模式** | 概念/理论/原理/模型 | 五步梯：锚→义→推→例→界 |

### 教学流程

```
诊断（水平 + 目标）
    ↓
规划（学习路线图）
    ↓
教学（轻量/深度模式）
    ↓
验证（真的懂了吗？）
```

---

## 🔍 什么时候用？

### 触发关键词

| 关键词 | 场景 |
|-------|------|
| "给我讲讲"、"解释一下"、"教我" | 概念教学 |
| "这是什么意思"、"帮我理解" | 代码/工具教学 |
| "深入理解"、"完整推导" | 深度模式 |
| "简单说一下" | 轻量模式 |

### 不适用场景

- 用户要的是"帮我做完"而不是"教我怎么做"
- 用户明确说"直接给我答案"
- 任务是纯执行型（写代码、跑命令），不需要理解
- 用户是L5熟练开发者，只需要查一个具体API/参数

---

## 🌐 兼容性

| Agent | 支持状态 | 安装方式 |
|-------|---------|---------|
| **Claude Code** | ✅ 完全支持 | Plugin marketplace |
| **Codex** | ✅ 完全支持 | `~/.codex/skills/` |
| **Cursor** | ✅ 支持 | `.cursor/rules/` |
| **Windsurf** | ✅ 支持 | Rules配置 |
| **Gemini CLI** | ✅ 支持 | `~/.gemini/skills/` |
| **任意 Agent** | ✅ 支持 | 复制SKILL.md到技能目录 |

---

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=CallMe1101/teaching-skill&type=Date)](https://star-history.com/#CallMe1101/teaching-skill&Date)

---

## 📖 设计来源

这个 Skill 的设计融合了以下来源的教学经验：

- 95+ 个官方/社区 Skill 的结构分析
- `teaching-code-to-beginners` Skill 的交互式教学方法
- `systematic-debugging` Skill 的"铁律"设计手法
- `humanizer` Skill 的 Before/After 对比法
- Study Mode 提示词的路线图 + 掌握度追踪设计
- 五步教学法（概念锚定→专业定义→完整推导→实践案例→差异对比）
- 科普作家提示词的比喻优先 + 故事化叙事方法

---

## 🤝 贡献

欢迎贡献！请查看 [CONTRIBUTING.md](CONTRIBUTING.md)。

### 如何贡献

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'feat: 添加你的特性描述'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

---

## 📄 许可证

MIT License - 详见 [LICENSE](LICENSE)

---

## 🙏 致谢

- [teaching-code-to-beginners](https://github.com/NousResearch/hermes-agent/blob/main/skills/teaching-code-to-beginners) - 代码教学Skill
- [nature-skills](https://github.com/Yuan1z0825/nature-skills) - 学术写作Skill
- 所有贡献者和测试者
