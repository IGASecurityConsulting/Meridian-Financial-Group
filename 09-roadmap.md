# Roadmap

## How This Gets Built

Bringing 4 million ungoverned identities under control cannot happen all at once, and it should not. This roadmap delivers the architecture in three phases over eighteen months, a longer timeline than Phantom Shield's twelve, reflecting Meridian's larger scale and the higher operational risk of touching live trading and compliance infrastructure carelessly. Each phase reduces real exposure the moment it goes live and is tested against non-production environments before touching anything generating revenue.

## Phase 1: Discovery and Inventory (Months 1 to 6)

This phase builds continuous automated discovery across Meridian's trading systems, cloud infrastructure, and compliance platforms, bringing all 4 million non-human identities into a single, continuously updated inventory for the first time.

This phase is first because nothing else in the architecture can function without it. Ownership cannot be assigned to an identity nobody knows exists. The policy engine cannot evaluate compliance for an identity that has not been discovered. Six months reflects the real integration effort required across a fragmented set of existing platforms, several of which will need custom connectors built specifically for this purpose.

By the end of Phase 1, Meridian has, for the first time, a complete and current answer to a question it currently cannot answer at all: what non-human identities exist across the environment.

## Phase 2: Lifecycle Automation and Ownership (Months 6 to 12)

This phase assigns accountable ownership to every identity in the inventory and enforces automated credential expiration and rotation as the default state. Legacy static credentials are transitioned to the new rotation model in waves, starting with lower-risk, non-production-adjacent systems and moving toward Meridian's most critical trading and compliance infrastructure only after the rollout process is validated at smaller scale.

This phase follows discovery because ownership and rotation policy can only be enforced against identities that are already fully inventoried. It runs over six months because rolling out credential rotation across live trading infrastructure carelessly risks real operational disruption, and the phased, tested approach described in Constraints and Risks takes real time to execute safely.

By the end of Phase 2, no non-human identity at Meridian exists without an accountable owner, and standing, indefinitely-valid credentials are the tracked exception rather than the default state.

## Phase 3: Policy Engine and Continuous Evidence (Months 12 to 18)

This phase deploys the deterministic policy engine and the continuous evidence generation layer, codifying Meridian's access control and lifecycle standards into enforceable rules and producing audit-ready evidence automatically, on an ongoing basis.

This phase is last because the policy engine evaluates the inventory and lifecycle data the first two phases produce. A policy engine built before the underlying discovery and ownership data exists would have nothing accurate to evaluate.

By the end of Phase 3, Meridian can answer an examiner's core question, what has access to what, why, and how do you know the control held, on demand, with evidence traceable to specific enforcement events rather than assembled manually under deadline pressure.

## Why This Sequence, Not Another

The sequence follows technical dependency, not convenience. Each phase requires the prior phase's output to function. Discovery has to exist before ownership can be assigned. Ownership and lifecycle data have to exist before a policy engine can evaluate compliance against them. Building any phase out of order would mean building on top of data that does not yet exist.

## What Does Not Wait Eighteen Months

Each phase produces real, usable value the moment it ships. Phase 1 alone gives Meridian something it has never had: a complete, current picture of its non-human identity population. If an examination occurs before Phase 3 is complete, Meridian can demonstrate a credible, evidence-backed picture of current state and active, measurable remediation progress, which is a fundamentally stronger position than having no answer at all.
