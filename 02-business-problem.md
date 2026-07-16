# Business Problem

## The Question Nobody Could Answer

An examiner is going to ask Meridian Financial Group a simple question: what has access to your systems, and why. Right now, nobody at Meridian can answer that question completely, and the reason is not a lack of effort. It is scale that outran the process meant to govern it.

Meridian's environment holds more than 4 million non-human identities, service accounts, API keys, trading bots, and AI agents, against a workforce of 28,000 humans. That ratio did not happen on purpose. It happened the way it happens everywhere: a developer spun up a service account to get a job done, an automated trading system needed an API key to talk to a data feed, an AI agent was deployed to handle compliance reporting and generated its own credentials along the way. Each decision was small and reasonable in the moment. None of them were tracked as part of a governed inventory. Four years of that adds up to millions of identities nobody owns.

## Why This Is Not Just a Technical Problem

A service account with no owner is not a technical inconvenience. It is a standing question nobody is answering: who is accountable if this credential is misused, and how would anyone know. Meridian's trading and compliance AI agents compound the problem, since agents do not just hold static credentials the way a service account does. They act autonomously, calling APIs, accessing data, and in some cases provisioning their own downstream access, without a human approving each action. An agent's blast radius is not fixed the way a traditional service account's is. It can grow at runtime, in ways no policy document anticipated when the agent was first deployed.

## Policy Exists. Enforcement Does Not.

Meridian is not starting from nothing. Access control policy exists. Identity governance standards exist. The problem is not the absence of policy, it is the absence of proof that policy is followed. Meridian's current model relies on periodic manual review, an analyst pulling a spreadsheet of accounts and checking whether each one still makes sense. At 4 million identities, that review is not a control. It is a sampling exercise that catches a fraction of what exists and misses everything created since the last review cycle.

This is precisely the gap regulators have started calling out directly. Recent examination findings across the industry cite firms with weak identity and access management controls, insufficient detection capability, and credentials that are not properly governed as recurring, cited deficiencies, not hypothetical risks. Meridian's upcoming examination is not going to accept a policy document as evidence. It is going to ask for proof of enforcement, and proof requires a system that can answer the question automatically, not a team that reviews a sample of accounts once a quarter.

## The Regulatory Clock Has Also Tightened

Even if Meridian could answer the ownership question today, it would still face a second problem: speed. Modern regulatory notification windows, some as short as 36 to 72 hours, assume an institution can produce a unified view of access and detect anomalies fast enough to meet the deadline. Meridian's identity data lives fragmented across trading systems, cloud platforms, and compliance tools that were never designed to answer a single question together. A fragmented identity picture cannot meet a 72-hour clock. It can only produce a partial answer, slowly, after the deadline has already passed.

## What This Actually Costs

The cost of this gap is not hypothetical. An examination finding citing inadequate identity and access controls triggers remediation requirements, increased examination frequency, and in serious cases, restrictions on operational activity. Beyond the direct regulatory cost, every one of those 4 million ungoverned identities is a potential path for exactly the kind of compromise the industry is already seeing at scale: leaked credentials, orphaned service accounts, and AI agents operating with more access than anyone intended, discovered only after something has already gone wrong.

## The Real Problem, Stated Plainly

Meridian does not have a policy problem. It has an enforcement and evidence problem. The architecture that fixes this has to do two things at once: bring 4 million ungoverned identities under a real lifecycle, with actual ownership and actual expiration, and produce continuous, automatic proof that the lifecycle is holding, so the answer to an examiner's question is immediate and complete, not a best effort assembled under deadline pressure.
