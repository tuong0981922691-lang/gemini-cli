# CPU benchmark suite v1

**Status: protocol only; no benchmark was executed.** Results must never be
filled from vendor marketing or a different tier.

## Hardware tiers and run matrix

| Tier | CPU/RAM baseline | Accelerator                        | Required resolutions           | FPS      |
| ---- | ---------------- | ---------------------------------- | ------------------------------ | -------- |
| C1   | 4C/8T, 16 GB     | none                               | 720p, 1080p, 4K where feasible | 24/30/60 |
| C2   | 8C/16T, 32 GB    | none; optional profile separate    | 720p, 1080p, 4K                | 24/30/60 |
| C3   | 16C/32T, 64 GB   | none; workstation profile separate | 720p, 1080p, 4K                | 24/30/60 |

Record exact CPU model/microcode, ISA, core policy, RAM channels/speed, storage,
OS/build, power mode, thermals, background services and tool/model hashes.

## Workloads

- Media: probe, decode, scale/color, representative filter graph, subtitle burn,
  encode and mux; SDR/HDR cases remain separate.
- Audio/speech: repair, mix/master, alignment and approved inference using fixed
  duration/language/noise strata.
- 2D: raster/vector composition, typography, alpha and motion-graphics frames.
- 3D: fixed scene classes (geometry-, texture-, shading-, simulation-bound) to
  checksummed image sequences, then compositor/sequencer and video encoding.
- Inference: FP32 baseline, optimized graph and each quantized candidate on the
  same frozen accuracy set.

## Measurements

Wall and CPU time, median/p95/p99 milliseconds per frame, frames/s, RTF, peak
and steady RSS, bytes read/written, cache size, cold/warm start, quality metric
with reference and configuration, task-specific accuracy, failed frames,
retries, crashes, and output-hash repeatability. Energy proxy is package energy
when a documented counter is available; otherwise wall-time × externally
measured average power, clearly labeled as a proxy.

## Reproducibility and pass gates

Use at least one warm-up and five measured repetitions; randomize test order;
report every run and confidence intervals rather than only the best result.
Thermal throttling, swap, fallback provider and quality-setting drift invalidate
a run. A production candidate must complete the declared matrix without crash,
stay inside tier RAM/storage limits, meet predeclared quality/latency thresholds
and reproduce its output within the workload’s declared tolerance.

Threshold values remain `CHƯA BIẾT` until business latency, target quality,
electricity assumptions and pilot distributions are approved.
