# Universal AI Tool Instructions (v1.1)

## Purpose

One canonical, tool-agnostic rule set to make AI outputs copy-paste-ready, minimize back-and-forth, and standardize risk handling across all projects.

---

## Scope & Precedence
- This file defines universal rules for any AI assistant (Copilot, ChatGPT, Claude, etc.).
- In GitHub repos, assistants MUST also read `.github/copilot-instructions.md` (repo‑wide) and any path‑specific files in `.github/instructions/*.instructions.md` (if present).
- If conflicts arise, apply: Organization → Repository‑wide → Path‑specific → User. (Declare the same precedence in repo instruction files.)

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

5. **Copy-paste-ready outputs**  
   Every shell block includes a correct `cd`; use complete blocks over piecemeal commands.

6. **Make everything clickable**  
   Provide direct URLs for external steps and commands to open local files.

7. **Multi-repo ergonomics**  
   Provide one script with echo headers per repo.

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
- Apps Script: undeploy/redeploy of production
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

### Templatesle Command
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

---

## 4. Research & Evidence (internet-sourced answers)rs)

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

Output shows: Branch: main, Status: M README.md

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
I've created the file at docs/new_guide.md
```

**GOOD:**
```
I've created the file at `docs/new_guide.md`

**Open it:**
```bash
cd /Users/laptop/Documents/GitHub/Candle_Data_Analysis_V2
code docs/new_guide.md
```

Or click: [docs/new_guide.md](file:///Users/laptop/Documents/GitHub/Candle_Data_Analysis_V2/docs/new_guide.md)
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

cd /Users/laptop/Documents/GitHub/C-DollasP2
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

echo -e "\n=== C-DollasP2 ==="
cd /Users/laptop/Documents/GitHub/C-DollasP2
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


