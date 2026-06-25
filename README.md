# Project Report Builder / 项目汇报文档生成器

[![Gitleaks Secret Scan](https://github.com/Gavin8233841/Project-report-builder-skill/actions/workflows/gitleaks.yml/badge.svg)](https://github.com/Gavin8233841/Project-report-builder-skill/actions/workflows/gitleaks.yml)
[![OpenSSF Scorecard](https://api.securityscorecards.dev/projects/github.com/Gavin8233841/Project-report-builder-skill/badge)](https://securityscorecards.dev/viewer/?uri=github.com/Gavin8233841/Project-report-builder-skill)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## English

**Project Report Builder** is a skill for turning vibe-coded software, rapid prototypes, demos, coursework, hackathon projects, app contest entries, portfolio pieces, and early products into professional project reports.

It helps developers turn working software into a first draft that judges, teachers, investors, teammates, or users can understand: evidence-backed writing, screenshot selection, scoring or audience mapping, layout direction, PDF export QA, and privacy review.

### What It Builds

- Project or product explanation documents
- Competition or coursework submissions
- Screenshot-rich product reports
- Technical implementation summaries
- Portfolio or open-source project briefs
- HTML/DOCX/PPTX source documents plus PDF-ready output plans
- Requirements or scoring mapping notes
- Asset manifests for screenshots and diagrams

### Supported Project Types

- iOS, HarmonyOS, Android, Web, Mini Program, desktop, and multi-platform apps
- Backend services, APIs, dashboards, and admin tools
- AI agents, model-powered workflows, automation tools, and demos
- Hackathon, app contest, classroom, portfolio, and investor review projects

### Not A Fit For

- Fabricating features, metrics, test results, compliance claims, or user traction
- Publishing private user data, screenshots, logs, keys, or unreleased business material
- Replacing legal, medical, financial, security, or compliance review
- Writing reports without any project evidence to inspect

### Platform Compatibility

This skill is **not limited to a single platform**. The core logic lives in `SKILL.md` (YAML frontmatter + Markdown), which is a plain-text instruction file with no executable code, no dependencies, and no runtime requirements:

| Platform | Support Level | Notes |
|---|---|---|
| **WorkBuddy / Codex** | ✅ Full support | `agents/openai.yaml` provided — supports implicit invocation & default prompt routing |
| **Claude Code** | ⚙️ Manual | Copy `SKILL.md` into `CLAUDE.md` or custom instructions |
| **Cursor** | ⚙️ Manual | Copy `SKILL.md` into `.cursorrules` |
| **Continue.dev / Cline** | ⚙️ Manual | Reference `SKILL.md` as skill instruction file |
| **ChatGPT / Claude / Gemini** | ⚡ Paste & use | Paste `SKILL.md` contents directly into chat |

> 💡 **Tip**: You can paste the contents of `SKILL.md` directly into any LLM chat session and it will follow the same workflow.

### Installation

Clone this repository:

```bash
git clone https://github.com/Gavin8233841/Project-report-builder-skill.git
```

**WorkBuddy / Codex:**

```bash
mkdir -p ~/.codex/skills/project-report-builder
cp -R Project-report-builder-skill/SKILL.md Project-report-builder-skill/agents Project-report-builder-skill/references ~/.codex/skills/project-report-builder/
```

**Other AI assistants (Claude Code, Cursor, etc.):**

Copy the contents of `SKILL.md` into your assistant's custom instructions file (e.g. `.cursorrules` for Cursor, `CLAUDE.md` for Claude Code). Place the `references/` folder alongside the instruction file.

### Usage

In WorkBuddy or Codex, ask:

```
Use $project-report-builder to turn this software project or prototype into a polished project report with evidence, screenshots, privacy review, and PDF-ready structure.
```

In other AI assistants, include the contents of `SKILL.md` as part of your system prompt or custom instructions, then describe your reporting task in plain language.

Good inputs include:

- Official template, rubric, scoring rules, or submission limits
- Existing draft text or notes
- README, architecture docs, logs, test output, or release notes
- Sanitized screenshots or demo video frames
- Product positioning, target audience, and preferred output format

The skill should first inventory evidence, identify sensitive material, map claims to proof, then draft and package the report.

### Privacy And Safety

Project reports often include screenshots, logs, configs, student/team details, business plans, medical or financial demo data, and API integrations. This skill is designed to be privacy-first:

- 🔒 Redact secrets and personal data before quoting, exporting, or publishing
- 🎭 Use synthetic demo data when real records appear in screenshots
- 📦 Do not copy private project assets into public examples or reusable skill repositories
- ⚠️ Avoid unsupported claims about compliance, diagnosis, treatment, investment advice, legal advice, security certification, privacy guarantees, or production readiness
- ✅ Verify external rules, deadlines, prices, APIs, or laws from primary or user-provided sources when they affect the report

### Security Review

This skill was reviewed before its initial public release. The review covered:

- **All skill files**: `SKILL.md`, `agents/openai.yaml`, `references/report-workflow.md`, `references/layout-and-export-qa.md`
- **Repository metadata**: `README.md`, `SECURITY.md`, `LICENSE`

| Category | Check | Result |
|---|---|---|
| Hardcoded secrets | No API keys, tokens, passwords, certificates, or private endpoints found | ✅ Pass |
| Personal data | No real names, phone numbers, email addresses, account IDs, or student IDs found | ✅ Pass |
| Private assets | No private screenshots, logs, or competition materials embedded | ✅ Pass |
| Agent instruction safety | Explicit boundaries against fabricating data, publishing private assets, overclaiming compliance/security | ✅ Pass |
| Implicit invocation | `allow_implicit_invocation: true` — document-building skill, no destructive capabilities | ✅ Safe |
| External calls | Skill does not instruct agents to make network requests, call external APIs, or access system resources | ✅ Safe |

**Result: no blocking issues found. Safe to publish.**

The review was performed using AI-assisted audit prior to the initial commit. For methodology, see [SECURITY.md](SECURITY.md).

### Automated Verification

Two GitHub Actions workflows enforce ongoing security hygiene:

| Workflow | Trigger | Purpose | Status |
|---|---|---|---|
| [**Gitleaks**](https://github.com/gitleaks/gitleaks) | Every push & PR | Scans all commits for hardcoded secrets (API keys, tokens, passwords, private keys) | [![Status](https://github.com/Gavin8233841/Project-report-builder-skill/actions/workflows/gitleaks.yml/badge.svg)](https://github.com/Gavin8233841/Project-report-builder-skill/actions/workflows/gitleaks.yml) |
| [**OpenSSF Scorecard**](https://github.com/ossf/scorecard) | Weekly + push to main | Evaluates repo against OpenSSF best-practices checklist, publishes public score badge | [![Scorecard](https://api.securityscorecards.dev/projects/github.com/Gavin8233841/Project-report-builder-skill/badge)](https://securityscorecards.dev/viewer/?uri=github.com/Gavin8233841/Project-report-builder-skill) |

> 📌 **Note**: If the OpenSSF Scorecard badge shows "invalid repo path", it means the workflow has not yet completed its first successful run. After the next scheduled or manual trigger, results will be published and the badge will activate automatically.

These checks provide an additional layer of automated assurance beyond the initial manual review. Click the badges above for live status.

If you find a security or privacy issue after publication, please follow the process described in [SECURITY.md](SECURITY.md).

### Repository Layout

```
.
├── SKILL.md                              # Core skill definition (YAML frontmatter + instructions)
├── agents/
│   └── openai.yaml                       # WorkBuddy / Codex interface config
├── references/
│   ├── layout-and-export-qa.md           # Layout guidance & export quality checklist
│   └── report-workflow.md                # Full report generation workflow
├── .github/
│   └── workflows/
│       ├── gitleaks.yml                  # Secret scanning CI
│       └── scorecard.yml                 # OpenSSF Scorecard CI
├── .gitleaks.toml                        # Gitleaks detection rules
├── README.md                             # This file
├── SECURITY.md                           # Security policy & disclosure process
├── LICENSE                               # MIT License
└── .gitignore
```

### Validation (Local)

Useful local checks (Python-based, no extra dependencies):

```bash
# Validate YAML frontmatter in SKILL.md
python -c "import yaml,sys; t=open('SKILL.md').read(); m=__import__('re').search(r'\A---\n(.*?)\n---\n',t,__import__('re').DOTALL); yaml.safe_load(m.group(1)) if m else sys.exit('missing frontmatter'); print('yaml ok')"

# Validate agents/openai.yaml
python -c "import yaml; yaml.safe_load(open('agents/openai.yaml')); print('yaml ok')"

# Check file sizes
wc -c SKILL.md references/report-workflow.md references/layout-and-export-qa.md agents/openai.yaml

# Check for common secret patterns
git status --short
```

Also run your preferred local secret scanner before publishing.

## License

MIT. See [LICENSE](LICENSE).

---

## 中文说明

### 这是什么？

**项目汇报文档生成器（Project Report Builder）** 是一个用于将 vibe-coded 项目、快速原型、演示 Demo、课程作业、黑客松项目、应用竞赛作品、个人 Portfolio 作品或早期产品转化为专业项目汇报文档的 Skill。

它帮助开发者将「能跑」的项目变成评审老师、投资人、队友或用户都能看懂的专业文档：有据可查的文字描述、精选截图、评分映射、排版指导、PDF 导出质量检查和隐私审查。

### 适用场景

| 场景 | 说明 |
|---|---|
| 🏆 竞赛提交 | 黑客松、App 大赛、课程设计等需要项目说明文档 |
| 📚 课程作业 | 需要附带项目报告的课程实验或期末大作业 |
| 💼 Portfolio | 个人作品集、开源项目简介 |
| 🚀 早期产品 | MVP 演示文档、融资路演材料 |
| 🎯 技术总结 | 团队内部技术分享、代码交接文档 |

### 支持的项目类型

- iOS / HarmonyOS / Android / Web / 小程序 / 桌面端 / 多端应用
- 后端服务 / API / 数据后台 / 管理工具
- AI Agent / 模型驱动工作流 / 自动化工具 / 演示项目
- 黑客松 / 应用竞赛 / 课堂作业 / Portfolio / 投资人评审项目

### 平台兼容性

本 Skill **不限于单一平台**。核心逻辑全部在 `SKILL.md` 中（YAML frontmatter + Markdown），这是一个纯文本指令文件，不含可执行代码、无依赖、无运行时要求：

| 平台 | 支持程度 | 说明 |
|---|---|---|
| **WorkBuddy / Codex** | ✅ 完整支持 | 提供 `agents/openai.yaml`，支持隐式调用和默认提示路由 |
| **Claude Code** | ⚙️ 手动配置 | 将 `SKILL.md` 内容复制到 `CLAUDE.md` 或自定义指令中 |
| **Cursor** | ⚙️ 手动配置 | 将 `SKILL.md` 内容复制到 `.cursorrules` |
| **Continue.dev / Cline** | ⚙️ 手动配置 | 引用 `SKILL.md` 作为技能指令文件 |
| **ChatGPT / Claude / Gemini** | ⚡ 直接粘贴 | 将 `SKILL.md` 内容直接粘贴到对话中使用 |

> 💡 **小技巧**：你可以把 `SKILL.md` 的内容直接粘贴到任何 LLM 对话中，它会按照同样的流程工作。

### 安装方法

克隆仓库：

```bash
git clone https://github.com/Gavin8233841/Project-report-builder-skill.git
```

**WorkBuddy / Codex 用户：**

```bash
mkdir -p ~/.codex/skills/project-report-builder
cp -R Project-report-builder-skill/SKILL.md Project-report-builder-skill/agents Project-report-builder-skill/references ~/.codex/skills/project-report-builder/
```

**其他 AI 助手（Claude Code、Cursor 等）：**

将 `SKILL.md` 的内容复制到你使用的 AI 助手的自定义指令文件中（如 Cursor 的 `.cursorrules`、Claude Code 的 `CLAUDE.md`），并将 `references/` 文件夹放在指令文件旁边。

### 使用方式

在 WorkBuddy 或 Codex 中输入：

```
使用 $project-report-builder 将这个软件项目或原型转化为专业的项目汇报文档，包含证据支撑、截图选取、隐私审查和可导出 PDF 的结构。
```

在其他 AI 助手中，将 `SKILL.md` 的内容作为系统提示词或自定义指令的一部分引入，然后用自然语言描述你的汇报任务。

推荐提供的输入素材：

- 官方模板、评分标准、提交规则或字数限制
- 已有的草稿文字或笔记
- README、架构文档、日志、测试输出或发版说明
- 脱敏后的截图或演示视频帧
- 产品定位、目标受众、期望输出格式

Skill 会先盘点证据 → 识别敏感内容 → 映射 claims 到 proof → 然后起草并打包报告。

### 隐私与安全

项目汇报文档通常包含截图、日志、配置、学生/团队信息、商业计划、医疗/财务演示数据和 API 集成信息。本 Skill 以隐私优先为原则设计：

- 🔒 在引用、导出或发布前脱敏处理密钥和个人数据
- 🎭 截图中出现真实数据时使用合成演示数据替代
- 📦 不要将私有项目资产复制到公开示例或可复用 Skill 仓库中
- ⚠️ 避免对合规性、诊断、治疗、投资建议、法律意见、安全认证、隐私保证或生产就绪性做出未经支持的声明
- ✅ 当报告涉及外部规则、截止日期、价格、API 或法律时，从主要来源或用户提供的信息核实

### 安全审查

本项目在首次公开发布前经过了完整的安全审查。审查覆盖范围：

- **所有 Skill 文件**: `SKILL.md`、`agents/openai.yaml`、`references/report-workflow.md`、`references/layout-and-export-qa.md`
- **仓库元数据**: `README.md`、`SECURITY.md`、`LICENSE`

| 审查类别 | 检查项 | 结果 |
|---|---|---|
| 硬编码密钥 | 未发现 API 密钥、Token、密码、证书或私有端点 | ✅ 通过 |
| 个人数据 | 未发现真实姓名、手机号、邮箱、账号 ID 或学号 | ✅ 通过 |
| 私有资产 | 未发现嵌入私有截图、日志或竞赛资料 | ✅ 通过 |
| 指令安全性 | 包含明确的边界规则：禁止伪造数据、发布私有资产、过度声明合规性或安全性 | ✅ 通过 |
| 隐式调用 | `allow_implicit_invocation: true` —— 纯文档构建类 Skill，无破坏性能力 | ✅ 安全 |
| 外部调用 | Skill 不指示 Agent 发起网络请求、调用外部 API 或访问系统资源 | ✅ 安全 |

**结论：未发现阻塞性问题，可以安全发布。**

审查由作者在初始提交前通过 WorkBuddy 内置的 AI 辅助审计完成。详细方法论见 [SECURITY.md](SECURITY.md)。

### 自动化安全验证

两个 GitHub Actions 工作流持续保障仓库安全：

| 工作流 | 触发条件 | 用途 | 状态 |
|---|---|---|---|
| [**Gitleaks**](https://github.com/gitleaks/gitleaks) | 每次 Push 和 PR | 扫描所有提交中的硬编码密钥（API Key、Token、密码、私钥） | [![状态](https://github.com/Gavin8233841/Project-report-builder-skill/actions/workflows/gitleaks.yml/badge.svg)](https://github.com/Gavin8233841/Project-report-builder-skill/actions/workflows/gitleaks.yml) |
| [**OpenSSF Scorecard**](https://github.com/ossf/scorecard) | 每周定时 + main 分支推送 | 按 OpenSSF 最佳实践清单评估仓库，发布公开分数徽章 | [![分数](https://api.securityscorecards.dev/projects/github.com/Gavin8233841/Project-report-builder-skill/badge)](https://securityscorecards.dev/viewer/?uri=github.com/Gavin8233841/Project-report-builder-skill) |

> 📌 **注意**：如果 OpenSSF Scorecard 徽章显示 "invalid repo path"，表示该工作流尚未完成首次成功运行。下次定时触发或手动触发后，结果会自动发布，徽章将正常显示。

这些自动化检查为初始人工审查提供了额外的安全保障层。点击上方徽章查看实时状态。

如果你在发布后发现任何安全问题或隐私隐患，请按照 [SECURITY.md](SECURITY.md) 中的流程进行反馈（不要直接开公开 Issue 提交敏感内容）。

### 目录结构

```
.
├── SKILL.md                              # 核心 Skill 定义（YAML frontmatter + 指令）
├── agents/
│   └── openai.yaml                       # WorkBuddy / Codex 接口配置
├── references/
│   ├── layout-and-export-qa.md           # 排版指导 & 导出质量检查清单
│   └── report-workflow.md                # 完整报告生成工作流
├── .github/
│   └── workflows/
│       ├── gitleaks.yml                  # 密钥扫描 CI
│       └── scorecard.yml                 # OpenSSF Scorecard CI
├── .gitleaks.toml                        # Gitleaks 检测规则
├── README.md                             # 本文件
├── SECURITY.md                           # 安全策略与漏洞披露流程
├── LICENSE                               # MIT 许可证
└── .gitignore
```

### 本地验证

有用的本地检查命令（基于 Python，无需额外依赖）：

```bash
# 验证 SKILL.md 的 YAML frontmatter
python -c "import yaml,sys; t=open('SKILL.md').read(); m=__import__('re').search(r'\A---\n(.*?)\n---\n',t,__import__('re').DOTALL); yaml.safe_load(m.group(1)) if m else sys.exit('missing frontmatter'); print('yaml ok')"

# 验证 agents/openai.yaml
python -c "import yaml; yaml.safe_load(open('agents/openai.yaml')); print('yaml ok')"

# 检查文件大小
wc -c SKILL.md references/report-workflow.md references/layout-and-export-qa.md agents/openai.yaml

# 检查常见密钥模式
git status --short
```

发布前也请运行你偏好的本地密钥扫描工具进行扫描。

## 开源协议

MIT 协议。详见 [LICENSE](LICENSE) 文件。
