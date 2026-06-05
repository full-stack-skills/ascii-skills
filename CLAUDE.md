# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

Skill-only package — no build, test, or lint commands. 13 ASCII art/visualization Agent Skills distributed via `npx skills`. Each skill is self-contained under `skills/` with `SKILL.md` and optional `scripts/`, `examples/`, `references/` subdirectories.

Part of the [Full Stack Skills](https://github.com/partme-ai/full-stack-skills) ecosystem maintained by PartMe.AI.

## Skill Listing (13)

| Skill | Script | Summary |
|-------|--------|---------|
| `ascii-ansi-colorizer` | `colorize.py` | Add ANSI color to existing ASCII output (gradient/rainbow) |
| `ascii-cli-logo-banner` | — | Entry point; routes to Python or figlet.js banner skill |
| `ascii-cli-logo-banner-figletjs` | `figlet_banner.mjs` | FIGlet-style banners via figlet.js (Node.js) |
| `ascii-cli-logo-banner-python` | `generate_banner.py` | Banners via built-in font (stdlib-only Python) |
| `ascii-diagram-boxflow` | `boxflow.py` | Box-flow diagrams (boxes + arrows) for plain-text rendering |
| `ascii-image-to-ascii` | `image_to_ascii.py` | Convert images to ASCII art (readable + detail variants) |
| `ascii-mini-charts` | `mini_charts.py` | Sparkline / bar / simple line charts for trend inspection |
| `ascii-motd-profile-banner` | — | MOTD / SSH login banner / shell profile welcome messages |
| `ascii-progress-and-spinner` | `demo.py` | Progress bars and spinners for CLI UX |
| `ascii-table-renderer` | `render_table.py` | Render structured data as aligned ASCII tables |
| `ascii-terminal-animation-pack` | `matrix_demo.py` | Terminal animations / screensaver-style output |
| `ascii-text-art-library` | `generate_templates.py` | Reusable ASCII text templates (titles, dividers, boxes) |
| `cli-ascii-logo` | `generate_logo.py` | CLI ASCII art logo/banner (box drawing, 24-bit ANSI gradient) |

## Directory Structure

```
skills/{skill-name}/       # kebab-case, matches SKILL.md frontmatter `name`
  SKILL.md                 # Required: YAML frontmatter + markdown body
  LICENSE.txt              # Required: Apache 2.0
  scripts/                 # Optional
  examples/                # Optional
  references/              # Optional
```

## SKILL.md Frontmatter

```yaml
---
name: {skill-name}              # kebab-case, matches directory name
description: {one sentence}     # Include trigger phrases agents use to activate
license: Complete terms in LICENSE.txt
dependencies:                   # Optional, only when scripts need a runtime
  - python>=3.8                 #   Python skills (stdlib — no pip packages)
  - node>=18                    #   Node.js skills
---
```

## Script Languages

- **Python** (10 scripts): `python>=3.8`, stdlib only — no pip packages
- **Node.js** (1 script): `node>=18`, `figlet_banner.mjs` in `ascii-cli-logo-banner-figletjs`
- **No bash scripts** exist despite the generic AGENTS.md template

## Plugin Discovery

`.claude-plugin/plugin.json` lists every skill path for Claude Code discovery. When adding or removing a skill, update the `skills` array there.

## Skill Metadata Sync Points

When adding or renaming a skill, update ALL of these:
1. `skills/{skill-name}/SKILL.md`
2. `.claude-plugin/plugin.json` — `skills[]` array
3. `README.md` — skill table (English)
4. `README.zh-CN.md` — skill table (Chinese)

## Bilingual Convention

User-facing documents have English + 简体中文 versions:
- `README.md` / `README.zh-CN.md`
- `AGENTS.md` (ZH) / `AGENTS_EN.md` (EN)

## Distribution

```bash
npx skills add full-statck-skills/ascii-skills
```

Flat source distribution — no zip packaging needed.
