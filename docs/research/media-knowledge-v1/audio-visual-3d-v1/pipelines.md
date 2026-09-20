# CPU-oriented pipeline designs

## Shared invariant

Every job pins source hashes, software/config versions, color/timebase, random
seeds where available, resource ceiling and output manifest. Deterministic and
classical stages are preferred for reproducibility; ML stages require model
provenance, an accuracy gate and a non-ML or manual fallback.

## Pipeline A — CPU-only commodity

`ingest/probe → proxy/audio conform → classical edit/2D/audio filters → optional small validated CPU model → image/audio intermediates → CPU encode/mux → QC`

- Target tier: 4C/8T, 16 GB; actual limits determined by benchmark, not assumed.
- Deterministic/classical: decode, resample, trim, mix, typography, simple
  compositing, color transforms, subtitle render, image sequence and encode.
- ML: opt-in, bounded by RAM/RTF/quality; unavailable model falls back to
  classical/manual processing rather than silently changing quality.
- Preview: low-resolution intraframe proxy, reduced effects, cached waveforms,
  draft render samples. Storage budget includes source + proxy + cache + image
  sequence + two output copies.
- Parallelism: conservative frame/tile queue with measured memory per worker;
  backpressure before swapping. Failed frames retry individually.

## Pipeline B — CPU-first with optional acceleration

`Pipeline A → capability probe → policy-approved GPU/NPU execution provider for eligible nodes → output-equivalence QC → CPU fallback`

- Target tier: 8C/16T, 32 GB plus optional accelerator/VRAM recorded at runtime.
- CPU remains the correctness baseline. Acceleration cannot change color,
  timestamp, safety or rights behavior without a separately approved profile.
- Cache keys include device/provider, precision, model, operator set and driver.
- Preview may use accelerated inference/render, but final fallback must be
  schedulable on CPU or explicitly declare “no CPU production path.”

## Pipeline C — professional workstation/farm

`validated assets → distributed scene/audio packages → frame/chunk queue → CPU/GPU workers → checksummed image/audio outputs → compositor → sequencer → mezzanine → delivery encodes/QC`

- Target tier: 16C/32T, 64 GB minimum study tier; GPU and farm are optional
  profiles, never hidden assumptions.
- Render to an image sequence with atomic frame manifests so a worker can resume
  or replace failed frames without losing a full program. Direct-to-video long
  render remains quarantined until failure/recovery tests justify it.
- Per-frame seed, asset hash, scene version, renderer and device are logged.
  Queue leases, retry count, deterministic merge and orphan cleanup are
  required.

The supplied Blender background/thread/device and compositor→sequencer claims
are collection leads, not verified operational guidance until pinned official
manual pages are archived. `[CHƯA BIẾT; AV-LEAD-BLENDER-CLI]`

## CPU inference strategy

1. Export with pinned framework/opset and retain the original model hash.
2. Validate structure, operator coverage and numerical parity on a frozen set.
3. Establish unoptimized FP32 CPU baseline before graph optimization.
4. Tune intra/inter-op threading, affinity and batching independently per tier.
5. Evaluate static/dynamic INT8 and, only where supported and meaningful, INT4.
6. Reject optimization when accuracy, safety, latency tail or memory gate fails.
7. Quarantine unsupported/custom operators, untraceable weights or license/data
   uncertainty; never “fix” by fetching runtime code.

ONNX Runtime Execution Provider/CPU-default and the PyTorch torchao/PT2E
transition are `CAN_XAC_MINH` leads. Pinning framework, runtime, opset and API
is mandatory regardless of their verification outcome.
`[CHƯA BIẾT; AV-LEAD-ONNXRUNTIME, AV-LEAD-PYTORCH-QUANT]`
