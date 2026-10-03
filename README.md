# No Defaults

Agent skills that stop your AI coding agent from shipping the generic "AI website": the centered hero, three icon cards, indigo gradient, instant everything.

This repo holds the **free** piece, `craft-led-interfaces`, plus the source of the kit's sales page as a worked example.

## craft-led-interfaces (free, MIT)

The element-level craft layer for any UI. It makes the agent refuse each library default, design the loading, empty and error states, spend motion only where it helps, take its palette and type from the subject, and run an 11-point check before shipping. It is framework-agnostic and works as a skill or pasted in as a project rule.

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

[`studio-sites`](https://buy.polar.sh/polar_cl_bl1zVAS4nvNMnnjmEnAWmtNOuRUmObzJhKxqA1dj2t4) is the other half: a concept phase that makes the agent write five lines before any code, then a Lenis, GSAP and Three.js build from recipes checked against current versions. The kit also includes install guides for six agents and free 1.x updates. One-time payment, 14-day refund.

**[Get the kit](https://buy.polar.sh/polar_cl_bl1zVAS4nvNMnnjmEnAWmtNOuRUmObzJhKxqA1dj2t4)**

## About this repo

- `craft-led-interfaces/SKILL.md` is MIT licensed.
- `index.html` is the kit's sales page, built with the kit and left open as a worked example.
- The paid `studio-sites` skill and its reference files are not in this repo.

Support: solalabsapp@gmail.com. Made by SolaLabs (solalabs.co.za).
