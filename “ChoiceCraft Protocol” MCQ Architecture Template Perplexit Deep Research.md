<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" class="logo" width="120"/>

# “ChoiceCraft Protocol” MCQ Architecture Template

## 1. Protocol Overview

**Name:** ChoiceCraft Protocol
**Purpose:** Transform any complex domain or task into a structured, choice-driven workflow that leverages human pattern-recognition and decision-making strengths.

## 2. Core Principles

1. **Batch MCQs**
    - Present multiple (3–5) multiple-choice questions at once, plus an “Other” option.
    - Encourage non-linear exploration and prevent premature narrowing of focus.
2. **Mess-to-Intent Translation**
    - Accept and record freeform responses, justifications, tangents, and clarifications.
    - Extract and embed user insights from “messy” input into the evolving context.
3. **Context Accumulation**
    - Maintain a running context log of all MCQs, answers, and user annotations.
    - Carry forward every piece of input—choices, justifications, and tangential notes.
4. **Flexible Structure**
    - Rules constrain only question count (3–5 options + “Other”) and answer capture format.
    - Content, language, and granularity adapt to topic, user cognitive style, and project phase.
5. **Bucket-Based Cognition**
    - Frame options as intuitive “buckets” that align with the user’s pattern recognition, not technical jargon.
    - Each choice label includes a concise tag and optional plain-language explanation.

## 3. Template Structure

### A. Initialization Block

```markdown
**Project Name:** [Your Project Title]  
**Domain / Topic:** [e.g., “ML Model Architecture”]  
**Objective:** [High-level goal statement]  
**User Profile Tags:** [e.g., “ADHD-style, top-down thinker”]  
**Initial Context Summary:**  
> [Brief freeform context or pasted notes]  
```


### B. MCQ Batch Definition

```markdown
### Step 1: Define Decision Points  
- Identify up to N key decision categories for this phase.  
- For each category, craft an MCQ with 3–5 distinct options + “Other.”  

#### Example MCQ  
1. **Category:** Model Paradigm  
   - A) Transformer-based [“Self-attention focus”]  
   - B) Convolutional [“Local feature extraction”]  
   - C) Recurrent [“Sequential dependency”]  
   - D) Graph-based [“Relational structures”]  
   - E) Other (please specify)  
```


### C. Answer \& Annotation Capture

```markdown
### Step 2: Capture Responses  
- For each MCQ, record:  
  1. **Selected Option(s):** [A–E]  
  2. **Justification / Tangents:** [Freeform text]  
  3. **Tags / Keywords Extracted:** [Auto-extracted or user-provided]  
```


### D. Context Update \& Reflection

```markdown
### Step 3: Context Synthesis  
- Append each response as a new node in the context log.  
- Summarize emerging themes or preferences.  

> **Context Log Entry:**  
> - MCQ1→B; “Prefer sequential reasoning”; tags: #sequence, #temporal  
> - MCQ2→D; “Need relational mapping”; tags: #graph, #relations  
```


### E. Iteration \& Generation

```markdown
### Step 4: Next-Phase Generation  
- Based on the updated context log, generate the next batch of MCQs or propose concrete deliverables.  
- Continue until objectives are met.  
```


## 4. Implementation Notes

- **“Other” Option Processing:** Treat open-text “Other” answers as mini-prompts—parse and integrate into context log.
- **Batch Size Tuning:** Default to 4 options; adjust to 3–5 based on complexity and user preference.
- **Tagging Conventions:** Always accompany numeric keys with descriptive tags (e.g., “\#UI”, “\#Performance”).
- **Context Log Format:** Maintain as an append-only chronologically ordered list.


## 5. Template Usage Example

```markdown
**Project Name:** Chatbot UI Design  
**Domain / Topic:** “User interface considerations”  
**Objective:** “Define core UI features for a conversational assistant.”  
**User Profile Tags:** ADHD-style, visual learner  
**Initial Context Summary:**  
> Needs highly visual, low-cognitive-load interface with color-driven cues.

### MCQ Batch  
1. **Primary Interaction Mode**  
   - A) Text input only  
   - B) Voice commands  
   - C) Hybrid text+voice  
   - D) Button-driven menus  
   - E) Other (specify)

2. **Color Theme**  
   - A) Cool tones (blue/green)  
   - B) Warm tones (red/orange)  
   - C) High-contrast (black/white)  
   - D) Pastel palette  
   - E) Other (specify)

### Responses  
- MCQ1→C; “Hybrid suits multi-modal users”; tags: #hybrid, #accessibility  
- MCQ2→A; “Calming colors reduce cognitive load”; tags: #calm, #lowLoad

### Context Log  
- Entry1: MCQ1→C; #hybrid, #accessibility  
- Entry2: MCQ2→A; #calm, #lowLoad  

### Next-Phase  
Generate wireframe layout emphasizing a combined text/voice input field with blue-green accent buttons.
```


## 6. Next Steps

1. **Validate Template:** Review and tailor option counts, tag formats, and log structure to your specific domain.
2. **Automate Logging:** Use any note-taking or document system to maintain the context log append-only.
3. **Integrate AI Agent:** When ready, feed this markdown template into your AI collaborator to drive the ChoiceCraft dance.

**ChoiceCraft Protocol** empowers a structured, flexible, and intuitive choice-driven workflow—turning every complex challenge into a series of meaningful MCQs that harness your innate decision-making strengths.

