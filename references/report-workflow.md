# Report Workflow Reference

## 1. Intake Checklist

Ask for or locate:

- Official template, rules, rubric, submission portal requirements, page/word/file-size limits.
- Existing drafts: DOCX, PPTX, HTML, Markdown, notes, product slogans, personal motivation.
- Project evidence: README, development logs, task notes, architecture docs, tests, screenshots, demo data, deploy URL, code stats.
- Platform facts: iOS, HarmonyOS, Android, Web, Mini Program, desktop, backend service, AI agent, model, database, privacy/storage, deployment target.
- User priorities: competition pass, product credibility, teacher review, investment pitch, portfolio, open-source README, poster.

If information may have changed or affects scoring/submission, verify from official sources or user-provided screenshots.

Do not start by reading every source file or opening every image. First inventory the evidence surface:

- Read top-level docs and official requirements.
- List screenshot and artifact folders, then select only the images that can prove key workflows.
- Use code search for exact product names, feature names, tests, routes, models, or APIs instead of broad source reading.
- For large repos, inspect only modules connected to claims that will appear in the report.

## 2. Safety And Redaction Gate

Before drafting or exporting, check whether evidence contains:

- Secrets: API keys, tokens, cookies, passwords, certificates, private endpoints, database URLs, signing files.
- Personal data: real names, phone numbers, email addresses, addresses, account IDs, student IDs, school/team private details.
- Sensitive domain data: medical records, financial information, legal materials, minors' data, private business documents.
- Publication risks: private repository URLs, competition portal screenshots, unreleased plans, internal comments, debug consoles, raw logs.

Actions:

- Do not quote or copy sensitive content into final documents, examples, README files, or reusable skill repositories.
- Prefer synthetic demo data, blurred/redacted screenshots, cropped UI evidence, or text summaries when real data is visible.
- If redaction changes the meaning of a claim, revise the claim instead of hiding the risk.
- If the user wants public release material, treat every asset as public unless explicitly marked private in the working notes.

## 3. Evidence Ledger

Create a working ledger with four columns:

- Claim: what the report might say.
- Evidence: file path, screenshot, code module, test result, demo behavior, log entry.
- Risk: overclaim, platform limitation, medical/legal/security ambiguity, unstable feature.
- Final wording: accurate version for the document.

Examples:

- "端侧模型已稳定可用" may become "已完成设备端模型接入探索，当前初赛核心体验不依赖其稳定输出".
- "隐私安全" may become "演示数据默认保存在本地浏览器，不上传真实健康数据".
- "完整后端" may become "当前 Demo 使用本地演示数据，领域规则已从核心模块迁移".

## 4. Section Patterns

Competition report:

1. Project title and author/team.
2. Problem background and target users.
3. Solution overview.
4. Core workflows with figures.
5. Innovation and differentiation.
6. Technical implementation and architecture.
7. Safety, privacy, accessibility, and boundaries.
8. Demo completion and verification.
9. Application value and future plan.

Product report:

1. Product one-liner.
2. User scenario and pain points.
3. Main experience.
4. Differentiated value.
5. Design system and interaction details.
6. Implementation proof.
7. Roadmap.

Technical report:

1. System goal.
2. Architecture diagram.
3. Domain model and data flow.
4. Key algorithms/rules.
5. Testing and quality.
6. Deployment and limitations.

Portfolio or open-source report:

1. What the project does.
2. Who it is for.
3. Product walkthrough.
4. Architecture and implementation evidence.
5. Setup or demo path.
6. Known limits and next steps.

AI agent or backend service report:

1. User task or integration context.
2. Inputs, outputs, and boundaries.
3. Tool/model/service architecture.
4. Evaluation, logs, or test evidence.
5. Safety, privacy, failure modes, and human review points.
6. Deployment and extension plan.

## 5. Writing Rules

- Use active, specific sentences.
- Prefer "how it works" over slogan language.
- Use first-person origin story sparingly when it adds authenticity.
- Avoid claiming "industry-leading" unless benchmarked.
- Keep limitations visible but framed as engineering boundaries.
- Use consistent product names and platform names.
- Do not invent code stats; compute or read them.
- Avoid platform lock-in language unless the project is truly platform-specific.
- For medical, financial, legal, education, or public-sector projects, write capability and boundary statements conservatively.

## 6. Figure Planning

For each figure decide:

- What claim does it prove?
- Should it be full-width, side-by-side, or grouped?
- Does it need a caption, callout, or in-text reference?
- Is the image sharp at print/PDF scale?
- Does it reveal private data, keys, personal identifiers, or unfinished debug UI?

High-value software report figures:

- First-screen workflow.
- Add/create flow.
- Record/history review.
- AI/boundary screen.
- Report/export screen.
- Architecture or data flow.
- Test/build/code scale evidence.
- Before/after or product poster when appropriate.

When choosing figures:

- Start with a small set that proves the main workflow, usually 4-10 images for a short report.
- Prefer one clear workflow sequence over many similar screens.
- Never use screenshots that expose secrets, private records, private portal pages, or unrelated user projects.
- Keep an asset manifest with source path, intended caption, redaction status, and final use.

## 7. Editing User Drafts

When the user has already edited a draft:

- Do not rewrite everything by default.
- Infer why the user changed wording.
- Mark proposed wording changes separately if requested.
- Preserve emotionally important origin statements unless they hurt clarity or compliance.
- Move weak but meaningful text into a lighter paragraph rather than deleting it.
