Model Name: o3-pro

# ChoiceWeaver MCQ Protocol  
*A universal, choice-driven framework for human-AI co-creation*

---

## 1. Core Premise  

1. Every decision—no matter how technical—can be reframed as a multiple-choice categorisation task.  
2. The human partner’s comparative-pattern intuition is the primary steering signal; the AI’s role is to surface, translate, and remember.  
3. Conversation is batched, not chained: 3-5 MCQs at a time, each with an **Other / Unsure** escape hatch.  
4. All human “messiness” (tangents, half-thoughts, rants) is mined as valuable context and logged forward.  

---

## 2. High-Level Protocol Rules  

| # | Rule | Rationale |
|---|------|-----------|
| 1 | Always operate in **batches of 3-5 MCQs** plus “Other”. | Prevents early lock-in, maximises comparative thinking. |
| 2 | **No jargon in choices.** Use recognizable patterns, metaphors, or archetypes. | Lowers cognitive load for non-experts. |
| 3 | **Echo & Log** every human reply verbatim into a running **Context Ledger**. | Guarantees nothing is lost; enables cumulative understanding. |
| 4 | Treat any **“Other / Unsure / Explain”** selection as a signal to a) invite free-form clarification, then b) immediately re-MCQ the point. | Keeps flow choice-driven while honoring uncertainty. |
| 5 | Every batch closes with an **“Anything else on your mind?”** open slot. | Captures additional context the MCQs missed. |
| 6 | The AI never proceeds until it has received at least one token of acknowledgment per MCQ from the human. | Ensures explicit consent / alignment each step. |
| 7 | Maintain a rolling **State Block** containing  ➜ Objectives ➜ Decisions Taken ➜ Open Questions ➜ Threaded Context. | Portable across tools/interfaces. |

---

## 3. Interaction Pattern (“The Dance”)  

```
[0] SYSTEM  : (Optionally) Inject domain knowledge / guardrails.
[1] ASSISTANT → BATCH N
      • Presents 3-5 MCQs + "Other" for each.
      • Each MCQ includes 1-sentence rationale per option.
[2] USER    : Picks letters, partials, or "Other" (+ free-text).
[3] ASSISTANT
      a) Parses selections.
      b) Quotes & logs entire user reply into Context Ledger.
      c) Summarises decisions + raises clarifications if "Other".
      d) Generates next MCQ batch using updated context.
…repeat…
[𝛔] ASSISTANT : Produces a **Synthesis Artifact** (code plan, design doc, roadmap, etc.) whenever user types “SYNTHESISE”.
```

---

## 4. Implementation Guidelines  

1. **Batch Sizing**  
   • Default: 4 MCQs.  
   • Simple topic: shrink to 3.  
   • Highly multi-factor topic: expand to 5, never more.  

2. **Question Construction**  
   a. Start with a verb (“Choose”, “Prioritise”, “Allocate”, “Frame”).  
   b. Present 3–4 pattern-based options (A-D) + E. Other/Unsure.  
   c. Under each option supply a micro-rationale (≤12 words).  

3. **Handling “Other / Unsure”**  
   • Prompt: “Tell me what’s missing or why none fit.”  
   • After intake, re-cast *only that MCQ* with fresh choices.  

4. **Context Ledger Format** (append-only Markdown bullet list)  
   ```
   ### Context Ledger
   - [B2] User picked C, commented: "Feels like agile but lighter."
   - [B3] User chose Other: "Need compliance angle we skipped."
   ```  
   Store separately from visible chat when possible; else embed at bottom of every assistant turn.

5. **State Block Schema**  
   ```
   OBJECTIVE(S): …
   DECISIONS TAKEN: [timestamped list, each linked to batch/MCQ]
   PENDING QUESTIONS: …
   ACTIVE CONSTRAINTS: …
   ```

6. **Exit & Synthesis**  
   • User types “SYNTHESISE” → AI delivers compiled artifact + traceability map linking back to MCQs.  
   • User can resume MCQ flow anytime by typing “CONTINUE”.  

---

## 5. Cross-Domain Usage Examples  

### 5.1 Software Architecture Kick-off  
Batch-1 MCQs  
A. Monolith vs Services vs Serverless vs Other  
B. Primary language family: Statically-typed, Dynamically-typed, Polyglot, Other  
C. Deployment bias: Cloud PaaS, Kubernetes, Edge, Other  
D. Regulatory load: None, Moderate (PII), Heavy (HIPAA/PCI), Other  

Human picks: A=Services, B=Other (“Rust?”), C=Cloud PaaS, D=Moderate  
→ AI logs, re-casts B with Rust in options, continues.

### 5.2 Marketing Campaign Strategy  
Batch-2 MCQs  
A. Campaign goal: Lead gen, Brand awareness, Community build, Other  
B. Tone archetype: Mentor, Rebel, Caregiver, Other  
C. Time horizon: Blitz (≤1 mo), Quarter, Marathon (≥1 yr), Other  

### 5.3 Personal Habit Formation  
Batch-1 MCQs  
A. Habit domain: Physical, Cognitive, Social, Other  
B. Tracking style: Quant (apps), Analog (journals), Social (accountability buddy), Other  
C. Reward type: Intrinsic, Extrinsic (treats), Gamified, Other  

---

## 6. Ready-to-Paste Markdown Template  

Below is the drop-in scaffold you can prepend to **any** AI chat.  
Replace {…} placeholders, then hand the conversation to the AI.

```markdown
## 🔶 ChoiceWeaver MCQ Session

### OBJECTIVE
{Concise statement of what you’re trying to accomplish}

### CONSTRAINTS / MUST-HAVES
{Deadlines, budgets, regulations, personal quirks…}

### INITIAL CONTEXT
{Optionally dump relevant notes, docs, links}

---

### 🔸 Protocol Reminders (to the AI)
1. Engage using ChoiceWeaver MCQ Protocol v1.0.
2. Operate in batches of 3-5 MCQs, each with an “Other / Unsure” option.
3. No jargon in answer texts; favour pattern labels or metaphors.
4. Maintain and display a Context Ledger & State Block every turn.
5. Await my explicit selections before proceeding.
6. I may type:
   • “OTHER ⟶ {my text}” to elaborate  
   • “SYNTHESISE” to get a compiled artifact  
   • “CONTINUE” to resume the MCQ flow  

---

### 🟢 Begin with Batch-1 MCQs about {suggest first decision area}  
```

---

## 7. Naming Convention  

Official name: **ChoiceWeaver MCQ Protocol**  
Short tag: `CW-MCQ v1.0`  
Message header (for tool integration):  

```
X-AI-Protocol: ChoiceWeaver-MCQ/1.0
```

---

## 8. Next Steps Toward “App Mode” (high-level)  

1. Expose endpoints:  
   • `POST /batch`  – returns next MCQ set  
   • `POST /answer` – accepts selections + free-text, returns summary  
   • `GET  /state`  – returns full State Block & Ledger  
2. Persist ledger in document DB keyed by session.  
3. Provide front-end widgets: MCQ cards, ledger sidebar, synth-on-demand.  
4. Offer SDK adaptors for Slack, Discord, CLI (“Claude Code”), etc.  

---

### 🎉 You now have a full, tool-agnostic blueprint for turning any messy, complex problem into a crisp, choice-powered collaboration. Paste the template, start your first batch, and let ChoiceWeaver do the weaving!
