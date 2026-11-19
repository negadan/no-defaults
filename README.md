# No Defaults

Agent skills that stop your AI coding agent from shipping the generic "AI website": the centered hero, three icon cards, indigo gradient, instant everything.

This repo holds the **free** piece, `craft-led-interfaces`, plus the source of the kit's sales page as a worked example.

## craft-led-interfaces (free, MIT)

The element-level craft layer for any UI. It makes the agent refuse each library default, design the loading, empty and error states, spend motion only where it helps, take its palette and type from the subject, and run a 15-point check before shipping. It is framework-agnostic and works as a skill or pasted in as a project rule.

### Install

Copy the `craft-led-interfaces` folder into your agent's skills folder:

| Agent | All projects | One project |
|---|---|---|
| Claude Code | `~/.claude/skills/` | `.claude/skills/` |
| Cursor | `~/.cursor/skills/` | `.cursor/skills/` |
| OpenAI Codex | `~/.agents/skills/` | `.agents/skills/` |
| GitHub Copilot (VS Code) | `~/.copilot/skills/` | `.github/skills/` |
| Gemini CLI | `~/.gemini/skills/` | `.gemini/skills/` |

```bash
mkdir -p ~/.claude/skills && cp -R craft-led-interfaces ~/.claude/skills/
```

Restart the agent, then ask for a site or interface as usual. For other tools, paste the body of `SKILL.md` into a project rule.

## The full kit ($19)

[`studio-sites`](https://solalabs.co.za/no-defaults/) is the other half: the agent first researches how the subject's work is really done, writes a five-line concept before any code, builds the page from the subject's own objects, then adds the lightest motion that carries the concept. See two demo sites an agent built from one-line prompts at https://solalabs.co.za/no-defaults/#demos. Native CSS scroll animations come first, with Lenis, GSAP and Three.js only where they earn their weight, all from recipes checked against current versions. The kit also includes install guides for six agents and free 1.x updates. One-time payment, 14-day refund.

**[Get the kit for $19](https://buy.polar.sh/polar_cl_bl1zVAS4nvNMnnjmEnAWmtNOuRUmObzJhKxqA1dj2t4)** · in South Africa, [pay R349 with PayFast](https://solalabs.co.za/no-defaults/buy) · [about the kit](https://solalabs.co.za/no-defaults/)

## About this repo

- `craft-led-interfaces/SKILL.md` is MIT licensed.
- `index.html` is the source of the kit's sales page ([live here](https://solalabs.co.za/no-defaults/)), built with the kit and left open as a worked example.
- The paid `studio-sites` skill and its reference files are not in this repo.

Support: solalabsapp@gmail.com. Made by SolaLabs (solalabs.co.za).
