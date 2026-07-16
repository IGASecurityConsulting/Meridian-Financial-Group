# As-Is Architecture

## Identity Sits in Fragments, Not One Place

Meridian's non-human identities are created and managed independently across trading systems, cloud infrastructure, and compliance platforms, with no single system of record tying them together. A service account created in the cloud infrastructure team's AWS environment has no visibility to the trading systems team, and an API key generated for a compliance reporting integration is invisible to whoever is trying to answer a question about the institution's overall identity posture. There is no inventory. There are only fragments, each accurate to the team that created it and invisible to everyone else.

## Provisioning Is Ad Hoc

A new non-human identity comes into existence whenever an engineer, a trading system, or an AI agent needs one, provisioned directly by whoever needs it, through whatever mechanism their platform makes easiest. A developer generates an API key in a configuration console. A trading system spins up a service account to connect to a data feed. An AI agent deployed for compliance reporting creates its own downstream credentials as part of its normal operation. None of this goes through a centralized request, approval, or registration process. Each identity is technically functional and organizationally invisible from the moment it is created.

## Credentials Do Not Expire

Static, long-lived credentials are the default across the environment. API keys and service account passwords are set once and left in place indefinitely, since nothing in the current architecture requires or enforces rotation. A credential created four years ago for a project that no longer exists is functionally identical, from the system's perspective, to a credential created yesterday for an active trading system. Both work exactly the same way, indefinitely, until someone manually notices and removes one.

## Ownership Is Assumed, Not Assigned

No formal mechanism ties any non-human identity to an accountable human owner. In practice, the closest thing to ownership is institutional memory: someone on a team probably remembers why a given service account exists, until that person changes roles or leaves the organization, at which point the memory leaves with them and the credential remains, now with no one who can explain what it does or whether it is still needed.

## AI Agents Operate With the Least Visibility of Any Identity Category

Meridian's trading and compliance AI agents were deployed to solve immediate operational problems, faster trade execution, automated compliance report generation, without a governance model built for how agents actually behave. Agents authenticate using credentials provisioned the same ad hoc way as any other service account, but unlike a static service account, an agent can take chained actions and, in some deployments, request additional access at runtime as part of completing a task. The current architecture has no mechanism to distinguish an agent acting within its intended purpose from one that has drifted outside it, because nothing is tracking the agent's actual behavior against its original intended scope in the first place.

## Access Review Is a Manual, Periodic Sample

The closest thing Meridian has to identity governance today is a quarterly manual review, where an analyst pulls whatever account listings are available from each platform and checks a sample against expected business need. At a population of 4 million non-human identities, this review touches a small fraction of what actually exists, and it reviews a snapshot that is already outdated by the time the review is complete, since new identities are created continuously in the gaps between review cycles.

## No System Can Answer the Question That Matters

If asked today what has access to a specific system, why, and whether that access is still appropriate, no single system at Meridian can produce that answer. Producing even a partial answer requires manually querying multiple disconnected platforms, cross-referencing spreadsheets, and relying on whichever team members happen to still remember the context behind identities that predate current staff. This is the exact capability an examiner will test directly, and it is the exact capability the current architecture cannot deliver.
