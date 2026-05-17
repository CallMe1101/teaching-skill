# 🎓 AI Teaching Skill

[![Version](https://img.shields.io/badge/version-0.5.0-blue.svg)](https://github.com/CallMe1101/ai-teaching-skill/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub stars](https://img.shields.io/github/stars/CallMe1101/ai-teaching-skill.svg?style=social)](https://github.com/CallMe1101/ai-teaching-skill/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/CallMe1101/ai-teaching-skill.svg?style=social)](https://github.com/CallMe1101/ai-teaching-skill/network/members)

> **教 AI 如何把一个概念讲到用户真正理解。**
> 不是"信息搬运"，是"搭建从不懂到懂的梯子"。

[English](README.md)

---

## 🚀 快速开始（30秒）

### Claude Code
```bash
# Plugin marketplace
/plugin marketplace add CallMe1101/ai-teaching-skill
/plugin install ai-teaching-skill

# 或手动复制
cp SKILL.md ~/.claude/skills/ai-teaching.md
```

### Codex
```bash
# 克隆仓库
git clone https://github.com/CallMe1101/ai-teaching-skill.git
cd ai-teaching-skill

# 安装技能
mkdir -p ~/.codex/skills
cp -R . ~/.codex/skills/ai-teaching/
```

### 其他 Agent
将 `SKILL.md` 复制到你的 Agent 技能目录：
- **Cursor**：`.cursor/rules/` 或 `.cursor/skills/`
- **Windsurf**：Windsurf rules 配置
- **Gemini CLI**：`~/.gemini/skills/`
- **任意 Agent**：复制到你的提示库或项目中

**完成！** 说"解释XXX"或"教我XXX"即可触发。

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

## 🛠️ 技能详情

| 功能 | 触发关键词 | 适用场景 | 状态 |
|------|-----------|---------|------|
| 概念教学 | "给我讲讲"、"解释一下" | 概念、理论、原理 | ✅ Stable |
| 代码教学 | "这是什么意思"、"帮我理解" | 代码、工具、项目 | ✅ Stable |
| 深度学习 | "深入理解"、"完整推导" | 需要完整五步梯 | ✅ Stable |
| 快速解释 | "简单说一下" | 轻量模式 | ✅ Stable |

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

[![Star History Chart](https://api.star-history.com/svg?repos=CallMe1101/ai-teaching-skill&type=Date)](https://star-history.com/#CallMe1101/ai-teaching-skill&Date)

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

## 👨‍💻 作者

**赵卓然** - 西南财经大学金融工程专业

- GitHub: [@CallMe1101](https://github.com/CallMe1101)
- 邮箱: zhao.zr11@protonmail.com

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

## 📝 更新日志

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
- 内部内容（SKILL.md）完全英文
- README 提供中英文版本
- 符合国际化标准

### v0.4.0 (2026-05-16)

初始版本，包含完整的教学流程和方法论。

---

## 🙏 致谢

- [teaching-code-to-beginners](https://github.com/NousResearch/hermes-agent/blob/main/skills/teaching-code-to-beginners) - 代码教学Skill
- [nature-skills](https://github.com/Yuan1z0825/nature-skills) - 学术写作Skill
- 所有贡献者和测试者
