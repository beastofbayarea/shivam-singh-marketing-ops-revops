# Shivam Singh — Marketing Operations & Revenue Operations

Revenue operations is the system that turns a market signal into a defensible company action.

A useful system can answer where the signal came from, which identity and commercial state it belongs to, what policy allows the next step, who owns the exception, and how the eventual outcome returns to the model. The five projects here build that system from different directions.

[Resume](./shivam-singh-marketing-ops-revops.pdf) · [LinkedIn](https://www.linkedin.com/in/beastofbayarea) · [shiv-mkt-ops@umich.edu](mailto:shiv-mkt-ops@umich.edu)

## Start with evidence, not an answer engine

[The cloud-AI revenue-intelligence engine](./projects/cloud-ai-revenue-intelligence-engine.md) connected product, CRM, documentation, engineering, pricing, and compliance through one source-linked evidence graph. I split research from commitment: the system could assemble a cited answer and bounded calculation, but customer promises still required an authorized owner. Incorrect answers became source defects and operating feedback rather than hidden model failures.

Seller research fell from 24 minutes to under 30 seconds; security RFP response fell from as much as fourteen days to under 48 hours; and roughly 1,200 monthly hours were recaptured. In a 90-day matched-territory comparison, opportunities closed 28% faster and win rate was 19% higher. The associated $10 million is described as accelerated ARR timing, not automatically net-new revenue.

## Encode judgment so routine work stops waiting

[Revenue-data integration as policy-as-code](./projects/revenue-data-integration-policy-as-code-governance.md) began with a four-day queue dominated by time waiting for one expert. Three weeks of decision archaeology turned regional, identity, security, and exception judgment into twenty executable controls and three work lanes. Standard connectors and infrastructure patterns handled routine requests; ambiguity still reached expert review.

For 80% of requests, provision-ready time fell from roughly four days to about fifteen minutes. Reporting quality moved from 70% to 98%, enterprise onboarding was reported ten times faster, and a roughly $200,000 annual license alternative was avoided. The $850,000 commercial result is preserved as commercial value—not mislabeled market share.

## Make every commercial workflow an explicit state machine

[Influencer operations](./projects/influencer-operations-smart-contract-automation.md) moved from documents and handoffs to an executable lifecycle:

**invited → verified → contracted → delivered → approved → paid → learned**

Identity proof, versioned legal logic, milestone evidence, idempotent payment, exception ownership, and SAP reconciliation reduced the cycle from fourteen days to under 48 hours and expanded capacity tenfold without Operations hiring. Administration cost fell by roughly $500 per contract and annual operating value was reported at $2.2 million. Earlier campaign timing supported a $5 million annualized revenue model, kept separate from booked revenue.

## Reconcile ledgers before claiming growth

[Mobile affiliate cross-app attribution](./projects/mobile-affiliate-cross-app-attribution.md) treated a broken customer route, a missing identity, and a finance dispute as one product-governance problem. Deep linking and server-to-server events joined the internal click, merchant order, affiliate-network record, and finance-eligible transaction. Merchant launch time fell from 45 days to nine, deep-link failures fell 90%, and reconciliation accuracy rose 25%.

The repaired system made roughly $2 million of previously hidden activity visible inside as much as $15 million of total attributed revenue. A four-week, 20%-market holdout compared 2.3% control conversion with 3.1% exposed conversion, preserving the distinction between recovered tracking, attribution, and incrementality.

## Model the relationship, not the lead

[Institutional ABM and investor transparency](./projects/institutional-abm-investor-transparency.md) replaced lead volume with a first-party fiduciary graph: investor, mandate, consultant, vehicle, beneficial relationship, evidence viewed, question asked, and offline outcome. Guided risk transparency became part of the sales product, while China required a distinct access and operating channel.

The system influenced a reported $4.2 billion pipeline, increased the sales-velocity composite by 64%, reduced cost per qualified lead from $850 to $420, and moved China access from more than fifteen seconds and roughly two monthly leads to under two seconds and roughly 25. Pipeline remained a decision stock—not revenue, AUM, or single-function causality.

## Architecture answer — a minimal, governed MarTech stack

**Q: How do you structure a MarTech stack?**

**A:** I work backward from customer and revenue decisions, then use the smallest practical set of systems that can execute, preserve truth, govern movement, and measure outcomes. I separate the stack into five layers and give every important object one authoritative owner.

1. **Execution:** A platform such as Marketo, Braze, Iterable, HubSpot, or SFMC should own campaigns and journeys only where its state machine is useful. It should not become the master for product, contract, or financial truth.
2. **Customer and commercial record:** CRM—often Salesforce or HubSpot—owns accounts, contacts, consented lifecycle state, opportunities, territories, routing, and seller action. Finance systems such as SAP own settlement and recognized financial events.
3. **Data and identity:** A warehouse such as Snowflake or BigQuery, fed through governed event contracts, connects product behavior, campaign exposure, CRM, support, and finance. SQL and Python support analysis and controlled pipelines; identity rules precede segmentation or attribution.
4. **Integration and governance:** Standard connectors or tools such as Workato or Tray handle common movement; lightweight automation is appropriate only for low-consequence tasks. Policy-as-code governs consent, region, identity, security, freshness, retries, reconciliation, and exception ownership.
5. **Measurement and learning:** Attribution, holdouts, lifecycle cohorts, data-quality monitoring, and finance reconciliation determine what changed, what was merely observed, and which source or workflow needs repair.

The projects show why those boundaries matter. In the revenue-data integration program, fifteen Oracle, SAP, EDI, SQL, and mainframe systems depended on one architect. I encoded twenty recurring decisions and created routine, conditional, and exception lanes. For 80% of requests, provision-ready time fell from roughly four days to fifteen minutes and reporting quality rose from 70% to 98%, while a $200,000 annual license alternative was avoided.

In the cloud-AI revenue-intelligence engine, an evidence graph connected product, CRM, documentation, engineering, pricing, and compliance. Research could be automated; customer commitments still required an authorized owner. Seller research fell from 24 minutes to under 30 seconds and security RFP response from as much as fourteen days to under 48 hours. In mobile affiliate attribution, the internal click, merchant order, network record, and finance-eligible transaction remained separate ledgers; merchant launch time fell from 45 days to nine and a 20%-market holdout separated attribution from incrementality.

My operating rule is that adding a tool must remove a real constraint without creating a second source of truth. Before scale, I pilot mappings, consent, routing, failure recovery, and reconciliation. The stack is successful when teams make faster decisions and Finance can still explain the outcome—not when the architecture diagram contains more logos.

## The revenue graph I build

Across these projects, the underlying flow is:

**source fact → governed identity → lifecycle state → permitted action → owner/exception → financial outcome → learning**

I own the definitions, data contracts, routing and service policies, attribution boundaries, automation controls, operating cadences, and executive measurement that make that flow dependable. Marketing, Sales, Product, Finance, Legal, Security, and Operations still own their decisions; RevOps makes those decisions legible and connected.
