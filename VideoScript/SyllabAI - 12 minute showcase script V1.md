# SyllabAI — Faculty Showcase

### Approx. 12 minutes

---

## 0:00–0:20 — Opening

### SCREEN

Title slide.

**SyllabAI**

**An Adaptive Learning & Examination Preparation Platform**

Underneath:

> Curriculum → Evidence → Diagnosis → Intervention → Learning

Then your name / team / department.

### SAY

“Imagine a student preparing for an important examination.

They have a syllabus, hundreds of pages of resources, past papers, mark schemes and questions.

But the real problem isn't access to content.

The problem is knowing **what to study, what they actually understand, where they are making mistakes, and what they should do next.**

That is the problem SyllabAI is designed to solve.”

---

# 0:20–1:00 — Problem Statement

### SCREEN

Move to a problem slide.

Show something like:

**Traditional exam preparation**

`Syllabus → PDFs → Practice → Marks → Repeat`

Then underneath, highlight:

* Same resources for everyone
* Weak areas discovered too late
* Feedback is fragmented
* AI answers are not necessarily curriculum-grounded
* Student progress is difficult to model at concept level

### SAY

“Most digital learning systems are essentially collections of resources.

A student reads a note, answers a question, receives a mark, and then moves on.

But a mark alone doesn't tell us enough.

If a student loses marks on a chemistry question, for example, we want to know:

Is this a knowledge problem?

A misconception?

A prerequisite gap?

A procedural problem?

Or simply an issue with exam technique?

And once we know that, the system should be able to respond differently.

So our goal was not simply to build an AI tutor.

Our goal was to build a system that can **understand the relationship between curriculum, assessment evidence and the learner.**”

---

# 1:00–1:35 — Our Solution

### SCREEN

Show the central SyllabAI architecture diagram:

```text
Official Curriculum
        ↓
Educational Knowledge Graph
        ↓
Validated Learning Content
        ↓
Learner interacts
        ↓
Learning Evidence
        ↓
Diagnosis
        ↓
Targeted Intervention
        ↓
Assessment
        ↓
Learner Model Update
        ↺
```

Animate the arrow returning to the learner.

### SAY

“This is the central idea behind SyllabAI.

We start with the official curriculum.

We turn that curriculum into structured educational knowledge, with specification points acting as canonical anchors.

We connect validated revision content and assessment questions to those anchors.

Then, as the student learns and answers questions, we collect **learning evidence**.

That evidence is used to update the learner model.

And the learner model can then influence what the student should do next.

So instead of:

**content → chatbot → answer**

we are building:

**curriculum → evidence → diagnosis → intervention → assessment → learner update.**

That feedback loop is the core of SyllabAI.”

---

# 1:35–2:00 — Why SyllabAI?

### SCREEN

Final introduction slide:

## What makes SyllabAI different?

**1. Curriculum-grounded**

**2. Evidence-driven**

**3. Learner-aware**

**4. Assessment-integrated**

**5. AI-assisted, not AI-authoritative**

### SAY

“And importantly, AI is not the source of educational truth.

SyllabAI remains authoritative over curriculum semantics, assessment identity and learner state.

The AI operates inside those boundaries.

With that context, let me show the actual system.”

---

# 2:00 — TRANSITION TO LIVE HUB

### SCREEN

Open the SyllabAI Hub.

Preferably start at the **4CH1 Chemistry course hub**, rather than the generic homepage.

### SAY

“This is the SyllabAI Hub — the student-facing product frontend.

For this demonstration I'm going to use our Edexcel IGCSE Chemistry 4CH1 pilot because this is currently the course connected end-to-end to our backend learner model.”

Pause for one second.

“I'm going to follow the journey of a student rather than simply clicking through features.”

---

# 2:00–2:45 — The Learning Hub

### SCREEN ACTIONS

Open:

**Courses → Edexcel IGCSE Chemistry 4CH1**

Show:

* course title
* specification code
* Exam Practice
* Revision
* Exam Questions
* Past Papers
* Practice Papers
* Revision Notes
* Flashcards
* Specification

Don't click everything.

Focus on the organization.

### SAY

“The first thing to notice is that SyllabAI is organized around the actual course.

For example, this is Edexcel IGCSE Chemistry, specification 4CH1.

The student doesn't just get a generic collection of AI-generated material.

The learning environment is organized around the subject, its specification and its assessment structure.

Here we have revision notes, exam questions, past papers, practice papers and flashcards.

And these resources are organized around the underlying specification.”

Click **Specification** or the specification link.

---

# 2:45–3:40 — Curriculum as the Backbone

### SCREEN ACTIONS

Open the **Specification** view.

Show the specification tree.

Then click into a topic/specification point.

### SAY

“This is important architecturally.

The specification is not just text displayed on a webpage.

It becomes a structured backbone for the rest of the system.

A concept can be connected to a specification point.

Questions can be mapped to specification points.

Learning evidence can be associated with those concepts.

And eventually, the learner model can tell us how the learner is performing against that structure.

So the curriculum becomes the stable reference frame for personalization.”

---

# 3:40–5:00 — Assessment: From Question to Evidence

### SCREEN ACTIONS

Go back to:

**Exam Questions**

Choose a question that is visually clear and has multiple marks if possible.

Show the question.

Then answer it yourself.

Prefer a structured-answer question rather than a trivial MCQ.

### SAY

“Now let's move from learning to assessment.

Suppose I'm the student.

I select an exam-style question.

Instead of just seeing the correct answer, I actually have to produce my own response.”

Enter a deliberately imperfect answer.

Pause.

“I'm going to submit this answer.”

Click submit.

---

## Smart Mark

### SCREEN ACTIONS

Click **Smart Mark**.

Let the system process.

Show:

* awarded marks
* mark-point breakdown
* rationale
* authoritative / indicative status if visible
* coaching actions

### SAY

“Now we can see something much more interesting.

SyllabAI doesn't just return a generic percentage.

The answer goes through the Smart Mark pipeline.

The system evaluates the response against the assessment structure and produces a per-part breakdown.

This gives us structured assessment evidence rather than just a chat message saying ‘good job’ or ‘try again.’”

Point at the mark-point breakdown.

“These individual outcomes are important because they can become evidence about the learner's understanding.”

---

# 5:00–6:00 — The Learner Model

### SCREEN ACTIONS

Open **My Progress / Learner**.

Show:

* My State
* mastery
* topic state
* specification-point state
* History
* assignments if useful

### SAY

“And this is where SyllabAI starts to differ from a conventional question bank.

The student's interaction is not simply discarded after the question is marked.

The backend learner model can use assessment evidence to maintain a representation of the learner's current state.

Here we can see the learner's progress, history and state.

For the 4CH1 pilot, this is backed by the real SyllabAI core learner model.”

Point to the provenance indicator if visible.

“Notice that we also expose provenance.

Where the state is measured from the backend, we identify it as measured rather than pretending that simulated or locally-derived information is authoritative.”

---

# 6:00–7:15 — Knowledge Graph

### SCREEN ACTIONS

Open:

**Knowledge Graph**

Let the graph render.

Show:

* nodes
* relationships
* specification points
* learner overlay
* measured state indicator

Open the state drawer if useful.

### SAY

“This is the Knowledge Graph.

The important idea here is that the graph represents the educational structure.

We can see relationships between concepts and specification points.

But we also have a second layer:

the learner's state.

The learner state is an overlay on top of the curriculum structure.

That distinction is very important.

The curriculum does not change because a student gets a question wrong.

Instead, the learner model changes.

So we have:

**curriculum truth**

plus

**learner state**

rather than mixing the two together.”

Open a learner-state detail.

“This gives us a foundation for much more precise personalization.

Instead of saying ‘the student is weak at chemistry,’ we can reason at a much more granular level.”

---

# 7:15–9:15 — The AI Tutor

### SCREEN ACTIONS

Open:

**Tutor**

Show the Tutor interface.

Before typing, briefly show:

* conversation history
* subject/context
* grounded tutor UI

Then type a question such as:

> “Explain ionic bonding and relate it to what I need to know for 4CH1.”

### SAY

“Now let's bring AI into the system.

This is the SyllabAI Tutor.

But there is an important architectural difference between this and simply opening ChatGPT and asking the same question.”

Send the question.

Wait for answer.

### SAY

“The Tutor is grounded in the SyllabAI educational context.

The answer is generated using the system's curriculum and retrieval context, rather than treating a language model as the source of truth.”

Point to citations.

“Notice the citations.

The Tutor can show the evidence supporting the response.”

Click/open a citation if the demo environment makes that useful.

“This is particularly important for an educational system.

We don't just want an answer that sounds plausible.

We want an answer that can be traced back to appropriate educational evidence.”

---

## Tutor question identity

### SCREEN ACTIONS

Ask something specification-specific:

> “What does 4CH1-1.25 require about ionic bonding?”

### SAY

“And because SyllabAI understands specification identity, I can also ask about a specific specification point.”

Send.

“This is one of the places where our curriculum model matters.

The Tutor is not simply doing semantic search across arbitrary documents.

The request can be anchored to the actual course and specification context.”

---

# 9:15–10:15 — Contextual Learning Assistant

### SCREEN ACTIONS

Navigate back to a revision note or exam question.

Find **Ask about this / Explain / Hint** or the contextual assistant entry point.

Open it.

### SAY

“There's another interaction pattern I want to demonstrate.

Instead of leaving the learning material and opening a completely separate chatbot, SyllabAI can provide contextual assistance from the material the student is already studying.”

Ask something specific to the note/question.

### SAY

“This is the contextual learning assistant.

The important distinction is context.

The assistant knows what resource or question the learner is currently working with, so the interaction can remain anchored to that educational context.”

If **Hint** is available:

“Rather than immediately revealing the answer, we can also move toward guided assistance — for example, giving a hint or helping the learner approach the problem.”

---

# 10:15–11:15 — Show the Closed Loop

### SCREEN

Now stop clicking.

Return to the **Learner / Knowledge Graph** view.

Show the relevant state again.

### SAY

“So let's step back from the individual screens.

What we just demonstrated was not a collection of independent features.

We followed one learning loop.”

Animate / verbally point:

```text
Curriculum
    ↓
Learning material
    ↓
Exam question
    ↓
Student answer
    ↓
Smart Mark
    ↓
Learning evidence
    ↓
Learner model
    ↓
Knowledge Graph
    ↓
Tutor / contextual intervention
    ↓
More learning
    ↺
```

### SAY

“The student starts with curriculum-grounded content.

They attempt an assessment.

The attempt produces structured evidence.

That evidence contributes to the learner model.

The learner state can be visualized against the knowledge structure.

And the Tutor can then provide context-aware assistance.

The goal is that the next learning interaction is informed by what the system has learned about the student.”

Pause.

“That is the adaptive learning loop we're building.”

---

# 11:15–12:00 — Architecture + Closing

### SCREEN

Return to your architecture slide, but now show the system components:

```text
              SYLLABAI
                  │
        ┌─────────┴─────────┐
        │                   │
   Curriculum          Learner
   + Knowledge          Model
      Graph                │
        │                  │
        └──────┬───────────┘
               │
        Assessment Evidence
               │
        ┌──────┴──────┐
        │             │
     Retrieval       Tutor
        │             │
        └──────┬──────┘
               │
          Next Action
```

### SAY

“Underneath the interface, SyllabAI is split into several major layers.

The Hub provides the student and teacher experience.

SyllabAI Core manages identity, learner state, assessment evidence and AI services.

The curriculum and educational knowledge graph provide the educational structure.

And the retrieval and Tutor layers provide grounded assistance on top of that structure.”

Then:

“What we are deliberately avoiding is making the language model the center of the architecture.

The model is one component.

The educational system around it is what makes SyllabAI an adaptive learning platform rather than simply an AI chatbot.”

### FINAL

“Ultimately, our vision is simple:

A student should not have to figure out what they need to learn next.

SyllabAI should use the curriculum, their assessment evidence and their learning history to help answer that question.

**What do I know?**

**What don't I know?**

**Why am I struggling?**

And most importantly:

**What should I do next?**

That is SyllabAI.”

End on the SyllabAI logo/title.

---

# End card

**SyllabAI**

### Adaptive Learning. Grounded in the Curriculum. Driven by Evidence.

`Curriculum → Learn → Assess → Diagnose → Intervene → Improve`
