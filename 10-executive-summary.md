# Executive Summary

## Meridian Financial Group: Non-Human Identity Governance Architecture

Meridian Financial Group manages $340 billion in assets across retail banking, wealth management, and institutional trading in twelve countries. No breach has occurred. No fine has been issued. The institution is stable, profitable, and, by every outward measure, secure.

An internal audit ahead of a regulatory examination found something the outward measures do not capture: Meridian's environment holds more than 4 million non-human identities, service accounts, API keys, trading bots, and AI agents, against a workforce of 28,000 humans. No formal ownership model exists for the majority of them. Credentials do not expire. If an examiner asked what has access to Meridian's systems and why, no one at the institution could answer completely.

That is not a hypothetical exposure. It is the exact finding category regulators across the industry have started citing directly: firms with identity and access controls that exist on paper but cannot be demonstrated as enforced.

## Why This Happened

Four years of rapid AI adoption in trading, compliance reporting, and loan processing built Meridian's non-human identity population one reasonable decision at a time. Every service account, every API key, every AI agent deployed to solve an immediate operational problem was justified in the moment. None of it was tracked centrally. The result is a governance gap that grew invisibly, exactly the way this gap grows at every institution moving as fast as Meridian has.

## The Actual Problem

Meridian does not lack policy. It lacks proof. Its current governance model relies on quarterly manual review, a process that was adequate at a fraction of today's scale and cannot meaningfully cover 4 million identities no matter how it is staffed. Compounding this, modern regulatory notification windows, some as short as 36 to 72 hours, assume an institution can produce a unified access picture on demand. Meridian's identity data is fragmented across systems that were never built to answer that question together, which means the institution cannot currently meet its own regulatory deadlines even if asked today.

## The Architecture

This proposal is built on three decisions, each defensible on its own merit and documented as such.

Non-human identities are discovered continuously and governed through automated lifecycle management, ownership assigned at creation, credentials expiring on a defined schedule, unused access automatically revoked. Nothing depends on a human noticing or remembering.

Compliance is enforced through a deterministic policy engine, not assessed through AI judgment alone. Every access decision traces to a specific, codified rule that either held or did not, the standard of proof an actual examination requires, mirroring the same layered governance model already implemented in the Identity Security Copilot.

Evidence is generated continuously, not assembled under deadline pressure. When an examiner asks what has access to what and how Meridian knows the control held, the answer already exists, retrievable in minutes, not reconstructed from spreadsheets in the hours before a notification deadline passes.

## The Delivery

The architecture is delivered in three phases over eighteen months. Discovery and inventory, completed by month six, gives Meridian its first complete picture of what actually exists. Lifecycle automation and ownership, completed by month twelve, closes the standing-credential exposure that represents the institution's largest preventable risk. The policy engine and continuous evidence layer, completed by month eighteen, gives Meridian the ability to answer a regulator's core question on demand, with evidence, not assurance.

## The Ask

Fund the three-phase governance architecture now, while the timeline is still Meridian's own to set.

The alternative is not the status quo. The alternative is an examination that finds exactly what this audit already found, with no remediation plan underway and no credible answer to offer, or an incident, sourced from one of 4 million ungoverned credentials, that forces the same conversation on worse terms.

An institution that can show a regulator a complete inventory, an active remediation plan, and a measurable pace of progress is in a fundamentally different position than one that has no answer at all. That difference is available to Meridian starting the day this architecture is approved, not the day it is finished.
