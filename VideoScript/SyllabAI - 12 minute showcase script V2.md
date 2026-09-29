# SyllabAI — 12-Minute Faculty Demo

**Core story:**
One student struggles → SyllabAI understands why → the student gets targeted support → the teacher sees the pattern → the teacher creates targeted assessment → the result feeds back into the learner model.

---

## 0:00–0:35 — Opening: The Problem

**ON SCREEN**

Quiet Green title screen.

**SyllabAI**

*From curriculum to understanding.*

Then:

> **What if a learning platform could understand not only what a student answered — but what they actually know?**

Pause.

**SPOKEN**

> “Most learning platforms can tell us whether a student got something right or wrong.
>
> But that isn't the same as understanding the student.
>
> A teacher needs to know:
> What does this student understand?
> Where are they struggling?
> Is the problem a missing concept, a misconception, or simply lack of practice?
>
> And importantly — what should happen next?”

Transition from the title into the SyllabAI architecture.

---

# 0:35–1:20 — What SyllabAI Is

**ON SCREEN**

Animated architecture:

```text
Official Curriculum
        ↓
Educational Knowledge
        ↓
Learner Evidence
        ↓
Diagnosis
        ↓
Targeted Intervention
        ↓
Assessment
        ↓
Learner Update
        ↓
Next Best Action
```

**SPOKEN**

> “SyllabAI is designed around that complete learning loop.
>
> It starts with the curriculum.
>
> Curriculum and educational semantics remain authoritative. From there, SyllabAI connects validated learning resources, questions and concepts to a structured knowledge model.
>
> As students interact with the system, those interactions become learning evidence.
>
> That evidence can contribute to a picture of what the learner understands, where they are uncertain, and where intervention may be useful.
>
> And then we close the loop with practice and assessment.”

**TRANSITION**

Zoom through the architecture and land inside the student experience.

---

# 1:20–2:00 — Meet the Student

**ON SCREEN**

Open the student experience in `syllabai-hub`.

Show the student's main dashboard.

Do **not** rush.

Let the audience see that this is a real learning environment rather than a chatbot interface.

**SPOKEN**

> “Let's follow one student.
>
> The student doesn't start with an AI conversation.
>
> They start with their learning environment — their subjects, resources, revision, practice and progress.
>
> The important thing here is that the AI sits inside the learning system.
>
> It has context: the subject, the curriculum, the learning resources, the concepts being studied, and — where appropriate — the learner's evidence.”

---

# 2:00–3:30 — The Tutor

**ON SCREEN**

Open Tutor.

Ask a realistic curriculum question.

For example:

> “I don't understand why increasing temperature changes the rate of reaction.”

Show the Tutor response.

Then ask a follow-up that exposes the student's misunderstanding.

For example:

> “So does that mean every particle reacts when the temperature increases?”

**SPOKEN**

> “Now the student asks for help.
>
> This is where SyllabAI's Tutor becomes more interesting than a generic chatbot.
>
> The goal isn't simply to generate a plausible answer.
>
> The Tutor should be grounded in the learning context around the student.”

Show relevant contextual material / resource context where available.

> “The system can work with the relevant curriculum and learning context rather than treating the conversation as an isolated question.”

Show the Tutor guiding rather than immediately dumping an answer.

> “And for learning tasks, the interaction can become progressively more supportive.
>
> Instead of immediately giving the student the answer, we can move from understanding the question, to a hint, to an approach, to working through the problem, and eventually to feedback on the student's own attempt.”

Pause.

> “That distinction matters.
>
> We're not just trying to answer questions.
>
> We're trying to create useful learning interactions.”

---

# 3:30–4:20 — Resources and Revision

**ON SCREEN**

Navigate from Tutor into the relevant resource / revision material.

Show:

* definitions
* explanations
* common pitfalls
* exam help
* contextual material

**SPOKEN**

> “The Tutor also connects back into the learning environment.
>
> If the student needs revision rather than conversation, they can move directly into the relevant learning material.
>
> So the AI interaction doesn't have to end with an AI-generated paragraph.
>
> It can lead the student back into structured learning content.”

**TRANSITION**

Move from resource → practice.

---

# 4:20–5:20 — Practice and Evidence

**ON SCREEN**

Open relevant questions/practice.

Student attempts a question.

Show an incorrect or incomplete response.

Then show feedback / Smart Mark / guided interaction as appropriate.

**SPOKEN**

> “Now we can test whether the explanation actually helped.
>
> The student attempts a question.
>
> This is important because the answer itself is only one piece of information.
>
> SyllabAI is interested in the evidence around the attempt — what concept was being tested, what the student attempted, whether the response indicates understanding, uncertainty, or a recurring difficulty.”

Show the interaction/evidence concept visually.

> “The conversation and the assessment attempt aren't simply thrown away.
>
> They become part of the evidence that can contribute to the learner model.”

---

# 5:20–6:15 — From One Interaction to Learner Understanding

**ON SCREEN**

Animate:

```text
Student interaction
        ↓
Learning evidence
        ↓
Patterns over time
        ↓
Learner model
```

**SPOKEN**

> “And this is one of the fundamental ideas behind SyllabAI.
>
> We don't want one sentence from a student to magically rewrite their mastery.
>
> A single interaction is evidence.
>
> Repeated and supported evidence can contribute to learner patterns.
>
> Those patterns can then inform the governed learner model.”

Show conceptual learner state.

> “That gives us a very different foundation for adaptation.
>
> The system isn't adapting because an LLM decided that a student ‘seems weak’ at something.
>
> It's adapting from structured learning evidence connected back to the curriculum.”

---

# 6:15–7:45 — Teacher Dashboard

**ON SCREEN**

Hard transition into the **Teacher Dashboard**.

Start with the class overview.

Show:

* class
* students
* mastery/progress
* concept-level information
* areas of difficulty

**SPOKEN**

> “Now let's switch perspective.
>
> Because the other half of the problem is the teacher.
>
> An adaptive learning system isn't very useful if all of its intelligence disappears inside the student's private chat.”

Show class-level mastery.

> “The teacher needs to see the class.
>
> Not just a collection of marks, but where the class is actually struggling.”

Move through concept-level mastery.

> “Here we can look at mastery across the class and identify areas where students are having difficulty.”

Then show individual student information.

> “And we can move from the class to an individual student.”

Show a student's weaknesses / learning patterns.

> “Now the teacher can investigate an individual learner and see the areas that need attention.”

Pause.

> “This changes the teacher's question from:
>
> ‘Who got question seven wrong?’
>
> to:
>
> ‘What underlying concept appears to be causing difficulty, and which students are affected?’”

---

# 7:45–8:40 — Class-Level Diagnosis

**ON SCREEN**

Return to class dashboard.

Highlight a concept where multiple students are weak.

**SPOKEN**

> “And the class view matters because teachers often don't need another report telling them that a class scored 62 percent.
>
> They need to know what that 62 percent means.
>
> Is the class struggling with one particular concept?
>
> Are a few students responsible for the result?
>
> Or is there a broader learning gap?”

Show the class → concept → students relationship.

> “SyllabAI is designed to make that relationship visible:
>
> curriculum concept,
> class,
> individual learners,
> and learning evidence.”

---

# 8:40–9:50 — Test Builder

**ON SCREEN**

Open **Test Builder**.

Start with the teacher selecting relevant curriculum/concepts.

Then show question selection / assessment construction.

**SPOKEN**

> “And this is where the teacher workflow connects back to assessment.
>
> Once the teacher knows where the class is struggling, they need a way to act on that information.”

Show Test Builder.

> “The teacher can build an assessment around the learning objectives or concepts they want to assess.”

If the UI supports targeted selection:

> “Instead of treating assessment as completely separate from the learner model, the assessment can be constructed around the areas that actually need attention.”

Show the test being assembled.

> “So the workflow becomes:
>
> identify the learning need,
> select what should be assessed,
> build the test,
> and send it to the students.”

---

# 9:50–10:40 — Closing the Loop

**ON SCREEN**

Animate:

```text
Teacher identifies gap
        ↓
Targeted assessment
        ↓
Student attempts
        ↓
New evidence
        ↓
Learner state updates
        ↓
Teacher sees change
```

**SPOKEN**

> “And now we can close the loop.
>
> The student takes the targeted assessment.
>
> Those new attempts create new learning evidence.
>
> That evidence contributes to the learner's evolving state.
>
> And the teacher can return to the dashboard and see what changed.”

Show before/after if the UI supports it.

> “So assessment isn't the end of the process.
>
> It's another source of evidence.”

---

# 10:40–11:20 — Why the Architecture Matters

**ON SCREEN**

Return to the architecture.

Animate each layer.

```text
Curriculum
   ↓
Knowledge
   ↓
Retrieval
   ↓
Learner Evidence
   ↓
Diagnosis
   ↓
Intervention
   ↓
Assessment
```

**SPOKEN**

> “Underneath the interface is an important architectural distinction.
>
> SyllabAI doesn't treat the LLM as the source of educational truth.
>
> The curriculum and structured educational knowledge remain authoritative.
>
> Retrieval is a way of finding relevant evidence.
>
> Learner interactions are evidence rather than automatic truth.
>
> And the learner model sits on top of the curriculum — it doesn't rewrite the curriculum itself.”

---

# 11:20–12:00 — Closing

**ON SCREEN**

Full-screen Quiet Green.

The architecture collapses into one simple loop:

```text
UNDERSTAND
      ↓
DIAGNOSE
      ↓
INTERVENE
      ↓
ASSESS
      ↓
LEARN
      ↺
```

Then:

> **SyllabAI**
>
> *Turning learning data into the next useful learning action.*

**SPOKEN**

> “That's ultimately what we're building with SyllabAI.
>
> Not an AI chatbot attached to an education platform.
>
> A learning system where curriculum, educational knowledge, learner evidence, diagnosis, intervention and assessment are connected.
>
> For the student, that means more contextual and targeted support.
>
> For the teacher, it means visibility into what students actually need.
>
> And for the system, every meaningful learning interaction can become evidence for what should happen next.
>
> The goal is simple:
>
> understand the learner,
> identify what they need,
> help them,
> assess whether it worked,
> and keep learning from the result.”

**END CARD**

> **SyllabAI**
>
> **From curriculum to understanding.**

Hold for 3 seconds.
