# devpace

> Control how much AI helps you code — so you stay sharp while still moving fast.

---

## The Problem

AI coding tools are powerful. But there's a quiet side effect: the more AI codes for you, the less you actually think. You stop catching bugs in review. You approve code you didn't write and barely read. Your instincts dull.

This isn't a hypothetical. It's already happening.

**devpace** is a set of copy-paste instruction templates for AI agents (Claude, Cursor, Copilot, ChatGPT). You set an **agility level** (0–3) in the file. The AI respects it. You stay in control of how much you depend on it.

---

## How to Use

1. Copy the right file for your AI tool into your project root:
   - Claude Code / Claude API → copy `CLAUDE.md`
   - Cursor → copy `.cursorrules`
   - ChatGPT / Copilot Chat / others → copy `AGENTS.md`

2. Set your agility level at the top of the file:
   ```
   AGILITY = 1
   ```

3. (Optional) Set your override keyword — a private word that lets you bypass the level when you consciously choose to:
   ```
   OVERRIDE_KEYWORD = YOURWORD
   ```

4. That's it. The AI will read it and adjust its behavior.

---

## Agility Levels

| Level | Name | What the AI can do |
|---|---|---|
| `0` | **Guardian** | Consulting only. Explains concepts, discusses approaches, points to docs. No code, no tests, nothing written for you. |
| `1` | **Reviewer** | Adds unit tests for code you wrote. Reviews your code and flags issues. Still writes nothing new. |
| `2` | **Collaborator** | Simple, isolated utility functions (short, no critical logic). Autocomplete suggestions for repetitive patterns. No business logic, no multi-component code, no architectural decisions. |
| `3` | **Partner** | Full code generation. Vibe coding. No restrictions. Use when you're on a deadline or consciously choosing speed over practice. |

**Default:** If no `AGILITY` is set, the AI defaults to level `0`.

---

## Override Mechanisms

### `OVERRIDE_KEYWORD` — permanent personal bypass
Set a private word (e.g. `HESOIAM`) in the config. Including it anywhere in your message unlocks full generation for that request, regardless of agility level. This is your conscious "I know what I'm doing, just do it" escape hatch.

### `VAMOS` — one-shot override
Type `VAMOS` in any message to unlock full generation for that single message only. The level resets to your configured value afterward. No config needed.

---

## Why Not Just Use the AI Freely?

Because the skill erosion is subtle. You don't notice it on day one. You notice it six months later when you're staring at a bug you would have caught instantly before — but your eye is no longer trained.

The point of devpace isn't to be anti-AI. It's to be intentional. You decide the level. You can change it anytime. The tool just makes sure you've made a conscious choice.

---

## Compatible Tools

| File | Works with |
|---|---|
| `CLAUDE.md` | Claude Code CLI, Claude API (system prompt), Claude.ai projects |
| `.cursorrules` | Cursor IDE |
| `AGENTS.md` | ChatGPT custom instructions, GitHub Copilot Chat, any agent that reads a context file |

---

## Contributing

This is a living spec. If you find a better way to phrase a level, or a new tool needs its own template, open a PR.

---

## Inspiration

- ["AI Isn't Replacing Developers. It's Doing Something Worse"](https://levelup.gitconnected.com/ai-isnt-replacing-developers-it-s-doing-something-worse-2d18fb595362) — the quiet problem this project addresses
