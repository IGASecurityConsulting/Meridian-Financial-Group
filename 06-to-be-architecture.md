# To-Be Architecture

## The Governing Principle

Meridian does not need a better spreadsheet. It needs an architecture where every non-human identity is discovered automatically, owned by default, expires on a schedule, and produces its own evidence of compliance continuously. Nothing in this design depends on a human noticing, remembering, or getting to it during the next review cycle. Enforcement is a property of the system, not a task on someone's list.

## Layer One: Continuous Discovery and Inventory

An automated discovery layer scans every trading system, cloud platform, and compliance tool Meridian operates, continuously, not on a periodic schedule. Every non-human identity found, service account, API key, trading bot, or AI agent, is registered into a single, unified inventory the moment it is discovered, regardless of which team or system created it. An identity that exists anywhere in Meridian's environment now exists in exactly one place from a governance perspective, not scattered across a dozen disconnected systems each blind to the others.

Discovery does not wait for a quarterly cycle. New identities are captured continuously, so the inventory reflects current reality at any given moment rather than a snapshot that is already stale by the time it is compiled.

## Layer Two: Ownership and Lifecycle Automation

Every identity entering the inventory is assigned an accountable human owner at the point of creation, tied to the request or process that generated it. When an owner leaves the organization or changes roles, the identity is automatically flagged for reassignment within a defined window, or automatically disabled if no reassignment occurs, so an orphaned credential never simply persists indefinitely on the assumption someone will eventually notice.

Credentials rotate on a defined schedule by default, automatically, without requiring a human to initiate the process. Static, indefinitely-valid credentials are eliminated as the default state. Access that goes unused past a defined threshold is automatically revoked, since unused access carries risk with no offsetting business value.

This is the same lifecycle automation model implemented in the NHI Lifecycle Automation Agent: identity governance treated as a continuous, automated process rather than a periodic manual task, scaled to operate across millions of identities without requiring proportional growth in review staffing.

## Layer Three: The Policy Engine, Deterministic Enforcement

This is the layer that closes the gap between having a policy and proving a policy holds. A deterministic rules engine evaluates every non-human identity against Meridian's access control and lifecycle policy continuously, not through periodic sampling. The engine answers specific, checkable questions directly: does this identity's access match least privilege for its function, is its credential current, is its owner still active, has it acquired permissions beyond its original approved scope.

The distinction that matters here is between a probabilistic judgment and a deterministic rule. An AI system can explain what a policy says and help a human reason through an ambiguous case. It cannot, by itself, serve as evidence that a specific control was enforced, because a probabilistic answer can be second-guessed. A deterministic rule either fired or it did not, and that firing is the evidence. This is the architecture already built into the Identity Security Copilot's governance layer: an LLM layer for explanation and reasoning, sitting on top of a deterministic policy engine that actually enforces and records the outcome.

## Layer Four: Scoped AI Agent Governance

AI agents are governed as a distinct category, not treated as a variant of a static service account. Every agent operates under a defined execution scope established at deployment, and any action or permission request outside that scope requires validation independent of the agent's own stated intent, rather than trusting the agent's request at face value. An agent that begins operating outside its intended purpose is flagged and, depending on severity, automatically suspended, the same pattern applied to any anomalous non-human identity behavior, but evaluated against the agent's specific declared scope rather than generic anomaly detection alone.

## Layer Five: Continuous Evidence Generation

Every enforcement decision the policy engine makes, and every discovery, ownership assignment, and credential rotation event, is logged to an immutable evidence record, continuously, not assembled after the fact in response to an examination request. The record answers the question an examiner will actually ask, what has access to what, why, and how do you know the control held, on demand, with the answer traceable to the specific rule or event that produced it.

This directly addresses the fixed regulatory clock. A notification window of 36 to 72 hours is survivable when the evidence already exists and only needs to be retrieved, and it is not survivable when the evidence has to be manually reconstructed from fragmented systems under deadline pressure.

## How the Layers Work Together

Discovery feeds the inventory. The inventory feeds lifecycle automation, which keeps ownership and credentials current without manual intervention. The policy engine continuously checks the inventory against policy and produces the evidence an examiner needs. AI agents are governed through the same pipeline, with additional scope-specific checks layered on top. No single layer is asked to solve the whole problem alone, which is the same layered-defense principle applied throughout this portfolio: a failure in any one layer does not become a governance failure across the whole architecture.

## Why This Scales to Millions

The entire design assumes automation as the default operating mode, not manual review with automation bolted on as a convenience. A rules engine evaluating a defined policy against 4 million identities does not require 4 million times the staffing a manual review would. It requires the policy to be written once, correctly, and enforced continuously, which is the only approach that actually holds at Meridian's scale.
