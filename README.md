<div align="center">

# ascii-skills

**Terminal ASCII art and visualization skills — banners, diagrams, charts, animations**

[![GitHub](https://img.shields.io/badge/github-full--statck--skills%2Fascii-skills-green.svg)](https://github.com/full-statck-skills/ascii-skills)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)
[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-Compatible-purple.svg)](https://agentskills.io)

English | [简体中文](./README.zh-CN.md)

[Introduction](#-introduction) ·
[Install](#-install) ·
[Skills](#-skills) ·
[Supported Agents](#-supported-agents) ·
[Ecosystem](#-ecosystem)

</div>

---

## 📖 Introduction

**ASCII Art Skills** is a curated collection of Agent Skills for AI coding agents, part of the [Full Stack Skills](https://github.com/partme-ai/full-stack-skills) ecosystem maintained by [PartMe.AI](https://github.com/partme-ai).

This package includes **13 skills**. Each skill is a self-contained `SKILL.md` file that AI agents load on-demand.

## 📦 Install

```bash
npx skills add full-statck-skills/ascii-skills
```

Or install specific skills:

```bash
npx skills add full-statck-skills/ascii-skills --skill <skill-name>
```

## 🎯 Skills (13)

| Skill | Description |
|-------|-------------|
| `ascii-ansi-colorizer` | Add an ANSI color layer to existing ASCII/plain-text output (gradient/rainbow/highlights) with alignment-safe rules a... |
| `ascii-cli-logo-banner-figletjs` | Generate TAAG/FIGlet-style ASCII art banners using figlet.js (FIGfont spec), with layout controls (horizontal/vertica... |
| `ascii-cli-logo-banner-python` | Generate copy-pastable ASCII banners with a built-in font (no external font deps), including compact fallback and opt... |
| `ascii-cli-logo-banner` | Entry point for ASCII CLI banners. Choose the Python built-in font skill or the figlet.js/FIGfont skill depending on ... |
| `ascii-diagram-boxflow` | Generate plain ASCII box-flow diagrams (boxes + arrows) for environments without renderers, with alignment rules and ... |
| `ascii-image-to-ascii` | Convert an image into ASCII art (readable + detail variants, width/charset controls, optional ANSI), for terminal pre... |
| `ascii-mini-charts` | Generate ASCII mini charts (sparkline/bar/simple line) for plain-text trend inspection, with minimal + annotated vari... |
| `ascii-motd-profile-banner` | Generate ASCII-only MOTD / SSH login banner / shell profile welcome messages (short/long variants, quiet mode guidanc... |
| `ascii-progress-and-spinner` | Design ASCII progress bars and spinners for CLI UX (determinate/indeterminate, TTY single-line refresh, non-interacti... |
| `ascii-table-renderer` | Render structured data as aligned ASCII tables (column width rules, truncate/wrap, border styles, compact/readable va... |
| `ascii-terminal-animation-pack` | Plan and generate terminal ASCII animations/screensaver-style output (FPS, refresh rules, loop policy, low-flicker gu... |
| `ascii-text-art-library` | Generate a reusable ASCII-only text template library (titles, dividers, notice boxes, slogans/CTA), with naming conve... |
| `cli-ascii-logo` | 生成 CLI 的 ASCII 艺术 Logo/Banner（支持 box drawing 边框、█ 块字符、ANSI 24-bit 渐变色）并提供可运行脚本与集成代码。适用于“做一个像 Spec Kit CLI 的终端 Logo / ... |

## 🤖 Supported Agents

Works with [Claude Code](https://code.claude.com), [Codex](https://developers.openai.com/codex), [Cursor](https://cursor.com), [OpenCode](https://opencode.ai), [Gemini CLI](https://geminicli.com), [GitHub Copilot](https://github.com/features/copilot), [Windsurf](https://codeium.com/windsurf), and [70+ others](https://agentskills.io/clients).

### Claude Code Installation

**Option 1: npx skills CLI (Recommended)**

```bash
npx skills add full-statck-skills/ascii-skills
```

**Option 2: Manual Installation**

```bash
git clone https://github.com/full-statck-skills/ascii-skills.git
cp -r ascii-skills/skills/* .claude/skills/
```

For more details, see the [Claude Code Skills Guide](https://code.claude.com/docs/en/skills) and [Agent Skills Spec](https://agentskills.io/).

## 🌐 Ecosystem

| Resource | Link |
|----------|------|
| **Full Stack Skills** | [github.com/partme-ai/full-stack-skills](https://github.com/partme-ai/full-stack-skills) |
| **All Skill Groups** | [github.com/full-statck-skills](https://github.com/full-statck-skills) |
| **Agent Skills Spec** | [agentskills.io](https://agentskills.io) |
| **Skills CLI** | [github.com/vercel-labs/skills](https://github.com/vercel-labs/skills) |

## 📄 License

Apache 2.0 — see [LICENSE](LICENSE).
