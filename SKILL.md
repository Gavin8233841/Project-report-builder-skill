---
name: project-report-builder
description: Build polished project or product explanation documents for vibe-coded software, rapid prototypes, hackathons, app contests, demos, portfolios, coursework, or investor/teacher review. Use when the user wants to turn an existing software product or prototype across iOS, HarmonyOS, Android, Web, Mini Program, desktop, backend service, AI agent, or multi-platform work into a professional report, DOCX/HTML/PDF document, product brief, competition submission, scoring-aligned writeup, screenshot-rich explanation, or final deliverable package.
---

# Project Report Builder

Use this skill to help developers turn vibe-coded or quickly prototyped software into a professional first draft that judges, teachers, investors, teammates, or users can understand. The core job is not only writing; it is editorial strategy, evidence selection, privacy-aware cleanup, layout direction, and export QA.

## Operating Principles

- Start from source evidence: project docs, logs, code, screenshots, demos, templates, scoring rules, and the user's own wording.
- Preserve the user's intent and voice. Rewrite only when needed for clarity, accuracy, tone, or scoring fit.
- Make claims concrete: pair innovation, engineering effort, and user value with screenshots, code facts, test facts, architecture facts, or demo behavior.
- Prefer professional restraint over decoration. The report should feel clear, structured, and credible.
- Treat screenshots as evidence, not wallpaper. Each image should prove a capability, design decision, or user workflow.
- Avoid overclaiming backend, AI, platform, privacy, medical, financial, or security abilities.
- Work by progressive disclosure: inventory available evidence first, then open only the files, screenshots, logs, or source modules needed to support the report.
- Redact secrets and private data before quoting, exporting, or copying any evidence.

## Safety And Privacy Boundaries

- Do not include API keys, tokens, passwords, cookies, private certificates, database URLs, private repository URLs, account identifiers, addresses, phone numbers, email addresses, student IDs, school/team private details, medical records, financial records, legal case details, or unreleased business material in public deliverables.
- If screenshots, logs, configs, network captures, or test data contain sensitive content, pause before publication work and either redact locally, replace with synthetic data, or ask the user for a sanitized asset.
- Do not copy user project assets, competition drafts, private screenshots, or domain-specific confidential material into reusable skill repositories or public examples.
- Do not claim compliance, diagnosis, treatment, investment advice, legal advice, security certification, privacy protection, or production readiness unless verified from user-provided evidence.
- For external facts, official rules, submission deadlines, pricing, APIs, or laws, verify from primary or user-provided sources when they affect the report.

## Workflow

1. **Intake And Evidence Audit**
   - Read the official template or submission rule first when present.
   - Inventory project README, logs, handoff files, roadmap, task notes, architecture docs, tests, and screenshot folders before opening many files.
   - Inspect the runnable product or source when claims depend on current behavior.
   - Prefer targeted reads over whole-repository sweeps; summarize large directories before selecting evidence.
   - Build a short list of verified facts, uncertain facts, and risky claims.
   - Build a redaction list for any sensitive text, screenshots, logs, or identifiers found during review.

2. **Scoring Or Audience Mapping**
   - Map each required section or scoring point to concrete product evidence.
   - If no scoring rubric exists, use: problem, target users, solution, interaction flow, innovation, implementation, safety/privacy, feasibility, future work.
   - Keep a separate mapping note for the user; do not put internal audit traces in the final document.

3. **Document Architecture**
   - Choose the report shape before writing: page count, section order, figure plan, and export format.
   - For competition docs, front-load problem, originality, runnable proof, and application value.
   - For product docs, front-load user value, workflow, market/scene fit, and implementation credibility.
   - For technical docs, front-load architecture, data flow, rules, tests, and limitations.

4. **Drafting**
   - Use the user's original phrasing where it carries authentic motivation or product insight.
   - Remove empty AI phrases such as "赋能", "极大提升", "全方位", "智能化闭环" unless supported by specifics.
   - Use measured claims: "已实现", "当前 Demo 支持", "设计为", "后续可扩展".
   - Cross-reference figures in text, e.g. "今日任务以时间线呈现（图 3）".

5. **Visual Composition**
   - Prefer HTML/CSS when layout, typography, figures, and export control matter.
   - Use Word/DOCX when the user must hand-edit heavily or official templates demand it.
   - Use PPT only when the deliverable is presentation-first or poster-like.
   - Use figure groups for related screenshots instead of scattering many single images.
   - Leave room for labels or arrows only where they explain a complex interaction.
   - Use sanitized screenshots for public-facing reports and examples.

6. **Export And QA**
   - Produce a standard PDF when selectable text matters.
   - Produce an image-only PDF when font/render fidelity matters.
   - Verify page count, file size, image clarity, title wrapping, author area, figure overlap, text layer, and per-page rendering.
   - Create a separate scoring/requirements mapping file for the user to audit.
   - Before final handoff, confirm public deliverables contain no secrets, private data, debug-only identifiers, or unrelated user assets.

## When More Detail Is Needed

- Read `references/report-workflow.md` for the full evidence-to-document process.
- Read `references/layout-and-export-qa.md` for HTML/Word/PDF layout and verification rules.

## Default Deliverables

- Source document: HTML, DOCX, or PPTX according to the user's workflow.
- Final PDF or two PDFs: standard and image-only.
- Requirements mapping note: Markdown is usually enough.
- Asset manifest: list which screenshots, diagrams, posters, or generated images were used.
- Change note: concise summary of what was edited and what the user should review.
