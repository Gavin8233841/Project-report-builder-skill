# Security Policy

## Scope

This repository contains an AI assistant skill for building project and product report documents. It should not contain private project assets, real user records, API keys, credentials, unreleased competition material, private screenshots, or logs from user projects.

## Sensitive Data Rules

- Do not commit secrets, tokens, cookies, passwords, private keys, certificates, database URLs, signing files, or private endpoints.
- Do not commit real personal data such as names, phone numbers, email addresses, addresses, account IDs, student IDs, or private school/team information.
- Do not commit medical, financial, legal, minors' data, private business documents, or unreleased product plans.
- Use synthetic data, cropped screenshots, blurred screenshots, diagrams, or summaries for examples.
- Treat screenshots and PDF exports as public artifacts unless they are kept in a private working directory outside this repository.

## Reporting A Problem

If you find a security or privacy issue in this skill:

1. Do not post secrets or private data in a public issue.
2. Use the hosting platform's private vulnerability reporting feature when available.
3. If private reporting is not available, open a public issue that describes the problem class without including sensitive content.

## For Maintainers

Before publishing a release:

- Run a secret scan or at least search for common key, token, password, and private URL patterns.
- Check all examples for private screenshots, real personal data, private repository paths, and hidden PDF metadata.
- Confirm README examples use generic repository names only.
- Confirm the skill does not instruct agents to read or publish unrelated private project files.
