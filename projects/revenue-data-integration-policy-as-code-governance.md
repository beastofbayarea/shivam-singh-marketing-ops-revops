# Productizing a Senior Architect's Integration Judgment

I led a revenue-data integration redesign at Microsoft. I had identified that client and reporting teams were waiting on one senior architect because the rules for connecting old systems existed in his judgment rather than in a shared product. I worked with that architect, system owners, developers, security and privacy teams, data stewards, client-onboarding teams, Finance, and platform engineering.

Fifteen Oracle, SAP, EDI, SQL, and mainframe systems fed the operation. A routine connection spent about four days in the queue, reporting was judged only 70% accurate, and point-to-point scripts made each new request another dependency on the same person.

## The queue was mostly waiting, not engineering

A time-and-motion review showed that 80% of elapsed time was queueing. The architect was doing two jobs at once:

1. applying undocumented policy—region, source/destination permission, identity, encryption, data quality, and exception judgment;
2. running or approving configuration that could have been standardized.

Replacing him with a form would have automated ignorance. I spent three weeks walking prior and live requests with him, asking not only “what did you decide?” but “what fact would have changed the decision?”

## Twenty rules created three service lanes

I converted the recurring judgment into a 20-point policy engine covering residency, approved interfaces, identity, privilege, encryption, data class, retention, lineage, quality, recovery, ownership, and exception evidence.

Every request entered one of three lanes:

**Pass:** all required facts were present and policy allowed the source–destination pair. Standard infrastructure and connector templates could provision the environment.

**Correct:** a known defect—missing owner, invalid field, unsupported protocol, incomplete retention instruction—returned to the requester with a specific fix.

**Review:** policy was ambiguous, the requested exception was novel, or the risk exceeded delegated authority. The architect received the relevant facts instead of reconstructing the request from email.

The system failed closed. Unknown did not mean allowed.

## A three-system experiment prevented a superficial buy decision

I evaluated a commercial integration suite against three representative systems rather than comparing feature lists. Older SAP and Oracle interfaces exposed customization and control gaps. The controlled internal option avoided about $200,000 in recurring annual license fees and preserved the company-specific decision logic.

That is **license cost avoided**, not total savings. The internal platform had engineering, support, hosting, and policy-maintenance costs that the retained record does not quantify. My build decision rested on control fit and reusable institutional logic; the license figure was one input, not a complete TCO comparison.

## The executable release record

A request could not become provision-ready without:

`request schema + data owner + classification + permitted region + identity mapping + connector contract + quality checks + recovery owner + policy result + audit event`

Standard connectors and APIs decoupled the legacy system from the policy layer. Infrastructure-as-code made the approved configuration reproducible. The governance view showed policy version, pass/fail, exemption, owner, freshness, and reporting quality.

Microsoft's platform-engineering guidance now describes the same general pattern: infrastructure-as-code plus delivery workflows enables auditable self-service, and policy-as-code can use tools such as Azure Policy or Open Policy Agent. Azure Policy itself is designed to enforce standards and surface compliance at scale. Those public sources validate the architecture pattern, not the private result.

## Exceptions made the platform smarter

Expert review ended in one of three durable outputs:

- correct the request without changing policy;
- grant and time-bound a one-off exception with an owner;
- add or revise a reusable rule after review.

The architect became policy author and escalation owner. Delivery teams gained speed on stable work; expert capacity moved toward novel risk. I accepted a three-week delivery dip while we built the first control plane because one emergency override would have preserved the four-day queue forever.

## Results, with units repaired

| Outcome | Baseline | Result | Measurement boundary |
|---|---:|---:|---|
| routine request latency | ~4 elapsed days | ~15 minutes for 80% | request received to **provision-ready**; not necessarily full source cutover |
| queue share | 80% of elapsed time | routine queue largely removed | time-and-motion sampling; sample size not retained |
| reporting accuracy | 70% | 98% | reported reconciliation/quality measure; exact field and tolerance definition not retained |
| enterprise onboarding speed | baseline not retained | 10× faster | reported relative change; cannot reconstruct absolute days |
| commercial value | none attributed to platform | $850K reported | dollar-denominated new business/value; not “market share,” which is a percentage |
| recurring license expense | ~$200K/year alternative | avoided | quoted commercial license cost; internal TCO excluded |

The 70% → 98% accuracy change is +28 percentage points, or 40% relative improvement. Without the denominator and reconciliation rule, I would not describe it as record-level truth across all 15 systems.

Likewise, $850,000 cannot literally be “new market share.” I corrected the unit to reported commercial value associated with faster onboarding. The source does not preserve whether that means booked revenue, contract value, or retained value, so it should not be made more precise than the evidence.

## The real asset

The project did not merely connect 15 systems. It created a governed way to make the sixteenth connection without rediscovering policy, and a mechanism for novel cases to improve the policy rather than recreate gatekeeping.

I owned discovery of the tacit rules, the policy product, build-versus-buy experiment, operating lanes, adoption trade-off, measurement, and stakeholder alignment. The architect retained risk judgment and policy authorship; system owners built adapters; Security and Privacy approved controls; client teams owned cutover and business acceptance.

For current architectural grounding, see [Microsoft's self-service platform guidance](https://learn.microsoft.com/en-us/platform-engineering/about/self-service), [Azure Policy overview](https://learn.microsoft.com/en-us/azure/governance/policy/overview), [NIST Privacy Framework](https://www.nist.gov/privacy-framework/privacy-framework), and [NIST SP 800-53 Revision 5](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final).

