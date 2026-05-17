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

## 📚 Skill Index

| Feature | Status | Purpose | Trigger Keywords |
|---------|--------|---------|------------------|
| **Concept Teaching** | ✅ Stable | Teach concepts, theory, principles using metaphors and structured explanation | "explain", "teach me", "what is", "give me a lecture", "讲解", "解释", "教我" |
| **Code Teaching** | ✅ Stable | Teach code, tools, projects using show-guess-confirm method | "what does this mean", "help me understand this code", "这段代码是什么意思", "帮我理解" |
| **Deep Learning** | ✅ Stable | Full Five-Step Ladder for deep understanding of complex concepts | "deep understanding", "full derivation", "深入理解", "完整推导", "详细讲解" |
| **Quick Explanation** | ✅ Stable | Light mode for quick, concise explanations | "quick explanation", "briefly explain", "简单说一下", "快速解释" |

---

## 🔍 Skill Details

### Concept Teaching

**What it does** — Teaches concepts, theory, and principles using a structured approach: metaphor first, then professional definition, then verification. Ensures students truly understand before moving forward.

**Core rules enforced**

| Domain | Core rule |
|--------|-----------|
| Metaphor first | Always start with a life analogy to build mental model |
| One concept at a time | Never introduce multiple concepts in one exchange |
| Verify understanding | Ask student to explain in their own words |
| Connect to reality | Link concept to student's actual scenarios |

**Example workflow**

```
User: "What is cointegration?"
AI: [Uses metaphor: walking a dog]
AI: [Provides professional definition]
AI: [Asks verification question]
AI: [Connects to student's project]
```

### Code Teaching

**What it does** — Teaches code, tools, and projects using a show-guess-confirm method: show real code, have student guess meaning, confirm or correct, then hands-on practice.

**Core rules enforced**

| Domain | Core rule |
|--------|-----------|
| Real code first | Use student's own project code, not textbook examples |
| Guess before explain | Have student guess meaning before explaining |
| Hands-on practice | Always have student try themselves |
| Progressive difficulty | Start simple, increase complexity gradually |

**Example workflow**

```
User: "What does this CSS flex do?"
AI: [Shows code from student's project]
AI: "What do you think this line does?"
AI: [Confirms or corrects student's guess]
AI: "Try changing it to see what happens"
```

### Deep Learning

**What it does** — Provides full Five-Step Ladder teaching for complex concepts: Anchor (metaphor) → Define (professional definition) → Derive (step-by-step derivation) → Example (real cases) → Compare (boundary analysis).

**Core rules enforced**

| Domain | Core rule |
|--------|-----------|
| Five-Step Ladder | Follow Anchor → Define → Derive → Example → Compare |
| Zero jumps | Show every step in derivation, no magic formulas |
| Symbol glossary | Explain every symbol in formulas |
| At least 2 examples | One basic, one advanced case |

**Example workflow**

```
User: "Explain Bayesian theorem in detail"
AI: [Step 1: Metaphor - medical test]
AI: [Step 2: Professional definition]
AI: [Step 3: Full derivation with symbols]
AI: [Step 4: Two examples]
AI: [Step 5: Compare with frequentist approach]
```

### Quick Explanation

**What it does** — Provides light, concise explanations for simple concepts or when user just needs a quick overview. Uses metaphor and one-sentence summary.

**Core rules enforced**

| Domain | Core rule |
|--------|-----------|
| One metaphor | Use one clear metaphor to explain |
| One sentence summary | End with a clear takeaway |
| No verification | Don't ask verification questions |
| Keep it short | 2-3 paragraphs maximum |

**Example workflow**

```
User: "Quickly explain what is API"
AI: "API is like a waiter in a restaurant..."
AI: "Remember: API is the bridge between different software."
```

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
