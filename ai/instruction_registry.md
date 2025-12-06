---
audience: ["Instruction authors", "Operations", "AI maintainers"]
tier: T1
applies_to:
  - "handbook/ai/instruction_registry.md"
owner: operations
last_reviewed: 2025-11-29
source_of_truth: "handbook/ai/instruction_registry.md (this doc)"
---

# Instruction Registry (Human Index)

**Maintained by:** operations  
**Last reviewed:** 2025-11-28

This document is the **human-readable atlas** for every instruction artifact. Pair it with the machine manifest at `.github/instruction-registry.yml`:

- `instruction_registry.md` → narrative descriptions, routing notes, context, and responsibilities.
- `instruction-registry.yml` → strict schema for automation (AI Tool Check, dashboards, lint checks).

Both must list the **same IDs** so humans and scripts stay synchronized.

## Legend

- **Tier:** T0 (universal) → T4 (public/web excerpt)
- **Audience:** Intended consumers (internal AI tools, repo-specific agents, public web tools)
- **Status:** Active, In Progress, Planned, Blocked
- **Public Mirror:** Path to the redacted version (if `audience` includes public/web)

## Registry Table

| ID | Tier | Path | Audience | Owner | Last Reviewed | Status | Public Mirror / Notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `t0-universal` | T0 | `handbook/ai/universal.instructions.md` | Internal AI + repo agents | operations | 2025-11-28 | Active | Public-safe excerpt will live at `handbook/ai/public/copilot_public_playbook.md` (planned). |
| `t0-definitions` | T0 | `handbook/definitions/all_purpose_use.md` | Internal AI + repo agents | operations | 2025-11-28 | Active | Provides canonical terminology referenced by every repo. |
| `t1-registry-md` | T1 | `handbook/ai/instruction_registry.md` | Instruction authors, reviewers | operations | 2025-11-28 | Active | Human index (this file); cross-links to YAML manifest. |
| `t1-registry-yml` | T1 | `.github/instruction-registry.yml` | Automation scripts | operations | 2025-11-28 | Active | Consumed by `scripts/ai_tool_check.py`. |
| `t1-workspace-overlay` | T1 | `.github/workspace.instructions.md` | Workspace AI overlays | operations | 2025-11-28 | Active | Multi-repo templates, routing expectations, document staging rules. |
| `t1-meta-discovery-optimized` | T1 | `.github/prompts/meta-discovery-optimized.prompt.md` | Workspace AI overlays | operations | 2025-11-30 | Active | Workspace meta-discovery workflow, promoted from Candle Source_of_Truth. |
| `t2-awesome-copilot-mcp` | T2 | `Workspace_Governance/docs/Source_of_Truth/governance/ai_playbooks/awesome_copilot_mcp_server.md` | Internal AI | operations | 2025-11-30 | Active | MCP server install/config/troubleshooting playbook; link instead of duplicating in repos. |
| `t2-drive-access-playbook` | T2 | `C-DollasP2/docs/Source_of_Truth/ai_playbooks/drive_access.md` | Internal AI | operations | Pending | Planned | Currently lives as `docs/planning/Research/Copilot_GoogleDrive_Access`; needs promotion. |
| `t2-xlsx-export-playbook` | T2 | `Workspace_Governance/docs/Source_of_Truth/governance/ai_playbooks/xlsx_export_tool.md` | Internal AI | operations | 2025-11-29 | Active | Canonical XLSX exporter instructions shared across repos; legacy copies now point here. |
| `t3-candle-best-practices` | T3 | `Candle_Data_Analysis_V2/docs/Source_of_Truth/prompts/copilot_instructions_best_practices.md` | Historical reference only | user | 2025-11-28 | Retired | Guidance moved to T0/T1/T3 instruction files; keep for audit trail. |
| `t3-backtesting-repo` | T3 | `Backtesting_Pattern_Mining_Machine_V1/.github/copilot-instructions.md` | Repo AI only | backtesting-maintainer | 2025-11-28 | Active | References T0/T2 docs instead of copying text. |
| `t3-backtesting-scripts` | T3 | `Backtesting_Pattern_Mining_Machine_V1/scripts/README.md` | Repo AI + maintainers | backtesting-maintainer | 2025-11-28 | Active | Script reuse table documenting `ingest_spy.py` & `run_jobs.py` as repo-specific; update when promotion tasks are opened. |
| `t3-candle-repo` | T3 | `Candle_Data_Analysis_V2/.github/copilot-instructions.md` | Repo AI only | candle-maintainer | 2025-11-28 | Active | Must link to Source_of_Truth best-practices doc once moved. |
| `t3-candle-meta-discovery` | T3 | `Candle_Data_Analysis_V2/docs/Source_of_Truth/prompts/meta-discovery-optimized.prompt.md` | Repo AI only | candle-maintainer | 2025-11-30 | Retired | Historical reference after promotion to `t1-meta-discovery-optimized`; file removed. |
| `t3-cdollasp2-repo` | T3 | `C-DollasP2/.github/copilot-instructions.md` | Repo AI only | operations | 2025-11-28 | Active | Houses personal/operations clarifications flagged “Needs Review.” |
| `t3-cdollasp1-repo` | T3 | `C-DollasP1/.github/copilot-instructions.md` | Repo AI only | operations | 2025-11-28 | Active | Lightweight instructions for Prompt Playground repo. |
| `t3-repo-template` | T3 | `Repo_Template_V1/.github/copilot-instructions.md` | Template consumers | operations | 2025-11-28 | Active | Baseline text for new repos; should ingest T0 references. |
| `t3-github-mini-circuit` | T3 | `github-mini-circuit/.github/copilot-instructions.md` | Training repo AI | operations | 2025-11-28 | Active | Introductory Git practice instructions. |
| `t4-public-playbook` | T4 | `handbook/ai/public/copilot_public_playbook.md` | Public/web AI | operations | Pending | Planned | Redacted excerpt of `t0-universal`; creation tracked under Phase P3. |

## Maintenance Checklist

- Update this file **whenever** an instruction file is added, moved, or re-tiered.
- Keep IDs stable; automation depends on them.
- Mirror the same entries in `.github/instruction-registry.yml` (including `status`).
- When promoting drafts from inboxes, update `Last Reviewed` and add routing notes.
- For public mirrors, verify sensitive content is removed before publishing.
