# Turning an Influencer Agreement into an Executable Operations Process

I led the redesign of influencer contract and payment operations during my Rakuten role. I had identified that creators were waiting on disconnected identity, legal, campaign, approval, and finance teams, while the company could not tell whether the right person completed the agreed work. I worked with creators, campaign managers, Legal, Marketing Operations, Finance, procurement, identity and platform specialists, and payment-system owners.

This project ran from June to December 2023. The existing process took 14 days from agreement to payment and consumed about 40% of Marketing Operations capacity in manual checks and handoffs. Smaller creators bore the greatest burden because they lacked an enterprise legal or administrative team.

My redesign crossed identity, contract state, disclosure, deliverable evidence, exceptions, SAP payment, reconciliation, and future creator selection. The operating scope was large enough to increase partner capacity tenfold without adding Operations headcount, reduce the standard cycle below 48 hours, and support a reported $2.2 million annual savings case—while keeping the separate $5 million campaign-timing estimate labeled as modeled revenue.

## The product was the transition between states

A PDF recorded terms but could not safely advance the next step. I modeled the operation as a state machine:

| State | Evidence required to enter | Automatic consequence | Human exception |
|---|---|---|---|
| invited | approved campaign and creator record | identity request | duplicate or restricted party |
| verified | identity and liveness evidence | present approved contract version | mismatch, low confidence, inaccessible verification |
| contracted | signature, version, disclosure terms | activate campaign brief | redline or nonstandard right |
| delivered | required content and platform event | evaluate milestone | deleted post, disputed metric, platform outage |
| approved | milestone and disclosure checks pass | create payment instruction | fraud signal, quality dispute, missing approval |
| paid | SAP confirms settlement | close payable and retain audit event | rejection, duplicate, currency or tax exception |
| learned | performance window closes | update future selection features | appeal or corrected platform data |

Each transition was idempotent: replaying a delivery or payment event could not pay twice. Each exception had a reason code, owner, service level, and return state. The ledger made the history tamper-evident; it did not prove that an Instagram audience was genuine or that creative work met a subjective brief.

## I stopped treating blockchain infrastructure as differentiation

The first design owned too much protocol plumbing. Nodes, upgrades, and operational support absorbed effort that did not shorten the creator's journey. I shifted the commodity protocol layer to ConsenSys and kept internal ownership of identity, contract logic, evidence, exception handling, SAP reconciliation, and the creator experience.

The source notes list slash-separated technology alternatives—Entra Verified ID or Amazon Cognito; SQL Ledger or Amazon QLDB; Power Automate or Step Functions; Teams or Chime. Those are credible design options but not a credible claim that all were one production stack. The final deployment bill of materials is not retained, so I describe the functional layers rather than inventing a vendor combination:

`verified identity → versioned legal template → milestone evaluator → tamper-evident event history → approval/exception workflow → SAP payment and reconciliation`

NIST's blockchain overview reinforces this restraint: distributed ledgers and smart contracts change trust and record properties, but external data, key management, governance, and bugs remain real dependencies.

## Legal became a product-design function

Legal reviewed recurring disputes and converted stable decisions into versioned templates. Routine terms advanced automatically; usage rights, exclusivity, unusual jurisdictions, ambiguous deliverables, or custom payment conditions remained reviewable.

Disclosure obligations were structured data attached to the campaign and delivery event. The FTC's 2023 Endorsement Guides clarified advertiser, endorser, and intermediary responsibility and warned that a platform disclosure tool may be insufficient. I therefore treated proof of a required disclosure as part of delivery evidence, not a sentence buried in the contract.

Automation increased the blast radius of a bad template, so release controls included template version, effective date, authorized approver, test cases, rollback, and an override that recorded who changed what and why.

## Payment followed evidence, not a blockchain event

The payment rule required four independent facts: verified party, accepted terms, verified deliverable, and authorized approval. Only then could the workflow create a payment instruction. SAP remained the financial system of record and returned settlement or rejection status for reconciliation.

When platform metrics arrived late or conflicted, the contract paused. It did not guess, average the sources, or release money because an on-chain timer expired. That exception behavior is the difference between automation and abdication.

Performance evidence then informed future creator selection and spend, subject to a review window. The system did not equate followers with reach or engagement with incrementality. Reported fake-engagement exposure could be as high as 20%, but the retained record does not define the vendor method or confirm actual fraud incidence; I use it as the risk that justified verification, not as fraud prevented.

## Economics and capacity

The process moved from 14 days to under 48 hours. Using 48 hours as the conservative endpoint, the reduction was at least 12 days, or 85.7%. Partner-volume capacity increased 10× without additional Operations headcount.

The remaining financial claims need separate treatment:

- **~$500 lower administrative cost per contract** was the unit saving.
- **$2.2M annual operating savings** would require about 4,400 contract-equivalents at $500 each if unit savings were the only driver. The source does not preserve whether labor, platform retirement, dispute reduction, or payment operations contributed, so I do not present that division as measured volume.
- **~$5M annualized revenue uplift** was attributed to launching campaigns earlier. It is a modeled timing benefit, not booked revenue; the retained record does not preserve delayed-versus-launched campaign cohorts.
- **113% ROAS** is ambiguous. Standard ROAS would be 1.13× revenue/spend, while “113% return” may mean a different numerator. I omit it from the headline until the formula and scope are recovered.

## What scaling actually meant

Anchor campaigns received white-glove migration because contract or payment disruption could damage a high-value relationship. The long tail used a low-code onboarding path and the same evidence states with fewer manual steps. Work moved in three-week increments: identity, templates, delivery verification, payment, then selection feedback.

The target was not zero exceptions. It was to make standard work fast and exceptions legible. The next scorecard I would insist on includes identity false-rejection rate, delivery disputes, auto-approval share, duplicate-event prevention, time in each exception state, payment rejection, reconciliation break rate, creator satisfaction, and disclosure compliance.

I owned the process model, build-versus-partner decision, upstream Legal design, evidence rules, exception policy, rollout sequence, and business case. Legal owned term approval; Finance owned payment controls; campaign owners accepted delivery; identity and platform providers supplied evidence; creators retained appeal and correction paths.

### Research anchors

[NIST IR 8202, *Blockchain Technology Overview*](https://doi.org/10.6028/NIST.IR.8202) is the basis for the ledger, smart-contract, key, and off-chain trust boundaries. [The FTC's 2023 Endorsement Guides announcement](https://www.ftc.gov/news-events/news/press-releases/2023/06/federal-trade-commission-announces-updated-advertising-guides-combat-deceptive-reviews-endorsements) establishes the period-appropriate disclosure and responsibility context. The [FTC influencer guidance hub](https://www.ftc.gov/business-guidance/advertising-marketing/endorsements-influencers-reviews) supports the ongoing monitoring responsibility rather than a one-time contract clause.
