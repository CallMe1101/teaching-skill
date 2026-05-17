# AI Teaching Skill

> **Teach AI how to explain concepts until users truly understand.**
> Not "information dumping" — it's "building a ladder from confusion to clarity."

[![Version](https://img.shields.io/badge/version-0.5.0-blue.svg)](https://github.com/CallMe1101/ai-teaching-skill/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub stars](https://img.shields.io/github/stars/CallMe1101/ai-teaching-skill.svg?style=social)](https://github.com/CallMe1101/ai-teaching-skill/stargazers)

[English](README.md) | [中文文档](README.zh.md)

---

## What is this?

A skill file for AI agents (Claude Code, Codex, Cursor, etc.) that teaches AI how to explain concepts systematically. Instead of dumping information, it guides students from confusion to understanding through structured teaching methods.

**Core idea**: Good teaching = student can explain the concept to others in their own words.

---

## 🚀 Installation

### 1. Claude Code

Claude Code can use this skill directly as a local skill. This is the simplest installation path.

**Primary method: Plugin marketplace installation**

This repository is published as a Claude Code plugin, making installation simple.

```bash
# Add the marketplace (one-time)
/plugin marketplace add https://github.com/CallMe1101/ai-teaching-skill

# Install the plugin
/plugin install ai-teaching-skill

# Reload to apply
/reload-plugins
```

The skill is available automatically after reload. No manual wrapper setup needed.

**Alternative: Manual copy**

If you prefer manual control, copy the SKILL.md file to your Claude skills directory:

```bash
mkdir -p ~/.claude/skills
cp SKILL.md ~/.claude/skills/ai-teaching.md
```

Then open a new Claude Code session and invoke it naturally:

```
Explain what is API
Teach me about machine learning
```

**Official Claude Code docs**:
- [Skills](https://docs.anthropic.com/en/docs/claude-code/skills)
- [Slash commands](https://docs.anthropic.com/en/docs/claude-code/commands)

### 2. Codex

Codex can use this skill directly as a local skill. This is the simplest installation path.

**Clone the repo**

```bash
git clone https://github.com/CallMe1101/ai-teaching-skill.git
cd ai-teaching-skill
```

**Install the skill**

```bash
mkdir -p ~/.codex/skills
cp -R . ~/.codex/skills/ai-teaching/
```

**Update after pulling new changes**

```bash
git pull
cp -R . ~/.codex/skills/ai-teaching/
```

**Finish**

Restart Codex so newly added skills are picked up.

Then ask naturally, for example:
- `Explain what is API`
- `Teach me about machine learning`

If you prefer not to use the terminal, copying the skill folder into `~/.codex/skills/` manually works as well.

### 3. Other agents or manual use

If your agent supports reusable prompt files, system prompts, or agent profiles, the minimum portable unit is the skill directory itself:

```
ai-teaching-skill/
├── README.md
├── SKILL.md
└── references/...
```

In that case:

1. Copy the whole skill directory into your prompt library or project.
2. Preserve `SKILL.md` and any `references/` files together.
3. Adapt the frontmatter and body to the target agent's native format if needed.

**Supported agents**:
- **Cursor**: `.cursor/rules/` or `.cursor/skills/`
- **Windsurf**: Windsurf rules configuration
- **Gemini CLI**: `~/.gemini/skills/`
- **Any Agent**: Copy to your prompt library or project

---

## 💡 Usage Example

**User**: "Explain what is API"

**AI (with skill)**:
> Before we start, I'd like to understand your current level. Have you encountered "API" before? For example, while learning programming, using tools, or reading documentation? Try to describe what you think an API is in your own words (even just one word or a metaphor is fine).
>
> Don't worry, just say what you think, and I'll adjust the pace based on your answer. 😊

**User**: "I've heard of it but don't really understand"

**AI**:
> Great! Let me use a metaphor to help you understand.
>
> Imagine you're at a restaurant. You (the client) want to order food, but you can't directly go into the kitchen to cook. You need a waiter (API) to convey your needs.
>
> The waiter's job:
> 1. Takes your order (request)
> 2. Tells the kitchen (server)
> 3. Brings the food to you (response)
>
> **An API is like a "waiter" in the software world.** It lets you get food (data) without knowing how the kitchen (server) works.

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
- Task is pure execution (write code, run commands), no understanding needed
- User is L5 proficient developer, only needs specific API/parameter lookup

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
| **Claude Code** | ✅ Full Support | Plugin marketplace |
| **Codex** | ✅ Full Support | `~/.codex/skills/` |
| **Cursor** | ✅ Supported | `.cursor/rules/` |
| **Windsurf** | ✅ Supported | Rules config |
| **Gemini CLI** | ✅ Supported | `~/.gemini/skills/` |
| **Any Agent** | ✅ Supported | Copy SKILL.md to skill directory |

---

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=CallMe1101/ai-teaching-skill&type=Date)](https://star-history.com/#CallMe1101/ai-teaching-skill&Date)

---

## 📖 Design Sources

This skill's design incorporates teaching experience from:

- 95+ official/community skills structure analysis
- `teaching-code-to-beginners` skill's interactive teaching method
- `systematic-debugging` skill's "iron law" design technique
- `humanizer` skill's Before/After comparison method
- Study Mode prompt's roadmap + mastery tracking design
- Five-step teaching method (concept anchoring → professional definition → complete derivation → practice cases → difference comparison)
- Science writer prompt's metaphor-first + storytelling narrative method

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

## 🙏 Acknowledgments

- [teaching-code-to-beginners](https://github.com/NousResearch/hermes-agent/blob/main/skills/teaching-code-to-beginners) - Code teaching skill
- [nature-skills](https://github.com/Yuan1z0825/nature-skills) - Academic writing skills
- All contributors and testers
