# ScopeGuard — Product Decisions

This document records the reasoning behind the current V1 product choices. It is intentionally written as a decision log rather than a feature list.

## Decision 01 — Make evidence-backed comparison the V1 core

**Decision:** Prioritize comparison of the original agreement against the new client request.

**Why:** The product hypothesis is that the fundamental user problem is uncertainty about exactly what changed. Client-response generation is downstream of that understanding and can be considered later.

**Trade-off:** V1 does not attempt to solve the entire communication workflow.

**Validation needed:** Confirm through freelancer research that identifying the scope delta is a meaningful and frequent pain point.

## Decision 02 — Use an evidence-first scope assessment

**Decision:** Present the assessment together with supporting source evidence and an explanation.

**Why:** A black-box AI verdict is difficult to trust in a client-facing workflow. Showing evidence makes the assessment inspectable and gives the user a basis for deciding whether to act.

**Trade-off:** Evidence presentation may be more verbose than a simple classification, but trust and inspectability are more important for this workflow.

## Decision 03 — Treat uncertainty as a product state

**Decision:** If the available material does not establish a scope change clearly, ScopeGuard should report insufficient evidence rather than force a confident answer.

**Why:** A false positive could cause a freelancer to challenge a client incorrectly. In this context, calibrated uncertainty is preferable to confident unsupported output.

## Decision 04 — Evidence strength over model confidence

**Decision:** The product should emphasize the strength and availability of source evidence rather than exposing an unexplained model-confidence percentage as the primary trust signal.

**Why:** A statement such as “96% model confidence” does not tell a freelancer why the assessment is defensible. Direct evidence is more actionable.

## Decision 05 — Decision support, not autonomous negotiation

**Decision:** ScopeGuard can suggest a cautious next step but should not independently determine price, legal validity, or contractual obligations.

**Why:** Those decisions require context that may not exist in the supplied documents and can create material risk if the system overreaches.

## Decision 06 — Keep V1 narrow

**Decision:** V1 uses only two primary inputs: the original agreement and the new client request.

**Why:** A narrow input/output boundary makes the first product hypothesis easier to test and the AI evaluation problem easier to define.

## Decision 07 — Do not manufacture validation metrics

**Decision:** No user-adoption, conversion, or accuracy targets will be presented as achieved until a research and evaluation methodology exists.

**Why:** The prototype is currently an unvalidated product hypothesis. Honest measurement is more valuable than impressive but unsupported numbers.
