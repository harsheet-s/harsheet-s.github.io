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

**Status: completed**

### Module completion

- **Working Ethically in the IT Industry** — completed November 2026. Covers the IT code of
  ethics, privacy and data protection, intellectual property and copyright, cybersecurity
  and ethical hacking, emerging challenges and social implications, power and
  whistleblowing, and an ethical thinking framework.
- **Indigenous Professional Capability** — completed November 2026. Covers reconciliation in
  Australia, Reconciliation Action Plans, Indigenous Data Sovereignty, Free Prior and
  Informed Consent, collecting and researching Indigenous data, and a case study on an
  ethical dilemma.

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

### Reflective artefact: what I would change, having completed the modules

I wrote the DesignR analysis *before* completing the Indigenous Professional Capability
module. This piece records what the module changed: that my email was better at explaining
what the firm was doing wrong than at setting out how the work could proceed responsibly,
and that the Free Prior and Informed Consent problem I raised is an unresolved question in
the field rather than a gap in my own understanding.

**[What I would change in my ethical analysis (PDF)](artefacts/reflection-post-module.pdf)**

---

## Goal 3 — Software development practice

**Status: completed — both module assessments passed and the applied artefact built**

### Module assessments

- **GitHub Essentials (Quiz 1)** — 9/10
- **GitHub Workflow (Quiz 2)** — 10/10

Both were sat *after* the rebuild below rather than before it. I built the capability by
doing the work; the assessments confirmed it afterwards.

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
from the original build that turned out to be what made the code testable at all. Because
the model has no interface dependency, the workflow installs only the development
requirements rather than Pillow, which it has no use for.

Two behaviours the tests document that are not obvious from reading the code: `Card.copy()`
returns a card at full health regardless of the original's state, which is what stops a
damaged card library poisoning new decks; and the secondary deck card rotates between
players each round through `(round_counter - 1) % len(players)`.

**On the module content.** I have not worked through every page of the Software Development
module, and I record that rather than imply otherwise. The capabilities it covers —
branching, pull requests, YAML, GitHub Actions — were developed through this rebuild, and
the two module assessments above are the independent check on whether that worked.

---

## Goal 2 — Foundational cybersecurity

**Status: module content completed and both quizzes passed; the third assessment not
attempted**

### Module assessments

- **Cybersecurity Assessment 1 (Quiz)** — 19.5/20
- **Cybersecurity Assessment 2 (Quiz)** — 19/20
- **Cybersecurity Assessment 3 — Incident and Defence Strategies (60 pts)** — not attempted

The module covers the CIA triad, security management, risk assessment, preventive,
detection and recovery controls, cyber threat intelligence, operational security and secure
coding.

### What it found in the Goal 3 repository

The most useful outcome was not the quiz results. Having rebuilt the card game repository
around process — pull requests, CI, pinned dependencies, automated tests — I had been
treating that process as evidence of quality. None of it demonstrates the application is
secure. Pinning dependencies makes builds reproducible and says nothing about whether the
pinned versions carry known vulnerabilities.

Three things I would change, each a pull request:

1. Add dependency vulnerability scanning to the CI workflow
2. Review what permissions that workflow actually holds
3. Extend the test suite to cover security-relevant behaviour, not only whether features
   work

Engineering discipline and security are not the same property, and I had been assuming the
first produced the second.

---

## Goal 4 — Model deployment and MLOps

**Status: not undertaken.** Recorded in the original plan as additional self-directed work
outside the credit-point requirement. It remains the largest gap in the audit and is a
forward goal for mid-2027.

---

## Contact

[github.com/harsheet-s](https://github.com/harsheet-s)
