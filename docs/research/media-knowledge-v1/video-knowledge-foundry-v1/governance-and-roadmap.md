# Governance, cost model and roadmap

## Legal/security heatmap and Deal Breaker Index

DBI values are provisional prioritization assumptions, not measured risk or
legal conclusions.

| Rank | Risk                                          | DBI | Prevent/detect/correct                                          | Owner           |
| ---: | --------------------------------------------- | --: | --------------------------------------------------------------- | --------------- |
|    1 | Missing rights/consent or infringement        | 100 | rights gate / manifest audit / block-takedown                   | Legal/Rights    |
|    2 | Defamation or unsupported material claim      |  98 | evidence/right-of-reply / fact audit / correct-retract          | Editorial/Legal |
|    3 | Untrusted tool/model supply chain             |  95 | immutable source+deny execute / scan+sandbox / revoke-purge     | Security        |
|    4 | Privacy/secret/customer-data exposure         |  94 | minimization+scoped secrets / DLP+audit / contain-notify-delete | Privacy/SRE     |
|    5 | Irreproducible or misleading synthetic output |  90 | lineage+label / deterministic/QC audit / relabel-remove         | Standards/QC    |

Jurisdiction is unknown. No fine, retention term or legal deadline is asserted.
Create country workstreams for privacy, defamation, copyright/moral rights,
consumer/advertising rules, synthetic-media disclosure, labor/voice likeness,
codec patents and records/legal hold, reviewed by qualified counsel.

## Incident, takedown and continuity

Severity determines stop-publish authority, evidence preservation, credential/
connector isolation, stakeholder/legal notification, correction/takedown,
root-cause review and controlled restoration. Legal hold freezes relevant
source, artifact, approval and audit revisions without granting continued
publication. Audit export is hash-manifested, access-controlled and
independently readable.

Backups cover metadata/events, object artifacts, configuration, keys through an
approved recovery mechanism and rebuild instructions for indexes. DR exercises
must restore an end-to-end publication lineage. RPO/RTO and notification times
remain board/legal decisions.

## Five-year conditional model

Currency baseline: **USD**, constant-year basis; all numbers remain variables
because no market, pricing, staffing or volume evidence was supplied.

`Revenue = active_customers × ARPA + usage_revenue`;
`COGS = compute + storage + egress + support + third_party`;
`EBITDA = Revenue - COGS - operating_expense`;
`burn = cash_operating_outflow - cash_inflow`; `runway = cash / monthly_burn`.

| Year | Capability/KPI gate                                            | Capital allocation intent                  | Pivot trigger                                            |
| ---- | -------------------------------------------------------------- | ------------------------------------------ | -------------------------------------------------------- |
| Y1   | evidence coverage, 12 E2E cases, reproducibility, P0 incidents | schemas, corpus, local MVP, legal/security | P0 gate cannot close or rework/cost exceeds approved cap |
| Y2   | pilot adoption, edit time, unit cost, reliability              | hardened adapters, accessibility, support  | no repeatable paid/approved use case                     |
| Y3   | retention, gross margin, throughput, support load              | scale only benchmarked bottlenecks         | downside revenue breaks runway floor                     |
| Y4   | multi-market compliance and partner interoperability           | jurisdiction packs, resilience             | compliance cost exceeds risk-adjusted value              |
| Y5   | EBITDA path, renewal, auditability and migration readiness     | optimize/replace/deprecate                 | lock-in, quality or rights risk exceeds threshold        |

Board model must run base, revenue downside `−30%`, and hardware/electricity/
cloud costs `±20%`, jointly and independently. Replace all variables with dated
finance evidence, include headcount/tax/working capital/capex/depreciation and
report runway and covenant effects. No EBITDA claim is currently possible.

## 90-day MVP backlog

1. Days 0–30: approve charter, jurisdictions/risk owners and artifact schemas;
   acquire/hash source report and canonical sources; freeze rights-cleared
   corpus.
2. Days 31–60: build metadata/object/event skeleton, offline lexical retrieval,
   quarantine separation, claim/citation checks and deterministic stub adapters.
3. Days 61–90: run 12 E2E cases on C1/C2/C3, exercise resume/rollback/takedown/
   restore, measure human rework and submit evidence to the board gate.

## Counter-arguments and stop criteria

| Challenge                       | Control                                            | Stop/pivot criterion                                 |
| ------------------------------- | -------------------------------------------------- | ---------------------------------------------------- |
| Scope is too broad              | vertical slices and P0 families first              | coverage growth does not improve target decisions    |
| Curation is too expensive       | evidence reuse, bounded schemas, active sampling   | marginal verified record exceeds approved value/cost |
| Benchmarks become stale         | expiry/event revalidation and frozen environments  | stale rate breaches board threshold                  |
| RAG cannot replace experts      | expert approval at material/high-risk gates        | calibrated system cannot identify escalation cases   |
| CPU is too slow                 | proxies, queues, optional compliant remote adapter | p95 deadline/cost misses after optimization          |
| Open source carries obligations | exact texts, SBOM and distribution review          | obligations incompatible with business model         |
| Provenance is not factuality    | claim/counter-evidence and human fact-check        | citation correctness fails to predict factuality     |

## Decisions and five final self-checks

Board must approve scope, jurisdictions, risk appetite, quality/SLO thresholds,
rights/consent policy, publication authority, budget/currency assumptions,
staffing, sandbox/cloud egress, data retention/legal hold, RPO/RTO and pivot
caps.

1. **Missing:** source report, authoritative evidence packs, benchmark results,
   legal opinions, customer/market data, prices, staffing and operating SLOs.
2. **Assumed:** ontology boundaries, architecture, weights, tiers, DBI, 90-day
   capacity and five-year sequencing.
3. **Low confidence:** production fit, throughput/cost, revenue, legal scope and
   all quarantined technologies.
4. **Board challenge:** the architecture is coherent but has no measured
   business case, implementation pilot or legal clearance.
5. **Board-ready?** **Conditional only.** Approve evidence/MVP discovery; do not
   approve production or procurement until P0 evidence, benchmark, business case
   and jurisdiction-specific legal opinion exist.
