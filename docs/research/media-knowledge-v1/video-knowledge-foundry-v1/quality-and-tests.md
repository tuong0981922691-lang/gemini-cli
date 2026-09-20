# Stage gates, technology matrix and end-to-end tests

## Lifecycle

`Research Candidate → Sandboxed → Benchmarked → Approved → Production → Deprecated`

| Gate               | Required evidence                                                                 |
| ------------------ | --------------------------------------------------------------------------------- |
| Research Candidate | canonical lead, owner, problem and quarantine record                              |
| Sandboxed          | immutable snapshot, static license/security/dependency review, approved test plan |
| Benchmarked        | pinned environment, all runs/failures, quality/resource/recovery evidence         |
| Approved           | rights/consent/provenance known, minimum quality met, owner and fallback          |
| Production         | operational SLO, monitoring, incident/rollback/backup drills and support plan     |
| Deprecated         | replacement/migration, evidence retention, publication impact and deadline        |

P0 fail: unknown or unacceptable license, consent, provenance, malicious
behavior, reproducibility or minimum quality. A human override cannot legalize
missing rights or provenance.

## Weighted technology matrix

| Criterion                     | Weight |
| ----------------------------- | -----: |
| Output quality and task fit   |    17% |
| Evidence/provenance           |    13% |
| CPU performance/RAM           |    12% |
| Reliability/recovery          |    10% |
| Interoperability/editability  |    10% |
| Privacy/security              |    10% |
| License/rights/patent clarity |    10% |
| Maintainability/support       |     7% |
| Offline/degraded capability   |     6% |
| Total cost of ownership       |     5% |

Score 1–10 only after P0 gates. Run ±20% sensitivity on all weights and cost
inputs; report rank reversals rather than hiding instability.

## Twelve-archetype corpus

| ID     | Archetype                   | Dominant P0 checks                                             |
| ------ | --------------------------- | -------------------------------------------------------------- |
| E2E-01 | breaking-news update        | freshness, attribution, correction, factuality                 |
| E2E-02 | versioned software tutorial | prerequisite, safe steps, rollback, platform version           |
| E2E-03 | comparative review          | disclosed protocol/conflict, reproducibility                   |
| E2E-04 | concept education           | misconception, transfer, accessibility                         |
| E2E-05 | philosophy reflection       | premise/analogy limits; no metaphor-as-evidence                |
| E2E-06 | structured debate           | steelman, burden, evidence symmetry/false balance              |
| E2E-07 | documentary investigation   | corroboration, right of reply, reconstruction label            |
| E2E-08 | corporate case study        | substantiated claims, sponsor/conflict disclosure              |
| E2E-09 | factual short video         | first-frame promise without factual compression                |
| E2E-10 | visual podcast              | quote/edit ethics, chapters, loudness and captions             |
| E2E-11 | original safe mystery       | clue continuity, original expression, safety                   |
| E2E-12 | 3D technical explainer      | geometry/material lineage, render determinism, visual accuracy |

Across all cases measure factual precision/recall and unsupported claims; script
rubric; voice intelligibility/pronunciation; loudness/true peak; AV/subtitle
sync; visual/entity consistency; accessibility; render repeatability; CPU time,
peak RAM, storage/energy proxy/cost; crashes/retries; and human rework minutes
and revision distance. Gold records and reviewer agreement are versioned.
