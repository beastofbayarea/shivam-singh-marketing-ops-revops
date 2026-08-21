# Recovering a Mobile Purchase Without Confusing Tracking with Growth

I led a client project to repair mobile affiliate journeys and measurement during my McKinsey role. I had identified that shoppers were being sent to the wrong place when they crossed from a web offer into a merchant app, while merchants, Finance, Engineering, and the affiliate network held different transaction records. I worked with shoppers, merchant product and engineering teams, affiliate and growth teams, Finance, Legal and privacy teams, and client leadership.

The source page says the story could be adapted to Rakuten or Microsoft. This repository assigns it to my July 2014–June 2016 McKinsey experience, so I treat it as a client engagement and do not claim the platform as an employer-owned product.

Within that client boundary, I led the recovery from shopper route through Finance reconciliation: the SDK build-versus-buy choice, merchant integration contract, cross-app identity, server event, three-ledger match, commission truth, and 20%-market holdout. The system ultimately connected $15 million of attributed revenue and recovered roughly $2 million previously hidden from reporting, while keeping those amounts separate from the +0.8-point incremental-conversion evidence.

## The incident had two casualties

A mobile-web click opened a merchant app but lost the intended product path and affiliate context. The shopper landed on a home screen or wrong item. If a purchase still happened, the merchant, internal platform, and affiliate network could disagree about credit.

The same defect therefore hurt both **conversion** and **financial evidence**. Improving one without the other would leave either a smoother unmeasured journey or more precise accounting for a bad experience.

## I chose time-to-recovery over a nine-month platform build

An internal deep-link system was estimated at nine months. I chose a replaceable external SDK that could ship within one quarter and kept the interface modular so the client could change vendors later.

The choice was technically period-appropriate. Apple introduced Universal Links with iOS 9 in 2015, using an HTTPS site-association file and app entitlement to open the corresponding in-app content. Android App Links arrived with Android 6, using a hosted Digital Asset Links file to verify the app–website association. These platform primitives validated the secure routing model even though the retained record does not identify the SDK vendor.

The release contract covered installed-app routing, web fallback, deferred destination, campaign parameters, merchant product identifier, and failure reason. A link was not “successful” because the app opened; it was successful when the intended product or offer rendered.

## A transaction needed one identity across three ledgers

I standardized campaign, click, merchant, transaction, timestamp, currency, amount, return/cancel, and commission fields. Server-to-server conversion events reduced dependence on the client transition and created a durable merchant record.

The reconciliation chain was:

`internal click/route → merchant order event → affiliate-network record → finance-eligible transaction`

New and old paths ran in parallel. Variance above 5% triggered investigation and could stop rollout. A 20% volume drop generated an operational alert. The independent network report was the contractual tie-breaker while the teams investigated why systems differed; it was not assumed to be technically infallible.

The shared view exposed matched amount, missing event, duplicate, timestamp drift, return status, commission, and owner. “Attribution accuracy improved 25%” is a reported relative result; the source does not preserve the exact match-rate baseline or whether accuracy meant event match, amount match, or partner agreement.

## Merchant integration became a product

The existing merchant guide ran to 40 pages and onboarding took 45 days. I reduced the requirement to a one-page implementation pack:

- accepted link and campaign parameters;
- destination and fallback behavior;
- server event schema and signing/authentication;
- test purchase, cancellation, and duplicate cases;
- 5% reconciliation rule and escalation owner;
- launch and rollback checklist.

Onboarding fell to nine days—36 days faster, an 80% reduction. The pack did not remove engineering work; it removed interpretation and made acceptance observable.

## I forced Finance and Growth to use different revenue words

The source reports $15 million in attributed revenue and about $2 million in previously hidden revenue recovered after tracking repair. Those measures answer **which transactions can now be connected?** They do not answer **which purchases would not have happened without the affiliate exposure?**

To address the second question, I ran a four-week geographic holdout covering 20% of markets. Exposed-market conversion was 3.1% versus 2.3% in control: +0.8 percentage points, or 34.8% relative lift. The study estimated that about 35% of attributed revenue was incremental and 65% likely would have occurred organically.

Multiplying 35% by $15 million yields $5.25 million, but I do **not** claim that as measured incremental revenue because the source does not prove the holdout and $15 million cover the same markets, time window, eligible population, or revenue definition. Likewise, the $2 million recovered is not added to $15 million if it is already included in attributed revenue.

## Outcome ledger

| Question | Baseline | Result | How it was measured | Remaining limitation |
|---|---:|---:|---|---|
| Did the shopper reach the intended content? | broken-path rate not retained | deep-link failures -90% | route/fallback telemetry | denominator and device mix absent |
| Did the ledgers agree? | match baseline not retained | attribution accuracy +25% | three-record reconciliation | “accuracy” definition absent |
| Could a merchant launch faster? | 45 days | 9 days | request-to-production dates | merchant complexity mix absent |
| How much revenue became attributable? | ~$2M previously hidden | $15M total attributed, including ~$2M recovered if scopes match | reconciled transactions | inclusion of recovered amount must be confirmed |
| Was the channel incremental? | control conversion 2.3% | exposed 3.1%; +0.8 points | four-week, 20%-market geo holdout | market assignment and confidence interval absent |
| Did the customer base grow? | prior year | +18% YoY membership | registered/eligible members | cannot isolate this project |
| Was acquisition efficient? | plan target | CAC 10% below target | spend/acquired member | acquired-member definition absent |

The geo test was the best causal evidence, but a four-week window can miss delayed purchases and seasonal effects. I would now pre-register market assignment, test pre-period balance, report confidence intervals, and reconcile device/privacy differences.

I owned reframing the defect, SDK build-versus-buy decision, event and reconciliation contract, holdout, merchant enablement, and cross-functional operating view. Merchant engineers implemented their endpoint and app route; the client product team owned release; Finance owned commission recognition; Legal and privacy teams approved identifiers and consent; the network retained contractual reporting duties.

The period-specific technical references are Apple's archived [Universal Links guide](https://developer.apple.com/library/archive/documentation/General/Conceptual/AppSearch/UniversalLinks.html) and the current [Android App Links architecture](https://developer.android.com/training/app-links/about), whose verified association pattern began with Android 6. The counterfactual method is grounded in the World Bank's [*Impact Evaluation in Practice*](https://www.worldbank.org/en/programs/sief-trust-fund/publication/impact-evaluation-in-practice). Current Apple attribution and privacy systems are materially different, so I do not project the 2015 design unchanged onto today's platform.
