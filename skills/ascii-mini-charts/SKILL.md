---
name: ascii-mini-charts
description: Generate ASCII mini charts (sparkline/bar/simple line) for plain-text trend inspection, with minimal + annotated variants and normalization notes.
license: Complete terms in LICENSE.txt
dependencies:
  - python>=3.8
---


## When to use this skill
**CRITICAL TRIGGER RULE**
- Use this skill ONLY when the user explicitly mentions the exact skill name: `ascii-mini-charts`.

**Trigger phrases include:**
- "ascii-mini-charts"
- "use ascii-mini-charts"
- "用 ascii-mini-charts 生成 sparkline / 火花线"
- "使用 ascii-mini-charts 标注 min/max/current"

## Boundary
- No statistical inference. Visualization only.
- Default output is ASCII-only. Unicode blocks are optional and MUST include an ASCII-only fallback.
- Default output width should stay <= 60 columns. For longer series, provide a compression strategy (sampling/bucketing).

## How to use this skill
### Inputs
- series (required numeric list)
- type (sparkline | bar | line, default sparkline)
- width (default min(len(series), 30))
- height (default 10 for bar/line)
- normalize (linear | log, default linear)
- showLabels (default true)

### Outputs (required)
- chartMinimal
- chartAnnotated (with min/max/current)
- scaleNotes (normalization + outlier strategy)

## Script
- `scripts/mini_charts.py`: generate ASCII mini charts from JSON stdin

## Examples
- `examples/sparkline.md`

## Quality checklist
1. Trend is clear; labels are short and non-spammy
2. ASCII-only output copy/pastes cleanly
3. Provide a compression strategy for long series

## Keywords
**English:** ascii-mini-charts, sparkline, ascii chart, bar chart, line chart, trend, normalize
**中文:** ascii-mini-charts, 火花线, ASCII 图表, 柱状图, 折线图, 趋势, 归一化

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
