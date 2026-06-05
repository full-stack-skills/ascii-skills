---
name: ascii-ansi-colorizer
description: Add an ANSI color layer to existing ASCII/plain-text output (gradient/rainbow/highlights) with alignment-safe rules and a required no-color fallback.
license: Complete terms in LICENSE.txt
dependencies:
  - python>=3.8
---


## When to use this skill
**CRITICAL TRIGGER RULE**
- Use this skill ONLY when the user explicitly mentions the exact skill name: `ascii-ansi-colorizer`.

**Trigger phrases include:**
- "ascii-ansi-colorizer"
- "use ascii-ansi-colorizer"
- "用 ascii-ansi-colorizer 给 ASCII 上色"
- "使用 ascii-ansi-colorizer 做 ANSI 渐变/彩虹"

## Boundary
- This skill only adds color to existing text. It does not generate the ASCII art itself (pair with `ascii-cli-logo-banner` if needed).
- Required outputs: `coloredText` + `plainTextFallback`.
- ANSI must not break alignment: do not colorize spaces by default; colorize visible characters only.

## How to use this skill
### Inputs
- textOrAscii (required)
- palette (rainbow | gradient | brandColors)
- direction (leftToRight | topToBottom, default leftToRight)
- colorDepth (ansi16 | ansi256 | truecolor, default ansi256)
- scope (logoOnly | highlightsOnly | fullText, default logoOnly)

### Outputs (required)
- coloredText: ANSI-colored output
- plainTextFallback: no-color fallback (identical content, no ANSI)
- compatNotes: copy/paste and redirection guidance (NO_COLOR / --no-color suggestions)

### Steps
1. Pick `colorDepth` (default: ansi256).
2. Choose a stable coloring strategy:
   - Column-wise gradients (leftToRight) are usually the safest
   - Colorize non-space characters only
3. Output both `coloredText` and `plainTextFallback`.
4. Provide no-color guidance (semantic suggestions): `NO_COLOR` / `--no-color`.

## Script
- `scripts/colorize.py`: apply ANSI 256 gradient or rainbow to stdin

## Examples
- `examples/gradient.md`

## Quality checklist
1. Removing ANSI keeps the same readable content (`plainTextFallback`).
2. Alignment does not change after coloring.
3. Colors should not overpower the informational lines.

## Keywords
**English:** ascii-ansi-colorizer, ansi, color, gradient, rainbow, terminal, no-color, plain text, ascii
**中文:** ascii-ansi-colorizer, ANSI, 上色, 渐变, 彩虹, 终端, 无色回退, 纯文本, ASCII

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
