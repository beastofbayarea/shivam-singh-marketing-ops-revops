# Productizing a senior architect’s integration judgment

Fifteen Oracle, SAP, EDI, SQL, and mainframe systems depended on one senior architect. Routine connection requests waited about four days, 80% of elapsed time was queueing, and reporting was judged only 70% accurate.

During my Microsoft role, I led the redesign across that architect, system owners, developers, security/privacy, data stewards, onboarding, Finance, and platform engineering.

The bottleneck was not simply expertise. It was undocumented policy—region, source/destination permission, identity, encryption, data quality, recovery, and exceptions—combined with repeatable configuration.

## Three weeks of decision archaeology

I walked historical and live requests with the architect. The key question was not “what did you decide?” but “which fact would have changed your decision?”

That uncovered 20 recurring controls across residency, interfaces, identity, privilege, encryption, classification, retention, lineage, quality, recovery, ownership, and exception evidence.

Automating the form before extracting those rules would have automated ignorance.

## Three lanes replaced one queue

**Pass:** required facts complete and source–destination pair allowed. Standard connector and infrastructure templates could provision.

**Correct:** known defect—missing owner, invalid field, unsupported protocol, incomplete retention—returned with a specific repair.

**Review:** novel exception, ambiguous policy, or risk above delegated authority. The expert received relevant facts rather than rebuilding the request from email.

Unknown failed closed.

The architect became policy author and escalation owner. Stable work became self-service; expert capacity moved to genuinely novel risk. An exception ended as either corrected request, time-bound one-off with owner, or reviewed reusable rule change.

## I tested build versus buy on real systems

A commercial suite ran against three representative systems. Older SAP and Oracle interfaces exposed customization and control gaps. The controlled internal option preserved company-specific decision logic and avoided a quoted ~$200,000 annual license.

That is license expense avoided, not total savings. Engineering, hosting, support, and policy maintenance remain internal TCO. Control fit and reusable judgment drove the decision; price was one input.

## Provision-ready had an executable definition

A request needed:

**schema + data owner + classification + permitted region + identity mapping + connector contract + quality checks + recovery owner + policy result + audit event**

Standard APIs/connectors decoupled legacy systems from policy. Infrastructure-as-code made approved configuration reproducible. Governance views exposed policy version, decision, exception, owner, freshness, and reporting quality.

Current Microsoft [self-service platform guidance](https://learn.microsoft.com/en-us/platform-engineering/about/self-service) and [Azure Policy](https://learn.microsoft.com/en-us/azure/governance/policy/overview) reflect the same pattern: governed infrastructure-as-code and policy enforcement enable auditable self-service. They validate the architecture, not private outcomes.

I accepted a three-week delivery dip to build the control plane. Allowing an emergency bypass would have preserved the four-day queue permanently.

## Result and unit repair

| Outcome | Baseline → target → recorded result | Boundary |
|---|---|---|
| Routine latency | ~4 days → minutes → ~15 min for 80% | Request to provision-ready, not necessarily complete source cutover |
| Queue share | 80% elapsed → remove routine waiting → largely removed | Time-and-motion sample; size absent |
| Reporting quality | 70% → high confidence → 98% | Reconciliation/quality definition absent; +28 points / +40% relative |
| Enterprise onboarding | baseline absent → accelerate → 10× faster | Relative result; absolute days absent |
| Commercial value | none attributed → support faster onboarding → $850K reported | Unit corrected from “market share”; booked/contract/retained classification absent |
| License option | ~$200K/year → avoid if build fit held → avoided | Internal TCO excluded |

I owned tacit-rule discovery, policy product, buy/build proof, lane design, exception learning, adoption trade-off, measurement, and stakeholder alignment. The architect retained risk judgment; system owners built adapters; security/privacy approved controls; client teams owned cutover/acceptance.

The asset was not the first 15 integrations. It was a governed way to make the sixteenth without rediscovering institutional policy—and a feedback system in which every new exception improved the shared product instead of recreating gatekeeping.
