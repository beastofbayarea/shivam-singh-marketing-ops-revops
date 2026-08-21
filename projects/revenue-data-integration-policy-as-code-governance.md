# Turning Revenue Data Integration into Governed Self-Service

I led this work during my [Microsoft experience from January 2020 to August 2022](https://github.com/beastofbayarea/shivam-singh-marketing-ops-revops/blob/main/shivam-singh-marketing-ops-revops.pdf).

Fifteen Oracle, SAP, EDI, SQL, and mainframe systems fed customer and revenue operations. Every new connection depended on one senior architect's undocumented judgment, so a routine request waited about four days. Point-to-point links also left reporting stale and only 70% accurate.

I did not try to automate the architect away. I made the architect's decision process explicit, testable, and reusable.

## I shadowed the exception logic

The visible task was connecting systems; the scarce capability was knowing when a connection violated a regional, identity, security, data-quality, or operating rule.

I worked through previous requests with the architect and translated the recurring decisions into a 20-point policy set. A request that satisfied the rules could move toward provisioning. A failure or ambiguous answer went to expert review with the relevant evidence attached.

Every reviewed exception ended in one of three outcomes: correct the request, document a one-time decision, or add a reusable policy. The queue therefore became a learning system rather than an endless collection of special cases.

## A three-system MVP tested build versus buy

I used three representative systems to validate whether a commercial platform could handle the legacy constraints. The experiment exposed incompatibilities in older interfaces and gave us a more realistic view of customization, license cost, and control.

I chose a controlled internal platform with standard connector and identity contracts. The decision avoided roughly $200,000 in annual licensing cost, but cost alone was not the deciding factor; the internal pattern could encode the institution's actual exception logic.

## Policy became executable release evidence

NIST's Privacy Framework influenced the data-processing and privacy-risk design. NIST SP 800-53 Revision 5 provided the broader control catalogue across access, audit, configuration, contingency, privacy, and accountability.

The platform evaluated policy before provisioning, recorded the decision, and exposed data quality, exception ownership, and reporting reliability on a governance dashboard. It failed closed: an unrecognized condition could delay a connection, but it could not silently bypass review.

I accepted a three-week dip in delivery while the first reusable control plane was built. That temporary cost removed a much larger recurring queue.

## The operating result

- Eighty percent of requests became provision-ready in about 15 minutes instead of four days.
- Reporting accuracy increased from 70% to 98%.
- Enterprise client onboarding became ten times faster.
- The platform captured $850,000 in new market share.
- The internal approach avoided approximately $200,000 in annual recurring license cost.

## Why the ownership model worked

The senior architect became the policy author and escalation owner. Delivery teams could execute routine work, while expert attention moved to novel risk and rule evolution. That preserved institutional judgment and reduced dependence on one person's availability.

My general rule is to automate the stable decision, not the unexplained expert. Once the boundary and evidence are visible, self-service and governance can improve together.

## External foundations

These sources supplied the primary privacy and control methodology. My resume establishes employment chronology only.

| Source | How I applied it |
|---|---|
| [NIST — Privacy Framework 1.0 (2020)](https://www.nist.gov/privacy-framework/privacy-framework) | I used its data-processing and privacy-risk lifecycle to define policy and governance requirements. |
| [NIST — SP 800-53 Revision 5 (2020)](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final) | I used its access, audit, configuration, contingency, privacy, and accountability controls to structure executable gates and evidence. |
