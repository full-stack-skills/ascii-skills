---
name: ascii-motd-profile-banner
description: Generate ASCII-only MOTD / SSH login banner / shell profile welcome messages (short/long variants, quiet mode guidance, security notices).
license: Complete terms in LICENSE.txt
---


## When to use this skill
**CRITICAL TRIGGER RULE**
- Use this skill ONLY when the user explicitly mentions the exact skill name: `ascii-motd-profile-banner`.

**Trigger phrases include:**
- "ascii-motd-profile-banner"
- "use ascii-motd-profile-banner"
- "用 ascii-motd-profile-banner 生成 SSH 登录欢迎"
- "使用 ascii-motd-profile-banner 输出 MOTD（短版/长版）"

## Boundary
- Produce templates and placement guidance only; do not modify system files.
- Never include sensitive information (tokens, internal URLs, account details, personal data).
- Default output is ASCII-only; ANSI color is optional and must have a no-color fallback.

## How to use this skill
### Inputs
- title (required)
- messageBullets (1–5 bullet points, required)
- mode (short | long, default short)
- width (default 80)
- includeLinks (optional: Docs / Tickets / Repo)
- colorMode (none | ansi256, default none)
- quietHint (default true: recommend quiet output for non-interactive shells)

### Outputs (required)
- bannerShort (<= 12 lines)
- bannerLong (<= 30 lines)
- safetyNotes (>= 3 actionable security notes)
- toggleAdvice (interactive vs non-interactive display guidance)

## Examples
- `examples/ssh-short.md`
- `examples/ssh-long.md`

## Quality checklist
1. Short mode does not spam (<= 12 lines)
2. Copy/paste safe (no trailing spaces)
3. Security notes are clear, short, and actionable

## Keywords
**English:** ascii-motd-profile-banner, motd, ssh banner, profile, welcome message, security notice, terminal
**中文:** ascii-motd-profile-banner, MOTD, SSH Banner, 登录欢迎, Profile, 安全提示, 终端

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
