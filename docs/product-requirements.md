# ScopeGuard V1 - Product Requirements

**Status:** Prototype / validation in progress  
**Product type:** AI-assisted product workflow  
**Primary user:** Freelancers working directly with clients on project-based engagements

## 1. Product objective

ScopeGuard V1 explores an evidence-first workflow for helping freelancers determine whether a new client request represents a change from the original agreement.

The product should reduce uncertainty by making the comparison explicit, showing supporting evidence, and clearly surfacing situations where the supplied material is insufficient to make a reliable assessment.

## 2. Problem hypothesis

Freelancers may recognize that a client request has moved beyond the original agreement but struggle to identify exactly what changed and communicate that boundary confidently.

This is currently a **hypothesis**. User research is in progress and will be used to validate or revise it.

## 3. V1 input

ScopeGuard V1 accepts:

- The original agreement / agreed scope
- The new client request

The product should treat these supplied materials as the evidence boundary for its assessment.

## 4. Core V1 capability

### Evidence-first scope assessment

Given the original agreement and new client request, ScopeGuard should identify potential scope changes and explain the assessment using source evidence.

The core experience should answer:

> **What changed, and what evidence supports that conclusion?**

## 5. V1 output

For each relevant finding, the intended output contains:

### Assessment

A concise determination such as:

- Scope change detected — high evidence strength
- Potential scope change — insufficient evidence
- No evidence of a scope change

### Evidence

Exact or appropriately bounded excerpts from the supplied materials supporting the assessment.

### Explanation

A concise explanation of how the supplied evidence leads to the assessment.

### Recommended next step

Cautious decision support for the freelancer. The product should help the user decide how to proceed without independently determining pricing, legal validity, or contractual obligations.

## 6. AI behavior requirements

### R1 - Source grounding

The system must base scope assessments only on information contained in the supplied original agreement and new client request.

### R2 - No unsupported claims

The system must not invent requirements, client intent, contractual terms, dates, pricing, or other facts that are absent from the supplied material.

### R3 - Evidence visibility

A material assessment should expose the evidence supporting it so the user can inspect the reasoning rather than blindly trust an AI conclusion.

### R4 - Explicit uncertainty

If the supplied material does not provide enough evidence for a reliable determination, the system should surface the uncertainty rather than force a confident answer.

### R5 - Decision-support boundary

The system should assist with understanding and communicating a potential scope change. It should not independently provide legal conclusions or make commercial decisions on behalf of the freelancer.

## 7. Release scope

### Included in V1

- Original agreement as input
- New client request as input
- AI-assisted comparison
- Scope-change assessment
- Evidence from supplied source material
- Explanation of assessment
- Explicit insufficient-evidence state
- Basic next-step guidance

### Explicitly out of scope for V1

- Automated client messaging
- Automatic price calculation
- Contract/legal interpretation
- Automated negotiation
- Payment collection
- Client-side product experience
- External project-management integrations
- Claims based on information not supplied by the user

## 8. Primary success hypothesis

V1 will be considered promising if target users consistently report that the evidence-backed assessment makes it easier to understand and communicate potential scope changes than their existing workflow.

Quantitative thresholds will be defined after baseline user research and an evaluation set exist. Accuracy targets should not be selected arbitrarily before the product's error modes and evaluation methodology are established.

## 9. Key risks

| Risk | Why it matters | Product response |
|---|---|---|
| Unsupported AI claim | User could challenge a client based on false information | Source grounding + visible evidence |
| Ambiguous agreement | Original scope may not contain enough detail | Explicit insufficient-evidence state |
| False confidence | A confident-looking output may be trusted too easily | Evidence-first output and uncertainty handling |
| User adoption | Existing workflows may already be sufficient | Validate current workflows and pain severity |
| Privacy/security | Client agreements may contain sensitive information | Treat data handling and access controls as product requirements before production use |

## 10. Validation plan

The current prototype is not presented as validated product-market fit.

Next validation steps:

1. Conduct asynchronous interviews with freelancers.
2. Understand current scope-tracking and client-communication workflows.
3. Test whether identifying the exact scope delta is a meaningful pain point.
4. Test whether users trust evidence-backed AI assessment more than an unsupported AI summary.
5. Build an evaluation set containing representative original agreements and new requests.
6. Measure factuality, evidence attribution, assessment quality, and failure modes.
7. Iterate the product based on observed user and model failures.
