---
name: ascii-image-to-ascii
description: Convert an image into ASCII art (readable + detail variants, width/charset controls, optional ANSI), for terminal previews and plain-text “image substitutes”.
license: Complete terms in LICENSE.txt
dependencies:
  - python>=3.8
  - pillow
---


## When to use this skill
**CRITICAL TRIGGER RULE**
- Use this skill ONLY when the user explicitly mentions the exact skill name: `ascii-image-to-ascii`.

**Trigger phrases include:**
- "ascii-image-to-ascii"
- "use ascii-image-to-ascii"
- "用 ascii-image-to-ascii 把图片转字符画"
- "使用 ascii-image-to-ascii 生成可读优先/细节优先两版"

## Boundary
- Default output is ASCII-only; ANSI coloring is optional.
- The bundled script is for local conversion/verification only. Do not fetch/upload images on the user’s behalf.
- Always give pre-processing advice (crop subject, raise contrast, simplify background) before generating the final ASCII art.

## How to use this skill
### Inputs
- imagePath (local path, required)
- width (default 100; common: 80/100/120)
- charset (default ` .:-=+*#%@`, from light to dark)
- mode (readable | detail; if outputting both, this can be ignored)
- background (light | dark | unknown, default unknown)
- colorMode (none | ansi256, default none)

### Outputs (required)
- asciiReadable: readable-first (less noise, clearer silhouette)
- asciiDetail: detail-first (more levels, richer texture)
- paramsGuide: recommended width/charset + pre-processing tips
- pitfalls: 3-5 common failure modes with fixes

### Steps
1. Pre-processing advice (required):
   - Crop the subject, remove irrelevant background
   - Increase contrast to reduce gradient noise
   - Target width usually 80–120 columns
2. Charset + mapping direction:
   - Space is the lightest, `@` is the darkest (or invert consistently)
3. Generate two variants:
   - readable: fewer levels (less noise)
   - detail: more levels (more texture)
4. Optional ANSI:
   - Use color only as a hint; keep the silhouette readable
   - Always provide a no-color fallback

## Script
- `scripts/image_to_ascii.py`
  - Requires Python + Pillow (`pip install pillow`)
  - Supports: readable/detail variants, optional `--ansi256`

## Examples
- `examples/readable-vs-detail.md`

## Quality checklist
1. Lines are consistent and `<= width`
2. The readable variant must preserve the main silhouette
3. No trailing spaces (copy/paste safe)

## Keywords
**English:** ascii-image-to-ascii, image to ascii, ascii art, terminal preview, charset, grayscale, dithering, ansi
**中文:** ascii-image-to-ascii, 图片转字符画, ASCII 字符画, 终端预览, 字符集, 灰度映射, 降噪, ANSI 彩色

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
