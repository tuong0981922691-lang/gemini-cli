# CPU-first scheduler and capacity model

## Scheduling design

At worker registration, detect CPU topology/ISA, logical and physical cores,
NUMA nodes where exposed, RAM, storage, approved accelerator and software
capabilities. Detection never implies benchmark fitness.

Queues reserve RAM and scratch space before threads. Per-class thread pools
separate latency-sensitive preview, audio, decode/encode, inference and render
work. Backpressure stops admission before swap or storage exhaustion. Cache keys
include every input/config/tool/model/device hash and are invalidated by
compatibility rules, not filenames.

Frame, tile, scene and audio-chunk parallelism use measured working-set and
dependency graphs. Long 3D jobs emit atomic image-sequence frames and manifests;
retries replace individual failed frames. Low-resolution/proxy preview uses a
separate quality profile and cannot be silently published. Overnight queues have
deadline, energy/cost cap, pause/resume and morning failure summary.

Remote GPU is an optional adapter with explicit transfer, privacy, license,
residency, cost and output-equivalence gates. Failure returns to a checkpoint or
declares “no compliant fallback”; it never downgrades silently.

## Capacity equations

For workload `w` on tier `t`:

- `service_time = frames × measured_seconds_per_frame + cold_start + fixed_io`.
- `safe_workers = min(physical_core_limit, floor(available_RAM / p95_RAM_w), scratch_IO_limit)`.
- `daily_capacity = available_seconds × utilization_gate × safe_workers / p95_service_time`.
- `deadline_slack = deadline - queue_wait_p95 - service_time_p95 - QC/retry`.

Use measured p95 values and arrival distributions; averages cannot size a
production queue. Capacity includes retries, cache misses, QC and publication
packaging.

## Three study configurations

| Tier | Baseline       | Intended study                                            | Unproven limitation                     |
| ---- | -------------- | --------------------------------------------------------- | --------------------------------------- |
| C1   | 4C/8T, 16 GB   | offline research, script, proxy, light 2D/audio/media     | 4K/ML/3D deadline and RAM fitness       |
| C2   | 8C/16T, 32 GB  | concurrent edit/encode, bounded ML, richer previews       | sustained 4K/3D and energy              |
| C3   | 16C/32T, 64 GB | image-sequence 3D, parallel media and larger local models | production throughput without benchmark |

No throughput number is supplied because Lệnh 2 contains a protocol, not
results. A capacity plan is blocked until representative fixtures and target
machines produce reproducible measurements.
