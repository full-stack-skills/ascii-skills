---
name: ascii-progress-and-spinner
description: Design ASCII progress bars and spinners for CLI UX (determinate/indeterminate, TTY single-line refresh, non-interactive log fallback) with copy-pastable style specs.
license: Complete terms in LICENSE.txt
dependencies:
  - python>=3.8
---


## When to use this skill
**CRITICAL TRIGGER RULE**
- Use this skill ONLY when the user explicitly mentions the exact skill name: `ascii-progress-and-spinner`.

**Trigger phrases include:**
- "ascii-progress-and-spinner"
- "use ascii-progress-and-spinner"
- "用 ascii-progress-and-spinner 生成 ASCII 进度条"
- "使用 ascii-progress-and-spinner 做 spinner / loading"

## Boundary
- Do not integrate a specific UI framework; output styles + refresh rules + fallback protocol + examples.
- Must cover:
  - determinate progress bars
  - indeterminate spinners
  - non-TTY / redirected-output fallback (log lines, no carriage-return updates)

## How to use this skill
### Inputs
- mode (determinate | indeterminate)
- width (default 40)
- showPercent (default true)
- showEta (optional)
- multiTask (optional)
- colorMode (none | ansi256, default none)

### Outputs (required)
- progressBarStyles (>= 3)
- spinnerStyles (>= 2)
- renderRules (TTY single-line refresh vs logLines)
- fallbackRules (non-interactive / redirected output)

### Recommended render rules
- **TTY (interactive):** single-line refresh (overwrite previous line), avoid log spam
- **Non-TTY (logs):** print log lines (no overwrite). Each line may include task name + percent.

## Script
- `scripts/demo.py`: local demo for progress bar + spinner shapes

## Examples
- `examples/styles.md`

## Quality checklist
1. Fixed width (percent field is fixed-width to avoid jitter)
2. Log mode is grep-friendly (no overwrite)
3. ASCII-only defaults are available (avoid ambiguous-width Unicode)

## Keywords
**English:** ascii-progress-and-spinner, progress bar, spinner, loading, tty, non-interactive, log output, ascii
**中文:** ascii-progress-and-spinner, 进度条, Spinner, Loading, 终端, TTY, 日志降级, ASCII

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
