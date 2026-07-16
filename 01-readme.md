# Meridian Financial Group: Non-Human Identity Governance Architecture

Meridian Financial Group is a multinational financial institution operating retail banking, wealth management, and institutional trading across twelve countries, with over $340 billion in assets under management and 28,000 employees. Meridian has invested heavily in AI-driven trading systems, automated compliance reporting, and algorithmic loan processing over the past four years.

That investment created a problem nobody was watching. An internal audit, prompted by an upcoming regulatory examination, found Meridian's environment holds over 4 million non-human identities, service accounts, API keys, trading bots, and AI agents, against a workforce of 28,000 humans. No formal ownership model exists for the majority of them. Credentials do not expire. Nobody can produce, on demand, a list of what has access to what, or why.

The regulatory examination is not going to ask whether Meridian has an identity policy. It is going to ask whether Meridian can prove that policy is actually enforced. Right now, Meridian cannot answer that question, and the gap between having a policy and proving a policy holds is the exact finding examiners are increasingly citing across the industry.

This case study documents the architecture Meridian needs to close that gap: not just governing non-human identity sprawl, but building the deterministic, evidence-producing control layer that turns a policy statement into something a regulator can actually verify.
