# Definitions & Frameworks 

> **Purpose:** Standard reference definitions to prevent repeated explanations across projects and AI tool conversations.

This page summarizes the key concepts (SBPC, STIG1, Resource Coverage System, AI TOOLs) used across repos so they can be referenced from any AI TOOL or platform.

  

---



## SBPC – Strategic Best Path with Coverage

**Definition:**  
SBPC (Strategic Best Path with Coverage) is the fastest and most efficient way to achieve stated goals that is within reasonable access of resources and personal comfort boundaries **and** has been selected after a minimum level of Resource Coverage has been applied (i.e., we looked broadly enough that we are unlikely to be missing an obviously better option within reasonable reach).

**Note:** Previous name was THE SOLUTION and may not have been updated in all locations. SBPC is the current preferred term.

### Qualification Criteria

1. **No Significantly Better Alternative:**  
   - There is no other known solution that is significantly more efficient and faster.
   - No one can prove a better solution exists.
   - Won't discover a superior option later that could have been found with proper research.

2. **No Upstream Elimination:**  
   - There isn't a reasonable solution or system "above this" that would completely remove the need for this task or problem being solved in the first place.
   - **Example:** Instead of creating efficient spreadsheet export scripts, implementing Copilot API integration with Drive access eliminated the export task entirely (upstream elimination).

3. **Within Resource Access:**  
   - Solution is accessible with available resources (financial, technical, time).
   - Doesn't require resources significantly outside current capacity.

4. **Within Comfort Boundaries:**  
   - Doesn't cross moral boundaries.
   - Example of outside comfort: Business models that profit from others' suffering.
   - Aligns with personal values and ethical standards.

### Validation Process

When evaluating if something is SBPC:

1. ✅ **Effectiveness Check:** Is there any alternative that is significantly better (faster, more efficient)?
2. ✅ **Upstream Check:** Is there a higher-level solution that eliminates the need entirely?
3. ✅ **Access Check:** Can this be implemented with available resources?
4. ✅ **Comfort Check:** Does this align with personal boundaries and values?
5. ✅ **Coverage Check:** Has a reasonable Resource Coverage level been applied so that we are unlikely to be missing an obviously superior option that is accessible?

### Usage Examples

**Correct:**  
- "Copilot API integration is SBPC for spreadsheet data access - it eliminates the export task upstream"

**Not SBPC (but good solutions):**  
- A solution that works but a significantly better option exists
- A solution that addresses a problem that could be eliminated entirely
- A temporary workaround when a permanent fix is possible
- A solution outside resource access or comfort boundaries

---



## Resource Coverage System


**Goal:**  
Ensure that when we search for solutions (for example, methods that satisfy STIG1), we cover **all reasonably accessible, low-to-medium effort resources**, and we know what we did and did not look at.

At a high level, the Resource Coverage System:
- Defines **coverage levels** (e.g. L1/L2/L3) that specify:
  - Which source types to search (public web, paid tools, research platforms, etc.).
  - How deep to go in each (queries, pages, tools, time).
- Produces a **Coverage Report** that answers:
  - What categories and sources were searched.
  - What was explicitly skipped (with reasons).
  - Any known gaps or limitations.
- Is used as part of SBPC validation to reduce the risk of missing obvious, accessible options.

### Coverage Levels

- **Level 1 – Minimal:**  
  - A handful of obvious searches and a surface scan of big-name services.  
  - Mostly useful for quick sanity checks, not for SBPC decisions.

- **Level 2 – Reasonable (Recommended Baseline):**  
  - For each major method category (e.g., trading, online businesses, services), AI TOOLs:  
    - Use a defined query playbook (for example, 10–20 search patterns with operators). Document what queries were performed and where.
    - Check top N results on major indexes (Google, YouTube, maybe one alt source) and a few "meta" threads (e.g., "X ways people earn $10k/day").  
    - Survey known "lists of lists" and aggregator posts.  
    - Cross-reference candidate methods against goal filters and constraints.

- **Level 3 – Aggressive:**  
  - Everything in Level 2, plus:  
    - Systematic exploration of niche communities, forums, and smaller search indexes.  
    - Proactive use of paid tools/services for discovery (within a set budget).  
    - Potential structured outreach or expert interviews (if desired).

### Measuring Coverage

**Quantitative Metrics:**
- Number of distinct search queries used
- Number of distinct sources (domains/platforms) touched
- Method categories covered
- Candidate methods found and evaluated

**Qualitative Metrics:**
- "What did we look at?"
- "What did we explicitly skip and why?"
- "What known patterns of missed hits are we vulnerable to?" (for example, non-English sources)

### Choosing Coverage Guarantee Strength

- **Option A – Pragmatic Guarantee:**  
  "We did Level 2 coverage; we're unlikely to have missed any big, widely known, reasonably documented methods."

- **Option B – Stronger Guarantee:**  
  "We did Level 2 + targeted Level 3; it is unlikely that any easy-to-access method of similar scale exists that we did not at least see and either keep or explicitly reject."

---

## AI TOOLs

**Definition:**  
The collective suite of AI-powered development and problem-solving tools currently in use, with emphasis on intelligent model selection and multi-tool validation.

### Included Tools

1. **ChatGPT (All Models & Features):**
   - Latest GPT models
   - o1-preview (complex reasoning)
   - o1-mini (efficient reasoning)
   - Deep Research (comprehensive internet research)
   - Canvas (iterative editing)
   - Data Analysis mode
   - Voice mode

2. **GitHub Copilot (All Configurations):**
   - Copilot Chat (latest models)
   - Inline Chat
   - Code completions
   - Copilot Edits (multi-file editing)
   - Code Reviews

3. **Codex:**
   - Various model configurations
   - API integration capabilities

4. **Other AI Platforms:**
   - Gemini (Google)
   - Claude (Anthropic)
   - Other emerging tools as they become relevant

### Usage Strategy

**Standard Practice:**
- **Minimum:** Try 2-3 tools that currently provide highest quality results
- **High-Impact Items:** Try 6+ different tool/model combinations
- **Complex Problems:** Multiple prompts across multiple tools

---


## SBPC Quality Validation (AI Guardrails)

When using AI TOOLs to support SBPC decisions:

1. **Multiple Tool Validation**
   - Never trust a single model/tool for high‑impact SBPC calls.
   - Cross‑check key conclusions with 2–3+ tools or model variants.
   - Higher stakes ⇒ more tools + more prompt variations.

2. **Evidence Requirement**
   - Require sources, concrete data, or backtests where possible.
   - Reject shallow "top 3 Google results" style answers.
   - Watch for "contaminated context" (AI relying on bad assumptions or stale constraints).

3. **Upstream Thinking**
   - Always ask: "Is there a higher‑level approach that removes this work?"
   - Example: prefer an integration that eliminates a task over optimizing a manual workaround.

---

## Integration with Other Frameworks

### P0/P1/P2 Priority System
- **SBPC-targeted work** (e.g., projects aiming at goals like STIG1) is always treated as **P0** because it directly blocks milestone goals.
- For P0 items, AI TOOLs **must** follow SBPC Quality Validation:
  - Multi-tool validation
  - Evidence requirement
  - Upstream thinking
- P1/P2 items can use lighter-weight approaches (fewer tools, faster models).

### Task Elimination Framework
- Before implementing any SBPC path, always check for **upstream elimination**:
  - Ask: "Is there a higher-level change (integration, automation, process change) that removes this task or goal entirely?"
- When a higher-level change removes a lower-level task, that upstream change is the new SBPC.
- Track an "elimination ratio" (how many downstream tasks disappear) as one signal of SBPC quality.

### Resource Coverage
- SBPC candidates must be **discoverable through the Resource Coverage System** at the chosen Coverage Level (L1/L2/L3).
- If a supposed "best path" only appears when coverage is weak or narrow, treat it as **not fully SBPC-validated**.
- If we can't find an SBPC after running the agreed Coverage Level, the next step is:
  - Improve coverage (queries, sources, tools), or
  - Switch to "construct a method" projects (e.g., pattern‑mining/backtesting).

---

## Examples from Project History

### Example 1: Spreadsheet Export Task
- **Initial Problem:** Need efficient way to export spreadsheet data to ChatGPT
- **Attempted Solution:** Create export scripts (CSV, JSON automation)
- **SBPC:** Copilot API integration with Drive access
- **Why:** Eliminated export task entirely (upstream elimination)
- **Result:** 1:∞ elimination ratio, zero ongoing maintenance

### Example 2: Model Selection for Use Cases
- **Problem:** Which AI model for which task?
- **Not SBPC:** "Use ChatGPT for everything" (not optimized)
- **SBPC:** Hybrid model approach:
  - Deep Research + Newest Strongest GPT Model: Pre-market analysis, financial frameworks
  - o1-preview + Data Analysis: Strategy development, feature bank
  - Copilot + o1: Code generation
  - 4o + Data Analysis: Backtest analysis, trade reviews
- **Why:** Each model optimized for specific task requirements

---

## How to Use This Page with AI TOOLs

When starting a new conversation with any AI TOOL that cannot directly see your repos, you can:

1. Share the link to this page and say:  
   "When I say SBPC, STIG1, or AI TOOLs, use the definitions at: [your-github-pages-url]"
2. Optionally paste short definitions as a preamble.

This reduces how often you have to re-explain core concepts.

---

## When to Reference These Definitions

**Use SBPC:**
- When evaluating if current approach is optimal
- When someone suggests "just use X" without validation
- When determining if more research is needed
- When prioritizing tasks (elimination vs. optimization)

**Use AI TOOLs:**
- When discussing which models/tools to use
- When establishing quality standards for AI responses
- When explaining multi-tool validation approach

**In Documentation:**
- Always use consistent terminology (SBPC, AI TOOLs)
- Link to this page when using terms
- Update this page if definitions evolve

---

**Last Updated:** November 16, 2025
