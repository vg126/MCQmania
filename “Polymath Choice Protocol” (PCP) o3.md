<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" class="logo" width="120"/>

# “Polymath Choice Protocol” (PCP)

*A universal template that turns any complex task into a batch-MCQ conversation between a Human Decider and an AI Executor*

## 0. Overview

PCP is a lightweight but extensible schema.

- It captures *all* user intent (even messy tangents).
- It presents decision points as **batches of 3-4 options + “Other/Free-text”**.
- It preserves full context across rounds.
- It ends with a structured “Decision Ledger” the Executor AI can act on or export to another tool/app.


## 1. Roles

| Role | Capability | Responsibilities |
| :-- | :-- | :-- |
| **Human Decider (HD)** | Strategic vision, preference, intuition | Chooses options, writes free-text comments |
| **MCQ Engine (AI-Front)** | Domain analysis, question framing | Generates batched MCQs, digests messy input into structured picks |
| **Executor AI (AI-Back)** | Technical work, synthesis | Consumes the Decision Ledger, produces deliverables (code, plans, etc.) |

## 2. Conversation Phases

1. **Kick-off** – HD states goal in free text.
2. **Batch-MCQ Generation** – MCQ Engine returns *N* (default = 5) MCQs.
3. **Response Harvest** – HD selects an option per MCQ and may append any commentary.
4. **Context Merge** – MCQ Engine stores choice + commentary in the Ledger.
5. **Repeat** – Continue until HD types “/synthesize” (or predetermined convergence rule).
6. **Synthesis / Handoff** – Executor AI consumes the Ledger and acts.

## 3. Data Structures

### 3.1 Decision Ledger (single canonical JSON object)

```jsonc
{
  "session_id": "auto-uuid",
  "goal": "<HD kickoff text>",
  "mcq_batches": [
    {
      "batch_id": 1,
      "questions": [
        {
          "id": "Q1",
          "prompt": "…",
          "options": {
            "A": "…",
            "B": "…",
            "C": "…",
            "D": "…",
            "X": "Other"
          },
          "selection": "B",
          "commentary": "HD free-text",
          "timestamp": "ISO-8601"
        }
        …
      ]
    }
    …
  ],
  "final_notes": "",
  "status": "in-progress | synthesized"
}
```


### 3.2 MCQ Template (markdown sent to HD)

```markdown
### Batch {{batch_id}}

**Q{{num}}. {{prompt}}**  
A. {{option_A}}  
B. {{option_B}}  
C. {{option_C}}  
D. {{option_D}}  
X. Other (explain)  
```


## 4. MCQ Generation Rules

1. **Batch Size**: 3–7 questions (tunable).
2. **Option Count**: 3–4 concrete options + X(Other).
3. **Clarity over Jargon**: Titles plain-language; deeper tech details within each option’s 1-sentence rationale.
4. **Mutual Exclusivity**: Options should not overlap.
5. **Spread**: Cover the space (e.g., conservative → radical, low → high complexity).
6. **Tagging**: Each option internally marked with tags (`["ui","color"]`, `["arch","monolith"]`, etc.) for downstream filtering.
7. **Difficulty Flag** *(optional)*: `difficulty: 1–5` meta-field per MCQ if HD requested gradients.

## 5. Response Syntax for HD

HD may reply in any style, but the engine must be able to parse one of:

- `Q1:B  Q2:D  Q3:X=“My custom idea…” …`
- Natural prose (the engine will fuzzy match).
- Voice transcript (same parsing rule).


## 6. Context-Preservation Logic

After each batch:

1. Append selections \& commentary to Ledger.
2. Recompute “Known Constraints” summary (≤ 120 words).
3. Future MCQs must:
    - Avoid re-asking settled topics.
    - Reference past picks when relevant (`“Earlier you chose a Free-Form UI; now pick the color palette”`).

## 7. Synthesis Blueprint (what the Executor receives)

1. **Executive Summary** – 1-paragraph distilled purpose.
2. **Constraints \& Preferences** – bullet list from tags.
3. **Ordered Decision List** – each Q with chosen option \& rationale.
4. **Open Items** – MCQs marked “X/Other” that need creative filling.
5. **Recommended Next Actions** – auto-suggested workflow steps.

## 8. Extensibility Hooks

- `pre_generator()` – inject custom domain ontology before MCQ generation.
- `post_synthesis()` – custom renderers (code scaffolders, spec writers, UI mockers).
- `export(format="yaml|json|markdown")` – produce artifacts for IDEs, PM tools, etc.


## 9. Minimal Example Flow (compressed)

HD: “I want a habit-tracking mobile app.”
AI: (Batch 1)
Q1. Platform? A-iOS, B-Android, C-Cross-platform, D-Web, X-Other
Q2. Data store? A-Local, B-Firebase, C-Postgres Cloud, D-NoSQL, X
Q3. UI tone? A-Playful, B-Minimal, C-Business, D-Dark, X
HD: “Q1:C Q2:B Q3:A. Also it must work offline.”
AI logs, summarizes, generates Batch 2 focusing on sync strategy, gamification, etc.
…
HD types “/synthesize”.
Executor AI receives structured Ledger → outputs Flutter scaffold \& design brief.

## 10. Usage Cheat-Sheet

- Kick-off prompt → “Generate first batch.”
- During loop → “Next batch” or “Why am I seeing this question?”
- At any time → “Show Ledger” to audit.
- Done → “/synthesize”.


### End of Polymath Choice Protocol Template

