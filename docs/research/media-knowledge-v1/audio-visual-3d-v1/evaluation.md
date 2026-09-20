# Evaluation matrix, shortlist gate and BOM

## Weighted technology matrix

Score 1–10 only after evidence gates pass. Initial weights are a design
assumption and sum to 100.

| Criterion                  | Weight |
| -------------------------- | -----: |
| Quality                    |    16% |
| CPU speed                  |    14% |
| RAM efficiency             |     8% |
| Stability                  |    10% |
| Batch/headless             |     7% |
| Editability                |     7% |
| Interoperability           |     8% |
| License/patent clarity     |     8% |
| Maintenance                |     6% |
| Security                   |     6% |
| Community/support evidence |     4% |
| Total cost of ownership    |     6% |

Run sensitivity with hardware price, electricity and cloud cost independently
and jointly at −20%/base/+20%; report score/rank changes and any reversed
Build/Buy/Integrate decision. Missing license, provenance, consent, factuality
or safety yields no aggregate score.

## Tier shortlist policy

| Tier             | Eligible component class                                | Production decision now |
| ---------------- | ------------------------------------------------------- | ----------------------- |
| C1 4C/8T–16 GB   | deterministic media/audio/2D; only bounded validated ML | None—benchmark absent   |
| C2 8C/16T–32 GB  | C1 plus heavier batch and optional acceleration         | None—benchmark absent   |
| C3 16C/32T–64 GB | 3D/image sequence, parallel encode and approved ML      | None—benchmark absent   |

No named technology is shortlisted for production in Phase 1. A shortlist is a
result of static verification plus the benchmark suite, not reputation, stars or
marketing demonstrations.

## Provisional software/hardware BOM schema

- Hardware: exact CPU, RAM topology, storage capacity/endurance, optional GPU/
  NPU and VRAM, audio interface/microphone/monitoring, display/color device,
  network/UPS, measured power and driver/firmware versions.
- Software: OS, media backend/build flags, audio/graphics/3D tools, runtimes/
  execution providers, models/weights, fonts/assets/plugins,
  queue/observability, exact versions/hashes, seats/cost, license and support
  expiry.
- Capacity: source, proxy, cache, image sequence, intermediate, output, backup
  and growth factor are separate line items.

Actual SKUs, prices and production BOM remain `CHƯA BIẾT` pending geography,
budget, workload volume, benchmark and procurement/security constraints.
