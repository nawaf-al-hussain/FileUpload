# SyllabAI Knowledge Graph Context — Student & Teacher

**Status:** Canonical Knowledge Graph context document  
**Date:** 2026-09-08  
**Scope:** Student Knowledge Graph + Teacher Knowledge Graph lens  
**Project:** SyllabAI  
**Applies to:** `syllabai`, `syllabai-core`, `syllabai-web`, `syllabai-parser`  
**Primary related architecture:** `SUBJECT_ARCHITECTURE.md`, `TEACHER_ARCHITECTURE.md`, `QUESTION_ATTEMPT_AND_LEARNING_EVIDENCE.md`, `RECOMMENDATION_SYSTEM_ARCHITECTURE.md`, `MASTER_SPEC.md`

---

## 0. Purpose

This document is the dedicated working context for the SyllabAI Knowledge Graph.

It exists so that any engineer, coding agent, UI agent, data/AI agent, or future graph-visualization implementation can understand the graph without reconstructing its meaning from scattered documents or previous conversations.

The Knowledge Graph is not merely a decorative visualization. It is the shared academic structure through which SyllabAI connects:

```text
Official curriculum
        ↓
SpecificationPoint
        ↓
Concept / skill / prerequisite structure
        ↓
Questions + resources
        ↓
Assessment evidence
        ↓
Learner state
        ↓
Diagnosis
        ↓
Recommendation / Tutor / Practice
```

The student and teacher experiences are two different **lenses over the same academic graph**.

```text
                         SAME ACADEMIC GRAPH
                                  │
             ┌────────────────────┴────────────────────┐
             │                                         │
       STUDENT LENS                               TEACHER LENS
             │                                         │
  personal learner overlay                teaching + class overlays
             │                                         │
  “What do I know?”                         “What have I taught?”
  “What do I need?”                         “What does my class know?”
  “What next?”                              “Who needs attention?”
```

A second curriculum graph must not be created for teachers.

A second learner model must not be created for teachers.

A second question-attempt ledger must not be created for graph purposes.

---

# 1. Product role of the Knowledge Graph

SyllabAI is a syllabus-grounded adaptive learning platform rather than a generic document chatbot.

The graph is one of the central structures that makes the adaptive loop possible:

```text
Official specification
        ↓
Structured curriculum
        ↓
Knowledge Graph
        ↓
Questions / resources
        ↓
Learner interaction
        ↓
Learning evidence
        ↓
Learner model
        ↓
Graph overlay
        ↓
Diagnosis
        ↓
Tutor / recommendation / practice
        ↓
New evidence
```

The graph therefore serves three distinct but connected purposes:

1. **Academic structure** — what exists in the curriculum and how knowledge relates.
2. **Grounding structure** — what content, questions, explanations and resources support each academic concept.
3. **Learner/teacher lens structure** — what a learner appears to know, what the class has been taught, and where attention may be warranted.

The graph does not itself become the learner model. The graph stores the stable academic topology and its provenance; time-varying learner/teacher state is attached as overlays/read models.

---

# 2. Core principles

## 2.1 Official curriculum is authoritative

The official curriculum hierarchy is source material and must be versioned.

```text
Board
→ Qualification
→ Subject
→ CurriculumVersion / SpecificationVersion
→ Unit / Section
→ Topic / SubTopic
→ SpecificationPoint
```

The graph must preserve the selected board/specification's structure rather than inventing a new pedagogical hierarchy and calling it official.

## 2.2 SpecificationPoint is first-class

`SpecificationPoint` is the canonical fine-grained curriculum anchor for official learning objectives.

A SpecificationPoint is not a generic tag.

It should retain, as applicable:

- stable internal identifier
- curriculum version identifier
- official code
- verbatim official learning-objective statement
- display title, when available from the source
- official ordering
- parent hierarchy
- source document/version
- source page/section/element provenance
- validation/extraction status
- applicability metadata such as Core/Supplement, tier, unit, paper, or route where the specification explicitly defines it
- parser/extraction version where relevant

Never replace the canonical official objective text with a silently paraphrased LLM summary.

A separate summary may exist, but it must not overwrite the source field.

## 2.3 Hierarchy and knowledge are different

The curriculum tree is not the entire knowledge graph.

Example:

```text
Curriculum hierarchy:

Unit
 └── Topic
      └── SubTopic
           ├── SpecificationPoint 1.1
           ├── SpecificationPoint 1.2
           └── SpecificationPoint 1.3
```

Knowledge relationships may cross that hierarchy:

```text
SpecificationPoint 1.3
      │
      ├── REQUIRES_PREREQUISITE → SpecificationPoint 2.1
      ├── RELATED_TO             → SpecificationPoint 1.1
      ├── EXPLAINS               → Concept X
      └── REMEDIATED_BY          → Resource Y
```

Two points can be siblings in the official specification but have an actual prerequisite relationship.

A point can also depend on concepts elsewhere in the subject.

Therefore the system must preserve the official tree exactly while allowing cross-tree knowledge relations.

## 2.4 Learner state is an overlay

Do not mutate curriculum nodes with learner state.

Bad:

```text
SpecificationPoint 1.2
mastery = 0.73
```

Correct conceptual model:

```text
SpecificationPoint 1.2
        │
        └── learner overlay for Student A
              ├── mastery = derived value
              ├── misconception state
              ├── confidence evidence
              ├── fluency state
              ├── exposure / attempt evidence
              └── review state
```

The academic graph should remain stable across students.

---

# 3. Canonical graph layers

The graph should be thought of as several semantic layers rather than one undifferentiated collection of nodes.

## Layer A — Identity / curriculum

```text
Board
Qualification
Subject
CurriculumVersion
Unit
Section
Topic
SubTopic
SpecificationPoint
```

## Layer B — Academic knowledge

```text
Concept
Skill
PracticalSkill
Procedure
Misconception
Definition
Example
CounterExample
Formula / Rule
```

Not every deployment needs every type immediately. The key requirement is that the model can represent knowledge that is finer or different in kind from the official specification tree.

## Layer C — assessment

```text
ExamPaper
Question
QuestionVersion
QuestionPart
MarkScheme
MarkPoint
AssessmentObjective
QuestionType
```

## Layer D — learning resources

```text
Document
RevisionNote
Flashcard
WorkedExample
InteractiveResource
VideoResource
SmartLessonStep
TutorEvidence
```

## Layer E — evidence

```text
QuestionAttempt
AssessmentEvidence
ConfidenceObservation
ReviewState
ReviewSchedule
TeacherObservation
AssignmentSubmission
```

Evidence is not the same thing as derived learner state.

## Layer F — learner overlay

```text
SkillState
LearnerState
MisconceptionState
ProceduralFluencyState
ConfidenceState / observations
ReviewState
```

## Layer G — teacher overlay

```text
TeachingAssignment
Class
ClassEnrollment
TeachingCoverage
ClassAggregateLearnerState
TeacherAttention / RiskSignal
Assignment / Assessment coverage
```

The teacher overlay is additional context. It does not change the underlying curriculum.

---

# 4. Canonical node types

The following semantic node types are recognized by the architecture.

## 4.1 Board

Represents an examination/education board.

Example:

```text
Edexcel
Cambridge International
```

Properties may include:

- id
- name
- canonical code
- source URL / provenance
- lifecycle status

## 4.2 Qualification

Represents a qualification under a board.

Example:

```text
International GCSE
International Advanced Level
```

## 4.3 Subject

Represents a subject identity within a qualification.

Example:

```text
Chemistry
Biology
Mathematics
```

Subject identity is critical for isolation.

## 4.4 CurriculumVersion / SpecificationVersion

Represents a specific version of a board's specification.

This is the boundary at which official curriculum versioning becomes explicit.

Two versions must not be silently treated as the same graph.

Historical questions/resources may be linked across versions, but the applicability of those links must be explicit.

## 4.5 Unit / Section / Topic / SubTopic

These represent the structure supplied by the selected official curriculum.

The exact levels can vary by board. The implementation should not assume every board has exactly Unit → Topic → SubTopic.

The canonical system may preserve generic hierarchy semantics while retaining the source's own structure and codes.

## 4.6 SpecificationPoint

The principal fine-grained syllabus anchor.

It can connect to:

- questions
- question parts
- mark points
- revision notes
- flashcards
- examples
- misconceptions
- concepts
- procedures
- tutor evidence
- learner state
- recommendations

## 4.7 Concept

Represents a conceptual knowledge entity that may cut across official specification boundaries.

A concept should not automatically be created for every word in the specification.

It needs a reason to exist as a graph object, such as:

- independent prerequisite structure
- reusable conceptual grounding
- multi-point assessment relevance
- misconception linkage
- resource linkage

## 4.8 Skill

Represents a skill or capability that can be demonstrated through evidence.

Examples in a chemistry context might include:

```text
balance an equation
interpret titration data
apply a formula
identify a trend in experimental data
```

Do not infer that every assessment objective is a learner skill without preserving the source semantics.

## 4.9 Misconception

Represents a known or hypothesized incorrect mental model.

Misconceptions should preserve evidence/provenance and validation status.

A misconception node is not the same as:

```text
wrong answer
low mastery
flagged question
```

Those are different concepts.

## 4.10 Question / QuestionPart

Question identity is canonical across sessions and product surfaces.

A question may have multiple parts.

```text
Question
 ├── QuestionPart A
 ├── QuestionPart B
 └── QuestionPart C
```

QuestionPart is usually the more precise assessment-learning anchor because marking, skill demand, and specification coverage may vary by part.

## 4.11 Resource

Represents a learning resource connected to graph nodes.

A resource can cover multiple specification points.

Never force a one-to-one mapping when the content genuinely spans several objectives.

---

# 5. Canonical edge types

Minimum supported semantic relationships include:

```text
PART_OF
REQUIRES_PREREQUISITE
RELATED_TO
TESTED_BY
MISCONCEPTION_OF
EXPLAINED_BY
REMEDIATED_BY
```

The implementation may also use more explicit domain vocabulary where necessary, such as:

```text
MAPS_TO
ASSESSES
COVERS
SUPPORTS
DERIVED_FROM
EXEMPLIFIED_BY
CONTRASTS_WITH
DEPENDS_ON
```

Every edge that influences a learner-facing decision should preserve provenance and status.

Recommended edge metadata:

```text
edgeId
sourceNodeId
targetNodeId
relationType
strength / confidence
provenance
rationale
createdBy
createdAt
validationStatus
version
validFrom
validTo (where applicable)
```

Algorithmically suggested edges must be distinguishable from SME/teacher validated edges.

An LLM suggestion is evidence for review, not automatically truth.

---

# 6. Prerequisite relations

Prerequisites are particularly important because they drive:

- diagnosis
- tutor explanations
- next-best actions
- Target Tests
- Smart Lessons
- student graph interpretation
- teacher intervention

The graph must distinguish at least conceptually between:

```text
OFFICIAL / EXPLICIT
```

and

```text
INFERRED / SUGGESTED
```

and

```text
VALIDATED
```

The curriculum outline parser must not invent prerequisites merely because one section appears before another.

A sequence in an official specification is not automatically a pedagogical prerequisite relation.

---

# 7. Assessment mapping

QuestionPart is mapped to one or more SpecificationPoints where evidence supports the mapping.

```text
QuestionPart B
   ├── ASSESSES → SpecificationPoint 2.3
   ├── ASSESSES → SpecificationPoint 2.4
   └── ASSESSES → SpecificationPoint 3.1
```

This multi-mapping is essential for:

- multi-concept questions
- applied questions
- practical/data questions
- questions with several skill demands
- learner-state inference
- recommendation reasons

A missing mapping is allowed.

An uncertain mapping must remain uncertain.

A model-generated mapping should carry its generation/review metadata and must not be silently promoted to validated curriculum truth.

---

# 8. Resource mapping

Resources should connect to the smallest meaningful academic anchors available.

Preferred mapping order:

```text
Resource
→ SpecificationPoint
→ Concept / Skill / related graph nodes
```

A resource can cover multiple points.

Example:

```text
Revision Note: “Rates of reaction practical interpretation”
    ├── COVERS → SpecificationPoint 4.2
    ├── COVERS → SpecificationPoint 4.3
    └── SUPPORTS → Skill: interpret experimental graphs
```

Resource validity/servability status must be preserved.

A resource being semantically relevant does not mean it is learner-servable.

---

# 8A. Knowledge Graph Construction & Corpus Mapping

## 8A.1 Purpose

This section defines how the SyllabAI academic Knowledge Graph is constructed from the curriculum and educational corpus.

The Knowledge Graph must not be created by allowing an LLM to freely invent a graph from the available documents.

The construction process is:

```text
Authoritative curriculum
        ↓
CurriculumVersion
        ↓
SpecificationPoint Registry
        ↓
SpecificationPoint → source mapping
        ↓
Concept / Skill extraction
        ↓
Resource enrichment
        ↓
Candidate relationships
        ↓
Provenance + confidence
        ↓
Validation / review
        ↓
Canonical Academic Knowledge Graph
        ↓
Assessment + learner-state overlays
```

The graph therefore has a strict distinction between:

* **what the curriculum explicitly says**
* **what can be deterministically derived from the curriculum**
* **what educational sources support**
* **what an AI/model suggests**
* **what has been human-validated**

The Knowledge Graph is a structured representation of evidence-backed academic relationships, not an unconstrained LLM-generated ontology.

---

## 8A.2 Current Corpus Scope

The current corpus-construction work described by this section concerns:

> **Pearson Edexcel International GCSE Chemistry (4CH1)**

This must not be confused with the SyllabAI Cycle-1 product scope:

> **Edexcel International Advanced Level (IAL) Chemistry**

SyllabAI is intended to support multiple qualifications and curriculum versions. The architecture must therefore allow both IGCSE and IAL Chemistry to coexist without cross-contamination.

```text
Board
└── Pearson Edexcel
    ├── International GCSE
    │   └── Chemistry
    │       └── CurriculumVersion
    │
    └── International Advanced Level
        └── Chemistry
            └── CurriculumVersion
```

A SpecificationPoint, QuestionPart, Resource, Concept, relationship, assessment mapping, or learner state must never be implicitly shared across incompatible qualifications or curriculum versions.

All graph construction and retrieval operations must therefore remain scoped to the applicable:

```text
Board
→ Qualification
→ Subject
→ CurriculumVersion
```

---

## 8A.3 Source Authority Hierarchy

Different corpus sources have different authority.

The graph builder must preserve source role rather than treating every document as equally authoritative.

### Tier 1 — Official Curriculum

Examples:

* official Pearson specification
* official curriculum documentation
* official qualification structure

Authoritative for:

* qualification identity
* curriculum version
* unit/section hierarchy
* SpecificationPoint codes
* official SpecificationPoint wording
* ordering
* applicability
* official practical requirements
* official command-word definitions
* other explicitly stated curriculum constraints

The official curriculum is the canonical source of syllabus truth.

Revision notes, textbooks, and LLM output must not silently redefine or replace it.

---

### Tier 2 — Official Assessment Sources

Examples:

* official past papers
* official mark schemes
* official examiner materials
* official assessment documentation

Authoritative for:

* assessment evidence
* question structure
* marks
* assessment objectives
* command-word usage
* observed specification-point assessment
* official mark-point interpretation

These sources enrich the academic graph and assessment graph but do not rewrite the curriculum hierarchy.

---

### Tier 3 — Instructional / Educational Sources

Examples:

* Pearson Student Book
* approved instructional resources
* SME revision notes

These sources may provide:

* explanations
* terminology
* examples
* worked methods
* skills
* conceptual relationships
* common misconceptions
* prerequisite clues
* practical interpretation
* alternative explanations
* resource-to-SpecificationPoint mappings

They enrich the canonical curriculum graph but cannot redefine official SpecificationPoint identity or wording.

---

### Tier 4 — AI / Algorithmically Derived Knowledge

Examples:

* LLM-extracted concepts
* LLM-generated prerequisite candidates
* automated concept clustering
* automated misconception candidates
* semantic similarity mappings
* inferred relationships

These are **candidate knowledge**, not canonical truth.

AI-generated relationships must carry provenance, confidence, evidence anchors, and validation status.

They must not become learner-facing truth merely because a model generated them.

---

## 8A.4 Knowledge Status

Every graph object or relationship that can affect learning decisions should have an explicit epistemic status.

At minimum:

```text
PUBLISHER / PROVIDER
AI_SUGGESTED
RULE_DERIVED
HUMAN_VALIDATED
```

### PUBLISHER / PROVIDER

Directly supported by an authoritative source.

Examples:

```text
SpecificationPoint 1.26
    source = official Pearson specification
```

or:

```text
QuestionPart
    ASSESSES
SpecificationPoint 1.26
    source = official assessment evidence
```

### RULE_DERIVED

Produced deterministically from explicit source structure or a documented rule.

Examples:

```text
SpecificationPoint
    BELONGS_TO
Section
```

or:

```text
SpecificationPoint
    ORDERED_AFTER
SpecificationPoint
```

when that relationship is directly derived from official ordering.

### AI_SUGGESTED

Produced by an AI or probabilistic extraction process.

Examples:

```text
Concept A
    PREREQUISITE_OF
Concept B
```

when no authoritative source explicitly states that relationship.

AI-suggested knowledge must remain distinguishable from validated knowledge.

### HUMAN_VALIDATED

A candidate relationship or mapping reviewed and explicitly accepted by an authorized human reviewer.

Human validation does not erase its original provenance. The graph should retain both:

```text
generated_by = AI
validated_by = human
validation_status = HUMAN_VALIDATED
```

---

## 8A.5 Canonical, Derived, and Suggested Knowledge

The graph must distinguish three conceptual categories:

### Canonical

Directly supported by authoritative curriculum or assessment sources.

Examples:

* SpecificationPoint identity
* official SpecificationPoint wording
* official hierarchy
* official applicability
* official question/mark-scheme evidence

### Derived

Constructed deterministically or through transparent rules from authoritative or educational sources.

Examples:

* section membership
* ordering
* normalized aliases
* resource coverage inferred from explicit source metadata
* aggregate coverage calculations

### Suggested

Produced through probabilistic or AI-assisted inference and awaiting validation.

Examples:

* prerequisite relationships
* inferred conceptual dependencies
* candidate misconceptions
* candidate skill relationships
* uncertain semantic mappings

Suggested knowledge must never silently become canonical.

---

## 8A.6 Phase 1 — SpecificationPoint Registry

The first graph-building phase is the deterministic extraction of the official curriculum structure.

The official specification is parsed into a canonical SpecificationPoint registry.

The registry must preserve, at minimum:

```text
SpecificationPoint
├── id
├── officialCode
├── officialWording
├── curriculumVersionId
├── section/unit
├── ordering
├── applicability
├── sourceDocument
├── sourceLocation
├── extractionMethod
└── validationStatus
```

The extraction process should be deterministic wherever possible.

LLM interpretation is not required to identify a SpecificationPoint that is explicitly represented in the official specification.

For the current Pearson Edexcel International GCSE Chemistry specification, the deterministic extraction baseline is the set of unique official SpecificationPoint codes present in the source specification.

The parser must validate:

* duplicate codes
* missing codes
* malformed codes
* section assignment
* ordering
* missing wording
* unexpected table structures
* C-point handling
* source-location provenance

The generated registry becomes the backbone against which subsequent corpus mappings are checked.

---

## 8A.7 Phase 2 — Resource-to-SpecificationPoint Mapping

After the SpecificationPoint registry exists, educational resources are mapped to the official points.

The preferred relationship is:

```text
Resource
    └── COVERS
        └── SpecificationPoint
```

A resource may map to multiple SpecificationPoints.

A SpecificationPoint may be covered by multiple resources.

The mapping must preserve uncertainty.

```text
Resource A
    ├── COVERS → SP-1.26       confidence = high
    ├── COVERS → SP-1.27       confidence = high
    └── COVERS → SP-1.28       confidence = candidate
```

### Mapping signals

Mapping may use:

1. explicit source metadata
2. official specification ordering
3. resource headings
4. source URLs/slugs
5. textual references to specification codes
6. semantic similarity
7. LLM-assisted candidate mapping
8. human review

Explicit publisher/source evidence should outrank semantic similarity.

For example, if a revision-note URL or source structure explicitly identifies a syllabus topic, that evidence should be retained as provenance rather than discarded after an embedding-based mapping is generated.

---

## 8A.8 Phase 3 — Concept and Skill Extraction

Once SpecificationPoints are established and resources are mapped, SyllabAI may extract concepts and skills.

The initial objective is not to produce the largest possible ontology.

The objective is to produce a useful, auditable academic structure.

Recommended progression:

```text
SpecificationPoint
        ↓
candidate concepts
        ↓
candidate skills
        ↓
deduplication / identity resolution
        ↓
evidence attachment
        ↓
validated concept registry
```

Concept identity must be handled carefully.

Equivalent terminology should not automatically become separate nodes:

```text
molar mass
relative formula mass
amount of substance
```

should only be separated or merged according to their actual academic meaning and curriculum usage, not simply because an embedding model considers them similar.

Conversely, superficially similar terms must not be merged if they represent distinct concepts.

The graph should prefer a smaller number of well-supported concepts over thousands of weakly differentiated nodes.

---

## 8A.9 Phase 4 — Relationship Generation

Relationships may then be proposed between concepts, skills, SpecificationPoints, and other academic nodes.

Candidate relationships include:

```text
PREREQUISITE_OF
DEPENDS_ON
RELATED_TO
PART_OF
APPLIES_TO
SUPPORTS
REQUIRES_SKILL
DEVELOPS_SKILL
COMMONLY_CONFUSED_WITH
```

The existence of a relationship must be distinguishable from the confidence in that relationship.

For example:

```text
Concept A
    PREREQUISITE_OF
Concept B

status:
    AI_SUGGESTED

evidence:
    Revision Note X
    Student Book p. 83

confidence:
    0.78
```

A relationship should not be served as a strong prerequisite merely because an LLM generated it.

---

## 8A.10 Prerequisite Semantics

The official specification should not be assumed to explicitly define prerequisite relationships.

Therefore:

> **Absence of an official prerequisite statement does not make an inferred prerequisite authoritative.**

Prerequisite relationships may be derived from:

* explicit instructional sequencing
* pedagogical evidence
* assessment dependency
* resource explanations
* validated expert review
* AI-assisted candidate generation

but the provenance must remain visible.

For example:

```text
Concept A
    PREREQUISITE_OF
Concept B
```

does not imply:

```text
Pearson officially states A is a prerequisite for B
```

unless the source actually states that.

A prerequisite candidate should therefore carry:

```text
source
evidenceAnchor
rationale
createdBy
confidence
validationStatus
```

The graph serving layer may use only relationships meeting the applicable validation policy.

---

## 8A.11 Misconception Modeling

Misconceptions require an even higher evidence threshold.

A misconception must not be invented simply because an LLM can imagine a plausible student error.

Preferred evidence sources include:

* explicit SME/examiner statements
* repeated assessment evidence
* validated teacher observations
* documented misconception sources
* repeated learner evidence
* validated instructional material

An AI-generated misconception is initially:

```text
AI_SUGGESTED
```

and must retain its evidence anchor.

The graph must distinguish:

```text
COMMONLY_CONFUSED_WITH
```

from:

```text
MISCONCEPTION_OF
```

and from:

```text
WRONG_ANSWER_PATTERN
```

These are not interchangeable.

---

## 8A.12 Evidence Anchors

Every non-trivial inferred relationship should be traceable to evidence.

An evidence anchor should identify, where available:

```text
sourceDocument
sourceVersion
page
section
paragraph / heading
SpecificationPoint
resource
question / questionPart
markScheme
extractionMethod
```

For AI-generated candidates, retain:

```text
model
prompt/version
generation timestamp
candidate confidence
source context
```

The purpose is reproducibility and review.

A graph reviewer should be able to move from:

```text
Concept A
    PREREQUISITE_OF
Concept B
```

to:

```text
Why does this edge exist?
↓
What evidence supports it?
↓
Who generated it?
↓
Was it validated?
```

---

## 8A.13 Phase 5 — Validation

The graph-building pipeline must include a validation gate.

```text
Extract
   ↓
Normalize
   ↓
Generate candidates
   ↓
Attach provenance
   ↓
Validate
   ↓
Promote
```

Validation should occur at the smallest useful unit.

Examples:

* SpecificationPoint validation
* Resource mapping validation
* Concept identity validation
* Relationship validation
* Misconception validation
* Prerequisite validation

Validation must not require rebuilding the entire graph.

A candidate may remain explicitly uncertain:

```text
validationStatus = REVIEW_REQUIRED
```

rather than being forced into either accepted or rejected.

---

## 8A.14 Graph-as-Code

The canonical academic graph should initially be maintained as version-controlled graph data rather than introducing a dedicated graph database.

The preferred initial representation is structured graph-as-code, for example:

```text
graph/
├── specification_points.yaml
├── concepts.yaml
├── skills.yaml
├── relationships.yaml
├── mappings.yaml
└── validation/
```

The repository should preserve:

* stable IDs
* source provenance
* version information
* validation state
* confidence
* evidence anchors
* change history

Git commits and pull requests provide an auditable human-review boundary.

The graph may subsequently be projected into PostgreSQL and the existing SyllabAI Knowledge Graph machinery.

A Neo4j-style database is not required for the initial architecture.

---

## 8A.15 Assessment Integration

Assessment mapping is a subsequent enrichment stage.

The intended sequence is:

```text
Specification
        ↓
SpecificationPoint Registry
        ↓
Academic concept / skill graph
        ↓
Resources
        ↓
Questions / QuestionParts
        ↓
Assessment mappings
        ↓
Learning evidence
```

QuestionParts may map to multiple SpecificationPoints, concepts, and skills.

Assessment mapping must remain evidence-based and uncertain mappings must remain uncertain.

The absence of converted official past papers must therefore be treated as a corpus-readiness limitation rather than filled with fabricated assessment relationships.

SME topic-question material may be useful as an interim seed, but it must not be represented as equivalent to a complete official past-paper corpus.

---

## 8A.16 Corpus Construction Must Be Incremental

The graph should not be generated in one unconstrained pass over the entire corpus.

Recommended staged construction:

### Stage A

Build the official SpecificationPoint registry.

### Stage B

Map revision notes and other educational resources to SpecificationPoints.

### Stage C

Extract and normalize concepts and skills.

### Stage D

Generate candidate relationships.

### Stage E

Attach evidence, provenance, confidence, and validation status.

### Stage F

Validate high-value relationships.

### Stage G

Integrate assessment evidence.

### Stage H

Expose the graph to learner-state, recommendation, tutor, and teacher systems.

This prevents the failure mode:

```text
112 revision notes
       ↓
LLM
       ↓
thousands of nodes
       ↓
thousands of speculative edges
       ↓
apparently authoritative "Knowledge Graph"
```

Instead:

```text
167 official syllabus anchors
       ↓
controlled enrichment
       ↓
evidence-backed academic graph
```

The graph should grow in semantic depth before it grows in node count.

---

## 8A.17 Separation From Learner State

The academic graph is not the learner model.

The academic graph represents:

```text
What exists academically
How academic entities relate
What resources/questions support them
What evidence supports those relationships
```

The learner model represents:

```text
What this learner has demonstrated
What this learner may know
What this learner struggles with
What this learner should review
```

Therefore:

```text
Academic Graph
        +
Assessment Evidence
        ↓
Learner Model
        ↓
Learner-specific Graph Read Model
```

The graph itself must not mutate its academic relationships because a learner answers a question incorrectly.

For example:

```text
Student answers incorrectly
        ≠
Concept is a prerequisite
```

and:

```text
Student flags a question
        ≠
Concept becomes a misconception
```

Assessment evidence updates learner state; it does not rewrite curriculum truth.

---

## 8A.18 Relationship to the Student and Teacher Lenses

The construction pipeline produces the shared academic graph.

The student and teacher experiences consume different projections of that graph.

```text
                 Academic Knowledge Graph
                         │
              ┌──────────┴──────────┐
              ↓                     ↓
       Student lens           Teacher lens
              │                     │
       learner state          teaching coverage
       mastery evidence       class aggregates
       review state           risk/heatmaps
       recommendations        drill-down
```

The teacher lens must not create a second academic curriculum graph.

Likewise, learner-specific state must not be embedded into the canonical academic graph.

---

## 8A.19 Non-Negotiable Construction Rules

1. Official curriculum defines official curriculum truth.
2. SpecificationPoint is the canonical syllabus anchor.
3. Qualification and CurriculumVersion boundaries are mandatory.
4. Educational resources enrich the graph but do not redefine the curriculum.
5. AI-generated knowledge is candidate knowledge until validated.
6. Every consequential inferred relationship requires provenance.
7. Prerequisites are not assumed to be official unless explicitly supported.
8. Misconceptions require evidence; plausible LLM guesses are insufficient.
9. Uncertain mappings remain uncertain.
10. Missing assessment evidence must not be fabricated.
11. QuestionPart is preferred over whole-question mapping where granularity permits.
12. Academic graph state and learner state remain separate.
13. Learner evidence must not rewrite academic relationships.
14. The initial graph should favor auditable, useful relationships over maximum graph size.
15. Graph construction must be reproducible from versioned source material and extraction rules.
16. Human validation is a promotion mechanism, not a destructive replacement of provenance.
17. The graph should initially be maintained as version-controlled structured data and projected into existing SyllabAI persistence/read models.
18. IGCSE and IAL content must remain isolated by qualification and curriculum version.

---

## 8A.20 Canonical Construction Mental Model

The Knowledge Graph should ultimately be understood as:

```text
OFFICIAL CURRICULUM
        │
        ▼
SpecificationPoint Registry
        │
        ├───────────────┐
        ▼               ▼
 Concepts             Skills
        │               │
        └───────┬───────┘
                ▼
        Academic Relations
        │       │       │
        │       │       ├── prerequisites
        │       │       ├── dependencies
        │       │       ├── related concepts
        │       │       └── misconceptions
        │       │
        ▼       ▼
   Resources  Assessment
        │       │
        └───┬───┘
            ▼
     Evidence-backed
      Academic Graph
            │
     ┌──────┴──────┐
     ▼             ▼
 Student Lens   Teacher Lens
     │             │
 Learner State  Teaching State
```

The central principle is:

> **The curriculum establishes the anchors; evidence establishes the mappings; inference proposes relationships; validation determines what becomes trusted graph knowledge.**


# 9. Student Knowledge Graph

## 9.1 Student question

The student lens asks:

> **What do I know, what am I struggling with, and what should I do next?**

The student graph therefore combines:

```text
Stable academic graph
        +
Student-specific learner overlay
        +
Evidence/review context
        +
Relevant next actions
```

## 9.2 Student graph read model

Conceptually:

```text
Student
  ↓
Subject Enrollment
  ↓
CurriculumVersion
  ↓
Academic Graph
  ↓
Learner Overlay
```

The personalized read model may expose, per relevant node:

```text
node identity
academic title/code
hierarchy depth
relationships
mastery band/value when measured
misconception state where supported
evidence count
attempt count
confidence information
procedural fluency state
reviewDueAt
problematic state where applicable
last evidence timestamp
```

Unpractised nodes must not become fake zeros.

If the learner has no evidence for a node, the UI should be able to represent “not measured yet” distinctly from poor performance.

## 9.3 Student node states

A student-facing node may conceptually have states such as:

```text
NOT_MEASURED
MEASURED_STRONG
MEASURED_GOOD
MEASURED_DEVELOPING
MEASURED_WEAK
MEASURED_CRITICAL
```

These labels are presentation bands derived from learner state. They are not official curriculum semantics.

Exact thresholds belong to the learner-model/read-model implementation and must remain aligned across student views.

## 9.4 Student graph dimensions

A node can simultaneously have multiple dimensions.

Example:

```text
SpecificationPoint 2.4

Mastery:        DEVELOPING
Misconception:  POSSIBLE / EVIDENCED
Fluency:        TIMED GAP
Confidence:     LOW
Review:         DUE
Evidence:       6 attempts
```

Do not collapse all dimensions into one scalar color if the UI can reasonably expose more information.

A mastery color should never imply that confidence, misconception, or review state has the same meaning.

---

# 10. Student graph visual behavior

The current product direction is **2D-first**.

The graph is not required to be a 3D force graph for Cycle 1.

The current visualization direction is a structured, readable graph rather than a decorative physics simulation.

The existing implementation direction is consistent with:

```text
layered hierarchy / graph depth
+ academic relationships
+ learner-state node styling
+ node selection
+ accessible alternative tree representation
```

The visualizer should prioritize:

- separation of nodes
- readable labels
- relationship clarity
- deterministic layout
- keyboard accessibility
- meaningful selection state
- subject isolation
- clear distinction between measured and unmeasured state

It should avoid:

- placing every node on top of one another
- forcing all nodes into one dense cluster without hierarchy
- decorative animations that hide relationships
- physics movement that makes a stable academic structure feel unstable
- presenting learner-state color as if it were official curriculum truth

A graph may later evolve toward richer force-directed or 3D presentation, but that is not a prerequisite for Cycle 1.

---

# 11. Student graph interactions

Minimum meaningful interactions should include:

### Node selection

Selecting a node can expose:

```text
Node title/code
Official specification statement
Current learner-state band
Evidence summary
Misconception summary if available
Review status
Prerequisite links
Available practice
Available resources
Tutor CTA
```

### Expand / collapse

Large graph regions may be collapsed to maintain readability.

Collapsed nodes must not imply that child content is absent.

### Relationship inspection

Prerequisite and other relationship types should be distinguishable visually.

For example:

```text
PART_OF                solid hierarchy line
REQUIRES_PREREQUISITE  distinct relationship style
RELATED_TO             lower-emphasis relationship
```

Exact colors/styles are UI decisions; semantic distinctions are mandatory.

### Drill-down

The user should be able to move:

```text
Unit
→ Topic
→ SubTopic
→ SpecificationPoint
→ Question / Resource / Evidence
```

### Practice

A node should be able to lead to appropriate practice if validated questions exist.

If no valid questions exist, show an honest empty state.

Do not fabricate questions merely to fill a card.

### Tutor

A node or problematic question may provide a Tutor entry point.

The Tutor must receive the relevant subject/graph context but remain grounded in validated source material and actual learner evidence.

---

# 12. Student graph and learning evidence

The graph is a projection of evidence; it is not the evidence itself.

Canonical path:

```text
QuestionPart
   ↓
QuestionAttempt
   ↓
AssessmentEvidence
   ↓
Learner model
   ↓
Skill/SpecificationPoint state
   ↓
Student graph overlay
```

Important distinctions:

```text
WRONG ANSWER
≠
LOW MASTERY

FLAGGED QUESTION
≠
LOW MASTERY

SELF-DOUBT
≠
LOW MASTERY

UNPRACTISED
≠
LOW MASTERY

NOT MEASURED
≠
ZERO
```

The learner model determines how different evidence types contribute to inferred state.

The UI must not perform ad hoc mastery arithmetic.

---

# 13. Student graph and recommendations

The graph should make the recommendation system understandable, but the graph does not itself choose recommendations.

Recommendation flow:

```text
Learner evidence/state
        ↓
Graph context
        ↓
Candidate generation
        ↓
Next Best Learning Action
```

A node may be associated with reasons such as:

```text
Repeated low-mark evidence
Prerequisite weakness
Due review
Misconception evidence
Timed-vs-untimed gap
Uncovered SpecificationPoint
Teacher assignment
```

Recommendation explanations must refer to actual evidence or structured state.

Do not show:

> “AI thinks you should study this.”

Prefer:

> “You scored below your recent average on 4 recent questions covering this specification point.”

The exact language should be generated from structured reason codes, not invented by an LLM.

---

# 14. Student graph and review state

The graph may expose review urgency, but review state remains separate from mastery.

For example:

```text
Node: Mole calculations
Mastery: DEVELOPING
Review: DUE
Problematic questions: 2
```

Resolving a question flag does not itself make the graph node secure.

A later successful retrieval may change learner state.

---

# 15. Teacher Knowledge Graph

The teacher lens asks:

> **What have I taught, what does my class understand, which students need attention, and where should I intervene?**

The teacher graph therefore uses the same academic graph plus teacher-specific overlays.

Conceptually:

```text
Same Academic Graph
        +
Teaching Coverage Overlay
        +
Class Evidence Aggregation
        +
Teacher Authorization
        +
Optional Risk/Attention Signals
```

---

# 16. Teacher graph dimensions

A teacher graph must not collapse “teaching coverage” and “learner performance” into a single dimension.

At minimum there are two dimensions:

### Dimension A — Teaching coverage

Examples:

```text
NOT_TAUGHT
TAUGHT / COVERAGE_RECORDED
PARTIALLY_COVERED (if later supported)
```

### Dimension B — Class understanding

Examples:

```text
NOT_MEASURED
STRONG
GOOD
DEVELOPING
WEAK
CRITICAL
```

Therefore a node can be:

```text
NOT_TAUGHT + NOT_MEASURED
TAUGHT + NOT_MEASURED
TAUGHT + STRONG
TAUGHT + DEVELOPING
TAUGHT + CRITICAL
```

The system must never turn:

```text
NOT_TAUGHT
```

into:

```text
LOW_MASTERY
```

This is one of the most important semantic rules of the teacher graph.

---

# 17. Teacher graph aggregation

Teacher graph data should be aggregated from the same learner evidence substrate.

Conceptual flow:

```text
Class
  ↓
Authorized student enrollments
  ↓
Question attempts / AssessmentEvidence
  ↓
SpecificationPoint mappings
  ↓
Individual learner states
  ↓
Class aggregate
```

A graph node should support more than a single mean.

Useful class-level read-model fields include:

```text
studentCount
studentsWithEvidence
meanMastery
medianMastery where useful
proficientCount
proficientPercentage
developingCount
developingPercentage
strugglingCount
strugglingPercentage
misconceptionCount
misconceptionPrevalence
attemptCount
recentAttemptCount
confidence-performance divergence where available
lastTaughtAt / coverage timestamp where available
```

The exact aggregate set can evolve, but the principle is fixed:

> **A class average must not hide the distribution.**

Example:

```text
Node: Electrolysis

Mean mastery: 0.71
Secure:        46%
Developing:    32%
Struggling:    22%
Students with evidence: 41/48
Known misconception: 9 students
```

That is more informative than simply showing “71%”.

---

# 18. Teacher graph drill-down

Teacher drill-down should follow a controlled hierarchy:

```text
Class graph node
      ↓
Affected student cohort
      ↓
Individual student
      ↓
Student subject graph
      ↓
Questions / evidence / assignments
      ↓
Teacher action
```

Examples of teacher actions:

```text
Review recent attempts
Inspect misconceptions
Open student graph
Create targeted assignment
Open Test Builder
Create targeted test
Send announcement
Open Tutor/AI teaching assistance
```

All student-level drill-down is authorization-controlled.

A teacher must not be able to navigate from a graph node into unauthorized students merely because those students share the same specification point.

---

# 19. Teaching coverage model

Teaching coverage is teacher-side state and should have provenance.

A conceptual teaching coverage record may include:

```text
classId
teacherId
subjectId
curriculumVersionId
nodeId
coverageState
coveredAt
coverageMethod
sourceAssignmentId (where applicable)
notes / rationale
```

Coverage should be able to come from explicit teacher actions or well-defined system events.

Do not silently infer “taught” from a student's question attempt.

A student can know something before a teacher teaches it.

A teacher can “cover” a topic without students understanding it.

These are separate facts.

---

# 20. Teacher graph and assignments

Assignments provide another link between teacher intent and the graph.

Example:

```text
Teacher
  ↓
Assignment
  ↓
Question / Resource
  ↓
SpecificationPoint
  ↓
Student submission/evidence
  ↓
Class graph aggregation
```

An assignment being issued does not automatically mean that all underlying content is mastered.

An assignment resource being opened does not automatically create assessment evidence.

Only assessment-bearing submissions should contribute to learning evidence according to the configured evidence policy.

---

# 21. Teacher graph and at-risk signals

At-Risk Students is a separate inference/attention surface that may use graph state.

Example:

```text
Electrolysis
     ↓
22% of class struggling
     ↓
9 students with repeated misconception evidence
     ↓
3 students with recent decline
```

The graph can expose the area of concern.

The risk system determines whether a student is classified as “at risk”.

Do not make the graph color itself the risk classifier.

Risk flags should retain:

- evidence
- time window
- rule/model version
- relevant subject/class scope
- generation timestamp

---

# 22. Teacher Data Assistant and graph

The Data Assistant should query structured teacher-authorized read models first.

A query such as:

> “Which chemistry topics are weakest in 10A?”

should conceptually resolve to:

```text
Teacher scope
→ Class 10A
→ Chemistry subject
→ Current curriculum version
→ authorized learner evidence
→ graph aggregation
→ ordered weak nodes
```

The LLM may summarize the returned data, but it must not invent the statistics.

Responses should retain scope and time window where relevant.

---

# 23. Teacher AI Assistant and graph

Teacher AI Assistant can use graph context to support academic work.

Examples:

```text
Explain specification point 3.2.

Create a lesson starter for this node.

Find validated resources covering this point.

Explain which prerequisite knowledge students need first.
```

Grounding hierarchy should prefer:

```text
official specification
→ validated curriculum graph
→ validated resources
→ validated questions / mark schemes
→ approved teaching materials
```

Generated teaching material is a draft until it passes the relevant validation policy.

---

# 24. Graph provenance

Every graph object that can influence a learning or teaching decision should have enough provenance to answer:

```text
Where did this come from?
Who/what created it?
When?
Which source/version?
Was it validated?
Which parser/model generated it?
```

For curriculum nodes:

```text
source document
page
section/element
curriculum version
extraction method
validation status
```

For knowledge edges:

```text
source
rationale
created by
confidence
validation status
```

For learner overlays:

```text
evidence source
aggregation/model version
as-of timestamp
```

For teacher aggregates:

```text
class scope
student count
aggregation definition/version
time window
```

---

# 25. Versioning

The graph must be version-aware.

At minimum distinguish:

```text
Academic graph version
Curriculum/specification version
Knowledge relation version
Learner-state timestamp/model version
Teacher aggregation/read-model version
```

A curriculum update must not rewrite historical learner evidence against a new specification without preserving applicability/version context.

Historical assessments may remain useful while being mapped to a specific curriculum version or cross-version equivalence relation.

Never silently merge two specification versions because their titles look similar.

---

# 26. Multi-subject behavior

SyllabAI is subject-first.

All graph reads must be bounded by explicit academic identity:

```text
Board
Qualification
Subject
CurriculumVersion
```

Where appropriate, APIs should additionally scope by:

```text
Unit
Topic
SpecificationPoint
```

A student with multiple subjects must never accidentally see:

- another subject's learner state
- another specification's questions
- another subject's recommendations
- another subject's tutor context
- another class's teacher aggregate

Cross-subject relationships are possible in a future general knowledge layer, but learner-facing academic graph surfaces must remain subject-safe unless a deliberate cross-subject feature exists.

---

# 27. Authorization model

The graph is not an authorization bypass.

## Student

A student may read:

- their enrolled subject graph
- their own learner overlay
- their own attempt/evidence-derived summaries
- learner-servable resources/questions

A student must not read another student's learner overlay.

## Teacher

A teacher may read:

- the subject graphs within their teaching authorization
- class aggregates for their authorized classes
- individual student graphs for students within their authorized teaching scope
- assignment/assessment results within that scope

## Admin

Admin permissions follow the existing RBAC architecture and must not be inferred solely from frontend route visibility.

Backend authorization is authoritative.

---

# 28. API/read-model guidance

The exact endpoint names are implementation details, but the graph architecture should support reads equivalent to:

```text
Student:

GET /api/v1/learners/me/knowledge-graph
GET /api/v1/learners/me/knowledge-graph?rootId=...
GET /api/v1/learners/me/state
GET /api/v1/learners/me/recommendations
GET /api/v1/learners/me/question-attempts
```

Teacher:

```text
GET /api/v1/teacher/classes/{classId}/knowledge-graph
GET /api/v1/teacher/classes/{classId}/knowledge-graph?nodeId=...
GET /api/v1/teacher/classes/{classId}/students/{studentId}/knowledge-graph
```

Exact routes must follow the current implementation and security configuration; this document defines semantics, not permission to invent incompatible endpoints.

The graph API should return a **read model**, not raw database rows.

The read model should compose:

```text
academic node
+ relationships
+ relevant overlay state
+ provenance/metadata needed by the UI
```

Do not push client-side joins of multiple learner endpoints into the frontend when the server can provide one authoritative personalized read model.

---

# 29. Student graph read-model rules

The student graph read model should obey the following:

1. **No fabricated measurements.**
2. Unpractised nodes return null/NOT_MEASURED semantics, not zero mastery.
3. Misconception annotations appear only where the learner model has supported misconception state.
4. Review due state is derived from actual pending review records.
5. `asOf` timestamps must be respected where the decay/state calculation is time-sensitive.
6. Prerequisite edges should be returned in a way that supports deterministic rendering.
7. Subject and curriculum scope must be enforced server-side.
8. The graph should not mutate learner state as a side effect of reading it.

---

# 30. Teacher graph read-model rules

The teacher graph read model should obey:

1. Teaching coverage and class understanding are separate fields.
2. `NOT_TAUGHT` never means weak mastery.
3. Aggregates must have explicit scope and time semantics.
4. Students without evidence are not silently converted into zero mastery.
5. Student drill-down is authorization-controlled.
6. Aggregate calculations should use the same learner-state/evidence substrate as the student view.
7. Averages should not be the only class statistic when distribution information is available.
8. Risk signals are separate inferred outputs, not synonymous with graph color.
9. Reading a teacher graph must not mutate student state.
10. Class membership must come from the actual authorization/class model once the long-term class entity exists; the current Cycle-1 cohort shortcut must not be perpetuated indefinitely.

---

# 31. Current Cycle-1 implementation reality

The current implementation is intentionally 2D-first.

The current student graph direction includes:

```text
personalized KG endpoint
→ one composed learner graph payload
→ SVG-based 2D visualization
→ layered hierarchy/depth
→ prerequisite edges
→ learner-state styling
→ node selection/detail
→ tree alternative
→ practice deep links
```

The current teacher surface is focused on class/roster/marking/review and has not yet become the complete long-term class analytics graph described here.

Cycle 1 must not be expanded merely because the long-term graph model supports richer teacher functionality.

The long-term architecture remains:

```text
same graph
├── student lens
└── teacher lens
```

---

# 32. What the graph must NOT become

The graph must not become any of the following:

## Not a decorative map

A graph with circles and lines but no meaningful academic semantics is not SyllabAI's Knowledge Graph.

## Not a second curriculum

Do not maintain an official curriculum tree in one place and a different teacher/student curriculum tree elsewhere.

## Not a second learner model

Do not calculate learner mastery independently in graph UI code.

## Not a second evidence ledger

Do not store attempts or assessment facts inside graph nodes as an alternative history system.

## Not a recommendation engine

The graph provides context; recommendation policies decide actions.

## Not a risk classifier

Teacher graph state can expose evidence relevant to attention, but risk classification remains a separate inference layer.

## Not an LLM-owned truth system

LLMs can suggest mappings, relations, explanations and drafts. They do not automatically establish canonical curriculum truth.

---

# 33. Accessibility requirements

The graph must have an accessible alternative to visual navigation.

The existing product direction includes a tree representation.

At minimum, keyboard-accessible users should be able to:

```text
navigate nodes
inspect node labels
open node details
follow meaningful relationships
reach practice/resource/tutor actions
```

SVG labels and selection state should expose meaningful ARIA/accessibility semantics.

The visual graph must not be the only way to understand learner state.

---

# 34. Performance guidance

The graph can become large.

The first priority is correctness and semantic clarity, followed by scalable read patterns.

Prefer:

```text
server-composed read models
batched queries
bounded subgraphs
root/depth filtering
subject-scoped traversal
lazy loading for detailed relationships
```

Avoid:

```text
N+1 graph requests from the browser
client-side joining of large node/evidence datasets
loading the entire multi-subject graph for every dashboard view
```

The backend remains responsible for authorization and semantic composition.

---

# 35. Graph layout guidance

The academic graph is not an arbitrary social network.

Its layout should communicate academic structure.

Recommended conceptual hierarchy:

```text
Board / Qualification
          ↓
       Subject
          ↓
   CurriculumVersion
          ↓
     Unit / Section
          ↓
     Topic / SubTopic
          ↓
  SpecificationPoint
          ↓
Concept / Skill / relations
```

A visualization may hide upper identity levels after the subject context is established in order to maximize readability.

For student use, the default should emphasize:

```text
current subject
→ relevant syllabus region
→ learner state
→ prerequisites
→ actionable next steps
```

For teacher use, the default should emphasize:

```text
current subject/class
→ coverage
→ class distribution
→ weak clusters
→ student drill-down
```

Do not automatically render every possible relationship at the same visual prominence.

---

# 36. Graph selection behavior

Selecting a node should be contextual to the lens.

## Student selected node

Show:

```text
Official objective
Learner state
Evidence summary
Misconceptions
Review status
Prerequisites
Practice
Tutor
Resources
```

## Teacher selected node

Show:

```text
Official objective
Teaching coverage
Class distribution
Evidence count
Misconception prevalence
Affected students
Recent assessment activity
Assignment/test opportunities
```

The same underlying node can therefore expose different read-model panels without becoming two different nodes.

---

# 37. Graph → question workflow

Student:

```text
Graph node
→ practice CTA
→ validated question set
→ attempt
→ evidence
→ learner update
→ refreshed graph
```

Teacher:

```text
Graph node
→ inspect weak cohort
→ open questions / Test Builder
→ assign targeted work
→ new student evidence
→ refreshed class graph
```

This is an important product loop.

The graph should not be a dead-end visualization.

---

# 38. Graph → Tutor workflow

Student:

```text
Graph node / problematic question
→ Ask Tutor
→ Tutor receives subject + node + relevant learner context
→ grounded explanation
→ practice/retry
→ new evidence
```

The Tutor should not be asked to independently reconstruct the curriculum from the graph's label alone.

The backend should supply the relevant validated grounding context.

---

# 39. Graph → recommendation workflow

The recommendation engine may use the graph for candidate generation.

Example:

```text
Student Graph
   ↓
Weak measured node
   ↓
Prerequisite traversal
   ↓
Candidate resources / questions
   ↓
Next Best Learning Action
```

The recommendation engine remains responsible for ranking.

The graph remains responsible for academic relationships and learner-state context.

---

# 40. Graph → teacher action workflow

Teacher:

```text
Class Graph
   ↓
weak SpecificationPoint
   ↓
affected students
   ↓
inspect evidence
   ↓
create targeted Test Builder test / assignment
   ↓
students attempt
   ↓
assessment evidence
   ↓
class graph refresh
```

This is the teacher-side equivalent of the student's adaptive loop.

---

# 41. Empty and unknown states

The graph must distinguish:

```text
NO_DATA
NOT_MEASURED
NOT_TAUGHT
NOT_APPLICABLE
UNMAPPED
UNKNOWN
```

These are not interchangeable.

Examples:

### Student

```text
No attempts yet
→ NOT_MEASURED
```

not:

```text
mastery = 0
```

### Teacher

```text
No coverage record
→ NOT_TAUGHT / UNKNOWN COVERAGE
```

not:

```text
class is weak
```

### Question mapping

```text
No validated specification mapping yet
→ UNMAPPED
```

not:

```text
guessed topic
```

This semantic discipline is critical to the integrity of the graph.

---

# 42. Security/privacy rules for graph data

Graph views can reveal sensitive academic information.

Protect:

- student identifiers
- learner mastery
- misconceptions
- confidence
- teacher observations
- class-level distributions where group size is small
- assignment results
- risk/attention signals

Teacher views must be authorization-scoped.

Student views must be self-scoped.

Do not leak private student state through:

- graph search endpoints
- autocomplete
- node metadata
- error messages
- recommendation explanations
- client-side caches

---

# 43. Research integrity

The graph is also part of the research instrument.

Important distinction:

```text
Observed evidence
→ Learner-state inference
→ Graph display
```

The graph itself must not be treated as direct ground truth for educational claims.

For research-sensitive values, preserve:

```text
model/algorithm version
parameter version
as-of time
evidence window
source population
```

When the graph exposes a derived state, the system should be able to explain which learner-model output produced it.

Teacher graph aggregates should similarly preserve aggregation definitions and windows.

---

# 44. Implementation boundaries by repository

## `syllabai`

Contains the canonical project architecture, decisions, documentation and backlog.

This document belongs here as the durable graph context.

## `syllabai-core`

Owns graph domain behavior, persistence, traversal, learner-state composition, authorization and read-model APIs.

Relevant modules include:

```text
curriculum
knowledge
assessment
learner
diagnostic
recommendation
teacher
content
infrastructure
```

## `syllabai-web`

Owns graph presentation and interaction:

- student graph visualization
- teacher graph visualization when implemented
- selection/detail panels
- tree alternative
- accessibility
- navigation to practice/tutor/resource surfaces

It must not own authoritative learner-state calculations.

## `syllabai-parser`

Owns offline extraction/normalization of source material that may seed curriculum/content graph structures.

It must preserve provenance and use canonical document/curriculum contracts.

---

# 45. Relationship to current learner-state implementation

The existing learner-state implementation includes:

```text
BKT mastery
BDT misconception inference
Ebbinghaus decay/review
Timed-vs-untimed procedural fluency gap
Confidence/self-doubt evidence
Question-level learning evidence
```

The graph consumes these outputs.

It does not replace them.

A graph node should not independently re-run a separate mastery algorithm.

---

# 46. Relationship to current evidence architecture

The evidence architecture establishes:

```text
QuestionAttempt
        ↓
AssessmentEvidence
        ↓
Learner Model
        ↓
Graph Overlay
```

Review state runs alongside evidence:

```text
Attempt
 ↓
Problem / Doubt / Self-doubt
 ↓
Review State
```

The graph may display review urgency but must not turn a flag into a mastery decrement.

---

# 47. Relationship to current recommendation architecture

The recommendation architecture defines the graph as one of the main sources of structured learner context.

The graph can supply:

- weak nodes
- prerequisite relations
- uncovered points
- misconception locations
- due reviews
- resource/question mappings

The recommender combines this with evidence and hard constraints to produce Next Best Learning Actions.

The graph itself does not perform engagement optimization.

---

# 48. Relationship to current mock-exam architecture

The Mock Exam Generator uses the same academic graph and assessment substrate.

Relevant path:

```text
Blueprint
→ candidate Question/QuestionPart
→ SpecificationPoint mapping
→ learner evidence
→ personalized allocation where policy allows
→ mock
```

Mock results feed back into the existing Question Attempt / Learning Evidence layer and therefore may influence future graph state.

The mock generator must not create an independent graph or independent evidence model.

---

# 49. Future enhancements

These are long-term options, not automatic Cycle-1 scope:

- richer concept graph beyond SpecificationPoints
- 3D graph visualization
- force-directed exploratory graph modes
- graph search
- graph filtering by skill/type/evidence
- comparison of learner graph state over time
- teacher class-over-time graph replay
- prerequisite path explanation
- misconception cluster visualization
- cross-topic transfer visualization
- class-vs-specification coverage comparison
- curriculum-version comparison
- research graph analytics

Each must preserve the core semantics of this document.

---

# 50. Testing requirements

Graph functionality should have tests at several layers.

## Domain tests

Verify:

- hierarchy semantics
- relationship semantics
- subject isolation
- provenance propagation
- learner overlay composition
- teacher aggregation
- NOT_TAUGHT vs LOW_MASTERY

## Integration tests

Verify:

- recursive prerequisite retrieval
- personalized graph read model
- evidence → state → graph flow
- teacher class aggregation
- authorization
- correct behavior with empty/unmapped data

## Web tests

Verify:

- node rendering
- selection
- graph/tree toggle
- accessible navigation
- deep links
- honest empty states
- refresh after evidence changes

## End-to-end tests

The most important E2E scenario is:

```text
student attempt
→ evidence persisted
→ learner state updated
→ graph refreshed
→ recommendation changes
```

Teacher E2E:

```text
class evidence
→ graph aggregate changes
→ weak node visible
→ affected students drill-down
→ teacher action
```

---

# 51. Agent implementation checklist

Before changing graph code, an agent must ask itself:

1. Is this an academic-graph change, a learner-state change, a teacher-overlay change, or a UI change?
2. Am I creating a second representation of information that already exists?
3. Is the node/edge backed by a source or evidence?
4. Is the relationship validated or merely suggested?
5. Is the value observed, inferred, or recommended?
6. Is the information subject/curriculum scoped?
7. Is the value time/version sensitive?
8. Could the UI accidentally present unknown as zero?
9. Could teacher coverage be confused with learner mastery?
10. Could this leak another learner's data?
11. Does this belong in the server read model rather than frontend code?
12. Does this need an architecture decision, tracker update, or worklog entry?

---

# 52. Non-negotiable rules

The following rules are canonical.

1. **Student and teacher use the same academic graph.**
2. **The teacher graph is a lens, not a second graph.**
3. **SpecificationPoint is a first-class curriculum anchor.**
4. **Official curriculum hierarchy and conceptual knowledge relations are distinct layers.**
5. **Learner state is an overlay; it does not mutate official curriculum nodes.**
6. **QuestionPart may map to multiple SpecificationPoints.**
7. **Attempts/evidence live in the existing evidence system, not in graph-specific tracking tables.**
8. **Unmeasured is not zero.**
9. **Not taught is not low mastery.**
10. **Flagged/resolved is not direct mastery arithmetic.**
11. **Recommendation reasons must come from structured evidence/state.**
12. **LLM suggestions do not automatically become canonical graph truth.**
13. **Graph data is subject/curriculum scoped.**
14. **Teacher drill-down is authorization controlled.**
15. **Graph read models should be server-composed where practical.**
16. **Visual polish must not undermine academic semantics.**
17. **The accessible tree/structured alternative remains available when the graph is difficult to navigate visually.**
18. **Cycle-1 scope remains Edexcel IAL Chemistry unless explicitly changed.**
19. **3D/force-graph work is optional long-term polish, not a Cycle-1 correctness requirement.**
20. **The graph exists to make the adaptive learning system understandable and actionable, not merely to look impressive.**

---

# 53. Canonical mental model

When an agent needs to reason about SyllabAI's Knowledge Graph, use this model first:

```text
                         OFFICIAL ACADEMIC TRUTH
                                  │
      ┌───────────────────────────┼───────────────────────────┐
      │                           │                           │
 Curriculum Hierarchy      Knowledge Relations       Assessment/Resources
      │                           │                           │
      └───────────────────────────┼───────────────────────────┘
                                  ↓
                           SHARED GRAPH
                                  │
                ┌─────────────────┴─────────────────┐
                │                                   │
          STUDENT LENS                         TEACHER LENS
                │                                   │
       learner-state overlay                 coverage overlay
                │                                   │
       evidence / review                     class aggregation
                │                                   │
       “What do I know?”                     “What was taught?”
       “What next?”                          “What needs attention?”
                │                                   │
                └─────────────────┬─────────────────┘
                                  ↓
                         ACTION / INTERVENTION
                                  │
                 Tutor / Practice / Assignment /
                 Test Builder / Review / Recommendation
                                  │
                                  ↓
                             NEW EVIDENCE
                                  │
                                  └────────→ graph refresh
```

That model should remain stable even as individual graph technologies, layouts, database queries, or UI components evolve.

---

# 54. Source documents

This document should be read together with:

- `MASTER_SPEC.md`
- `SUBJECT_ARCHITECTURE.md`
- `TEACHER_ARCHITECTURE.md`
- `QUESTION_ATTEMPT_AND_LEARNING_EVIDENCE.md`
- `LEARNING_EVIDENCE_AGENT_ADDENDUM.md`
- `RECOMMENDATION_SYSTEM_ARCHITECTURE.md`
- `RECOMMENDATION_SYSTEM_AGENT_ADDENDUM.md`
- `MOCK_EXAM_GENERATOR_ARCHITECTURE.md`
- `AGENT.md`
- `PROJECT_CONTEXT.md`

The source-of-truth hierarchy remains governed by the Master Spec and the named architecture addenda. This document is canonical specifically for the **Knowledge Graph context, student lens, teacher lens, and the semantic rules connecting them**.
