# Project Report Builder

[![Gitleaks Secret Scan](https://github.com/Gavin8233841/Project-report-builder-skill/actions/workflows/gitleaks.yml/badge.svg)](https://github.com/Gavin8233841/Project-report-builder-skill/actions/workflows/gitleaks.yml)
[![OpenSSF Scorecard](https://api.securityscorecards.dev/projects/github.com/Gavin8233841/Project-report-builder-skill/badge)](https://securityscorecards.dev/viewer/?uri=github.com/Gavin8233841/Project-report-builder-skill)

Project Report Builder is a skill for turning vibe-coded software, rapid prototypes, demos, coursework, hackathon projects, app contest entries, portfolio pieces, and early products into professional project reports.

It helps developers turn working software into a first draft that judges, teachers, investors, teammates, or users can understand: evidence-backed writing, screenshot selection, scoring or audience mapping, layout direction, PDF export QA, and privacy review.

### Platform Compatibility

This skill is **not limited to a single platform**. The core logic lives in `SKILL.md` (YAML frontmatter + Markdown), which is a plain-text instruction file with no executable code, no dependencies, and no runtime requirements:

- **Primary target**: Codex — the only platform for which an interface configuration file (`agents/openai.yaml`) is provided. On this platform the skill supports implicit invocation and default prompt routing.
- **Also usable on**: Claude Code (custom instructions), Cursor (`.cursorrules`), or any AI coding assistant that accepts Markdown-based system prompts or skill instruction files. Simply copy or reference the content of `SKILL.md` as a system prompt.
- **Universal use**: You can paste the contents of `SKILL.md` directly into a chat with ChatGPT, Claude, Gemini, or any LLM that accepts user-provided instructions, and it will follow the same workflow.

If you need platform-specific configuration files for other assistants (e.g. Claude Code, Cursor, Continue.dev), contributions or requests via issues are welcome.

## What It Builds

- Project or product explanation documents
- Competition or coursework submissions
- Screenshot-rich product reports
- Technical implementation summaries
- Portfolio or open-source project briefs
- HTML/DOCX/PPTX source documents plus PDF-ready output plans
- Requirements or scoring mapping notes
- Asset manifests for screenshots and diagrams

## Supported Project Types

- iOS, HarmonyOS, Android, Web, Mini Program, desktop, and multi-platform apps
- Backend services, APIs, dashboards, and admin tools
- AI agents, model-powered workflows, automation tools, and demos
- Hackathon, app contest, classroom, portfolio, and investor review projects

## Not A Fit For

- Fabricating features, metrics, test results, compliance claims, or user traction
- Publishing private user data, screenshots, logs, keys, or unreleased business material
- Replacing legal, medical, financial, security, or compliance review
- Writing reports without any project evidence to inspect

## Installation

Clone this repository, then install or copy the skill directory into your AI assistant's skills or instructions folder.

**WorkBuddy / Codex:**

```bash
git clone https://github.com/Gavin8233841/Project-report-builder-skill.git
mkdir -p ~/.codex/skills/project-report-builder
cp -R Project-report-builder-skill/SKILL.md Project-report-builder-skill/agents Project-report-builder-skill/references ~/.codex/skills/project-report-builder/
```

**Other AI assistants (Claude Code, Cursor, etc.):**

Copy the contents of `SKILL.md` into your assistant's custom instructions file (e.g. `.cursorrules` for Cursor, `CLAUDE.md` for Claude Code). The `references/` folder can be placed alongside the instruction file and referenced by relative path.

## Usage

In WorkBuddy or Codex, ask:

```text
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

## Privacy And Safety

Project reports often include screenshots, logs, configs, student/team details, business plans, medical or financial demo data, and API integrations. This skill is designed to be privacy-first:

- Redact secrets and personal data before quoting, exporting, or publishing.
- Use synthetic demo data when real records appear in screenshots.
- Do not copy private project assets into public examples or reusable skill repositories.
- Avoid unsupported claims about compliance, diagnosis, treatment, investment advice, legal advice, security certification, privacy guarantees, or production readiness.
- Verify external rules, deadlines, prices, APIs, or laws from primary or user-provided sources when they affect the report.

## Repository Layout

```text
.
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
│   ├── layout-and-export-qa.md
│   └── report-workflow.md
├── .github/
│   └── workflows/
│       ├── gitleaks.yml
│       └── scorecard.yml
├── .gitleaks.toml
├── README.md
├── SECURITY.md
├── LICENSE
└── .gitignore
```

## Validation

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

## Security Review

This skill was reviewed before its initial public release. The review covered:

- **All skill files**: `SKILL.md`, `agents/openai.yaml`, `references/report-workflow.md`, `references/layout-and-export-qa.md`
- **Repository metadata**: `README.md`, `SECURITY.md`, `LICENSE`

**Review scope and criteria:**

| Category | Check |
|---|---|
| Hardcoded secrets | No API keys, tokens, passwords, certificates, or private endpoints found |
| Personal data | No real names, phone numbers, email addresses, account IDs, or student IDs found |
| Private assets | No private screenshots, logs, or competition materials embedded |
| Agent instruction safety | Skill instructions include explicit boundaries against fabricating data, publishing private assets, and overclaiming compliance or security |
| Implicit invocation | `allow_implicit_invocation: true` is intentional — this is a document-building skill with no destructive or external-write capabilities |
| External calls | Skill does not instruct agents to make network requests, call external APIs, or access local system resources |

**Result: no blocking issues found. Safe to publish.**

The review was performed by the author using WorkBuddy's built-in AI-assisted audit prior to the initial commit. For the review methodology, see [SECURITY.md](SECURITY.md).

### Automated Verification

Two GitHub Actions workflows enforce ongoing security hygiene:

- **[Gitleaks](https://github.com/gitleaks/gitleaks)** — runs on every push and PR to scan all commits for hardcoded secrets (API keys, tokens, passwords, private keys). Configured in `.github/workflows/gitleaks.yml`.
- **[OpenSSF Scorecard](https://github.com/ossf/scorecard)** — runs weekly and on push to main, evaluates the repository against the OpenSSF best-practices checklist, uploads results as SARIF to GitHub Code Scanning, and publishes a public score badge. Configured in `.github/workflows/scorecard.yml`.

These checks provide an additional layer of automated assurance beyond the initial manual review. Click the badges at the top of this README for live status.

If you find a security or privacy issue after publication, please follow the process described in [SECURITY.md](SECURITY.md) rather than opening a public issue with sensitive content.

## License

MIT. See [LICENSE](LICENSE).
