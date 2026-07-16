# ADR-002: Deterministic Policy Engine Over LLM-Only Compliance Assessment

**Status:** Accepted

## Business Context

Meridian needs to answer specific, checkable questions for a regulator: does this identity's access match least privilege for its function, is its credential current, is its owner still active. An AI system, including a large language model with full visibility into Meridian's policies and identity data, can reason about these questions and explain what the policy says. That is genuinely useful for a human trying to understand a complex case.

It is not, by itself, evidence that a control was enforced. An examiner asking "prove this specific identity's access complied with least privilege on this date" needs an answer that is either right or wrong, traceable to a specific rule, and not open to interpretation. A probabilistic model's judgment, however well-reasoned, can always be second-guessed, because it was a judgment, not a mechanical check against a defined rule.

## Options Considered

1. Rely on an LLM to assess compliance questions directly, using its reasoning over policy and identity data
2. A deterministic rules engine that evaluates identities against explicit, codified policy logic, with an LLM layer available separately for explanation and reasoning
3. Continue relying on human policy interpretation, unassisted by either approach

## Pros and Cons

**LLM-only assessment**
Pro: Flexible, can reason about nuanced or ambiguous cases a rigid rule set might not anticipate. Fast to stand up since it requires less upfront codification of policy logic.
Con: A probabilistic answer is not proof of enforcement. Two runs of the same question could, in principle, produce different reasoning paths. An examiner is unlikely to accept "the model said this complies" as audit evidence, and should not, since it cannot be mechanically verified after the fact the way a fired rule can.

**Deterministic policy engine, with LLM layered on top for explanation**
Pro: Every compliance determination traces to a specific, codified rule that either fired or did not. This is the standard of proof an examination actually requires. The LLM layer remains available to explain findings in plain language to a human, but the enforcement decision itself does not depend on the model's judgment.
Con: Requires policy logic to be codified explicitly in advance, which takes real effort and cannot cover every conceivable edge case as flexibly as a reasoning model can. Edge cases outside the codified rules require a defined escalation path rather than an automatic answer.

**Unassisted human interpretation**
Pro: No new technology required.
Con: This is functionally the same problem as manual review at scale, addressed in ADR-001. It does not scale to 4 million identities and does not produce continuous evidence.

## Risks and Impact

Codifying policy into deterministic rules requires upfront work to translate Meridian's actual access control and lifecycle standards into explicit logic, and some genuinely ambiguous cases will not fit cleanly into a rule and will need a defined human escalation path rather than an automatic determination.

The alternative risk, relying on an LLM's judgment as the compliance determination itself, is a control that cannot survive direct examiner scrutiny about how a specific finding was verified, which defeats the entire purpose of building an evidence-generating architecture in the first place.

## Final Recommendation

Deploy a deterministic policy engine as the enforcement and evidence layer, with the LLM reasoning layer positioned specifically for explanation, guidance, and handling escalated edge cases, not for making the compliance determination itself. This mirrors the layered architecture already implemented in the Identity Security Copilot: a probabilistic layer for explanation, a deterministic layer for enforcement, and a verification layer that confirms the deterministic layer functioned as intended.
