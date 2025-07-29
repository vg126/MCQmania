<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" class="logo" width="120"/>

# Now, now still, introducing the links here might be the wrong time to do it, but now forget about the API. Totally forget about the API. For this particular response, now focus, put your entire, entire focus on creating the best possible template that you can think of with the context that you know, without limiting yourself by whatever the API might limit itself to. Because as I said, the potential usage is so wide, this is just a speck of the dust in terms of where it can be applied. This is just a hookup, an add-on, which will be relevant not to you, but for Perplexity Labs. But your approach has to be maximal, maximal. Now go ahead, I think you've understood all of it. Generate the template for our MCQ protocol and what are we calling it? Okay, we're not, I'm not calling it anything. You can decide on a nice name. Decide on a nice name for that protocol. And yeah, just create it. Create it right away.

Below is my response to your query. I've internalized the full context from our conversation history, focusing on the refined vision of the MCQ protocol as a flexible, cognitive interface that transforms complex interactions into batch-presented multiple-choice questions (MCQs). This leverages your strengths in intuitive pattern recognition, bucket-based cognition, and strategic choice-making, while handling messy, tangential responses and accumulating all context for subsequent generations. It avoids forcing technical translations and respects the "haphazard" nature of real user input.

To give this protocol a fitting name, I've chosen **ChoiceWeave Protocol**. Why? "Choice" captures the core mechanic of MCQs as decision points; "Weave" evokes how it interlaces user intent (even messy or indirect) with AI execution, creating a cohesive workflow without rigid sequencing. It feels elegant and expansive, aligning with your "World is an MCQ" insight—turning any domain into navigable choices.

The template is designed as a **self-contained, reusable Markdown-based instruction set**. It's maximal in scope: tool-agnostic, adaptable to any AI collaborator (e.g., Claude, GPT, or custom interfaces), and applicable to diverse scenarios (from high-level strategy to granular preferences, coding to creative brainstorming). It can be copied-pasted as a prompt prefix for any AI chat, embedded in an app's logic, or used as a protocol guide for developers. I've structured it with clear sections for ease of use, including rules, examples, and adaptation guidelines.

I've kept it flexible yet structured, emphasizing batch processing, context preservation, and mess tolerance. No API limitations are considered here—this is the pure, unconstrained blueprint.

# **ChoiceWeave Protocol Template**

## **Protocol Overview**

The ChoiceWeave Protocol is a collaborative framework for AI-human interactions that reframes complex tasks into batches of multiple-choice questions (MCQs). It respects the user's cognitive strengths—such as intuitive categorization, pattern recognition, and preference-based decision-making—while the AI handles technical execution. Instead of explaining concepts for the user to "understand," the protocol identifies key decision junctures and presents them as choices, allowing the user to drive outcomes without technical burden.

**Core Philosophy**: The world is an MCQ. Transform any domain into navigable choices that trigger the user's top-down meaning creation. Handle "messy" input (tangents, justifications, indirect answers) as valuable signals of intent. Accumulate all context to inform progressive generations, creating a decision weave rather than a rigid tree.

**When to Use**: Any scenario requiring collaboration on complex, uncertain, or technical topics (e.g., app development, strategy planning, creative ideation). It's especially powerful for users with ADHD-like or top-down thinking styles, as it externalizes choice-making without demanding linear comprehension.

## **Key Protocol Rules**

These rules form the loose structure—adapt them flexibly based on the topic, user, and context. The AI must enforce them while remaining responsive to the user's style.

1. **Batch Presentation**: Present MCQs in groups (batches) of 3-8 questions at a time, not sequentially. This allows the user to "grapple and grasp" across the problem space freely, avoiding early lock-in. Batches should cover a mix of high-level (strategic) and granular (preference-based) decisions.
    - Why batches? They preserve user freedom and enable unconscious learning through exposure.
    - Batch size: Adjust based on complexity (e.g., 3 for simple topics, 8 for multifaceted ones).
2. **MCQ Structure**: Each MCQ must have 3-5 concrete options + an "Other" catch-all.
    - Options: Clear, contextualized choices that bucket concepts intuitively (e.g., "A: Focus on speed (like a sprint)" vs. technical jargon). Phrase to trigger pattern recognition without requiring deep understanding.
    - "Other": Always include for custom responses, explanations, or rejections (e.g., "Other: Explain why none fit" or "Other: Suggest something else").
    - Question Phrasing: Neutral, non-leading, and tied to the task's goals. Include brief context if needed, but avoid overloading with explanations.
    - Flexibility: No fixed number of options—let the topic dictate (e.g., 3 for binary-ish choices, 5 for nuanced ones).
3. **Response Handling (Mess Tolerance)**: Expect and embrace haphazard user input—tangents, justifications, indirect answers, or non-linear responses. Extract intent from the "mess" without judgment.
    - Process: Parse for choices (e.g., "I pick B because..."), but also capture all context (e.g., side thoughts as signals of broader intent).
    - If unclear: Gently probe in the next batch (e.g., "Based on your tangent about X, would you prefer...").
    - No enforcement: Users can answer partially, skip, or ramble—treat everything as data.
4. **Context Accumulation**: Carry forward *all* prior context into every response and generation.
    - Include: User's exact words, choices, justifications, tangents, and any evolving intent.
    - Mechanism: Maintain an internal "context weave" (a running summary or log) that informs new MCQ batches and final outputs.
    - Progression: After a batch, generate the next based on accumulated context. Only produce final outputs (e.g., code, plans) after sufficient batches, weaving everything together.
5. **AI Role and Workflow Continuity**:
    - AI as Facilitator: Generate MCQs, interpret responses, and execute technical steps based on choices. Do not explain unless requested—focus on advancing the task.
    - Iteration: Continue batches until the user signals completion (e.g., "Generate now" or "Done"). Then, synthesize into a coherent output.
    - Adaptability: Scale depth based on user preferences (e.g., high granularity for detailed control, low for quick strategy).
6. **Edge Cases and Adaptations**:
    - User Expertise Level: Tag options with descriptors (e.g., "A: Beginner-friendly (simple setup)").
    - Dead Ends: If choices lead to impossibilities, present MCQs to reroute (e.g., "Conflict detected—choose resolution:").
    - Generalizability: This protocol is tool-agnostic—apply to any AI (e.g., chat interfaces, CLIs, apps). For apps, map to UI elements like dropdowns or buttons.

## **Interaction Pattern (The "Dance")**

1. **Initiation**: User provides a query or task. AI responds with the first batch of MCQs, prefixed with a brief setup (e.g., "Based on your goal of [task], here's Batch 1:").
2. **User Response**: User answers messily (e.g., voice transcript, rambling text).
3. **AI Processing**: Acknowledge, extract intent, accumulate context, and generate the next batch or final output.
4. **Loop**: Repeat until resolution.
5. **Completion**: Weave all context into a final deliverable (e.g., code, plan, app prototype).

## **Example Usage**

### **Sample Prompt Prefix**

Copy this into any AI chat to activate the protocol:

"Follow the ChoiceWeave Protocol strictly. My task is [describe task, e.g., 'Build a simple web app for note-taking']. Generate the first batch of MCQs to guide decisions. Remember: Batches of 3-8 MCQs, 3-5 options + Other, full context accumulation, handle messy responses."

### **Example Batch (For App Development Task)**

**Batch 1: Core Decisions for Note-Taking App**

1. **Overall Architecture**: What foundation should we build on?
A: Web-based (like a browser app, easy access).
B: Mobile-first (optimized for phones, quick notes on-the-go).
C: Desktop tool (robust features, like a command center).
D: Hybrid (mix of web and mobile).
Other: Something else—explain.
2. **Key Feature Focus**: Which bucket of features matters most?
A: Simplicity (basic notes, no frills—like a digital sticky note).
B: Collaboration (sharing and real-time editing, team-oriented).
C: Organization (tags, search, folders—like a knowledge base).
D: Integration (connect to calendars or emails).
Other: Custom idea.
3. **UI Style Preference**: How should it feel?
A: Minimalist (clean, white space—like a zen garden).
B: Colorful and intuitive (vibrant, easy navigation).
C: Professional (structured, like office software).
Other: Describe your vibe.
4. **Technical Depth**: How involved do you want to be?
A: High-level only (I choose strategy, you handle details).
B: Mix (I pick some granular choices, like colors).
C: Full granular (MCQs for everything, even code functions).
Other: Adjust based on [explain].

**AI Follow-Up Example**: After user responds (e.g., "B for architecture, but with some A vibes, and tangent about security..."), accumulate context and generate Batch 2, weaving in the mess.

## **Customization Guidelines**

- **For Different Users**: Adjust batch size or option complexity (e.g., more tags for beginners).
- **Scaling**: For large tasks, add "meta-MCQs" about the protocol itself (e.g., "Batch size preference: Small/Medium/Large").
- **Output Formats**: End with deliverables like code snippets, diagrams, or plans—always grounded in the full context weave.
- **Ethical Note**: This protocol empowers user agency; AI should never override choices or censor ideas.

This template is now ready for use, adaptation, or integration. If you want refinements (e.g., more examples, a specific adaptation for Perplexity Labs), just say the word!

---

There you have it—the maximal, unconstrained template. It's designed to be a living document you can evolve. What's your take? Ready to test it on a sample task or move to the app phase?

