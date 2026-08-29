# Google SRE Interview Preparation

A focused preparation pack for a Google Site Reliability Engineering interview with two 45-minute rounds:

- **Coding** — practical problem solving, correctness, communication, edge cases, testing, and production reasoning.
- **Behavioral** — incident ownership, reliability judgment, collaboration, automation, learning, and measurable impact.

> **Unofficial resource.** This repository is independently created and is not affiliated with, endorsed by, or sponsored by Google.

## Who this is for

This pack is designed for candidates who already have an interview scheduled and need a short, execution-oriented preparation path rather than a large theory curriculum.

It is especially useful when your process contains:

- one **45-minute coding round**;
- one **45-minute behavioral round**; and
- only a few days left to prepare.

## What's included

| Resource | What it does | Length |
| --- | --- | ---: |
| [01 — 45-Minute Coding Mock](resources/01_GOOGLE_SRE_45_MIN_CODING_MOCK.pdf) | One timed coding interview with progressive follow-ups and production reasoning | 9 pages |
| [02 — Coding Drill Set](resources/02_GOOGLE_SRE_CODING_DRILL_SET.pdf) | 12 selected drills focused on implementation, data structures, edge cases, complexity, and communication | 16 pages |
| [03 — 45-Minute Behavioral Mock](resources/03_GOOGLE_SRE_BEHAVIORAL_MOCK.pdf) | Five behavioral themes with interviewer-style probing | 15 pages |
| [04 — Behavioral Story Bank](resources/04_GOOGLE_SRE_BEHAVIORAL_STORY_BANK.pdf) | Ten questions plus an SRE-specific framework for building reusable stories | 15 pages |
| [05 — 3-Day Prep Plan](resources/05_GOOGLE_SRE_3_DAY_PREP_PLAN.pdf) | A short execution schedule tying the entire pack together | 4 pages |

## Recommended 3-day path

### Day 1 — Coding execution

Use the coding drill set to practice solving under time pressure. Prioritize clear assumptions, correct implementation, test cases, complexity analysis, and verbal communication. Finish with the 45-minute coding mock.

### Day 2 — Behavioral evidence

Build a compact story bank around incidents, automation, reliability improvements, disagreement, failure, ambiguity, and cross-team work. Quantify impact wherever possible. Then run the behavioral mock aloud.

### Day 3 — Interview simulation

Do a small number of coding warm-ups, then simulate both rounds under realistic timing. Review mistakes, tighten stories, and stop adding new material late in the day.

Start here: ** https://tobiweissmann.gumroad.com/l/ouiwoi **.

## Coding round: what to demonstrate

A strong solution is more than code that passes the happy path. Practice showing the interviewer that you can:

1. Clarify ambiguous requirements before coding.
2. Choose a suitable data structure and explain why.
3. Produce a correct baseline solution.
4. Identify edge cases and write useful tests.
5. State time and space complexity.
6. Adapt when a follow-up changes scale or constraints.
7. Connect implementation choices to reliability and production behavior when relevant.

## Behavioral round: what to demonstrate

Avoid memorizing generic STAR scripts. Prepare evidence that shows:

- ownership during incidents;
- disciplined diagnosis under uncertainty;
- reliability and risk judgment;
- reduction of operational toil through automation;
- collaboration and technical disagreement;
- learning after mistakes;
- measurable outcomes; and
- mechanisms that prevented recurrence.

A useful answer shape is:

**Context → Reliability Risk → Diagnosis → Decision → Action → Measured Result → Learning**

## Repository structure

```text
google-sre-interview-preparation/
├── README.md
├── LICENSE.md
├── CONTRIBUTING.md
├── .gitignore
└── resources/
    ├── 01_GOOGLE_SRE_45_MIN_CODING_MOCK.pdf
    ├── 02_GOOGLE_SRE_CODING_DRILL_SET.pdf
    ├── 03_GOOGLE_SRE_BEHAVIORAL_MOCK.pdf
    ├── 04_GOOGLE_SRE_BEHAVIORAL_STORY_BANK.pdf
    └── 05_GOOGLE_SRE_3_DAY_PREP_PLAN.pdf
```

## How to use this repository

Do not try to finish every page passively. Use the PDFs as an execution system:

- solve coding problems **out loud**;
- use a timer;
- write tests before declaring a solution complete;
- answer behavioral questions aloud rather than only writing notes;
- record measurable outcomes in your story bank; and
- re-run the mocks after reviewing weak areas.

## Important note

Interview formats, question styles, and hiring processes can change. Treat this material as focused practice, not a claim about exact questions that Google will ask. Do not use or distribute confidential interview questions obtained in violation of an employer's or candidate's obligations.

## Author

**Tobias Weissmann**

Independent interview-preparation and production-engineering content creator.

If this repository helps you, consider starring it so you can find the preparation path again before your interview.
