# Requirements

## Functional Requirements

### Non-Human Identity Discovery and Inventory
- Automatically discover and catalog every non-human identity across trading systems, cloud platforms, and compliance tooling, including service accounts, API keys, trading bots, and AI agents
- Maintain a continuously updated inventory, not a point-in-time snapshot, since new identities are created constantly and a static inventory is stale the day it is produced
- Detect identities with no assigned owner and flag them for remediation rather than allowing them to persist unowned indefinitely

### Ownership and Lifecycle Governance
- Assign every non-human identity an accountable human owner at creation, not retroactively
- Automatically reassign or disable ownership when the accountable owner leaves the organization or changes roles
- Enforce credential expiration on a defined schedule for every non-human identity, with automatic rotation before expiration, eliminating indefinite standing credentials

### Scoped Access and Least Privilege
- Scope every non-human identity, including AI agents, to the minimum access required for its specific function
- Prevent AI agents from dynamically acquiring permissions beyond their originally approved scope without explicit, logged approval
- Automatically revoke access that has gone unused over a defined period, since unused access is exposure without offsetting business value

### Policy Enforcement, Not Just Policy Documentation
- Enforce access control and lifecycle policy through a deterministic rules engine, so compliance is a property of the system, not dependent on manual review
- Produce a clear, traceable answer for any policy question, whether a specific identity's access complies with least privilege, whether its credentials are current, whether its owner is still active, without requiring a human to manually investigate

### Continuous Evidence Generation
- Generate audit-ready evidence automatically and continuously, not assembled manually in response to an examination request
- Produce a complete, current answer to "what has access to what, and why" on demand, not after a multi-week reconciliation effort
- Retain evidence in a form that is verifiably unaltered, so evidence produced today can be trusted months later during an actual examination

## Non-Functional Requirements

### Scale
- Support governance and continuous monitoring of a non-human identity population in the millions, not the thousands, without requiring proportional growth in review staffing
- Perform discovery and policy evaluation fast enough that the identity inventory reflects current reality, not a lagging historical state

### Speed of Response
- Support production of a complete access and identity picture within regulatory notification windows as short as 36 to 72 hours
- Support automated anomaly detection fast enough to identify unusual non-human identity behavior before it becomes a reportable incident, not after

### Auditability
- Every enforcement decision and every piece of generated evidence must be traceable to the specific rule or policy that produced it
- The system must withstand direct examiner questioning about how a specific control was verified, not just whether a policy exists describing it

### Integration
- Operate across Meridian's existing trading systems, cloud infrastructure, and compliance platforms without requiring a wholesale replacement of underlying infrastructure
- Interoperate with identity providers and privileged access management tooling already in place, rather than introducing a competing, parallel identity system

## What Is Explicitly Out of Scope

- Human identity lifecycle management is addressed by Meridian's existing IAM program and is not the subject of this architecture
- This architecture does not replace Meridian's core banking, trading, or compliance platforms. It governs the identities that access them
- Physical access control and building security are out of scope
