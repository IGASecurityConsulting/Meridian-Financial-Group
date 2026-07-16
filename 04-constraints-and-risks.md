# Constraints and Risks

## Constraints

### Scale Constrains the Solution Design
Any approach requiring manual review or human-in-the-loop approval for each of Meridian's 4 million non-human identities is immediately disqualified by scale alone. A solution that works for thousands of identities does not simply work harder at millions, it fails differently and faster. The architecture has to be built for automation as the default, not automation as an enhancement layered onto a manual process.

### Existing Infrastructure Cannot Be Replaced Wholesale
Meridian's trading systems, cloud platforms, and compliance tooling represent years of investment and carry direct revenue dependency. A security architecture that requires ripping out and replacing core trading infrastructure to achieve identity governance is not a realistic proposal, regardless of how clean the design looks on paper. The architecture must integrate with what exists, not assume a clean-slate rebuild.

### The Regulatory Clock Is Fixed, Not Negotiable
Notification windows of 36 to 72 hours are set by regulators, not by Meridian, and they do not extend to accommodate a slower internal process. Any proposed control has to be evaluated against whether it can actually produce answers within that fixed window, not against an idealized timeline with no external deadline pressure.

### AI Agent Behavior Is Inherently Harder to Bound Than Static Credentials
Unlike a service account with a fixed, inventoriable scope, an AI agent can take sequences of actions and, in some architectures, acquire new permissions dynamically at runtime. Any governance model built only for static credentials will miss the fastest-growing and least predictable category of non-human identity Meridian actually has. The architecture has to account for agents as a fundamentally different governance problem, not a variation on the service account problem.

### Organizational Change Is Required, Not Just Technology
Assigning ownership to 4 million identities is not purely a technical exercise. It requires organizational agreement on who owns what, which touches teams across trading, compliance, engineering, and operations who have not historically had to think of themselves as identity owners. Technology can enforce ownership once it is assigned. It cannot manufacture organizational agreement on its own.

## Risks

### Risk: Remediation Effort Disrupts Production Trading Systems
Bringing 4 million ungoverned identities under lifecycle control means changing how existing systems authenticate and access resources. Done carelessly, this risks breaking live trading, compliance, or reporting functions that depend on those credentials continuing to work exactly as they do today.

**Mitigation:** Remediation is phased and tested against non-production environments first, with rollback capability at every stage, so a broken integration is caught before it reaches a system generating revenue in real time.

### Risk: False Positives in Ownership Assignment or Access Revocation
Automated ownership assignment or access revocation based on incomplete data could disable a credential that is still legitimately needed, causing an operational outage.

**Mitigation:** Initial deployment runs in observation mode, flagging findings without automatically enforcing revocation, until confidence in the discovery and ownership data reaches a validated threshold.

### Risk: AI Agents Circumvent Scoped Permissions Through Legitimate-Looking Requests
An AI agent operating within its nominal scope could still be manipulated, through prompt injection or unexpected chained behavior, into requesting access or taking actions that are technically within its permission boundary but outside its intended purpose.

**Mitigation:** High-risk actions require validation independent of the agent's own request, not reliance on the agent's stated intent alone, consistent with the AI system protection principles applied elsewhere in this portfolio.

### Risk: The Organization Treats This as a One-Time Cleanup Rather Than Ongoing Governance
The temptation after a large remediation effort is to treat the problem as solved and return to manual, periodic review. Given that new non-human identities are created constantly, this would recreate the sprawl within a year or two.

**Mitigation:** Continuous automated discovery and enforcement is built in from the start as the operating model, not a one-time project with a defined end date.

### Risk: Regulatory Examination Occurs Before Remediation Is Complete
Given the scale of the problem, full remediation of 4 million identities will take time. There is a real risk the examination happens mid-remediation, before every identity has an assigned owner and enforced lifecycle.

**Mitigation:** The architecture prioritizes producing a credible, evidence-backed picture of current state and active remediation progress early, since a regulator evaluating a firm that can demonstrably show what it has, what it is fixing, and the pace of the fix is in a fundamentally different position than a firm that cannot answer the question at all.
