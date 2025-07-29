Model Name: Kimi-K2-Instruct


────────────────────────────────────────
CHOICE CASCADE™ PROTOCOL  
A Complete Blueprint for Pattern-Driven, Context-Accumulating, Mess-Friendly Collaboration  
────────────────────────────────────────
Version 2.0 • 2024-06-XX • For immediate use or future automation

────────────────────────────────────────
0. 30-SECOND ELEVATOR PITCH  
You speak in butterflies; the system keeps the net.  
ChoiceCascade™ turns every gnarly decision into **simultaneous**, **jargon-free** multiple-choice cards.  
Your messy, tangential, ADHD-style brain stays at full throttle; the AI converts it into crisp technical artifacts without ever asking you to “translate.”

────────────────────────────────────────
1. PHILOSOPHICAL PRINCIPLES
1.1 Dual Expertise  
Human = Domain Intent & Pattern Sense  
Machine = Technical Translation & State Memory  

1.2 “World is an MCQ”  
Every knot becomes a choice between 3-5 **recognizable patterns** plus an escape hatch.  
Complexity is layered, not flattened.

1.3 Mess as Signal  
Unfiltered human voice (tangents, analogies, emotional tone) is treated as **primary data**.  
No polishing required.

1.4 Context Accretion  
All utterances—choices, justifications, jokes, frustrations—are appended to a **living context log** that is visible to both sides at any moment.

────────────────────────────────────────
2. PROTOCOL STRUCTURE
A **Session** is the full lifespan of one problem.  
A **Pulse** is one complete loop:  
AI → MCQ Batch → Human Response → Context Update.

2.1 Session Initialization
```
# Session-ID: 
# Domain: <“Software Architecture”, “Brand Strategy”, “Kitchen Remodel”, …>
# User Cognitive Style: 
# Hard Constraints: 
# Soft Preferences: 
```

2.2 Pulse Format
```
--- Pulse  ---
MCQ Batch:
1. [OptionText] | [PatternTag]
2. …
3. …
4. …
5. [Other] | free-form

Context Snapshot (last 200 tokens or 5 bullets)
---
```

2.3 Context Log (appended at bottom of each Pulse)
```
=== Living Context ===
- Pulse 1: User chose 2 (“Rails monolith”) because “reminds me of Lego”
- Pulse 2: Added constraint “must deploy on Heroku”
- …
======================
```

────────────────────────────────────────
3. INTERACTION PATTERNS
3.1 Batch Size Rule  
Default 3-5 MCQs.  
If user repeatedly chooses **Other**, auto-expand to 5-7 to widen the field.  
If user chooses same pattern >2 times in a row, auto-focus to 2-3.

3.2 Mess-to-Intent Translation
Human may answer:  
“2, because my dog once ate a USB cable and we learned redundancy the hard way”  
AI extracts:  
- Choice = 2  
- Rationale = redundancy mindset  
- Emotion = risk-averse  
All three elements are logged.

3.3 Context Compression
After every 5 Pulses, AI produces a **Précis** (≤120 words) capturing intent drift, emergent constraints, and emotional valence. This précis is re-inserted into the next prompt to prevent ballooning.

3.4 “Other” Escalation
- Level 1: Accept raw text, generate 3 new MCQs derived from it.  
- Level 2: If “Other” used >3 consecutive Pulses, switch to **Open Sketch Mode** (bullet brainstorm) for one Pulse, then fold results back into MCQs.

────────────────────────────────────────
4. MCQ DESIGN GUIDELINES
4.1 Option Framing  
Use metaphor, outcome, or feel rather than jargon:  
❌ “Use optimistic locking”  
✅ “Everyone edits freely, system merges later (Google Docs style)”

4.2 Pattern Tags  
Append invisible-to-human tags for AI bookkeeping:  
`|#scalability |#cost |#team-skill`

4.3 Emotional Resonance  
One option per batch may intentionally include affective language:  
“Feels safe and cozy, like legacy code that never breaks”

────────────────────────────────────────
5. IMPLEMENTATION GUIDELINES
5.1 Markdown Template (copy-paste into any chat)
```

# The ChoiceCascade™ Session
Domain: ___________
Hard Constraints: ______
Soft Preferences: ______

**Session Rules**  
- Human responds with option numbers + any free text  
- AI maintains Context Log at bottom  
- “Other” always an option  

--- Pulse 1 ---
MCQ Batch:
1. [Option 1] | [tag1]
2. [Option 2] | [tag2]
3. [Option 3] | [tag3]
4. [Option 4] | [tag4]
5. Other

Living Context: (empty for now)

```

5.2 Tools-Specific Hooks
• Claude CLI: prepend `--context-file rhythm.log` to auto-append.  
• ChatGPT: ask user to paste “=== Living Context ===” section each turn.  
• Custom app: POST `/pulse` endpoint expects JSON `{choices:[],mess:"..."}`.

5.3 Persistence
Context Log is plain text; can be diff’d, branched, or versioned like source code.

────────────────────────────────────────
6. USAGE EXAMPLES
6.1 Software Architecture
**Domain**: Green-field SaaS MVP  
**Pulse 3 MCQs**:  
1. “Start with a majestic monolith, carve later”  
2. “Micro-services from day one, terraform scripts ready”  
3. “Serverless all the way, pay per request”  
4. “Boring Rails 7 on Heroku, deploy tonight”  
5. Other

User: “4, because I want to demo at Friday’s pitch and I already know Rails.”  
Logged: `rush_to_demo=True`, `tech_comfort=rails`, `risk_appetite=low`

6.2 Creative Writing
**Domain**: Sci-fi short story climax  
**Pulse 2 MCQs**:  
1. “Hero sacrifices themselves, bittersweet ending”  
2. “Reality twist: it was all a simulation”  
3. “Alien alliance saves the day, hopeful”  
4. “Cliffhanger, sequel hook”  
5. Other

User: “3 + I’d like the alien language to mirror whale songs.”  
Logged: `tone=hopeful`, `motif=whale_song`, `genre_shift=eco-scifi`

6.3 Business Strategy
**Domain**: Pricing model for B2B SaaS  
**Pulse 5 MCQs**:  
1. “Flat seat-based pricing ($X per user)”  
2. “Usage-based, scales with value delivered”  
3. “Freemium with gated power features”  
4. “Enterprise only, high-touch sales”  
5. Other

User: “2, but my gut says customers hate surprise bills.”  
Logged: `model=usage`, `concern=bill_shock`, `opportunity=transparent_metering`

────────────────────────────────────────
7. ADVANCED FEATURES & EXTENSIONS
7.1 Parallel Tracks  
For especially broad problems, fork into **Track A** vs **Track B** each with its own MCQ stream. Re-merge later by asking which track feels “warmer.”

7.2 Confidence Meter  
AI appends *[confidence:0-100]* to each option based on how well it maps to logged constraints. Enables “soft veto” signals without hard rules.

7.3 Emotional Heat Map  
Tag every user utterance with a sentiment score. If cumulative negativity > threshold, inject a “pause & reflect” MCQ:  
“Right now the process feels ____. Would you like:  
1. A 5-min break?  
2. Simpler choices?  
3. Venting space?  
4. Continue as-is?”

7.4 Narrative Echo  
Every 5 Pulses, AI writes a single sentence story summarizing the journey so far. Keeps long sessions coherent and human-friendly.

────────────────────────────────────────
8. NAMING & LEXICON
- **ChoiceCascade™** – the overall protocol  
- **Pulse** – one AI↔Human loop  
- **Context Log** – living memory  
- **Précis** – rolling summary  
- **Pattern Tag** – invisible metadata  
- **Sketch Mode** – temporary open brainstorm  
- **Warmth Check** – quick gut-feel re-alignment

────────────────────────────────────────
9. QUICK START CHECKLIST
[ ] Paste template into chat.  
[ ] Fill Domain & constraints.  
[ ] Begin Pulse 1.  
[ ] After 5 Pulses, read Précis aloud
