# Security/license heatmap, backlog and Board gate

## Initial heatmap

Scores are provisional priority hypotheses, not measured likelihood.

| Risk                           | Impact   | Current uncertainty | Prevent/detect/correct                                         | Owner         |
| ------------------------------ | -------- | ------------------- | -------------------------------------------------------------- | ------------- |
| Unauthorized voice/persona     | Critical | High                | consent scope + revocation / identity audit / block-remove     | Privacy/Legal |
| Unknown model/data license     | Critical | High                | quarantine / provenance review / replace                       | Legal/MLOps   |
| Codec patent/distribution duty | High     | High                | separate patent review / build audit / disable-relicense       | Legal         |
| Untrusted plugin/model code    | Critical | High                | no execution / static scan+sandbox gate / purge                | Security      |
| Resource exhaustion/crash      | High     | High                | ceilings/proxy/queue / telemetry+fault tests / fallback-resume | Platform      |
| Color/loudness/timing drift    | High     | High                | versioned profiles / objective+human QC / re-render            | Media QC      |
| 3D interchange loss            | Medium   | High                | feature contract / round-trip fixtures / bake or replace       | 3D lead       |
| Accessibility failure          | High     | High                | timed-text/safe-area policy / review / repair track            | Accessibility |

## P0/P1/P2 experiment backlog

1. **P0:** acquire/hash the missing DOCX and official sources; verify current
   versions, licenses and canonical repositories; approve consent and patent
   policies.
2. **P0:** freeze representative, rights-cleared fixtures and acceptance
   thresholds; provision isolated C1/C2/C3 reference machines.
3. **P0:** static dependency/SBOM/security review; select candidates for
   sandbox.
4. **P1:** execute media/audio/2D/3D/inference benchmark matrices only after
   approval; publish all runs and failures.
5. **P1:** validate presets, timed-text adapters, image-sequence resume, CPU
   fallback and output equivalence.
6. **P2:** cost/energy sensitivity, long-duration soak, localization,
   accessibility and controlled optional-accelerator trials.

## Board decisions required

Workload volumes and quality thresholds; platform delivery profiles; budget,
deadline and electricity region; permitted codec/patent posture; voice consent
and synthetic-media disclosure; source/quote retention; sandbox egress; approved
licenses; data/model procurement; production risk appetite and human sign-off.

## Five final self-checks

1. **What is missing?** The DOCX, archived official sources, pinned component
   records, benchmark fixtures/results, prices and target delivery profiles.
2. **What is assumed?** Taxonomy boundaries, three pipeline shapes, weights,
   hardware tiers, risk priority and proposed schemas.
3. **What has low confidence?** Every named technology claim and production fit
   until official evidence and target-hardware tests are available.
4. **What would a CTO/creative lead challenge?** No measured quality, latency,
   energy, staffing, interoperability or cost evidence yet exists.
5. **Is it Board-ready?** No. It is ready only for approval of the Phase 2
   collection and benchmark plan; no component can be approved for production.
