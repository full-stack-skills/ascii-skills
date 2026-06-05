<div align="center">

# ascii-skills

**Terminal ASCII art and visualization skills — banners, diagrams, charts, animations**

[![GitHub](https://img.shields.io/badge/github-full--statck--skills%2Fascii-skills-green.svg)](https://github.com/full-statck-skills/ascii-skills)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)
[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-兼容-purple.svg)](https://agentskills.io)

[English](./README.md) | 简体中文

[简介](#-简介) ·
[安装](#-安装) ·
[技能列表](#-技能列表) ·
[支持的智能体](#-支持的智能体) ·
[生态](#-生态)

</div>

---

## 📖 简介

**ASCII 艺术技能** 是一组 AI 编码智能体技能，属于 [Full Stack Skills](https://github.com/partme-ai/full-stack-skills) 生态，由 [PartMe.AI](https://github.com/partme-ai) 维护。

本包包含 **13 个技能**。每个技能是一个独立的 `SKILL.md` 文件，AI 智能体按需加载。

## 📦 安装

```bash
npx skills add full-statck-skills/ascii-skills
```

或按需安装特定技能：

```bash
npx skills add full-statck-skills/ascii-skills --skill <skill-name>
```

## 🎯 技能列表 (13)

| 技能 | 描述 |
|------|------|
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

## 🤖 支持的智能体

适用于 [Claude Code](https://code.claude.com)、[Codex](https://developers.openai.com/codex)、[Cursor](https://cursor.com)、[OpenCode](https://opencode.ai)、[Gemini CLI](https://geminicli.com)、[GitHub Copilot](https://github.com/features/copilot)、[Windsurf](https://codeium.com/windsurf) 及 [70+ 其他智能体](https://agentskills.io/clients)。

## 🌐 生态

| 资源 | 链接 |
|------|------|
| **Full Stack Skills** | [github.com/partme-ai/full-stack-skills](https://github.com/partme-ai/full-stack-skills) |
| **全部技能组** | [github.com/full-statck-skills](https://github.com/full-statck-skills) |
| **Agent Skills 规范** | [agentskills.io](https://agentskills.io) |
| **Skills CLI** | [github.com/vercel-labs/skills](https://github.com/vercel-labs/skills) |

## 📄 许可证

Apache 2.0 — 详见 [LICENSE](LICENSE)。
