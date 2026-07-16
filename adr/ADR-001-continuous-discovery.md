# ADR-001: Continuous Automated Discovery Over Periodic Manual Review

**Status:** Accepted

## Business Context

Meridian's non-human identity population sits at roughly 4 million, against a workforce of 28,000 humans. The current governance model relies on a quarterly manual review, an analyst sampling account listings from whichever platforms happen to be accessible at the time.

That review was never built for this scale, and it shows. A quarterly sample touches a small fraction of 4 million identities, and by the time the review completes, new identities created during the review period are already invisible to it. The gap between what exists and what anyone can see is not closing. It is growing every quarter.

## Options Considered

1. Expand the manual review team and review more frequently
2. Continuous automated discovery across all platforms, feeding a single unified inventory
3. Accept the current sampling approach as sufficient, given cost constraints

## Pros and Cons

**Expand manual review**
Pro: No new technology required. Familiar process to scale up.
Con: Headcount would need to grow roughly in proportion to identity volume to meaningfully improve coverage, which is not a sustainable answer when identity volume is growing faster than any realistic hiring plan, driven by continued AI agent adoption.

**Continuous automated discovery**
Pro: Coverage is complete and current by design, not sampled. New identities are captured the moment they are created, not discovered months later during the next review cycle.
Con: Requires integration work across every platform, trading systems, cloud infrastructure, compliance tooling, to establish discovery coverage. Upfront engineering investment before the full inventory value is realized.

**Accept current sampling**
Pro: No investment required.
Con: An examiner asking "what has access to this system" gets a partial, stale answer, which is the exact finding pattern already being cited industry-wide. This option does not reduce risk, it just avoids the cost of addressing it until an incident or exam forces the issue anyway.

## Risks and Impact

Building continuous discovery requires real engineering effort across a fragmented set of existing systems, and some platforms may resist clean integration, requiring custom connectors. That cost is real but bounded and one-time.

The alternative risk, continuing with periodic sampling, is a governance model that becomes less accurate every quarter as identity volume grows, guaranteeing that whatever picture Meridian has when an examiner asks is worse than the picture it had the quarter before.

## Final Recommendation

Adopt continuous automated discovery across all platforms as the foundation of the identity governance architecture. Manual review at Meridian's scale is not a lighter-weight version of the same control. It is a fundamentally different, and insufficient, control.
