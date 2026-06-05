---
name: ascii-cli-logo-banner
description: Entry point for ASCII CLI banners. Choose the Python built-in font skill or the figlet.js/FIGfont skill depending on needs.
license: Complete terms in LICENSE.txt
---


## When to use this skill
**CRITICAL TRIGGER RULE**
- Use this skill ONLY when the user explicitly mentions the exact skill name: `ascii-cli-logo-banner`.

**Use this skill when the user says they want:**
- A startup banner / logo / welcome screen for a CLI or service

**Trigger phrases include:**
- "ascii-cli-logo-banner"
- "use ascii-cli-logo-banner"
- "用 ascii-cli-logo-banner"
- "使用 ascii-cli-logo-banner 生成启动 Banner"
- "用 ascii-cli-logo-banner 做一个 ASCII Logo"

## Boundary
- This skill is a routing/selection entry point. It does not provide its own generator implementation.
- For built-in (no external font engine): use `ascii-cli-logo-banner-python`.
- For TAAG/FIGlet style (FIGfont spec, smushing layouts): use `ascii-cli-logo-banner-figletjs`.

## How to use this skill
### Inputs (recommended)
- brandName (required)
- version (optional)
- author (optional)
- repoUrl / docsUrl (optional)
- width (default 80)
- slogan (optional, centered line under the logo)
- hint (optional, centered line under the slogan)
- glyph (ascii | block, default ascii)
- center (default true)
- rule (default true; set false for logo-only hero output)
- style (block | outline | thin, default block)
- colorMode (none | ansi256, default none; logo only in scripts)
- includeCta (default true)

### Outputs (required)
- bannerPlain: ASCII-only full banner (logo area + info block + horizontal rule)
- compactPlain: compact banner for `width < 60` (single-line title + rule + 1-2 info lines)
- plainTextFallback: no-color fallback when ANSI is enabled (same structure as bannerPlain)
- embedNotes: 3-5 embedding notes (CLI start / service start / README / tickets)

### Steps
1. Decide width and fallback:
   - Default `width=80`
   - If `width < 60`, output `compactPlain` and skip the big-letter logo
2. Generate an ASCII-only logo:
   - Avoid full-width characters and ambiguous-width Unicode
   - Ensure each line is `<= width`
3. Compose the banner structure (recommended order):
   - Logo area (or a single-line title in compact mode)
   - Horizontal rule: exactly `width` characters (`-` or `=`)
   - Info block: Name / Version / Repo / Docs / Author (only include fields provided)
   - Optional CTA: e.g. `Run: <command>` or `Docs: <url>`
4. Optional ANSI coloring (must not break alignment):
   - Colorize visible characters only; do not colorize spaces
   - Always provide `plainTextFallback`

## Script (optional)
- Use `ascii-cli-logo-banner-python` for the Python implementation.
- Use `ascii-cli-logo-banner-figletjs` for the figlet.js/FIGfont implementation.

## Examples
- See examples in the two implementation skills:
  - `ascii-cli-logo-banner-python/examples/*`
  - `ascii-cli-logo-banner-figletjs/examples/*`

## Quality checklist
1. Does not wrap or misalign at 80 columns; no trailing spaces
2. Copy-pastes cleanly into logs/email/tickets
3. Never prints secrets (tokens, internal URLs, personal data)

## Keywords
**English:** ascii, banner, logo, cli, terminal, startup, welcome, plain text, ansi, no-color
**中文:** ASCII, 启动横幅, 终端 Banner, CLI Logo, 欢迎页, 纯文本, ANSI 上色, 无色回退

## 常见陷阱 (Gotchas)

1. **版本兼容性**：注意框架版本与依赖库的兼容性，不同版本 API 可能有差异
2. **配置文件格式**：配置文件格式错误是最常见的问题，建议使用编辑器的语法检查
3. **环境变量**：确保所有必要的环境变量已正确设置，敏感信息不要硬编码
4. **依赖冲突**：多版本共存时注意依赖冲突，使用 lock 文件锁定版本
5. **性能陷阱**：大数据量场景下注意性能优化，避免 N+1 查询等常见问题

## 使用流程

### Step 1: 环境准备
确保开发环境已安装必要的依赖和工具。

### Step 2: 配置初始化
根据项目需求进行基础配置。

### Step 3: 核心功能使用
按照示例代码实现核心功能。

### Step 4: 测试验证
运行测试确保功能正常。

### Step 5: 部署上线
完成开发后进行部署和监控。
