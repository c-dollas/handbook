---
audience: ["public"]
tier: T4
applies_to: ["Web AI", "Browser assistants"]
owner: operations
last_reviewed: 2025-11-29
source_of_truth: handbook/ai/public/copilot_public_playbook (this doc)
public_mirror: https://github.com/c-dollas/handbook/blob/main/ai/public/copilot_public_playbook.md
---

# Copilot Public Playbook

This file is safe to share with browser-based AI tools (ChatGPT, Bing, etc.) so they follow the same guardrails as the VS Code workspace without exposing repo-private details.

## 1. Interaction Principles

1. Always begin shell instructions with the absolute `cd /Users/laptop/Documents/GitHub/<repo>` command.
2. Provide copy-paste-ready blocks that complete an entire workflow (no "run X then Y" prose).
3. Link to files or external consoles directly; avoid telling the user to "navigate" without a URL.
4. When referencing multiple repos, include loop headers so the user can run the same block per repo.

## 2. Drive & Sheets Access Guidance

- Refer to the internal playbook (Drive Access T2) for validation steps and only share the sanitized summary or relevant command block.
- Never invent Drive capabilities; if uncertain, instruct the user to run the `drive_access_check.py` helper and provide the block from the T2 playbook.

## 3. XLSX Export Guidance

- Use the shared `xlsx_export_tool.py` command block with real config/destination paths supplied by the user.
- Mention where the exported XLSX will land and how to verify success (sheet count, checksum).

## 4. Escalation & Logging

- For any governance-related action, remind the user to log the attempt in the relevant repo `docs/inbox/AI_Inbox/LOG.md`.
- If a task falls outside the published playbooks, instruct the user to stage a draft in the appropriate AI Inbox before proceeding.

## 5. Updating This Playbook

- Keep this document in sync with the T0 universal instructions and T2 playbooks.
- Date-stamp the `last_reviewed` field whenever content changes so the AI Tool Check can verify staleness.
