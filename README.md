# Google SRE Interview Preparation

> **Focused preparation for Google Site Reliability Engineering interviews — coding, reliability thinking, production judgment, and behavioral execution.**

Site Reliability Engineering interviews are not only about solving an algorithm.

A strong SRE candidate should be able to **write correct software, reason about production systems, diagnose failures, automate operational work, communicate during ambiguity, and make reliability trade-offs**.

This repository provides a focused preparation path for candidates preparing for Google SRE-style interviews, particularly when the interview process includes:

* a **45-minute coding round**
* a **45-minute behavioral round**
* only a few days remaining before the interview

---

## 🚀 Complete Google SRE Interview Preparation Pack

If your interview is approaching and you want the complete structured preparation package, including coding mocks, drills, behavioral simulations, story-building exercises, and the 3-day execution plan:

### 👉 [Get the Complete Google SRE Interview Preparation Pack](https://tobiweissmann.gumroad.com/l/ouiwoi)

**Included in the complete pack:**

* 45-Minute Google SRE Coding Mock
* 12 Coding Interview Drills
* 45-Minute Behavioral Mock
* SRE Behavioral Story Bank
* 3-Day Interview Preparation Plan
* Interview-style follow-up questions
* Scoring criteria
* Production and reliability reasoning exercises

> Built for candidates who need to **practice the interview**, not simply read more interview theory.

---

# What Does a Google SRE Actually Do?

Site Reliability Engineering combines two engineering disciplines:

```text
Software Engineering
        +
Systems Engineering
        ↓
Site Reliability Engineering
```

The objective is not merely keeping servers running.

SREs build and operate systems that need to remain:

* reliable
* scalable
* observable
* performant
* recoverable
* maintainable
* automatable

An SRE therefore moves between software development and production operations.

A simplified mental model is:

```text
Design
  ↓
Build
  ↓
Deploy
  ↓
Measure
  ↓
Detect Failure
  ↓
Respond
  ↓
Learn
  ↓
Automate
  ↓
Improve Reliability
```

That mindset should also appear in your interview answers.

---

# Core Google SRE Competencies

A useful preparation model is to think in terms of seven competency areas.

| Competency    | What a strong candidate demonstrates                                 |
| ------------- | -------------------------------------------------------------------- |
| Coding        | Correct, readable and testable implementation                        |
| Algorithms    | Appropriate data structures and complexity reasoning                 |
| Systems       | Understanding of operating systems, networks and distributed systems |
| Reliability   | Failure-aware design and operational judgment                        |
| Observability | Reasoning using metrics, logs, traces and system signals             |
| Automation    | Eliminating repetitive operational work with software                |
| Collaboration | Clear communication, ownership and decision-making under pressure    |

The strongest candidates connect these areas rather than treating them independently.

---

# The SRE Interview Mindset

Consider a coding problem.

A software-engineering-only response may stop after:

```text
Correct algorithm
+
Good complexity
```

An SRE-oriented candidate should be capable of going further:

```text
Correct algorithm
        ↓
Edge cases
        ↓
Failure conditions
        ↓
Testing
        ↓
Scale
        ↓
Operational consequences
```

You do not need to force production engineering into every coding answer.

But when the interviewer changes constraints, introduces failures, or asks what happens at scale, you should be comfortable extending your reasoning.

---

# Coding Round

A 45-minute coding interview usually leaves less implementation time than candidates expect.

A practical structure is:

```text
0–5 min
Understand and clarify

5–10 min
Choose approach and data structures

10–30 min
Implement

30–38 min
Test and debug

38–43 min
Complexity + follow-ups

43–45 min
Final review
```

Do not immediately start typing.

---

## What to Demonstrate During Coding

A strong coding performance should show that you can:

1. Clarify ambiguous requirements.
2. Identify important constraints.
3. Select appropriate data structures.
4. Explain the solution before implementation.
5. Produce correct, readable code.
6. Handle edge cases.
7. Test systematically.
8. State time and space complexity.
9. Respond to changing requirements.
10. Communicate continuously.

---

# Example SRE-Oriented Coding Exercise

Imagine receiving service events:

```text
timestamp
service
status
latency_ms
```

For example:

```text
12:01:01 payments 200 120
12:01:02 search   500 840
12:01:03 payments 503 920
12:01:04 search   200 180
```

You are asked:

> Return the failure count for each service.

The initial problem is straightforward.

But an SRE interview can become much more interesting through follow-ups.

### Follow-up 1

What if there are **10 million events**?

### Follow-up 2

What if events arrive continuously?

### Follow-up 3

What if events arrive out of order?

### Follow-up 4

What if memory is limited?

### Follow-up 5

What if you need the failure rate for only the **last five minutes**?

### Follow-up 6

How would you detect that one service is becoming unhealthy?

Now the exercise moves from:

```text
HashMap
```

toward:

```text
Streaming
+
Windowing
+
Memory bounds
+
Observability
+
Reliability reasoning
```

That progression is important for SRE preparation.

---

# Topics Worth Reviewing for Coding

Prioritize fundamentals rather than trying to solve hundreds of random problems.

### High priority

* arrays
* strings
* hash maps
* sets
* queues
* stacks
* trees
* graphs
* sorting
* binary search
* intervals
* BFS / DFS
* sliding windows

### Be comfortable explaining

```text
Time Complexity
Space Complexity
Data Structure Choice
Edge Cases
Testing Strategy
```

---

# Production Reasoning

SRE candidates should become comfortable asking questions such as:

> What happens when this dependency fails?

> What happens when traffic increases 10×?

> What happens if requests are duplicated?

> What happens if events arrive late?

> What happens if memory continues growing?

> How do we know the system is unhealthy?

> Can the operation safely be retried?

> What happens during partial failure?

These questions represent a useful reliability mindset.

---

# SRE Fundamentals Worth Knowing

Even when a particular interview contains only coding and behavioral rounds, understanding core SRE ideas makes your answers stronger.

---

## SLI

A **Service Level Indicator** is a measured signal describing service behavior.

Examples:

```text
Request success rate

p99 latency

availability

correct-response percentage
```

---

## SLO

A **Service Level Objective** defines the reliability target.

Example:

```text
99.9% of requests succeed
during a 30-day window.
```

---

## Error Budget

If the SLO is:

```text
99.9%
```

the remaining allowable unreliability is:

```text
0.1%
```

That allowance can be thought of as an error budget.

The idea helps teams balance:

```text
Reliability
     ↕
Engineering velocity
```

---

# Four Signals to Think About

When diagnosing a production service, useful signals commonly include:

### Latency

How long are operations taking?

### Traffic

How much demand is the system receiving?

### Errors

How frequently are operations failing?

### Saturation

How close is the system to resource limits?

In an interview scenario, these categories provide a useful starting point for investigation.

---

# Incident Reasoning

Suppose the interviewer says:

> API latency suddenly increased from 200 ms to 2 seconds.

Avoid immediately guessing:

> "The database is slow."

A stronger investigation looks like:

```text
Confirm impact
      ↓
Determine scope
      ↓
Check recent changes
      ↓
Inspect metrics
      ↓
Inspect dependencies
      ↓
Form hypotheses
      ↓
Test hypotheses
      ↓
Mitigate impact
      ↓
Find root cause
      ↓
Prevent recurrence
```

Strong SRE reasoning separates:

**symptom → evidence → hypothesis → mitigation → root cause → prevention**

---

# Behavioral Round

The behavioral interview should not be treated as a collection of generic HR questions.

For an SRE role, prepare evidence around engineering situations involving:

* incidents
* production ownership
* automation
* reliability improvements
* technical disagreement
* mistakes
* ambiguity
* cross-team collaboration
* operational risk
* prioritization

---

# Build These Six Stories First

If you have limited preparation time, prepare six strong stories.

### Story 1 — Production Incident

A serious outage or operational failure you helped resolve.

### Story 2 — Automation

Manual operational work that you replaced or reduced using software.

### Story 3 — Reliability Improvement

A change you made that measurably improved system reliability.

### Story 4 — Technical Disagreement

A disagreement where you used engineering evidence to reach a decision.

### Story 5 — Failure

A decision or implementation that did not work and what you learned.

### Story 6 — Ambiguity

A situation where requirements or available information were incomplete.

One strong story can often support several behavioral questions.

---

# A Better Framework Than Generic STAR

STAR is useful:

```text
Situation
Task
Action
Result
```

For SRE interviews, I recommend extending it.

## SRE Behavioral Framework

```text
Context
   ↓
Reliability Risk
   ↓
Diagnosis
   ↓
Decision
   ↓
Action
   ↓
Measured Result
   ↓
Learning
```

This forces the answer to include engineering judgment.

---

# Example

Instead of:

> We experienced an outage and I helped fix it.

Try to communicate something closer to:

```text
Context
Checkout latency increased after a deployment.

Risk
Customers were experiencing failed purchases.

Diagnosis
I compared deployment timing, service metrics and
downstream dependency latency.

Decision
We rolled back while continuing diagnosis.

Action
I coordinated rollback and isolated the regression.

Measured Result
Latency returned to baseline and customer impact stopped.

Learning
We added a deployment guard and alert so the failure
mode would be detected before broad rollout.
```

Notice the final step.

Strong candidates explain not only:

> How did you fix it?

but also:

> What changed so it was less likely to happen again?

---

# Quantify Your Behavioral Answers

Numbers make engineering stories more credible.

Instead of:

> I improved the monitoring system.

Prefer evidence such as:

```text
Alert volume ↓ 40%

MTTR ↓ from 45 minutes to 18 minutes

Manual operational work ↓ 12 hours/week

Deployment failures ↓ 30%

p99 latency ↓ from 1.2s to 450ms
```

Use real numbers from your own experience whenever possible.

Do not invent metrics.

---

# Behavioral Follow-Ups to Expect

After giving your initial answer, practice responding to questions like:

> What did **you personally** do?

> Why did you choose that approach?

> What alternatives did you consider?

> What was the biggest risk?

> What evidence supported your decision?

> Who disagreed with you?

> What was the measurable result?

> What would you do differently today?

> What mechanism prevented the problem from happening again?

A rehearsed story often breaks down during follow-ups.

Practice the follow-ups.

---

# Three-Day Google SRE Preparation Strategy

If your interview is approaching quickly, avoid trying to learn everything about SRE.

Optimize for **interview execution**.

---

## Day 1 — Coding

Focus on:

```text
Problem clarification
↓
Data structures
↓
Correct implementation
↓
Testing
↓
Complexity
↓
Follow-ups
```

Solve a small number of problems under interview conditions.

Explain your reasoning aloud.

Finish with a timed 45-minute coding mock.

---

## Day 2 — Behavioral

Build your six stories.

For every story capture:

```text
Context

Your responsibility

Technical challenge

Risk

Decision

Action

Result

Metrics

Learning
```

Then answer questions aloud.

Do not prepare behavioral interviews only by writing.

---

## Day 3 — Simulation

Run:

```text
45-minute Coding Mock

        +

45-minute Behavioral Mock
```

Treat them like the real interview.

Afterward classify mistakes.

### Coding

```text
Requirement mistake?

Algorithm mistake?

Implementation mistake?

Testing mistake?

Communication mistake?
```

### Behavioral

```text
Too vague?

Not enough ownership?

Missing technical detail?

Weak result?

No measurable impact?

No learning?
```

Fix the weakest signals.

Do not spend the final evening consuming large amounts of new material.

---

# Complete Google SRE Interview Pack

This repository explains the preparation framework.

The full preparation pack turns it into **practice**.

### 📦 The complete pack contains

| Resource                      | Purpose                                |
| ----------------------------- | -------------------------------------- |
| **45-Minute Coding Mock**     | Simulate the coding round              |
| **Coding Drill Set**          | 12 focused interview exercises         |
| **45-Minute Behavioral Mock** | Run a realistic behavioral simulation  |
| **Behavioral Story Bank**     | Prepare reusable SRE stories           |
| **3-Day Prep Plan**           | Execute the preparation systematically |

---

## 🔥 Preparing for an Interview Soon?

If your Google SRE interview is scheduled in the next few days or weeks, use the complete preparation pack:

### 👉 **[Google SRE Interview Preparation Pack](https://tobiweissmann.gumroad.com/l/ouiwoi)**

Instead of reading hundreds of interview questions, practice:

```text
Solve
→ Explain
→ Test
→ Handle Follow-Ups
→ Review
→ Repeat
```

---

# Free Repository Resources

If you are using the public repository version, start with the resources available here.

```text
google-sre-interview-preparation/

├── README.md
├── LICENSE.md
├── CONTRIBUTING.md
├── .gitignore
└── resources/
```

Depending on the repository edition, selected sample material may be available under `resources/`.

The complete preparation package is available separately.

---

# Final Readiness Checklist

Before your interview, you should be able to answer **yes** to most of these.

### Coding

* [ ] I clarify requirements before coding.
* [ ] I explain my approach before implementation.
* [ ] I can choose suitable data structures.
* [ ] I test edge cases without being prompted.
* [ ] I can explain time and space complexity.
* [ ] I can adapt when constraints change.
* [ ] I communicate while solving.

### SRE Thinking

* [ ] I reason explicitly about failure.
* [ ] I understand basic SLI/SLO concepts.
* [ ] I can discuss latency, traffic, errors and saturation.
* [ ] I understand why automation matters.
* [ ] I can reason about monitoring and incident response.

### Behavioral

* [ ] I have a strong incident story.
* [ ] I have an automation story.
* [ ] I have a reliability-improvement story.
* [ ] I have a disagreement story.
* [ ] I have a failure/learning story.
* [ ] I have an ambiguity story.
* [ ] My stories show my personal contribution.
* [ ] My stories include measurable outcomes where possible.

If several boxes remain unchecked, that tells you exactly where to spend your remaining preparation time.

---

# What Not to Do

Avoid these common preparation mistakes:

❌ Grinding hundreds of coding problems without reviewing mistakes

❌ Memorizing solutions

❌ Coding silently

❌ Ignoring testing

❌ Giving generic behavioral answers

❌ Describing only what "we" did

❌ Claiming impact without evidence

❌ Jumping directly to root-cause guesses during incident scenarios

❌ Trying to learn an entire SRE curriculum immediately before the interview

Instead optimize for:

```text
Clarity
+
Correctness
+
Evidence
+
Reliability Judgment
+
Communication
```

---

# Disclaimer

This is an **independent, unofficial interview-preparation resource**.

It is not affiliated with, endorsed by, sponsored by, or produced by Google.

Interview formats and hiring processes may change by role, level, location and hiring team.

The material is designed to teach transferable engineering and interview skills. It should not be interpreted as a claim that any particular question will appear in a Google interview.

Do not share or use confidential interview information obtained in violation of employer, interviewer, or candidate obligations.

---

# Author

**Tobias Weissmann**

Independent creator focused on:

* engineering interview preparation
* production engineering
* data engineering
* backend engineering
* reliability engineering
* applied AI engineering

---

## ⭐ Found This Useful?

If this repository helped your preparation:

**Star the repository** so you can return to it before your interview.

And if you want the complete practice system:

### 👉 **[Get the Google SRE Interview Preparation Pack](https://tobiweissmann.gumroad.com/l/ouiwoi)**

Good preparation is not about seeing the largest number of questions.

It is about becoming consistently good at:

**reasoning → implementation → reliability → communication.**
