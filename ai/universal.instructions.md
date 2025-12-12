---
name: UniversalAIInstructions
description: Canonical AI tool rules and ergonomics for every repository in the org
applyTo: '*'
---

---
audience: ["VS Code", "Copilot Chat", "Web AI"]
tier: T0
applies_to: ["workspace:/Users/laptop/Documents/GitHub"]
owner: operations
last_reviewed: 2025-11-28
source_of_truth: handbook/ai/universal.instructions.md (this doc)
---

# Universal AI Tool Instructions (v1.1)

## Purpose

One canonical, tool-agnostic rule set to make AI outputs copy-paste-ready, minimize back-and-forth, and standardize risk handling across all projects.

---

## Scope & Precedence
- This file defines universal rules for any AI assistant (Copilot, ChatGPT, Claude, etc.).
- In GitHub repos, assistants MUST also read `.github/workspace.instructions.md` (workspace overlay) plus each repo’s `.github/copilot-instructions.md` and any path-specific `.github/instructions/*.instructions.md` files.
- If conflicts arise, apply: Organization → Repository‑wide → Path‑specific → User. (Declare the same precedence in repo instruction files.)

> **Rename note:** This file was previously stored at `handbook/ai/universal_instructions.md`. Update bookmarks, VS Code profiles, and documentation references to the new scope-based filename.

---

## 1. Core Principles


1. **Don't block on retrievable info**  
   Attempt the check first (logs, file presence, permissions), include exact results; ask only for true blockers.

2. **Don't block on non-critical input**  
   Make reasonable assumptions, label them, proceed; ask once at the end.

3. **Work in parallel; ask once**  
   Complete all independent steps before presenting a single consolidated "Decisions Needed" list.

4. **Self-verify state before asking**  
   Confirm repo path, branch, tool versions, and credentials (read-only) before questions.
   
5. The Less Required Reading and Time Required From The User the Better

6. For Multi-step, Multi paragraph Deliverables in Chat, Provide a Concise Highlight Bullet Point Structured most critical information at the top or outline. 

5. **Copy-paste-ready outputs**  
   Every shell block includes a correct `cd`; use complete blocks over piecemeal commands.

6. **Make everything clickable**  
   Provide direct URLs for external steps and commands to open local files.

7. **Multi-repo ergonomics**  
   Provide one script with echo headers per repo.

8. **Always use true move operations for folder/file move requests**
   When a user requests to move folders or files, use a true move (rename) operation, not copy/create. This preserves history, avoids duplication, and keeps the repo clean. Clearly state in your response whether you moved, copied, or created files/folders, and never claim a move if you performed a copy/create.


   I Value Comparison Tables for Comparing Options. 

   I value Systematic Structure to Decisions and Systems. 

   I value Visual Diagrams, Visual WorkFlows, Visual Decision Trees

   I Value Tables in deliverables. 

---

## 2. Risk Policy

### SAFE — Auto-allow (read-only, reversible, no prod impact)
- `git status/log/diff/show`
- File reads: `cat/grep/find/ls`
- Non-mutating verification scripts
- Apps Script: `clasp pull/logs/open`

### PROMPT FIRST — Reversible writes
- `git add/commit/push`
- Tracked file edits
- Staging deployments
- Apps Script: `clasp push`, creating versions

### ALWAYS CONFIRM — Irreversible/prod-impacting
- Destructive git: `reset --hard`, `push --force`, branch deletes
- Production triggers
- Bulk deletions
- Apps Script: remove old production deployments before redeploying new versions
- Data-destructive Sheet operations

**Pre-flight before any write:** State intent, affected paths/resources, expected outcome, and include fallback plan.

---

## 3. Response Rules (formatting & ergonomics)

### Shell Blocks

Every shell block must begin with:
```bash
cd /ABSOLUTE/PATH/TO/[REPO_OR_DIR]
```

Prefer one complete script per task:
- Clear headers: `echo "=== Step X ==="`
- Comments explaining intent
- Final success echo

### Links & Artifacts

- **Links:** Include direct URLs and the exact UI element to click (button/menu text)
- **Artifacts:** When creating files, print their paths and how to open them

### Template Shell Command
```bash
# [What this does]
cd /ABSOLUTE/PATH/TO/[REPO]
[command]
```

#### Multi-Step Workflow
# [What this accomplishes]
cd /ABSOLUTE/PATH/TO/[REPO]

# Step 1: [description]
[command1]

# Step 2: [description]
[command2]

# Step 3: [description]
[command3]

# Verify success
echo "✅ [Success message]"
```

#### Multi-Repo
# [What this does across all repos]

echo "=== [Repo1] ==="
cd /ABSOLUTE/PATH/TO/[Repo1]
[commands]

echo -e "\n=== [Repo2] ==="
cd /ABSOLUTE/PATH/TO/[Repo2]
[commands]

echo -e "\n=== [Repo3] ==="
cd /ABSOLUTE/PATH/TO/[Repo3]
[commands]

echo -e "\n✅ Completed for all repos"
```

### Always Do (Execution Patterns)

- **Terminal Commands:** Every block MUST include the absolute `cd` into the target repo before any other command. Provide copy-paste-ready sequences rather than single commands.
- **File References:** When pointing at a file, include either a clickable absolute path (preferred) or the exact command to open it (`code`, `open`, etc.).
- **External Links:** Link directly to the console or document page and name the button/menu to select.
- **Multi-Repo Workflows:** When an action spans several repos, emit one script with echo headers per repo so the user can run everything in one paste.
- **Complex Multi-Step Tasks:** Provide the full workflow (cd, commands, verification echo) instead of numbered prose instructions.

### Never Do

- **Assume current directory knowledge.** Never say "run `git status`" without the preceding `cd`.
- **Say "navigate to…" without commands.** Give the literal `cd` or UI steps.
- **Reference files without links/context.** Provide clickable paths or the command to open them.
- **Paste raw URLs without telling the user what to do there.** Include the action ("Enable API" etc.).
- **Use relative paths without repo names.** Always anchor paths to `/Users/laptop/Documents/GitHub/<repo>/...` so there is no ambiguity.

### Execution Checklist (before you send instructions)

1. [ ] All shell blocks begin with the correct `cd`.
2. [ ] File references are clickable or include `code`/`open` commands.
3. [ ] External services include direct URLs plus the UI action to take.
4. [ ] Multi-step workflows are consolidated into a single paste-ready block with comments and a success echo.
5. [ ] Multi-repo actions include echo headers and per-repo `cd` statements.
6. [ ] You’ve stated any assumptions explicitly (e.g., placeholder branch names).
7. [ ] Verification commands or echo statements show the user how to confirm success.

---

## 4. Research & Evidence (internet-sourced answers)

- **Recency discipline:** Include both the event date and the publish/update date when relevant
- **Two-source rule:** Cite at least one primary/official source for non-trivial claims
- **Explicit UI cues:** When linking to consoles/settings, state the exact button/menu text to click
- **Unstable facts:** Re-verify before answering (APIs, prices, policies, product features)
- **Verification failures:** Mark as Assumption, proceed only where safe, list what needs confirmation

### Answer Format for Sourced Claims
```
Claim: <one sentence>
Source(s): <link 1>, <link 2> [accessed YYYY-MM-DD]
Notes: <any caveats>
```

## 5. Background-Style Tasks (no async promises)

Complete all non-blocking checks now in the same response (read-only where possible):
- Repo status
- Paths
- Config presence
- Link checks for your own output

### Status Block Format
```
### Status
- Actions Performed: [...]
- Artifacts Produced: [paths/links]
- Assumptions Made: [...]
- Decisions Needed (blocking only): [...]
```

## 6. Command Conventions (terminal specifics)

- **Always include cd** to the precise directory before commands

- **For opening files:**
  ```bash
  cd /ABSOLUTE/PATH/TO/[REPO]
  code README.md  # or: open README.md (macOS), start README.md (Windows)
  ```

- **Multi-repo commands:** Include echo headers and run per-repo

- **Script endings:** End each script with a success echo and, where useful, a one-line verification command



## 7. Apps Script Projects (Google Sheets/Docs/Slides/Forms)

### Goal
Set up projects so the AI assistant can run scripts, edit Sheets, and view logs safely using least-privilege scopes. 

**Official tooling:** `@google/clasp` (CLI)

### Read-only Pre-flight (Always Do)

*Will optimize later.* 


## 8. Link & Path Verification

- Before responding, verify that any in-repo paths you cite exist
- For docs, run link checks (CI or locally) and fix/replace dead links
- If a critical external link may move, include an alternate route (menu path) in the instructions

## 9. Examples: Common Violations & Fixes

### ❌ Example 1: Blocking on Retrievable Info

**BAD:**
```
AI: "What's your current git branch?"
```

**GOOD:**
```
AI: "Checking current branch..."
```bash
cd /Users/laptop/Documents/GitHub/Candle_Data_Analysis_V2
git branch --show-current
```
Output: `main`

Now proceeding with the commit to main...
```

---

### ❌ Example 2: Missing `cd` in Shell Blocks

**BAD:**
```bash
git status
git add .
git commit -m "Update docs"
```

**GOOD:**
```bash
cd /Users/laptop/Documents/GitHub/Candle_Data_Analysis_V2

git status
git add .
git commit -m "Update docs"
```

---

### ❌ Example 3: Piecemeal Commands

**BAD:**
```
First run this:
```bash
git add .
```

Then run this:
```bash
git commit -m "Update"
```

Then run this:
```bash
git push
```

**GOOD:**
```bash
cd /Users/laptop/Documents/GitHub/Candle_Data_Analysis_V2

git add .
git commit -m "Update docs"
git push

echo "✅ Changes committed and pushed"
```

---

### ❌ Example 4: Vague Links

**BAD:**
```
Go to the Google Cloud Console and enable the API.
```

**GOOD:**
```
1. Go to: https://console.cloud.google.com/apis/library
2. Click the **"ENABLE APIS AND SERVICES"** button (top of page)
3. Search for "Sheets API"
4. Click the result, then click the blue **"ENABLE"** button
```

---

### ❌ Example 5: Assumptions Hidden in Response

**BAD:**
```
I'll create the config file in the root directory...
```

**GOOD:**
```
I'll create the config file in the root directory.

**Assumption:** Placing config in root (not /config/) since no config folder exists yet.

[proceeds with implementation]
```

---

### ❌ Example 6: Multiple Questions Mid-Task

**BAD:**
```
AI: "What's your repo path?"
User: "/Users/laptop/Documents/GitHub/project"
AI: "What branch are you on?"
User: "main"
AI: "Do you want to commit now?"
User: "yes"
AI: [finally does the work]
```

**GOOD:**
```
AI: "Checking repo state..."
```bash
cd /Users/laptop/Documents/GitHub/project
echo "Branch: $(git branch --show-current)"
echo "Status: $(git status --short)"
```

Output shows: Branch: main, Status: M README (Markdown file)

**Decisions Needed:**
1. Commit message preference? (Suggestion: "Update README with new instructions")

[After single response, proceeds with full implementation]
```

---

### ❌ Example 7: No Risk Label

**BAD:**
```
I'll delete the old deployment and push the new one.
```

**GOOD:**
```
**⚠️ ALWAYS CONFIRM - Irreversible Action**

I'll delete the old production deployment and redeploy the new version.

**Affected Resource:** 
- Production Web App: `AKfycbwE01CY...`
- Deployment ID: `@5`

**Expected Outcome:** New version live, old version removed from deployments list

**Fallback Plan:** Can redeploy previous version from Apps Script version history

Proceed? (yes/no)
```

---

### ❌ Example 8: Non-Clickable File Paths

**BAD:**
```
I've created the file at `docs/new_guide` (Markdown file)
```

**GOOD:**
```
I've created the file at `docs/new_guide.md`

**Open it:**
```bash
cd /Users/laptop/Documents/GitHub/Candle_Data_Analysis_V2
code docs/new_guide.md
```

Or update the path to a real file before sharing a clickable link (never reference paths that don’t exist).
```

---

### ❌ Example 9: Internet Research Without Sources

**BAD:**
```
The Sheets API v4 supports batch updates.
```

**GOOD:**
```
**Claim:** The Sheets API v4 supports batch updates via `batchUpdate` method

**Source:** https://developers.google.com/sheets/api/reference/rest/v4/spreadsheets/batchUpdate [accessed 2025-11-16]

**Notes:** Available since v4 launch (2016); requires `https://www.googleapis.com/auth/spreadsheets` scope
```

---

### ❌ Example 10: Multi-Repo Without Echo Headers

**BAD:**
```bash
cd /Users/laptop/Documents/GitHub/Candle_Data_Analysis_V2
git status

cd /Users/laptop/Documents/GitHub/<Repo_B>
git status

cd /Users/laptop/Documents/GitHub/handbook
git status
```

**GOOD:**
```bash
# Check git status across all repos

echo "=== Candle_Data_Analysis_V2 ==="
cd /Users/laptop/Documents/GitHub/Candle_Data_Analysis_V2
git status --short

echo -e "\n=== <Repo_B> ==="
cd /Users/laptop/Documents/GitHub/<Repo_B>
git status --short

echo -e "\n=== handbook ==="
cd /Users/laptop/Documents/GitHub/handbook
git status --short

echo -e "\n✅ Status check complete for all repos"
```

---

## 10. Anticipatory QA (pre-send checklist)

Before sending any response, verify:

- [ ] Commands include cd to the correct path
- [ ] Files are clickable or include an open command
- [ ] External steps include direct URLs and expected UI text
- [ ] All retrievable checks were performed; results included
- [ ] Questions consolidated into one "Decisions Needed" list with blocking items only
- [ ] Risk labels attached (Safe / Prompt First / Always Confirm)
- [ ] For Copilot code review: content is concise and self-contained (no reliance on external links for essential rules)



