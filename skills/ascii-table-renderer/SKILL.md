---
name: ascii-table-renderer
description: Render structured data as aligned ASCII tables (column width rules, truncate/wrap, border styles, compact/readable variants) for terminal/log/email.
license: Complete terms in LICENSE.txt
dependencies:
  - python>=3.8
---


## When to use this skill
**CRITICAL TRIGGER RULE**
- Use this skill ONLY when the user explicitly mentions the exact skill name: `ascii-table-renderer`.

**Trigger phrases include:**
- "ascii-table-renderer"
- "use ascii-table-renderer"
- "用 ascii-table-renderer 把列表打印成表格"
- "使用 ascii-table-renderer 生成 ASCII 表格（对齐/列宽）"

## Boundary
- Do not fetch data (DB/API). Only render and format output.
- Default borders are ASCII-only: `+ - |`.
- Out of scope: merged cells, multi-row headers, complex spanning layouts.

## How to use this skill
### Inputs
- headers (required)
- rows (required)
- maxWidth (default 80)
- maxColWidth (default 20)
- borderStyle (light | minimal, default light)
- overflow (ellipsis | wrap, default ellipsis)
- align (left | right | center, default left)

### Outputs (required)
- tableCompact (log-friendly)
- tableReadable (interactive-friendly)
- rules (width/truncation/null/alignment rules)

### Steps
1. Compute per-column widths: `min(maxColWidth, max(contentWidth))`
2. Handle overflow:
   - ellipsis: use `...` consistently
   - wrap: wrap within column width while keeping row alignment
3. Output two variants:
   - compact: minimal or fewer separators
   - readable: clearer borders

## Script
- `scripts/render_table.py`: render tables from JSON stdin (compact/readable)

## Examples
- `examples/basic.md`

## Quality checklist
1. Columns align consistently; each line does not exceed maxWidth
2. Null values are rendered as `-`
3. Copy/paste safe (no trailing spaces)

## Keywords
**English:** ascii-table-renderer, ascii table, align, columns, rows, truncate, wrap, terminal, log
**中文:** ascii-table-renderer, ASCII 表格, 对齐, 列宽, 截断, 换行, 终端, 日志, 工单

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
