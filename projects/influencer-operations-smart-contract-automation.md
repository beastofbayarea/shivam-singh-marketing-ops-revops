# Redesigning Influencer Operations from Contract to Cash

I led this operating-model work during my [Rakuten experience from June to December 2023](https://github.com/beastofbayarea/shivam-singh-marketing-ops-revops/blob/main/shivam-singh-marketing-ops-revops.pdf).

Influencer and partner campaigns moved through manual identity checks, legal edits, performance validation, SAP entry, and payment. The process took 14 days, consumed about 40% of marketing operations capacity, and created a disadvantage for smaller partners who could not navigate enterprise administration. Reported fake engagement could expose as much as 20% of activity.

I redesigned the operation around verifiable workflow states rather than static documents.

## The state machine became the source of truth

I defined one lifecycle: invited, identity verified, terms accepted, work delivered, evidence approved, payment released, and performance learned. Each transition required named evidence, an accountable system or person, and a path for exceptions.

The workflow joined identity proof, versioned terms, delivery evidence, campaign requirements, approval, payment, and performance feedback. It did not assume that a ledger entry made an external fact true; audience and delivery evidence still had to be evaluated before the system could advance.

NIST's blockchain overview influenced how I treated ledgers, smart contracts, keys, trust boundaries, and technical limitations. I stopped operating custom blockchain plumbing and partnered for the commodity protocol layer, keeping internal effort on identity, workflow design, audit evidence, and the partner experience.

## Legal moved upstream

Custom redlines on every routine contract created delay without improving control. I worked with Legal to convert recurring decisions into approved, versioned templates and rules. Standard work could proceed automatically; unusual terms, low-confidence identity, conflicting evidence, or disputed delivery went to human review.

The FTC's updated Endorsement Guides supplied the disclosure and responsibility foundation. Disclosure requirements were encoded in campaign terms and delivery evidence rather than left to a final manual check.

Human override remained available, but the override created a recorded reason and an auditable state transition.

## Payment was automated only after evidence

The system released payment after verified identity, accepted terms, required delivery, and approval aligned. If evidence conflicted, the workflow paused instead of guessing. I also connected observed audience quality and campaign performance to future partner selection and spend allocation.

This closed the learning loop: contract and payment data did not disappear into Finance; they became part of the next campaign decision.

## The operating result

- Contract-to-cash fell from 14 days to under 48 hours, an improvement of about 86%.
- Partner capacity increased tenfold without additional Operations headcount.
- Administrative cost fell by roughly $500 per contract.
- Annual operating savings reached $2.2 million.
- Faster launch cycles supported an estimated $5 million in annualized revenue uplift, with reported return on ad spend of 113%.

I do not claim that automation eliminated fraud. I measure the evidence checked, exposure reduced, disputes resolved, and exceptions handled.

## What I learned

Smart contracts are useful when they execute a well-designed operating rule. They cannot decide whether the rule is fair, whether the external evidence is reliable, or when an exception deserves judgment. I automate the state transition only after those responsibilities are explicit.

## External foundations

These sources supplied the primary endorsement and blockchain methodology. My resume is linked only for employment chronology.

| Source | How I applied it |
|---|---|
| [U.S. Federal Trade Commission — Updated Endorsement Guides (June 2023)](https://www.ftc.gov/news-events/news/press-releases/2023/06/federal-trade-commission-announces-updated-advertising-guides-combat-deceptive-reviews-endorsements) | I used its disclosure and advertiser-responsibility guidance in contract and delivery requirements. |
| [NIST — Blockchain Technology Overview (2018)](https://doi.org/10.6028/NIST.IR.8202) | I used its treatment of smart contracts, keys, ledgers, trust, and limitations to define what the protocol could and could not automate. |
