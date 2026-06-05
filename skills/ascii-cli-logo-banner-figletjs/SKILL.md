---
name: ascii-cli-logo-banner-figletjs
description: Generate TAAG/FIGlet-style ASCII art banners using figlet.js (FIGfont spec), with layout controls (horizontal/vertical layout, width, whitespaceBreak) and optional ANSI 256 coloring.
license: Complete terms in LICENSE.txt
dependencies:
  - node>=18
  - npm
  - figlet (npm, powered by figlet.js)
---


## When to use this skill
**CRITICAL TRIGGER RULE**
- Use this skill ONLY when the user explicitly mentions the exact skill name: `ascii-cli-logo-banner-figletjs`.

**Trigger phrases include:**
- "ascii-cli-logo-banner-figletjs"
- "use ascii-cli-logo-banner-figletjs"
- "用 ascii-cli-logo-banner-figletjs 生成 TAAG/FIGlet 大字"
- "使用 ascii-cli-logo-banner-figletjs 调 horizontalLayout / verticalLayout"

## Boundary
- Output copy-pastable text and layout rules only. Do not modify project code.
- FIGlet/TAAG style is driven by FIGfont (.flf) rendering and layout “smushing/kerning” options.
- ANSI coloring is optional and MUST not break alignment (spaces are not colorized).
- Dependency note: `figlet` npm package is commonly used as the Node interface and is powered by `figlet.js`.

## How to use this skill
### Inputs (recommended)
- brand (required)
- width (default 80; if `< 60` use compact mode)
- font (default Standard)
- horizontalLayout (default | full | fitted | controlled smushing | universal smushing)
- verticalLayout (default | full | fitted | controlled smushing | universal smushing)
- whitespaceBreak (true|false, default true)
- slogan/hint (optional; centered lines under the logo)
- center (default true)
- rule (default true; set false for hero output)
- version/repo/docs/author (optional; only used when `rule=true`)
- colorMode (none | ansi256, default none; logo only)
- colorStart/colorEnd (0-255, defaults 33/129; only when `colorMode=ansi256`)

### Outputs (required)
- bannerPlain: banner text (no-color)
- coloredText: when `colorMode=ansi256`, provide colored logo output
- plainTextFallback: when colored, also provide a no-color fallback (same layout)

## Script
- `scripts/figlet_banner.mjs`

## Examples
- `examples/taag-figlet.md`
- `examples/color-ansi256.md`

## Quality checklist
1. Layout options are honored (horizontal/vertical layout)
2. 80-column output does not wrap; no trailing spaces
3. Color mode does not break alignment (spaces are not colorized)
4. Never prints secrets (tokens, internal URLs, personal data)

## Keywords
**English:** ascii-cli-logo-banner-figletjs, figlet, figlet.js, FIGfont, taag, ascii, banner, smushing, kerning, ansi256
**中文:** ascii-cli-logo-banner-figletjs, FIGlet 大字, TAAG, FIGfont 字体, 横向布局, 纵向布局, ANSI256 上色

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
