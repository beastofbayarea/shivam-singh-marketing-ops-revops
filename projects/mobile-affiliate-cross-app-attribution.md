# Repairing Mobile Affiliate Attribution Across App Boundaries

I completed this work during my [McKinsey experience from July 2014 to June 2016](https://github.com/beastofbayarea/shivam-singh-marketing-ops-revops/blob/main/shivam-singh-marketing-ops-revops.pdf).

Affiliate attribution broke when a customer moved from mobile web into a merchant's app. The customer often landed on the wrong screen, legitimate transactions disappeared from reporting, Finance questioned whether the channel created incremental value, and merchants faced a 45-day integration process.

I treated the problem as three connected failures: product routing, event integrity, and commercial governance.

## Time to value favored a modular partner

An internal build would take an estimated nine months. I selected a replaceable external SDK that could restore deep linking inside one quarter, with clear interface boundaries so the company could change the component later.

The routing design carried the customer into the intended product or offer while retaining standardized campaign parameters. Server-to-server events created a more durable transaction record than relying only on the client transition.

I used FTC guidance as the marketing baseline: the offer, destination, and attribution could not create a misleading customer experience. Repairing measurement did not justify obscure routing or unsupported claims.

## Three records had to reconcile

I standardized campaign parameters and compared internal events, merchant transactions, and affiliate-network logs. The old and new paths ran in parallel, with rollback if discrepancy exceeded 5%.

That threshold made the migration governable. A disagreement did not become a debate between teams; it produced a known investigation and release decision. One shared dashboard showed route success, attributed transaction, merchant confirmation, network record, discrepancy, and owner.

## Attribution was not the same as incrementality

A repaired tracking path could recover transactions that marketing touched, but it could not prove that marketing caused them. I ran a four-week geographic holdout covering 20% of markets.

The World Bank's impact-evaluation methodology shaped that counterfactual design. I compared conversion and revenue behavior in exposed and holdout geographies while keeping the distinction between observed attribution and estimated incremental value explicit.

The holdout showed a 0.8-percentage-point conversion lift and indicated that approximately 35% of attributed revenue was incremental.

## Merchant onboarding became part of the product

I replaced a long, bespoke integration process with a one-page implementation pack: required parameters, deep-link behavior, server event, test transaction, reconciliation rule, and escalation route. I also repositioned the proposition from “participate in cashback” to “measure and grow mobile merchant revenue.”

Onboarding fell from 45 days to nine.

## The combined result

- Deep-link failures declined 90%.
- Attribution accuracy improved 25%.
- Attributed revenue reached $15 million, including roughly $2 million recovered from previously hidden transactions.
- Merchant onboarding fell from 45 days to nine.
- The holdout estimated a 0.8-point conversion lift and 35% incremental share of attributed revenue.

## The operating lesson

Marketing measurement is part of the customer journey. If the link fails, both the experience and the evidence fail. I repair the route, reconcile the records, and then run a separate causal test before using attributed revenue as proof of growth.

## External foundations

These sources supplied the primary marketing and causal-measurement methodology. My resume is linked only for employment chronology.

| Source | How I applied it |
|---|---|
| [U.S. Federal Trade Commission — Advertising and Marketing Basics](https://www.ftc.gov/business-guidance/advertising-marketing) | I used its truthful and non-deceptive standard for the offer and destination experience. |
| [World Bank — Impact Evaluation in Practice](https://www.worldbank.org/en/programs/sief-trust-fund/publication/impact-evaluation-in-practice) | I used its counterfactual principles to separate attributed from incremental revenue. |
