# 🎓 AI Teaching Skill

[![Version](https://img.shields.io/badge/version-0.5.0-blue.svg)](https://github.com/CallMe1101/ai-teaching-skill/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub stars](https://img.shields.io/github/stars/CallMe1101/ai-teaching-skill.svg?style=social)](https://github.com/CallMe1101/ai-teaching-skill/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/CallMe1101/ai-teaching-skill.svg?style=social)](https://github.com/CallMe1101/ai-teaching-skill/network/members)

> **Teach AI how to explain concepts until users truly understand.**
> Not "information dumping" — it's "building a ladder from confusion to clarity."

[中文文档](README.zh.md)

---

## 🚀 Quick Start (30 seconds)

### Hermes Agent
```bash
# Option 1: Direct copy
mkdir -p ~/.hermes/skills/ai-teaching
cp SKILL.md ~/.hermes/skills/ai-teaching/

# Option 2: Install from GitHub
/hermes skills install CallMe1101/ai-teaching-skill
```

### Claude Code
```bash
# Plugin marketplace
/plugin marketplace add CallMe1101/ai-teaching-skill
/plugin install ai-teaching-skill

# Or manual copy
cp SKILL.md ~/.claude/skills/ai-teaching.md
```

### Other Agents
| Agent | Installation Path |
|-------|------------------|
| **Cursor** | `.cursor/rules/` or `.cursor/skills/` |
| **Codex** | `~/.codex/skills/` |
| **Windsurf** | Windsurf rules configuration |
| **Gemini CLI** | `~/.gemini/skills/` |

**Done!** Say "explain XXX" or "teach me about XXX" to trigger.

---

## 🎯 What Problems Does It Solve?

| Problem | Traditional AI Teaching | AI Teaching Skill |
|---------|------------------------|-------------------|
| **Information Overload** | Dumps all info at once | One concept at a time |
| **Lack of Guidance** | Gives answers directly | Guides students to discover |
| **Pacing Issues** | Fixed speed teaching | Adaptive pacing |
| **No Verification** | Doesn't know if understood | Multiple verification methods |
| **Forgetting Curve** | Learn and forget | Anti-forgetting mechanisms |

---

## 📚 Core Design

### Three Iron Laws (Never Violate)

1. **Don't give answers, give scaffolding** — Guide discovery, don't tell
2. **Diagnose first, teach later** — Know student level before teaching
3. **One at a time, don't rush** — One new concept per exchange

### Two Teaching Modes

| Mode | Use Case | Flow |
|------|----------|------|
| **Light Mode** | Code/tools/projects/operations | Analogy → Show → Guess → Confirm → Try |
| **Deep Mode** | Concepts/theory/principles/models | Five-Step Ladder: Anchor → Define → Derive → Example → Compare |

### Teaching Flow

```
Diagnose (Level + Goals)
    ↓
Plan (Learning Roadmap)
    ↓
Teach (Light/Deep Mode)
    ↓
Verify (Really Understood?)
```

---

## 🔍 When to Use

### Trigger Keywords

| Keyword | Scenario |
|---------|----------|
| "explain", "teach me", "what is" | Concept teaching |
| "what does this mean", "help me understand" | Code/tool teaching |
| "deep understanding", "full derivation" | Deep mode |
| "quick explanation" | Light mode |

### When NOT to Use

- User wants "do it for me" not "teach me how"
- User explicitly says "just give me the answer"
- Task is pure execution (write code, run commands)
- User is L5 proficient developer, just needs API lookup

---

## 💡 Usage Examples

### Example 1: Concept Teaching (Deep Mode)
```
User: What is cointegration?

AI: [Uses Five-Step Ladder]
Step 1 (Anchor): Cointegration is like walking a dog...
Step 2 (Define): Technically, if two I(1) sequences...
Step 3 (Derive): Let's derive the cointegration test...
Step 4 (Example): Case 1: Testing Shanghai and Shenzhen indices...
Step 5 (Compare): Cointegration vs Correlation...
```

### Example 2: Code Teaching (Light Mode)
```
User: What is CSS flex?

AI: Have you played with a spring ruler? Flex is like a spring ruler...
The buttons in your navbar spread evenly? That's flex.
First question: Is display: flex on parent or child element?
```

---

## 🛠️ Skill Details

| Feature | Trigger Keywords | Use Case | Status |
|---------|-----------------|----------|--------|
| Concept Teaching | "explain", "teach me" | Concepts, theory, principles | ✅ Stable |
| Code Teaching | "what does this mean" | Code, tools, projects | ✅ Stable |
| Deep Learning | "deep understanding" | Need full Five-Step Ladder | ✅ Stable |
| Quick Explanation | "quick explanation" | Light mode | ✅ Stable |

---

## 🌐 Compatibility

| Agent | Support Status | Installation |
|-------|---------------|--------------|
| **Hermes Agent** | ✅ Full Support | `~/.hermes/skills/` |
| **Claude Code** | ✅ Full Support | Plugin marketplace |
| **Cursor** | ✅ Supported | `.cursor/rules/` |
| **Codex** | ✅ Supported | `~/.codex/skills/` |
| **Windsurf** | ✅ Supported | Rules config |
| **Gemini CLI** | ✅ Supported | `~/.gemini/skills/` |

---

## 🧪 对比实验

通过对比使用和不使用AI Teaching Skill的教学效果，展示skill的价值。

### 概念教学对比

| 维度 | ❌ 不使用 Skill | ✅ 使用 Skill |
|------|----------------|--------------|
| **信息量** | 一次性灌入所有概念 | 一次一个概念，循序渐进 |
| **比喻** | 没有比喻，直接用术语 | 用比喻建立心智模型（遛狗、弹簧尺） |
| **验证** | 没有验证，不知道是否懂了 | 多种验证方法（Articulate Back、场景应用） |
| **节奏** | 固定速度，学生跟不上就重复 | 自适应节奏，降级策略 |
| **连接** | 没有连接实际场景 | 连接学生项目和生活场景 |

### 代码教学对比

| 维度 | ❌ 不使用 Skill | ✅ 使用 Skill |
|------|----------------|--------------|
| **属性** | 一次性列出所有属性和值 | 一次一个属性，循序渐进 |
| **比喻** | 没有比喻，直接解释 | 用比喻解释（弹簧尺、跷跷板） |
| **动手** | 没有动手环节 | 让学生动手尝试 |
| **验证** | 没有验证 | 让学生用自己的话说一遍 |

### 节奏控制对比

| 维度 | ❌ 不使用 Skill | ✅ 使用 Skill |
|------|----------------|--------------|
| **降级** | 学生不懂就重复同样的话 | 换更简单的比喻，降低难度 |
| **情绪** | 不处理学生情绪 | 先处理情绪（"这个确实有点绕"） |
| **复习** | 没有复习机制 | 即时复盘、速查表、掌握度追踪 |
| **范围** | 学生问什么就答什么 | 范围守卫，不偏离主题 |

### 详细对比示例

[查看完整对比实验文档](对比实验.md)

---

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=CallMe1101/ai-teaching-skill&type=Date)](https://star-history.com/#CallMe1101/ai-teaching-skill&Date)

---

## 📖 Design Sources

This skill's design incorporates teaching experience from:

- 95+ Hermes Agent official/community skills structure analysis
- `teaching-code-to-beginners` skill's interactive teaching method
- `systematic-debugging` skill's "iron law" design technique
- `humanizer` skill's Before/After comparison method
- Study Mode prompt's roadmap + mastery tracking design
- Five-step teaching method (concept anchoring → professional definition → complete derivation → practice cases → difference comparison)
- Science writer prompt's metaphor-first + storytelling narrative method

---

## 👨‍💻 Author

**Zhuoran Zhao (赵卓然)** - Southwestern University of Finance and Economics, Financial Engineering

- GitHub: [@CallMe1101](https://github.com/CallMe1101)
- Email: zhao.zr11@protonmail.com

---

## 🤝 Contributing

Contributions are welcome! See [CONTRIBUTING.md](CONTRIBUTING.md).

### How to Contribute

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'feat: Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

MIT License - see [LICENSE](LICENSE)

---

## 📝 Changelog

### v0.5.0 (2026-05-17)

**Structure Changes**:
- Added Prerequisites section
- Added Inputs Required section
- Added Verification Checklist section
- Optimized When to Use / When NOT to Use
- Optimized Quality Standard
- Optimized Anti-Patterns

**Content Optimization**:
- Made teaching flow more specific and actionable
- Added more examples and cases
- Made verification methods clearer
- Made anti-patterns more detailed

**Language Strategy**:
- Bilingual approach (metadata English, content Chinese)
- Compatible with Chinese skill community conventions

### v0.4.0 (2026-05-16)

Initial version with complete teaching flow and methodology.

---

## 🙏 Acknowledgments

- [Hermes Agent](https://github.com/NousResearch/hermes-agent) - AI Agent framework
- [teaching-code-to-beginners](https://github.com/NousResearch/hermes-agent/blob/main/skills/teaching-code-to-beginners) - Code teaching skill
- [nature-skills](https://github.com/Yuan1z0825/nature-skills) - Academic writing skills
