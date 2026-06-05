---
name: ascii-terminal-animation-pack
description: Plan and generate terminal ASCII animations/screensaver-style output (FPS, refresh rules, loop policy, low-flicker guidance), with a static poster frame and an optional local demo script.
license: Complete terms in LICENSE.txt
dependencies:
  - python>=3.8
---


## When to use this skill
**CRITICAL TRIGGER RULE**
- Use this skill ONLY when the user explicitly mentions the exact skill name: `ascii-terminal-animation-pack`.

**Trigger phrases include:**
- "ascii-terminal-animation-pack"
- "use ascii-terminal-animation-pack"
- "用 ascii-terminal-animation-pack 做终端动画"
- "使用 ascii-terminal-animation-pack 生成矩阵雨 demo"

## Boundary
- Animations must be explicitly triggered demos. Never default to animated output in normal logs.
- Must provide an ASCII-only static poster frame for README/tickets.
- Must provide disable guidance: skip animations for non-interactive / redirected output.

## How to use this skill
### Inputs
- theme (matrix | waves | custom, default matrix)
- width (default 80)
- height (default 24)
- fps (default 10)
- durationSeconds (default 3)
- loop (default false)
- colorMode (none | ansi256, default ansi256)

### Outputs (required)
- animationSpec (refresh rules, FPS, loop policy, disable conditions)
- staticPosterFrame (ASCII-only)
- safetyNotes (exit/disable guidance, avoid log spam)

## Script
- `scripts/matrix_demo.py`: best-effort matrix rain demo (short-run, TTY-only)

## Examples
- `examples/spec.md`
- `examples/poster.md`

## Quality checklist
1. Non-spam by default: short duration, easy exit, disabled for non-interactive output
2. Static frame is ASCII-only and copy/paste safe
3. Animated output should not mix with normal application logs (recommend separate command or stream)

## Keywords
**English:** ascii-terminal-animation-pack, terminal animation, ascii animation, matrix rain, demo, fps, non-interactive
**中文:** ascii-terminal-animation-pack, 终端动画, ASCII 动效, 矩阵雨, 演示, 帧率, 非交互禁用

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
