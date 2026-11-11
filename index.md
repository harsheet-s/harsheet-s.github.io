---
layout: default
title: Harsheet Singh Choudhary — Professional Portfolio
---

# Harsheet Singh Choudhary

Bachelor of Information Technology, Data Analytics major — University of Technology Sydney
Student ID 25748601

I am a second-year IT student working toward applied machine learning engineering. This
portfolio holds the evidence behind my professional learning during 43030 Professional
Practice in Computing, Spring 2026.

---

## Professional Learning Plan

The plan this portfolio reports against. It contains a SFIA-based skills audit of ten
capability areas drawn from two advertised roles — a Senior Machine Learning Engineer
position at PetSure and a Senior Data Scientist position at Real Time — and sets four
professional learning goals against the gaps that audit exposed.

The audit was deliberately unflattering. It records "None — below MLNG Level 2" for machine
learning and "None" for cloud platforms and MLOps, because SFIA 9 does not define those
skills below Level 2 and I could not yet evidence that level.

**[Professional Learning Plan and Skills Audit (PDF)](artefacts/professional-learning-plan.pdf)**

---

## Goal 1 — Ethical practice and Indigenous engagement

### Applied artefact: ethical analysis for a design firm

A professional email to the management of DesignR, a graphic design firm proposing to sell
AI-generated imagery "inspired by" Indigenous Australian art. The analysis argues that the
firm's four safeguards — literature research, disclaimers, a donation program and
rights-managed licensing — were all developed without Indigenous participation, and that
none of them substitutes for consent.

It draws on the AIATSIS Code of Ethics, Janke's True Tracks principles, UNDRIP Article 31
and the ACS Code of Professional Ethics, and distinguishes the ACCC's Birubi Art case from
DesignR's position rather than overstating the comparison.

**[Ethical analysis: AI-generated Indigenous imagery (PDF)](artefacts/ethical-analysis-designr.pdf)**

### Module completion

- Working Ethically in the IT Industry
- Indigenous Professional Capability

---

## Goal 3 — Software development practice

### Applied artefact: Around the Table

A multiplayer card game in Python and Tkinter, originally written for 48024 Programming 2
and rebuilt here with the engineering discipline the original lacked.

**[github.com/harsheet-s/around-the-table](https://github.com/harsheet-s/around-the-table)**

The rebuild was done across three reviewed pull requests rather than direct commits to
main:

1. **Project scaffolding and CI** — README, dependency pinning split between runtime and
   development requirements, `.gitignore`, and a GitHub Actions workflow
2. **Restoring button state management** — `updatebuttonstates()` had been left as a no-op
   with its body commented out, so the Deal and Play buttons stayed enabled regardless of
   game state. Both now reflect whether the decks can cover a round and whether every
   player has selected.
3. **Model test suite** — 37 unit tests covering card damage and copying, deck construction
   and exhaustion, player hand limits and health, dealer round sequencing, and the player
   cap

The tests run headless in continuous integration on every push and pull request. That is
possible because the model layer imports nothing from Tkinter — an architectural decision
from the original build that turned out to be what made the code testable at all.

Two behaviours the tests document that are not obvious from reading the code: `Card.copy()`
returns a card at full health regardless of the original's state, which is what stops a
damaged card library poisoning new decks; and the secondary deck card rotates between
players each round through `(round_counter - 1) % len(players)`.

---

## Goals not completed

**Goal 2 — Foundational cybersecurity.** Scoped but not undertaken. The Introduction to
Cybersecurity module carries three graded assessments, including a 60-point incident and
defence strategies task, and I judged partway through the session that completing two goals
properly was worth more than three partially. This remains scoped and is the first item in
my forward plan.

**Goal 4 — Model deployment and MLOps.** Recorded in the original plan as additional
self-directed work outside the credit-point requirement. Not undertaken.

---

## Contact

[github.com/harsheet-s](https://github.com/harsheet-s)
