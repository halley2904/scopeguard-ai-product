# ScopeGuard

**Evidence-first AI scope assessment for freelancers**

> V1 product prototype exploring how AI can help freelancers identify and communicate client-requested scope changes without relying on unsupported claims.

[**Live V1 Prototype →**](https://scope-guard-7555.taskade.app/)

## Product thesis

Freelancers can recognize that a client request may have moved beyond the original agreement, but it can be difficult to determine exactly **what changed**, **what evidence supports that conclusion**, and **how to respond confidently**.

ScopeGuard V1 tests an evidence-first workflow:

**Original agreement + new client request → scope assessment → evidence → confidence → next-step guidance**

## What V1 does

The prototype is intentionally narrow. The primary V1 job is to compare an original agreement with a new client request and surface evidence-backed scope changes.

### V1 input

- Original agreement
- New client request

### V1 output concept

For each identified change, ScopeGuard is designed to communicate:

1. **Assessment** — whether a scope change is detected or only potentially indicated
2. **Evidence** — exact supporting source text
3. **Explanation** — why the evidence supports the assessment
4. **Action guidance** — a cautious next step for the freelancer

When available evidence is insufficient, the intended behavior is to **surface uncertainty rather than invent a claim**.

## Product principles

### 1. Evidence over assertion

ScopeGuard should expose the source evidence behind an assessment so the user does not have to blindly trust an AI-generated conclusion.

### 2. Source-grounded AI

The system should use only the supplied agreement and request as evidence for a scope assessment. Unsupported facts, inferred client intent, or invented contractual terms should not be presented as established facts.

### 3. Decision support, not autonomous negotiation

ScopeGuard is intended to help the freelancer understand and communicate a potential scope change. It should not independently determine pricing, legal validity, or contractual obligations without explicit evidence.

### 4. Explicit uncertainty

When the available material does not establish a change clearly, the product should make that uncertainty visible instead of forcing a confident answer.

## Current product status

**V1 prototype — user validation in progress.**

This repository does **not** claim completed user research, production readiness, measured business impact, or validated accuracy. The current focus is testing the product hypothesis and refining the workflow through asynchronous conversations with freelancers.

## Product questions being validated

- How do freelancers currently determine whether a client request is outside the agreed scope?
- Is identifying the exact scope delta a meaningful pain point?
- Do freelancers want evidence-backed AI assistance for this task?
- What level of explanation or evidence is necessary for users to trust an assessment?
- When is a scope change too ambiguous for the product to make a reliable determination?

## Repository structure

```text
scopeguard-ai-product/
├── README.md
└── docs/
    ├── product-requirements.md
    ├── product-decisions.md
    ├── user-research.md
    └── evaluation-plan.md
```

## Why this project

ScopeGuard is a self-initiated AI product exercise focused on the product layer of applied AI: problem framing, workflow design, evidence requirements, failure modes, evaluation and user validation.

The goal is not to demonstrate a large software codebase. The goal is to show how an AI product is defined and de-risked before scaling it.

## Roadmap

### V1 — Prototype

- [x] Interactive prototype
- [x] Define core user problem hypothesis
- [x] Narrow V1 input and output
- [x] Define evidence-first behavior

### Next

- [ ] Complete asynchronous user interviews
- [ ] Synthesize user pain points and current workarounds
- [ ] Evaluate whether the scope-comparison workflow solves a high-value problem
- [ ] Build a structured evaluation set for evidence extraction and assessment quality
- [ ] Iterate V1 based on observed failure modes

## Disclaimer

ScopeGuard is an independent product prototype and is not intended to provide legal advice, determine contractual validity, or replace professional review of client agreements.
