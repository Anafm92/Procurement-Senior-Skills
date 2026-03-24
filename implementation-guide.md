# 📦 How to Implement Your Procurement Skill in Claude Code
## Complete Step-by-Step Guide for Ana

---

## 🧩 What You Have

You now have two key files:

| File | Purpose |
|------|---------|
| `CLAUDE.md` | The main configuration file — Claude reads this automatically at the start of every session |
| `senior-procurement-manager-EN.md` | Full English version of your skill (for reference, documentation, or sharing) |

---

## ✅ Option 1 — Project-Level Setup (Recommended)
*Claude behaves as the procurement manager only within a specific project folder*

### Step 1: Install Claude Code (if not already done)
```bash
npm install -g @anthropic-ai/claude-code
```
Then authenticate:
```bash
claude
```

### Step 2: Create your project folder
```bash
mkdir procurement-assistant
cd procurement-assistant
```

### Step 3: Place your CLAUDE.md file inside that folder
Copy the `CLAUDE.md` file directly into your project root:
```
procurement-assistant/
└── CLAUDE.md  ← paste it here
```

### Step 4: Launch Claude Code from that folder
```bash
claude
```

Claude will automatically read your CLAUDE.md at session start. From now on, every conversation in this folder will have the procurement manager persona active.

---

## ✅ Option 2 — Global Setup
*Claude behaves as the procurement manager in ALL your projects, everywhere*

### Step 1: Go to your global Claude config folder
```bash
cd ~/.claude
```

### Step 2: Place CLAUDE.md there
```
~/.claude/
└── CLAUDE.md  ← your procurement skill goes here
```

This applies the persona to every Claude Code session, regardless of which folder you're working in.

---

## ✅ Option 3 — Subagent Setup (Advanced)
*Create a named agent you can call explicitly with `/agent procurement`*

### Step 1: Create the agents folder
```bash
mkdir -p .claude/agents
```

### Step 2: Create your agent file
```bash
touch .claude/agents/procurement.md
```

### Step 3: Paste this header + your CLAUDE.md content into the file:
```markdown
---
name: procurement
description: Senior Procurement Manager for spices, condiments, and infusions. Activates for supplier analysis, import operations, RFQs, landed cost calculations, and sourcing strategy.
---

[paste the full content of CLAUDE.md here]
```

### Step 4: Call the agent during a session
```
/agent procurement
```
Or launch directly:
```bash
claude --agent procurement
```

---

## 💡 Quick Tips

### Adding memory on the fly
During any session, use `#` to add a new instruction:
```
# Always calculate landed cost when evaluating a new supplier
```
Claude saves this to the relevant CLAUDE.md automatically.

### Refreshing context mid-session
If the conversation gets long and Claude starts losing focus on the role:
```
/compact
```
Or start fresh while keeping your CLAUDE.md config:
```
/clear
```

### Verifying your CLAUDE.md is loaded
At the start of a session, ask:
```
What is your role in this project?
```
Claude should respond describing itself as the Senior Procurement Manager.

---

## 📁 Recommended Folder Structure

```
procurement-assistant/
├── CLAUDE.md                          ← Claude's persistent persona & instructions
├── senior-procurement-manager-EN.md  ← Full skill reference (English)
├── compras-senior.md                  ← Full skill reference (Spanish, original)
└── .claude/
    ├── agents/
    │   └── procurement.md             ← Optional: named subagent
    └── commands/
        ├── rfq.md                     ← Optional: /rfq custom command
        ├── landed-cost.md             ← Optional: /landed-cost command
        └── supplier-review.md        ← Optional: /supplier-review command
```

---

## 🔗 Useful Links

- Claude Code Docs: https://docs.anthropic.com/en/docs/claude-code/overview
- Memory & CLAUDE.md: https://code.claude.com/docs/en/memory
- Custom Subagents: https://code.claude.com/docs/en/sub-agents
- Claude Code Best Practices: https://www.anthropic.com/engineering/claude-code-best-practices

---

*Files generated for Ana — Senior Procurement Manager Skill Implementation*
