# clay-mate-interview

Shape your AI teammate through conversation. A deep interview skill for [Clay](https://github.com/chadbyte/clay)'s Mates system.

When you create a Mate in Clay, this skill runs the identity interview. The Mate asks questions, learns how you work, and builds its own personality file (CLAUDE.md) through natural conversation.

## Prerequisites

- [Clay](https://github.com/chadbyte/clay) must be installed and running. Mates is a Clay feature. This skill is used by Clay to conduct the Mate identity interview.

## Install

```bash
npx skills add chadbyte/clay-mate-interview
```

## What it does

When a new Mate is created (or an existing one is reshaped), the skill:

1. **Reads seed data** from the creation wizard (relationship, activity, communication style, autonomy)
2. **Conducts a conversation** where the Mate asks questions to understand you
3. **Adapts in real-time** by reflecting back what it learns ("Got it, you'd rather I suggest than fix directly")
4. **Lets you control the depth** with soft checkpoints ("More to say, or should I wrap up?")
5. **Generates CLAUDE.md** as the Mate's identity file, written in first person

## How it works

```
┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│   Creation   │────▶│     Deep     │────▶│   CLAUDE.md  │
│   Wizard     │     │  Interview   │     │  generated   │
│  (seed data) │     │  (this skill)│     │  (identity)  │
└──────────────┘     └──────────────┘     └──────────────┘

Wizard: click-based, collects relationship + activity + style + autonomy
Interview: free-form conversation, Mate asks questions as itself
Output: .claude/mates/[name]/CLAUDE.md
```

- The Mate speaks as itself, not as a facilitator
- No rigid phases. Conversation flows naturally across topics
- Soft checkpoints every few exchanges. User decides when to stop
- Quick users finish in 2-3 minutes. Thorough users can go 30+ minutes
- Can be re-run anytime to reshape a Mate

## Usage

Automatically triggered when creating a Mate in Clay's UI. Can also be invoked manually:

```
/clay-mate-interview
```

## License

MIT
