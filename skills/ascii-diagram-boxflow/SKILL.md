---
name: ascii-diagram-boxflow
description: Generate plain ASCII box-flow diagrams (boxes + arrows) for environments without renderers, with alignment rules and split strategies for complex graphs.
license: Complete terms in LICENSE.txt
dependencies:
  - python>=3.8
---


## When to use this skill
**CRITICAL TRIGGER RULE**
- Use this skill ONLY when the user explicitly mentions the exact skill name: `ascii-diagram-boxflow`.

**Trigger phrases include:**
- "ascii-diagram-boxflow"
- "use ascii-diagram-boxflow"
- "用 ascii-diagram-boxflow 画 ASCII 流程图/框图"
- "使用 ascii-diagram-boxflow 生成 box + 箭头连接图"

## Boundary
- ASCII output only. Do not output Mermaid/PlantUML.
- Recommended nodes <= 12; if larger, split into sub-diagrams.
- Auto-layout is best-effort for linear and simple branching. Complex layouts require manual ordering or splitting.

## How to use this skill
### Inputs
- nodes (node list; names required)
- edges (connections: from/to)
- direction (TB | LR, default TB)
- width (default 80)
- boxWidth (default 16)
- numbering (default false)

### Outputs (required)
- diagram (ASCII-only)
- layoutRules (box width + arrow/line rules)
- splitAdvice (how to split complex diagrams)

## Script
- `scripts/boxflow.py`: best-effort for linear flows and single 2-way branching

## Examples
- `examples/login-flow.md`

## Quality checklist
1. Arrow direction is unambiguous; avoid crossings
2. Line width `<= width`; no trailing spaces
3. Long node names must be truncated or wrapped consistently

## Keywords
**English:** ascii-diagram-boxflow, ascii diagram, flowchart, box, arrow, plain text, terminal
**中文:** ascii-diagram-boxflow, ASCII 框图, 流程图, 纯文本, 盒子, 箭头, 终端

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
