# ScopeGuard - AI Evaluation Plan

**Status:** Evaluation design / prototype stage

## Evaluation objective

Determine whether ScopeGuard can identify scope differences while remaining grounded in the supplied source material.

The evaluation should measure more than whether the final label looks correct. It should test whether the evidence and explanation actually support the assessment.

## Core evaluation dimensions

### 1. Scope-change assessment quality

Does the system correctly distinguish among:

- clear scope changes;
- potential / ambiguous changes;
- no supported scope change?

### 2. Evidence attribution

Does every material claim point to relevant information in the supplied agreement or request?

### 3. Unsupported-claim rate

How often does the system introduce a fact, requirement, intent, date, price, or contractual condition that is not present in the supplied material?

### 4. Uncertainty handling

When evidence is insufficient, does the system appropriately surface uncertainty rather than fabricate a conclusion?

### 5. Explanation quality

Does the explanation accurately connect the cited evidence to the assessment without adding unsupported interpretation?

## Proposed evaluation dataset

Create a representative set of paired inputs:

```text
(original agreement, new client request, expected assessment, supporting evidence)
```

Include:

- clear positive scope changes;
- clear non-changes;
- ambiguous cases;
- wording changes that do not change scope;
- additions that appear similar to existing deliverables;
- conflicting or incomplete information;
- dates and quantities that change;
- cases where no reliable assessment is possible.

## Important failure cases

The evaluation should specifically test for:

- hallucinated requirements;
- invented client intent;
- unsupported pricing conclusions;
- false certainty;
- evidence that does not support the stated conclusion;
- missing relevant evidence;
- confusing a wording change with a scope change.

## Release gate concept

Before a production-oriented release, ScopeGuard should meet a predefined evaluation threshold for factuality and evidence attribution and demonstrate acceptable behavior on ambiguous cases.

Exact thresholds should be selected after a labeled evaluation set exists. The current prototype should not claim a numerical accuracy result without such a dataset and methodology.

## Human review

For high-risk or ambiguous cases, evaluation should include human review of:

1. the source documents;
2. the system assessment;
3. the cited evidence;
4. the explanation;
5. the final recommended next step.

The key question is not simply:

> “Did the model get the label right?”

It is:

> **“Can the user inspect the evidence and reasonably understand why the product reached this assessment?”**
