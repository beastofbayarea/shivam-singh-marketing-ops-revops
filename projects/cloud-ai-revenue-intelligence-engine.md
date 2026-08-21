# Closing the gap between a cloud product change and a customer decision

The revenue system was losing two races.

A product change could take 72 hours to reach documentation. Sellers searched up to seven systems for 24 minutes to assemble an answer; a security questionnaire could sit open for two weeks.

A new user, meanwhile, showed configuration trouble within seven minutes. By the time support or sales responded, intent had expired.

During my AWS role, I led the revenue-intelligence program across sales, solution architects, product/engineering, security/compliance, documentation, pricing, support, data, and product users. The requirement was not “deploy a chatbot.” It was to produce an authorized answer or intervention inside the decision window—and make every failure repair the source that caused it.

## One evidence graph connected six signal systems

I joined:

- product usage and friction;
- CRM account/opportunity/territory/stage;
- documentation and release versions;
- engineering issues and defects;
- pricing APIs and approved commercial rules;
- security/compliance evidence.

Every entity carried product, version, effective date, source owner, permission, and account context. Generated prose was a view over evidence, never the evidence itself.

That distinction made stale documentation, contradictory definitions, missing approvals, permission failure, retrieval error, and model error separately measurable.

Amazon Bedrock [retrieval](https://docs.aws.amazon.com/bedrock/latest/userguide/kb-how-retrieval.html) illustrates source-chunk citation. AWS [ACL guidance](https://docs.aws.amazon.com/bedrock/latest/userguide/kb-managed-ds-custom-acl.html) also warns that filtering is not authentication. The application had to authenticate the user and pass verified identity; metadata did not become a security perimeter.

## I split research from commitment

### Research shield

Users received only entitled evidence, with citations, version/effective date, confidence, and conflicts. A security response below the approval threshold entered named review instead of becoming confident prose.

The retained threshold was 90% confidence for an unqualified response. Confidence routed work; it did not prove correctness. The recorded security-answer error rate was 0.08%—equivalent to eight per 10,000 if the denominator was reviewed answers—but sample size and error taxonomy are absent.

### Action builder

Approved tools could query pricing, populate a proposal shell, or run technical calculations. Deterministic code handled prices/capacity; templates constrained commitments; permissions governed tools; people approved wherever the underlying process required it.

This prevented a good answer from silently becoming a price, architecture promise, or compliance representation.

## Bad answers improved the operating system

A user could classify output as stale, unsupported, contradictory, or incomplete. The system opened an issue against the document, API, or control owner with the question, retrieved evidence, output, and reason.

The internal data-health index improved 60% in one quarter. That was a composite relative change, not “60% more accurate data.” The compounding value came from source repair: fixing an effective date or contradiction improved every later retrieval, unlike a prompt patch that fixed one phrasing.

## Minute seven became a measured intervention

Repeated refreshes or nine clicks on the same setup path indicated possible struggle. The product offered task-specific guidance or code, not generic chat.

The intervention had to be observable, relevant to the current task, dismissible, frequency-capped, and compared with a non-intervened cohort. Product behavior became a revenue signal without assuming every unusual click meant buying intent.

## Revenue and productivity account

| Operating question | Baseline → service target → result | Measurement |
|---|---|---|
| Seller research | 24 min → inside customer interaction → <30 sec | Request to cited answer; 23.5 min saved |
| Security RFP | up to 14 days → procurement cadence → <48 h | Open to approved response; complexity mix not retained |
| Monthly capacity | ~1,200 h consumed → return routine time → ~1,200 h recaptured | At 23.5 min/question implies ~3,064 monthly questions |
| Annualized productivity | manual cost → monetize capacity → ~$1.4M | 14,400 h/year implies ~$97/h; model, not cash saving |
| Data health | index 100 → fewer source defects → 160 | Composite +60%; weights absent |
| Commercial timing | matched territory control → faster governed response → closes 28% faster, win rate 19% higher | 90-day comparison; baselines and relative-vs-point definition absent |
| Revenue timing | none attached to interventions → identify pull-forward → $10M accelerated ARR | Logged intervention/opportunity timing; not necessarily net-new ARR |

Territory matching leaves selection and spillover risk. “Accelerated ARR” is timing stock and cannot be booked again as newly created demand.

I owned the ontology, evidence graph, research/action split, source-repair loop, behavioral policy, adoption, and measurement. Source owners approved facts; security/compliance retained authority; product instrumented use; sales owned decisions; engineers implemented the platform.

The strategic outcome was revenue speed as an operating property: answers arrived while customers were deciding, interventions arrived while users were struggling, and failures flowed back to the owner capable of preventing recurrence.
