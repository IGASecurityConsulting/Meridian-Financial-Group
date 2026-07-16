# Governance

## Why Governance Matters Here

An architecture that discovers 4 million identities, assigns ownership, and enforces expiration is only as good as the discipline that keeps it running after the initial rollout. Non-human identities do not stop being created once this architecture goes live. Every new trading system, every new AI agent, every new integration generates more of them. A governance model that is not built to operate continuously will drift back toward exactly the sprawl this architecture was built to fix, just more slowly.

This section defines who owns each layer of the architecture, how effectiveness gets measured, and what happens when something breaks.

## Control Ownership

Discovery and inventory accuracy is owned by the identity and security architecture function. They are accountable for ensuring new platforms and systems are onboarded into continuous discovery as they are adopted, so the inventory does not develop blind spots as Meridian's technology footprint evolves.

Lifecycle and ownership enforcement is owned jointly by security architecture and each business unit that generates non-human identities, trading, compliance, engineering, and operations. The business unit is accountable for assigning legitimate owners to identities their teams create. Security architecture is accountable for the automated enforcement that reassigns or disables identities when ownership lapses.

The policy engine and evidence generation is owned by security and compliance jointly. Security is accountable for the technical integrity of the deterministic rules. Compliance is accountable for ensuring the codified rules actually reflect current regulatory expectations, since a rules engine enforcing outdated policy logic is not a real control, regardless of how reliably it runs.

## Review Cadence

Two review timelines apply. A continuous, automated review confirms the architecture itself is functioning: is discovery capturing new identities, is ownership assignment happening at creation, are credentials rotating on schedule. This is not a human-driven review, it is the system checking itself, with automated alerts when any layer stops functioning as expected.

An annual architectural review, conducted by security architecture and compliance leadership together, asks a different question: is this architecture still sufficient given how Meridian's identity population and regulatory expectations have changed over the past year. Has AI agent adoption introduced a category of non-human identity the current governance model does not yet account for. Has a new regulatory expectation emerged that requires new rules in the policy engine. This is the review that determines whether a new ADR is needed.

## Exception Handling

Some identities will have a legitimate reason to deviate from standard lifecycle rules, a credential that genuinely cannot rotate on the standard schedule due to a legacy system constraint, for example. Exceptions are documented, time-boxed, and approved by the relevant control owner, never created informally by a team working around an inconvenient rule under deadline pressure. Every exception has an expiration date. An exception without one is a permanent gap wearing a temporary label.

## Metrics That Matter

Three metrics carry the weight of this architecture's credibility.

Percentage of non-human identities with a current, active, assigned owner. This is the number that proves the ownership model is holding, not just documented as a policy.

Percentage of credentials rotating on schedule versus those requiring an active exception. This is the number that shows whether the architecture is closing Meridian's largest source of standing risk or merely managing it in theory.

Time to produce a complete access and evidence answer for any given identity or system, measured against the regulatory notification windows Meridian actually faces. This is the number that determines whether Meridian can survive an actual examination or incident under a real deadline, not a hypothetical one.

## Escalation

A control failure discovered through the continuous automated review goes first to the accountable control owner. If the failure involves a gap that could affect regulatory examination readiness, it escalates immediately to compliance and executive leadership, not held for the next scheduled review meeting. Given the fixed, non-negotiable nature of Meridian's regulatory notification windows, a gap discovered and escalated immediately is a manageable problem. A gap discovered during an actual examination is not.
