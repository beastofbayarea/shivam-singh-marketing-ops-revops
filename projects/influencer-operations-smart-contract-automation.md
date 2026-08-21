# Turning an influencer agreement into an executable operations process

The old process took 14 days from agreement to payment and consumed about 40% of Marketing Operations capacity. Creators waited while identity, legal, campaign, approval, finance, and procurement handed work across disconnected systems; smaller creators bore the highest burden.

During my June–December 2023 Rakuten role, I re-engineered the creator operation with campaign teams, Legal, Marketing Operations, Finance, Procurement, Identity/Platform, SAP payment owners, and the creators themselves.

## The product was a state transition

A PDF recorded terms but could not advance the operation. I modeled the lifecycle:

**invited → verified → contracted → delivered → approved → paid → learned**

Each state required evidence, emitted an event, had an automatic consequence, and named human exceptions.

- **Verified:** identity/liveness; mismatch or accessibility failure went to review.
- **Contracted:** signed version and disclosure terms; redlines or unusual rights stayed with Legal.
- **Delivered:** required content/platform evidence; deleted posts, outages, and disputed metrics paused.
- **Approved:** milestone and disclosure checks; quality/fraud exceptions required a person.
- **Paid:** SAP settlement confirmation; duplicate, currency, tax, or rejection remained open.
- **Learned:** performance-window close; appeals/corrected platform data could amend future selection.

Transitions were idempotent so replaying a delivery or payment event could not pay twice. The ledger made history tamper-evident; it did not prove audience authenticity or subjective creative quality.

## I stopped owning commodity blockchain infrastructure

The first design spent effort on protocol nodes, upgrades, and support without shortening the creator journey. I partnered for that layer and retained internal ownership of:

**verified identity → versioned legal logic → milestone evidence → tamper-evident history → exceptions/approval → SAP reconciliation**

The source lists alternatives across Microsoft/AWS products but no final bill of materials. I preserve functional architecture rather than claim every option ran in production.

[NIST IR 8202](https://doi.org/10.6028/NIST.IR.8202) reinforces the boundary: ledgers and smart contracts alter record/trust properties, while external data, keys, governance, and bugs remain dependencies.

## Legal moved upstream into product design

Legal reviewed recurring disputes and converted stable decisions into versioned templates. Routine terms advanced; usage rights, exclusivity, unusual jurisdiction, ambiguous deliverables, and custom payment conditions stayed reviewable.

Disclosure became structured campaign/delivery evidence rather than hidden contract prose. The FTC’s [2023 Endorsement Guides announcement](https://www.ftc.gov/news-events/news/press-releases/2023/06/federal-trade-commission-announces-updated-advertising-guides-combat-deceptive-reviews-endorsements) clarified advertiser, endorser, and intermediary responsibility. A platform disclosure tool alone could be insufficient.

Because automation magnified bad terms, templates carried effective date, authorized owner, test cases, rollback, and override history.

## Payment remained a financial decision

Payment required four independent facts:

1. verified party;
2. accepted terms;
3. verified deliverable;
4. authorized approval.

Only then did the workflow create an SAP instruction. SAP returned settlement or rejection for reconciliation.

Late or conflicting platform metrics paused the contract. The system did not average sources, guess, or pay because a blockchain timer expired. That exception behavior separated automation from abdication.

Performance informed future creator selection after a review window. Followers did not equal reach; engagement did not equal incrementality. A source estimate of up to 20% fake-engagement exposure justified verification but did not establish fraud prevented.

## Scale and economics

- **Cycle:** 14 days → <48 h → at least 12 days / 85.7% lower using 48 h conservatively.
- **Capacity:** baseline partner volume → expand without Operations hires → 10×.
- **Unit administration:** baseline cost → reduce → ~$500 per contract lower.
- **Annual operating value:** baseline absent → material savings → $2.2M reported. At $500 each, this implies 4,400 contract-equivalents if unit savings were the only driver; source scope is incomplete.
- **Campaign timing:** baseline delay → earlier launch → ~$5M annualized modeled revenue. Not booked revenue; cohorts absent.
- **ROAS:** 113% reported but formula ambiguous, so excluded from headline.

Anchor campaigns received white-glove migration; long-tail creators used low-code onboarding. Work shipped in three-week increments: identity, templates, delivery, payment, then selection feedback.

The target was not zero exceptions. It was fast standard work and legible non-standard work. The state model, partner decision, upstream Legal design, evidence rules, exception policy, rollout, and economics were mine to integrate. Legal controlled terms; Finance payment; campaign owners acceptance; providers evidence; creators appeal/correction.

The operating asset was a verifiable transition from promise to payment. Technology mattered only where it made identity, obligation, delivery, approval, settlement, and learning observable to the people accountable for them.
