# ADR-003: Automated Credential Lifecycle and Expiration Over Static, Indefinite Credentials

**Status:** Accepted

## Business Context

The overwhelming majority of Meridian's non-human identities today hold static credentials, API keys and service account passwords set once and left in place indefinitely. Nothing in the current environment requires or enforces rotation. A credential created four years ago for a project that no longer exists functions identically, from the system's perspective, to a credential created yesterday for an active trading system.

This is not a hypothetical risk. Industry data consistently shows compromised non-human identities, service accounts, and API keys specifically, are now the dominant factor in identity-related breaches, and the reason is straightforward: a credential that never expires is a credential that remains useful to an attacker indefinitely, long after any legitimate business reason for it may have ended.

## Options Considered

1. Continue with static, indefinitely-valid credentials, relying on manual cleanup when someone notices an unused one
2. Automated credential expiration and rotation on a defined schedule, enforced by default across all non-human identities
3. Manual periodic credential rotation, performed by teams on an ad hoc schedule

## Pros and Cons

**Static, indefinite credentials**
Pro: No operational disruption. No engineering investment required.
Con: Every credential ever issued remains a standing risk for as long as it exists, which at Meridian's scale means millions of indefinitely valid credentials, an enormous and continuously growing attack surface with no natural expiration to shrink it.

**Automated expiration and rotation, enforced by default**
Pro: Removes the single largest source of standing risk in the environment without depending on anyone remembering to act. A credential that expires on schedule stops being useful to an attacker the moment it expires, regardless of whether the compromise was ever detected.
Con: Requires careful rollout to avoid breaking production systems that depend on a credential continuing to work exactly as it does today. Some legacy integrations may need remediation work before they can support rotation cleanly.

**Manual periodic rotation by teams**
Pro: Some improvement over no rotation at all, and requires less upfront engineering than full automation.
Con: Depends on individual teams remembering and prioritizing rotation amid competing operational demands, which is the same failure mode as manual identity review generally. Consistency and coverage will be uneven at best, and unmanaged at worst, across a workforce of teams with different priorities.

## Risks and Impact

Automated rotation, rolled out carelessly, risks breaking live trading or compliance integrations that depend on a specific credential continuing to work without interruption. This is a real operational risk, managed through phased rollout, testing in non-production environments first, and rollback capability at each stage, consistent with the remediation approach described in Constraints and Risks.

The alternative risk, continuing with static credentials, is a growing population of indefinitely valid credentials that represent Meridian's single largest and most preventable source of compromise, one that current industry data shows is already the dominant vector for identity-related breaches across the sector.

## Final Recommendation

Enforce automated credential expiration and rotation as the default state for every non-human identity, with static, indefinitely-valid credentials treated as the exception requiring explicit, time-bound justification, not the baseline condition. This is the same standing-privilege principle applied to human privileged access elsewhere in this portfolio, applied here to the credential population that actually represents Meridian's largest exposure.
