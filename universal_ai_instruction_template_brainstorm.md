# Universal AI Instruction Template - Brainstorm

**Created:** November 16, 2025  
**Purpose:** Create ONE consolidated universal AI instruction document that prevents repeating preferences across all AI tools (Copilot, ChatGPT, Claude, web, mobile)  
**Expected ROI:** 40-260 min/week saved (36-224 hours annually)

---

## SECTION 1: RAW BRAINSTORM (User's Exact Words)

### User's Original Request:
> I want a way to implement a Copilot / Codex / Chatgpt / or other AI TOOL Instructions Document
>
> **Goals:**
> - That can be accessed and utilized from VS Code, the web, From other apps that have related tools
> - As needed, I also want to make project specific AI TOOL instruction. which may be public, may not be, not sure depends on content of instruction.
>   - As I do more projects or have use cases I want to have Project Type templates if deemed appropriate.
> - **For now the main focus should be the general foundation of Instructions that will be used across all AI TOOL platforms.**
> - Prevent myself from repeating myself

### User's Core Problem Statement:
> "I want ONE CONSOLIDATED UNIVERSAL AI INSTRUCTION DOCUMENT that contains my working style (not project-specific details), universal preferences, learning profile, risk-based command approach, and core principles that apply to ALL projects. Single document, platform-agnostic, project-agnostic, easy to reference everywhere."

### What Makes It UNIVERSAL (User's Words):
- Single document (not scattered across 5+ files)
- Platform-agnostic (works with Copilot, ChatGPT, Claude, web, mobile)
- Project-agnostic (general style, not Candle_Data_Analysis_V2 specifics)
- Easy to reference (you can link/attach/paste it anywhere)

### How User Would Use It:
- Save as ONE markdown file (e.g., MY_AI_WORK_STYLE.md)
- Store in accessible location (Google Drive, Notion, GitHub gist)
- Reference it everywhere:
  - Paste into ChatGPT conversations
  - Link in Copilot instructions
  - Attach to Claude chats
  - Access from mobile

### User's Existing Examples (What to Include):

**From Copilot Instructions:**
- NEVER BLOCK ON RETRIEVABLE INFO
  - ❌ WRONG: "I need you to verify the service account sharing status before I proceed"
  - ✅ RIGHT: Run `drive_access_check.py` yourself, then proceed
- NEVER BLOCK ON NON-CRITICAL INPUT
  - ❌ WRONG: Stop entire task for minor detail when 10 other steps available
  - ✅ RIGHT: Make reasonable assumptions, complete all independent work, ask once
- "Always Allow" Command Classifications (Safe/Medium/High Risk)

**From Best Practices Document:**
- Always include `cd` commands - User is new to terminal navigation
- Provide direct links - Never say "go to X settings" without URL
- Make all references clickable
- Copy-paste ready commands
- Assume no terminal knowledge

**Universal Preferences:**
- Always include cd commands
- Clickable links everywhere
- Copy-paste ready workflows
- Never block on retrievable info
- Never block on non-critical input
- Parallel work, ask once

**Learning Profile:**
- New to: terminal, VS Code
- Strong in: Sheets/Apps Script
- Working across multiple devices

**Risk-Based Command Approach:**
- Safe commands (auto-allow)
- Medium risk (prompt first)
- High risk (always confirm)

**Core Principles:**
- Self-verification before asking
- Complete parallel work first
- Elimination ratio thinking (1:3+)
- Evidence-based decisions

---

## SECTION 2: REVISED/STRUCTURED ANALYSIS

### Core Problem Being Solved

**The Issue:**
User has to repeat the same preferences, work style instructions, and anti-patterns across multiple AI tools (GitHub Copilot, ChatGPT, Claude, etc.) and contexts (VS Code, web, mobile). This wastes 40-260 minutes per week because AI tools either:
1. Don't have access to preferences
2. Have scattered/incomplete preferences across 5+ documents
3. Ignore project-specific instructions that should be universal

**The Impact:**
- **Time waste:** 36-224 hours annually explaining the same things
- **Frustration:** Repeatedly asking for cd commands, links, verification-first approach
- **Inconsistency:** Different AI tools get different subsets of preferences
- **Maintenance burden:** Updates must be copied to multiple locations

**The Root Cause:**
No single, authoritative, platform-agnostic instruction document that travels with the user across all tools and projects.

---

### Why This Is High-Impact

**Quantified Evidence:**

| **Time Waste Category** | **Weekly Incidents** | **Time/Incident** | **Weekly Total** |
|------------------------|---------------------|------------------|-----------------|
| Retrievable info blocking | 3-5 | 5-10 min | 15-50 min |
| Terminal navigation issues | 2-3 | 2-5 min | 4-15 min |
| Missing links | 3-5 | 1-3 min | 3-15 min |
| Sequential blocking | 1-2 | 10-60 min | 10-120 min |
| Preference repetition | 1-2 | 10-30 min | 10-60 min |
| **TOTAL** | **10-17** | **Variable** | **42-260 min/week** |

**Annual Impact:** 36-224 hours saved  
**ROI:** Template creation (2-4 hours) pays back in 1-6 weeks → 9x-56x annual ROI

**Proven Pain Points (From Research):**
1. **JSON Jobs (CRITICAL):** Stated 10+ times but AI kept suggesting JSON format
2. **Terminal Navigation:** Had to repeatedly ask for `cd` commands
3. **Missing Links:** Had to repeatedly ask for direct URLs
4. **File References:** Had to ask for clickable links vs plain text
5. **Blocking on Info:** AI asked for IDs/permissions instead of checking

---

### Structured Breakdown

#### **What's Working (Keep These):**
- ✅ `USER_PREFERENCES_CRITICAL.md` - Maintenance protocol for tracking repeated preferences
- ✅ `copilot_instructions_best_practices.md` - UX templates for terminal commands, links, multi-repo
- ✅ `vscode_always_allow_setup.md` - Auto-execution configuration
- ✅ Risk-based command classification (Safe/Medium/High)
- ✅ "Never Block On" principles (retrievable info, non-critical input)

#### **What's Broken (Fix These):**
- ❌ Preferences scattered across 5+ documents
- ❌ Project-specific docs mixed with universal principles
- ❌ No single document accessible from all AI tools
- ❌ No enforcement mechanism (AI tools don't always read existing docs)
- ❌ Mobile/web access not considered

#### **Patterns/Themes That Emerged:**

**Theme 1: "Ask vs Check" Decision Framework**
- AI defaults to asking user for info instead of checking available sources
- Solution: Explicit checklist of what to check before asking (README, config files, API calls, scripts)

**Theme 2: "Terminal Novice" User Profile**
- User is new to terminal but experienced in Sheets/Apps Script
- Solution: ALWAYS include `cd` commands, never assume directory context

**Theme 3: "Copy-Paste Ready" Workflow**
- User wants single-block, complete commands (not multi-step manual processes)
- Solution: Template system for single/multi-step/multi-repo commands

**Theme 4: "Parallel Work, Ask Once"**
- AI stops entire task to ask about step 3 when steps 1,2,4-10 are independent
- Solution: Complete all parallelizable work first, consolidate questions

**Theme 5: "Link Everything"**
- User wastes time searching for files, navigating to services without direct URLs
- Solution: All file references clickable, all service references have direct URLs

---

### Core Concepts Identified

**Concept 1: Universal vs Project-Specific Split**
- **Universal:** Working style, learning profile, general preferences
- **Project-Specific:** Repo paths, spreadsheet IDs, command classifications for that project
- **Implementation:** ONE universal base document + lightweight project overlays

**Concept 2: Platform-Agnostic Core**
- Core principles work across Copilot, ChatGPT, Claude, web, mobile
- Platform-specific adaptations noted but not required
- Storage in universally accessible location (Google Drive, GitHub gist)

**Concept 3: Pre-Flight Checklist**
- AI tools must confirm they've read universal instructions before starting
- Enforcement through conversation protocol: "Did you read MY_AI_WORK_STYLE.md?"
- Alternative: Include in every prompt/conversation start

**Concept 4: Living Document with Maintenance Protocol**
- When user says "I've mentioned this multiple times" → Update immediately
- When AI violates principle → Add to anti-patterns section with correction
- Monthly review: What's working? What violations occurred? Refine accordingly

**Concept 5: Evidence-Based Decision Framework**
- Include ROI data, elimination ratios, time-reduction metrics
- Reference HIGH_IMPACT_AI_USE_CASES_THE_SOLUTION.md wisdom
- "Why NOT alternatives" reasoning for tool selection

---

### Real Examples from User's Project

**Example 1: JSON Jobs Failure (Repetition)**
- **Context:** User stated 10+ times: "NEVER use JSON jobs, only flag-based"
- **What Happened:** AI tools (Copilot, ChatGPT) continued suggesting JSON format
- **Why It Failed:** Preference scattered across conversations, not centralized
- **Solution in Template:** "Apps Script Jobs System: ALWAYS use RunJobsFromFlags() with flag columns. NEVER suggest JSON format. Reason: User's infrastructure designed for flag-based, JSON creates technical debt."

**Example 2: Terminal Navigation Frustration**
- **Context:** User is new to terminal, repeatedly told AI to include `cd` commands
- **What Happened:** AI gave commands like `git status` without directory context
- **Result:** User ran command in wrong folder → errors → had to ask "which folder?"
- **Solution in Template:** "ALWAYS include `cd /full/path` before every terminal command. User is new to terminal navigation. NEVER assume user knows which directory to be in."

**Example 3: Link Provision Failure**
- **Context:** AI said "Go to Cloud Project settings and change something"
- **What Happened:** User didn't know how to get there, had to ask for URL
- **Result:** 3-5 minutes wasted figuring out navigation
- **Solution in Template:** "When referencing external services, ALWAYS provide direct URL with context. Example: 'Enable the API at [Google Cloud Console - APIs & Services](https://console.cloud.google.com/apis/dashboard?project=YOUR_PROJECT)'"

**Example 4: Blocking on Share Status**
- **Context:** AI stopped task and asked: "Please verify share status before I proceed"
- **What Happened:** User had `drive_access_check.py` script that could verify automatically
- **Result:** Task stopped, user had to manually check, 5-10 minutes wasted
- **Solution in Template:** "NEVER block on retrievable information. Before asking user to verify: (1) Check README/config files, (2) Run available scripts, (3) Check API if accessible. Only ask if actual error occurs."

**Example 5: Sequential Blocking**
- **Context:** AI had 10-step task, asked about decision at step 3, waited for answer
- **What Happened:** Steps 4-10 were independent but AI didn't proceed
- **Result:** Potential hours wasted if user delayed responding
- **Solution in Template:** "Work in parallel, ask once. If task has 10 steps and only step 3 needs input, complete steps 1,2,4-10 first. Then present all progress with consolidated questions."

---

### Underlying Principles

**Principle 1: Task Elimination > Task Optimization**
- Best solution is NOT doing the task at all
- Second best is doing it once and never repeating
- Template eliminates repetition of preferences (elimination ratio: ∞)

**Principle 2: Knowledge Centralization**
- Scattered knowledge = repeated explanations
- Centralized knowledge = reference once, use everywhere
- Universal template = single source of truth for working style

**Principle 3: Self-Verification First, User Confirmation Last**
- AI should exhaust available verification methods before asking user
- Checklist approach: README → config files → scripts → API → THEN ask
- Reduces blocking, maintains momentum

**Principle 4: Assume Zero Terminal Knowledge**
- User is new to CLI but experienced in other domains
- Every command must be complete, self-contained, copy-paste ready
- Include directory context, explanatory comments, success verification

**Principle 5: Consolidation Bias**
- User explicitly stated: "The more consolidating the better. The less separate documents to have to keep track of the better."
- When in doubt, merge into universal template vs creating separate doc
- Only split when truly project-specific (repo paths, IDs, etc.)

---

## APPENDIX: RESEARCH FINDINGS & TIME WASTE QUANTIFICATION

### Detailed Pattern Analysis (From UNIVERSAL_AI_INSTRUCTION_IMPROVEMENTS_ANALYSIS)

**Time Waste Quantification:**

| Pattern Category | Instances/Week | Time/Instance | Total Waste/Week |
|-----------------|----------------|---------------|------------------|
| Retrievable info blocking | 3-5 | 5-10 min | 15-50 min |
| Terminal navigation issues | 2-3 | 2-5 min | 4-15 min |
| Missing links | 3-5 | 1-3 min | 3-15 min |
| Sequential blocking | 1-2 | 10-60 min | 10-120 min |
| Preference repetition | 1-2 | 10-30 min | 10-60 min |
| **TOTAL** | **10-17** | **Variable** | **42-260 min/week** |

**Potential Time Saved:** 0.7 - 4.3 hours per week  
**Annual Impact:** 36 - 224 hours saved

**ROI of Creating Universal Template:**
- Template creation time: 2-4 hours
- Time to recoup investment: 1-6 weeks
- Annual ROI: 9x - 56x

### Prioritized Improvement List

**Priority 1: HIGH IMPACT (Add to Universal Template)**

1. **"NEVER BLOCK ON RETRIEVABLE INFO" - Expanded Examples**
   - Frequency: Very high
   - Time Saved: 5-10 min per instance
   - **Add:** Generic verification checklist (check README, check config files, check API, THEN ask)

2. **"ALWAYS INCLUDE CD COMMANDS" - Make Universal**
   - Frequency: High
   - Time Saved: 2-5 min per instance
   - **Add:** Template system adaptable to any user's directory structure

3. **"PROVIDE CLICKABLE LINKS" - Universal**
   - Frequency: High
   - Time Saved: 1-5 min per instance
   - **Add:** Link templates for common services (GitHub, cloud providers, docs sites)

4. **"PARALLEL WORK, ASK ONCE" - Core Workflow Principle**
   - Frequency: Medium-High
   - Time Saved: Variable, potentially hours
   - **Add:** Decision tree: Is this critical? Can other steps proceed? If yes, do them first.

5. **"CENTRAL PREFERENCES DOC" - Enforcement System**
   - Frequency: CRITICAL (why template is being created)
   - Time Saved: Prevents all categories of repetition
   - **Add:** Pre-flight checklist, standard location, update protocol

**Priority 2: MEDIUM IMPACT (Consider for Template)**

6. **Risk-Based Command Classification**
   - Generic categories (Safe/Medium/High)
   - User fills in project-specific commands
   - Auto-approval guidance

7. **Multi-Tool Compatibility Note**
   - Explicitly state: "Works with Copilot, ChatGPT, Claude, etc."
   - Platform-specific adaptations where needed
   - Core principles remain universal

8. **File Reference Standards**
   - Always use absolute paths OR clear relative path with context
   - Always make clickable/linkable
   - Include terminal command alternative

9. **External Service Link Templates**
   - Common services: GitHub, Google Cloud, AWS, Azure, etc.
   - User fills in their project IDs
   - AI always provides direct links

**Priority 3: VALUABLE (Nice to Have)**

10. **User Learning Profile Section**
    - "New to: terminal, VS Code, etc."
    - "Strong in: Sheets, Apps Script, etc."
    - Helps AI calibrate assumptions

11. **Multi-Repo Command Templates**
    - If user has multiple repos
    - Provide complete commands for all
    - Echo headers for clarity

12. **Success Verification Patterns**
    - Always include `echo "✅ Success message"`
    - Helps user confirm completion
    - Reduces follow-up questions

13. **Decision Authority Guidelines**
    - When AI can decide autonomously
    - When AI must ask user
    - Clear criteria for each

### Identified Gaps Not Yet in Existing Docs

**Gap 1: Multi-Tool Orchestration Guidance**
- **Issue:** User wants instructions that work across Copilot, ChatGPT, Claude, etc.
- **Current State:** Most docs are Copilot-specific
- **Needed:** Platform-agnostic core principles section

**Gap 2: Mobile/Web Access Instructions**
- **Issue:** User wants to access instructions from mobile, web, not just VS Code
- **Current State:** All docs assume VS Code environment
- **Needed:** Storage/distribution strategy for universal access

**Gap 3: Project-Specific vs Universal Split**
- **Issue:** Current docs mix project-specific with universal preferences
- **Current State:** Hard to extract general principles
- **Needed:** Clear separation - universal base + project overlays

**Gap 4: "Living Document" Enforcement**
- **Issue:** How to ensure AI tools actually read preferences?
- **Current State:** No pre-flight checklist or confirmation system
- **Needed:** Mechanism to enforce "read preferences before starting task"

**Gap 5: Risk-Based Command Classification for All Projects**
- **Issue:** "Always allow" commands are project-specific
- **Current State:** Only works for specific project
- **Needed:** Generic risk categories + project-specific implementations

---

## SECTION 3: IMPLEMENTATION ASSESSMENT

### Files/Processes to Create

**Primary Deliverable:**
- **File:** `MY_AI_WORK_STYLE.md` (or similar universal name)
- **Location:** 
  - Option A: GitHub gist (universally accessible, version controlled)
  - Option B: Google Drive (accessible on mobile, web)
  - Option C: Sync both (gist as source of truth, Drive as copy)
- **Structure:** 7 sections (see template below)

**Supporting Updates:**
- Update `.github/copilot-instructions.md` in each repo to reference universal template
- Update `USER_PREFERENCES_CRITICAL.md` to point to universal template
- Archive/consolidate scattered preference documents
- Create quick-reference card for mobile access

---

### Implementation Plan (Prioritized)

#### **P0: Critical - Immediate Value (Week 1, 2-3 hours)**

**Task 1.1: Create Universal Template Document (90 min)**
- Draft 7-section structure (see below)
- Extract universal principles from existing docs
- Add anti-patterns with corrections
- Include real examples from user's project
- **Deliverable:** `MY_AI_WORK_STYLE.md` v1.0
- **Success Metric:** Document covers top 5 repetition patterns

**Task 1.2: Store in Accessible Location (15 min)**
- Create GitHub gist (public or private based on preference)
- Upload to Google Drive in accessible folder
- Generate shareable link
- **Deliverable:** Universal URL for template
- **Success Metric:** Accessible from VS Code, web, mobile

**Task 1.3: Update Existing Instruction Files (30 min)**
- Update `.github/copilot-instructions.md`: Add reference to universal template at top
- Update `docs/USER_PREFERENCES_CRITICAL.md`: Point to universal template
- Update `docs/planning/copilot_instructions_best_practices.md`: Note existence of universal base
- **Deliverable:** All project docs reference universal template
- **Success Metric:** No more scattered/duplicate instructions

**Task 1.4: Test Across AI Tools (45 min)**
- Paste universal template into ChatGPT conversation → Test if it follows principles
- Reference universal template URL in Claude chat → Test if accessible
- Keep as-is in Copilot (already in repo) → Test if violations decrease
- **Deliverable:** Validation report showing effectiveness per tool
- **Success Metric:** <2 violations per tool in test session

---

#### **P1: High Value - Short Term (Week 2-3, 2-3 hours)**

**Task 2.1: Create Project-Specific Overlays (60 min)**
- Extract project-specific content from current copilot-instructions.md
- Create lightweight overlay format that references universal base
- Template: "Read MY_AI_WORK_STYLE.md + these project-specific additions: [repo paths, IDs, project commands]"
- **Deliverable:** Project overlay template
- **Success Metric:** Project-specific instructions reduced to <50 lines

**Task 2.2: Create Mobile Quick-Reference (30 min)**
- Extract top 10 principles into mobile-friendly format
- Single-page, bullet-point version
- Save as separate file: `MY_AI_WORK_STYLE_MOBILE.md`
- **Deliverable:** Quick reference for mobile use
- **Success Metric:** Readable on phone without scrolling/zooming

**Task 2.3: Add Enforcement Mechanism (45 min)**
- Create pre-flight checklist for AI tools
- Template prompt: "Before starting, confirm you've read [link to universal template]"
- Add to conversation starters in each tool
- **Deliverable:** Standard conversation starter template
- **Success Metric:** AI confirms reading template in first message

**Task 2.4: Document Maintenance Protocol (30 min)**
- When to update universal template (triggers)
- How to update (process)
- Version control approach (if using gist)
- Monthly review checklist
- **Deliverable:** Maintenance protocol doc
- **Success Metric:** Clear criteria for when/how to update

---

#### **P2: Nice to Have - Medium Term (Month 2, 1-2 hours)**

**Task 3.1: Create Project-Type Templates (60 min)**
- Identify common project patterns (trading, data analysis, web app)
- Create template variations for each type
- Store as separate files that reference universal base
- **Deliverable:** 3-5 project-type templates
- **Success Metric:** New projects start with appropriate template

**Task 3.2: Build Examples Library (30 min)**
- Collect successful prompts that followed template
- Collect failed prompts that violated template (with corrections)
- Add to universal template as appendix
- **Deliverable:** Examples section in template
- **Success Metric:** 10+ before/after examples

**Task 3.3: Track Violation Metrics (30 min)**
- Log each time AI violates a principle
- Monthly summary: Most frequent violations
- Update template to emphasize problem areas
- **Deliverable:** Violation tracking log
- **Success Metric:** Decreasing violation trend over 3 months

---

### Proposed Template Structure

```markdown
# MY AI WORK STYLE - UNIVERSAL INSTRUCTIONS

**Version:** 1.0  
**Last Updated:** [Date]  
**Purpose:** Single source of truth for how I work with AI tools (Copilot, ChatGPT, Claude, etc.)

---

## SECTION 1: NEVER DO THESE THINGS

### 1.1 Never Block on Retrievable Information
**Rule:** Before asking me to verify something, check these sources first:
- [ ] README.md and other docs
- [ ] Config files (.clasp.json, package.json, etc.)
- [ ] Available scripts (list project-specific ones if applicable)
- [ ] API calls if accessible
- [ ] Only ask if you encounter actual error

**Examples:**
- ❌ WRONG: "Please verify share status before I proceed"
- ✅ RIGHT: Run verification script, then proceed or report error

### 1.2 Never Assume Terminal Navigation
**Rule:** ALWAYS include `cd /full/path` before every terminal command
- I'm new to terminal/CLI
- Don't assume I know which directory to be in
- Provide complete, copy-paste ready commands

**Examples:**
- ❌ WRONG: `git status`
- ✅ RIGHT: `cd /Users/laptop/Documents/GitHub/[repo] && git status`

### 1.3 Never Reference Without Links
**Rule:** All file and service references must be clickable/actionable
- Files: Use absolute paths or clickable markdown links
- Services: Provide direct URLs with context (not "go to X settings")

**Examples:**
- ❌ WRONG: "Check the README file"
- ✅ RIGHT: "Check `README.md`" (clickable in VS Code)

### 1.4 Never Block on Non-Critical Input
**Rule:** Complete all parallel work before asking questions
- If task has 10 steps, only step 3 needs input → Do 1,2,4-10 first
- Make reasonable assumptions, document them, ask critical questions once

**Examples:**
- ❌ WRONG: Stop at step 3, wait for answer before doing step 4
- ✅ RIGHT: Complete steps 1,2,4-10, then present progress with consolidated questions

### 1.5 Never Assume Technical Defaults
**Rule:** Verify current state instead of assuming based on documentation
- Old docs may be outdated
- Check actual implementation before suggesting changes

---

## SECTION 2: ALWAYS DO THESE THINGS

### 2.1 Always Verify State First
Self-verification checklist before asking me anything

### 2.2 Always Include Directory Context
Every terminal command must include `cd` to correct directory

### 2.3 Always Provide Clickable Links
File references, external services, documentation - all must be actionable

### 2.4 Always Complete Parallel Work
Work in parallel, ask once - maximize progress before blocking on my input

### 2.5 Always Make Reasonable Assumptions
Document assumptions, proceed with work, let me correct if needed (vs blocking)

---

## SECTION 3: CORE PRINCIPLES

### 3.1 Task Elimination > Task Optimization
- Best solution is NOT doing the task
- Second best is doing it once and never repeating
- Always ask: "Is there a way to eliminate this entirely?"

### 3.2 Evidence-Based Decisions
- Provide data, metrics, examples
- "Why NOT alternatives" reasoning
- Confidence scores for recommendations

### 3.3 Copy-Paste Ready Workflows
- Single-block, complete commands
- Include comments explaining each step
- Success verification at end (`echo "✅ Done"`)

### 3.4 Platform-Agnostic Design
- These principles work across all AI tools
- Some tools may have specific adaptations (noted where relevant)

---

## SECTION 4: MY CONTEXT

### 4.1 Learning Profile
- **New to:** Terminal/CLI, VS Code, Git workflows
- **Strong in:** Google Sheets/Apps Script, JavaScript, trading/finance
- **Working across:** 2 laptops, multiple devices (desktop, mobile)

### 4.2 Communication Preferences
- Direct, concise explanations
- Show examples (before/after, wrong/right)
- Assume I'm smart but new to specific tools

### 4.3 Work Environment
- **Primary Tools:** VS Code, GitHub, Google Sheets/Apps Script
- **Repos:** Multiple GitHub repos (paths listed in project-specific overlays)
- **Cloud:** Google Cloud Platform, Google Drive

---

## SECTION 5: COMMAND RISK CLASSIFICATION

### Safe (Auto-Allow / Don't Prompt)
Read-only operations:
- `git status`, `git log`, `git diff`
- `cat`, `head`, `tail`, `grep`, `find`
- `ls -la`
- [Project-specific safe scripts listed in overlay]

### Medium (Show Intent, Proceed Unless I Stop You)
Reversible writes:
- `git add`, `git commit`, `git push`
- File edits (tracked by git)
- [Project-specific medium-risk operations]

### High (Always Confirm Explicitly)
Irreversible or production-impacting:
- `git reset --hard`, `git push --force`
- `rm -rf`
- Production job triggers
- [Project-specific high-risk operations]

---

## SECTION 6: TEMPLATES

### 6.1 Single Command Template
```bash
# [What this does]:
cd /full/path/to/repo
[command]
```

### 6.2 Multi-Step Template
```bash
# [What this accomplishes]:
cd /full/path/to/repo

# Step 1: [description]
[command1]

# Step 2: [description]
[command2]

# Verify success
echo "✅ [Success message]"
```

### 6.3 Multi-Repo Template
```bash
# [What this does across all repos]:

echo "=== [Repo1] ==="
cd /full/path/to/repo1
[commands]

echo -e "\n=== [Repo2] ==="
cd /full/path/to/repo2
[commands]

echo -e "\n✅ Completed for all repos"
```

### 6.4 External Link Template
"[Action description] at [Service Name - Specific Page]([direct URL with params])"

Example:
"Enable the API at [Google Cloud Console - APIs & Services](https://console.cloud.google.com/apis/dashboard?project=YOUR_PROJECT)"

---

## SECTION 7: MAINTENANCE

### When to Update This Document
- I say "I've mentioned this multiple times" → Add to NEVER DO section
- AI violates a principle → Add to anti-patterns with correction
- New pattern emerges across multiple AI tools → Generalize and add

### How to Update
1. Edit source document (GitHub gist or Drive)
2. Update version number and date at top
3. Propagate changes to project-specific overlays if needed
4. Notify AI tools if significant changes ("Re-read updated template")

### Monthly Review
- Are principles being followed? (Track violations)
- What's working well? (Keep/emphasize)
- What needs clarification? (Refine wording)
- New patterns emerged? (Add to document)

---

## APPENDIX: PROJECT-SPECIFIC OVERLAYS

This universal template is supplemented by lightweight project-specific overlays that reference this document and add:
- Repo-specific paths
- Project-specific spreadsheet IDs, script names
- Custom command classifications for that project
- Domain-specific conventions

See project repos for their specific overlays.
```

---

### Time Estimates

**P0 (Week 1):**
- Template creation: 90 min
- Storage setup: 15 min
- Update existing docs: 30 min
- Testing: 45 min
- **Total:** 3 hours

**P1 (Week 2-3):**
- Project overlays: 60 min
- Mobile quick-reference: 30 min
- Enforcement mechanism: 45 min
- Maintenance protocol: 30 min
- **Total:** 2.75 hours

**P2 (Month 2):**
- Project-type templates: 60 min
- Examples library: 30 min
- Violation tracking: 30 min
- **Total:** 2 hours

**Grand Total:** 7.75 hours

---

### Expected ROI

**Time Investment:** 7.75 hours (all phases)  
**Time Savings:** 40-260 min/week  
**Payback Period:** 2-12 weeks  
**Annual ROI:** 4.6x - 29x

**Conservative Estimate (40 min/week saved):**
- Annual savings: 34.7 hours
- ROI: 4.6x

**Optimistic Estimate (260 min/week saved):**
- Annual savings: 225 hours
- ROI: 29x

---

### Success Metrics

**Week 1 (Post-P0):**
- [ ] Universal template exists and accessible from all devices
- [ ] Top 5 repetition patterns documented
- [ ] 0 violations in first test session with each AI tool

**Month 1 (Post-P1):**
- [ ] <5 total violations across all AI tools
- [ ] <2 instances of having to repeat preferences
- [ ] Project-specific docs reduced to <50 lines each

**Month 3 (Post-P2):**
- [ ] Decreasing violation trend (compared to Month 1)
- [ ] 10+ successful examples in library
- [ ] Time savings confirmed (track actual minutes saved)

---

### Cross-Project Impacts

**Immediate:**
- Candle_Data_Analysis_V2: Reference universal template in copilot-instructions.md
- C-DollasP1: Add universal template reference
- C-DollasP2: Add universal template reference
- Future projects: Start with universal template + project overlay

**Long-Term:**
- Consistency across all AI tool interactions
- Faster onboarding of new projects
- Reduced mental overhead (one place to maintain preferences)
- Easier collaboration (others can read universal template to understand work style)

---

### Open Questions / Decisions Needed

**Decision 1: Storage Location**
- Option A: GitHub gist (public/private?) - Version controlled, easy to share
- Option B: Google Drive - Accessible on mobile, familiar
- Option C: Both (gist as source, Drive as sync copy)
- **Recommendation:** Option C for redundancy and flexibility

**Decision 2: Enforcement Approach**
- Option A: Manual (paste template URL in each conversation)
- Option B: Pre-flight checklist prompt ("Did you read X?")
- Option C: Assumption (rely on project instructions referencing universal template)
- **Recommendation:** Option B for explicit confirmation

**Decision 3: Project-Specific Split**
- How much should be in universal template vs project overlays?
- Current threshold: If it applies to 2+ projects OR 2+ AI tools → Universal
- **Recommendation:** When in doubt, put in universal (consolidation bias)

**Decision 4: Mobile Access Priority**
- Should mobile quick-reference be P0 or P1?
- Depends on how often you access AI tools from mobile
- **Recommendation:** Keep as P1 unless mobile is daily use case
