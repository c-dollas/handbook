# Universal AI Tool Instructions (v1.1)

## Purpose
One canonical, tool-agnostic rule set to make AI outputs copy‑paste‑ready, minimize back‑and‑forth, and standardize risk handling across all projects.

## Scope & Precedence
- This file defines universal rules for any AI assistant (Copilot, ChatGPT, Claude, etc.).
- In GitHub repos, assistants MUST also read `.github/copilot-instructions.md` (repo‑wide) and any path‑specific files in `.github/instructions/*.instructions.md` (if present).
- If conflicts arise, apply: Organization → Repository‑wide → Path‑specific → User. (Declare the same precedence in repo instruction files.)

---

## 1) Core Principles
1. **Don’t block on retrievable info.** Attempt the check first (logs, file presence, permissions), include exact results; ask only for true blockers.
2. **Don’t block on non‑critical input.** Make reasonable assumptions, label them, proceed; ask once at the end.
3. **Work in parallel; ask once.** Complete all independent steps before presenting a single consolidated “Decisions Needed” list.
4. **Self‑verify state before asking.** Confirm repo path, branch, tool versions, and credentials (read‑only) before questions.
5. **Copy‑paste‑ready outputs.** Every shell block includes a correct `cd`; use complete blocks over piecemeal commands.
6. **Make everything clickable.** Provide direct URLs for external steps and commands to open local files.
7. **Multi‑repo ergonomics.** Provide one script with echo headers per repo.

---

## 2) Risk Policy
- **SAFE — Auto‑allow (read‑only, reversible, no prod impact):** `git status/log/diff/show`, file reads (`cat/grep/find/ls`), non‑mutating verification scripts, Apps Script `clasp pull/logs/open`.
- **PROMPT FIRST — Reversible writes:** `git add/commit/push`, tracked file edits, staging deployments, Apps Script `clasp push`, creating versions.
- **ALWAYS CONFIRM — Irreversible/prod‑impacting:** destructive git (`reset --hard`, `push --force`, branch deletes), production triggers, bulk deletions, Apps Script undeploy/redeploy of production, data‑destructive Sheet operations.

**Pre‑flight before any write:** state intent, affected paths/resources, and expected outcome; include fallback plan.

---

## 3) Response Rules (formatting & ergonomics)
- **Shell blocks** must begin with:
  ```bash
  cd /ABSOLUTE/PATH/TO/[REPO_OR_DIR]


4) Research & Evidence (internet‑sourced answers)

Recency discipline: include both the event date and the publish/update date when relevant.

Two‑source rule for non‑trivial claims: cite at least one primary/official source.

Explicit UI cues: when linking to consoles/settings, state the exact button/menu text the user should click.

Unstable facts: re‑verify before answering (APIs, prices, policies, product features).

If verification fails: mark as Assumption, proceed only where safe, and list what needs confirmation.

Answer format for sourced claims:

7) Apps Script Projects (Google Sheets/Docs/Slides/Forms)

Goal
Set up projects so the AI assistant can run scripts, edit Sheets, and view logs safely using least‑privilege scopes. Official tooling: @google/clasp (CLI).

Read‑only pre‑flight (Always Do)

Will optimize later. 


8) Link & Path Verification

Before responding, verify that any in‑repo paths you cite exist.

For docs, run link checks (CI or locally) and fix/replace dead links.

If a critical external link may move, include an alternate route (menu path) in the instructions.

9) Anticipatory QA (pre‑send checklist)

Commands include cd to the correct path.

Files are clickable or include an open command.

External steps include direct URLs and expected UI text.

All retrievable checks were performed; results included.

Questions consolidated into one “Decisions Needed” list with blocking items only.

Risk labels attached (Safe / Prompt First / Always Confirm).

For Copilot code review: content is concise and self‑contained (no reliance on external links for essential rules).


