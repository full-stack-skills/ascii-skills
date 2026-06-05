---
name: ascii-cli-logo-banner-python
description: Generate copy-pastable ASCII banners with a built-in font (no external font deps), including compact fallback and optional ANSI 256 coloring for the logo.
license: Complete terms in LICENSE.txt
dependencies:
  - python>=3.8
---


## When to use this skill
**CRITICAL TRIGGER RULE**
- Use this skill ONLY when the user explicitly mentions the exact skill name: `ascii-cli-logo-banner-python`.

**Trigger phrases include:**
- "ascii-cli-logo-banner-python"
- "use ascii-cli-logo-banner-python"
- "用 ascii-cli-logo-banner-python 生成启动 Banner"
- "使用 ascii-cli-logo-banner-python 输出 ASCII Logo + slogan（居中）"

## Boundary
- Output copy-pastable text and layout rules only. Do not modify project code.
- Default output is width-safe and copy/paste safe (no trailing spaces).
- ANSI coloring is optional and MUST be applied to visible characters only (spaces are not colorized).
- This skill uses a built-in 5x5 font. It is not a full FIGlet engine.

## How to use this skill
### Inputs (recommended)
- brand (required)
- width (default 80; if `< 60` use compact mode)
- slogan (optional; centered line under the logo)
- hint (optional; centered line under the slogan)
- glyph (ascii | block, default ascii)
- center (default true)
- rule (default true; set false for hero output)
- version/repo/docs/author (optional; only used when `rule=true`)
- colorMode (none | ansi256, default none; logo only)
- colorStart/colorEnd (0-255, defaults 33/129; only when `colorMode=ansi256`)

### Outputs (required)
- bannerPlain: banner text (ASCII-only when colorMode=none)
- compactPlain: compact banner when width < 60
- plainTextFallback: if colorMode is enabled, also provide a no-color fallback (same layout)

## Script
- `scripts/generate_banner.py`

## Examples
- `examples/banner-80.md`
- `examples/banner-compact.md`
- `examples/banner-slogan-centered.md`
- `examples/color-ansi256.md`

## Quality checklist
1. 80-column output does not wrap; no trailing spaces
2. Width < 60 uses compact mode
3. Color mode does not break alignment (spaces are not colorized)
4. Never prints secrets (tokens, internal URLs, personal data)

## Keywords
**English:** ascii-cli-logo-banner-python, ascii, banner, logo, cli, terminal, startup, slogan, ansi256
**中文:** ascii-cli-logo-banner-python, ASCII 启动横幅, 终端 Banner, 居中标语, ANSI256 上色

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
