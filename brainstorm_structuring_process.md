# Brainstorm Structuring Process

**Purpose:** Convert unorganized high-value brainstorms into actionable documentation

**When to Use:** When you have ideas/concepts that are high-impact but struggling to articulate clearly

---

## 🎯 THE PROCESS

### **Step 1: User Provides Brainstorm**

**What to include:**
- Raw thoughts (don't worry about organization)
- Context: What problem you're solving
- Why you believe it's high-value
- Any examples that illustrate the concept

**Template:**
```
I have a brainstorm about [TOPIC]. 

Context:
[What led to this thinking]

The brainstorm:
[Your raw notes]

Why I think this is high-value:
[What problem this solves / opportunity this addresses]

Examples:
[Real situations that illustrate the concept]
```

---

### **Step 2: AI Tool Creates Structured Document**

**Document must contain 3 sections:**

#### **Section 1: Raw Brainstorm**
- Preserve user's exact wording
- No edits, no cleanup
- Purpose: Maintain original intent/nuance

#### **Section 2: Revised/Structured Analysis**
AI analyzes:
- What is the core problem being described?
- Why is this high-impact? (quantify if possible)
- What patterns/themes emerge?
- What's the underlying principle?
- How does this connect to user's goals?

Then provides:
- **Structured version** with clear problem statement
- **Core concepts** identified and labeled
- **Real examples** from user's project
- **Why high-value** explanation with evidence

#### **Section 3: Implementation Assessment**

AI provides:
- **What to do with this information:**
  - Which files need updates
  - Which processes need changes
  - Which todos this relates to
  - What new workflows are needed

- **Prioritization:**
  - Rank by (Impact × Feasibility)
  - P0 (do now), P1 (this month), P2 (later)
  - Estimated time for each

- **Success metrics:**
  - How to measure if implementation worked
  - Leading vs lagging indicators

- **Cross-project impacts:**
  - What else this affects
  - Dependencies with other work

---

### **Step 3: Create Todo/Task**

**Todo format:**
```
Title: [Concise description of what gets implemented]

Description:
- Problem solved: [1-2 sentences]
- File: [Where documentation lives]
- Implementation: [P0/P1/P2 phases with time estimates]
- Expected ROI: [Measurable impact]
- Related todos: [#X, #Y that this connects to]
- Status: not-started
```

---

### **Step 4: Save & Commit**

**File location:**
- High-impact strategic: `docs/brainstorms/[descriptive-name].md`
- Process/workflow: `docs/processes/[name].md`
- Technical design: `docs/design/[name].md`

**Commit message:**
```
docs: [brief description] - [core benefit]

Example:
docs: AI context contamination framework - addresses 12x time waste root cause
```

---

## 📋 PROMPT TEMPLATE FOR USER

```
I have a high-value brainstorm. Please use the Brainstorm Structuring Process.

CONTEXT:
[What problem/goal this relates to]

RAW BRAINSTORM:
[Your unorganized notes]

WHY HIGH-VALUE:
[What this solves / enables]

EXAMPLES:
[Real situations from your work]

Please create:
1. Todo with effective name
2. Document with 3 sections (Raw / Revised / Implementation)
3. Commit to appropriate location
```

---

## 🎯 QUALITY CHECKLIST

Before completing, verify:

**Section 1 - Raw:**
- [ ] User's exact words preserved
- [ ] All examples included
- [ ] Context maintained

**Section 2 - Revised:**
- [ ] Core problem clearly stated
- [ ] Why high-impact explained with evidence
- [ ] Structured into logical sections
- [ ] Real examples from user's project
- [ ] Patterns/principles identified

**Section 3 - Implementation:**
- [ ] Specific files/processes identified
- [ ] Prioritized by ROI (P0/P1/P2)
- [ ] Time estimates provided
- [ ] Success metrics defined
- [ ] Cross-project impacts noted

**Todo:**
- [ ] Concise title
- [ ] Problem + solution + ROI in description
- [ ] File path included
- [ ] Related todos linked

**Commit:**
- [ ] Document saved to correct location
- [ ] Committed to git
- [ ] Pushed to GitHub (accessible from any device)

---

## 🔄 PROCESS IMPROVEMENTS

Track what works:
- Which prompts led to clearest outputs?
- What context was missing that caused confusion?
- How can template be refined?

Monthly review:
- Are brainstorms getting implemented?
- What's the time from brainstorm → implementation?
- Success rate: Did implementation achieve expected ROI?

---

## 📞 QUICK REFERENCE

**User says:** "I have ideas but struggling to organize them"

**AI responds:**
1. "Let's use the Brainstorm Structuring Process. Share your raw thoughts."
2. Create 3-section document (Raw / Revised / Implementation)
3. Add todo with prioritized action plan
4. Commit to git

**Output:** Actionable documentation + clear next steps
