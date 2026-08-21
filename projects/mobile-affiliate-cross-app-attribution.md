# Recovering a mobile purchase without confusing tracking with growth

One mobile defect harmed both the customer journey and the financial record.

A web affiliate click opened a merchant app but lost the intended product and campaign context. Shoppers landed at the home screen or wrong item. If they purchased anyway, merchant, platform, affiliate network, and Finance could disagree about credit.

During my McKinsey role, I took the repair from shopper route through Finance reconciliation, coordinating merchant Product/Engineering, Affiliate/Growth, Legal/Privacy, and client leaders.

## I chose recoverability over a nine-month build

An internal deep-link platform was estimated at nine months. I selected a replaceable external SDK that could ship within one quarter, with a modular interface preserving future vendor choice.

The timing was technically credible: Apple introduced Universal Links with iOS 9 in 2015; Android App Links arrived with Android 6. The association files verified app/site ownership and routed HTTPS links to corresponding in-app content.

The release contract covered installed-app destination, web fallback, deferred destination, campaign parameters, merchant product ID, and failure reason. “App opened” was not success; the intended product or offer had to render.

## One purchase needed one identity across three ledgers

I standardized campaign, click, merchant, order, timestamp, currency, amount, return/cancel, and commission fields. Server-to-server order events created a durable merchant record independent of the client transition.

**internal click/route → merchant order → network record → finance-eligible transaction**

Old and new paths ran in parallel. Variance above 5% triggered investigation and could stop rollout; a 20% volume drop triggered an operational alert. The network report served as contractual tie-breaker during investigation, not assumed technical truth.

The shared view showed matched amount, missing/duplicate event, timestamp drift, return, commission, and owner. The reported +25% attribution accuracy lacks a retained definition of accuracy or baseline match rate, so it remains a scoped relative result.

## Merchant integration became a one-page contract

The original guide was 40 pages and onboarding took 45 days. I reduced the interface to:

- accepted link/campaign parameters;
- destination/fallback behavior;
- signed/authenticated server schema;
- purchase, cancellation, duplicate test cases;
- 5% reconciliation rule and owner;
- launch/rollback checklist.

Onboarding fell to nine days—36 days and 80% lower. The document did not remove engineering; it removed interpretation and made acceptance observable.

## Finance and Growth used different revenue language

The repair connected $15 million of attributed revenue and surfaced roughly $2 million previously hidden. These answer **which transactions can be connected?**

Incrementality answers **which purchases would not otherwise have happened?**

I ran a four-week geographic holdout across 20% of markets. Exposed conversion was 3.1% versus 2.3% control: +0.8 points / +34.8% relative. The study estimated ~35% of attributed revenue incremental and 65% likely organic.

I do not multiply 35% × $15M into a claimed $5.25M because market, period, population, and revenue scope may differ. The $2M is not added to $15M if it is already included.

## Outcome ledger

| Question | Baseline → result | Method/limit |
|---|---|---|
| Did routing work? | broken-path rate absent → deep-link failures -90% | Route/fallback telemetry; denominator/device mix absent |
| Did ledgers reconcile? | match baseline absent → accuracy +25% | Three-record reconciliation; definition absent |
| Did merchants launch faster? | 45 days → 9 | Request to production; -80% |
| What became attributable? | ~$2M hidden → $15M total attributed (if scopes include it) | Reconciled orders; inclusion must be confirmed |
| Was channel activity incremental? | control 2.3% → exposed 3.1% | Four-week, 20%-market holdout; assignment/confidence absent |
| Did membership grow? | prior year → +18% YoY | Company membership; cannot isolate project |
| Did CAC beat plan? | target → 10% below | Spend / acquired-member definition absent |

Reframing, the SDK decision, routing/event contract, three-ledger reconciliation, merchant enablement, geo holdout, and operating view were my workstreams. Merchant engineers implemented; client Product released; Finance recognized commissions; Legal/Privacy approved identifiers; network partners reported contractually.

The enduring RevOps lesson was to keep customer conversion, attribution, financial reconciliation, and incrementality as four separate truths. A measurement system creates value only when it improves the journey and refuses to claim purchases it did not cause.
