---
name: ascii-text-art-library
description: Generate a reusable ASCII-only text template library (titles, dividers, notice boxes, slogans/CTA), with naming conventions and selection rules for consistent CLI/log/README output.
license: Complete terms in LICENSE.txt
dependencies:
  - python>=3.8
---


## When to use this skill
**CRITICAL TRIGGER RULE**
- Use this skill ONLY when the user explicitly mentions the exact skill name: `ascii-text-art-library`.

**Trigger phrases include:**
- "ascii-text-art-library"
- "use ascii-text-art-library"
- "用 ascii-text-art-library 生成 ASCII 模板库"
- "使用 ascii-text-art-library 输出提示框/分隔线/标题样式"

## Boundary
- Output templates + naming/selection rules only; do not modify repository files.
- ASCII-only by default to avoid ambiguous-width Unicode.
- Templates must be width-tunable (default 80 columns).

## How to use this skill
### Inputs
- width (default 80)
- language (zh | en, default zh)
- tone (serious | fun, default serious)
- categories (title/divider/info/warn/error/success/cta, default all)
- variantsPerCategory (default 2)

### Outputs (required)
- templates: grouped by category (>= 2 variants per category)
- namingRules: e.g. `TITLE_COMPACT_A`, `WARN_BOX_B`
- usageRules: selection guidance + anti-spam thresholds

## Script
- `scripts/generate_templates.py`: generate a baseline template set for a given width (local preview)

## Examples
- `examples/templates-80.md`

## Quality checklist
1. Stable alignment at 80 columns; no trailing spaces
2. Templates are semantically clear and not over-decorated
3. Notice boxes support multi-line content and remain readable

## Keywords
**English:** ascii-text-art-library, templates, ascii, divider, banner, notice box, warning, error, success, plain text
**中文:** ascii-text-art-library, 模板库, ASCII, 分隔线, 标题, 提示框, 警告, 错误, 成功, 纯文本

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
