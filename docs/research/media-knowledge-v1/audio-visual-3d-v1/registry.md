# Component registry and evidence plan

## Record contract

Each component record must include Knowledge ID, capability, architecture role,
canonical URL/owner, default branch and full commit, release, access date,
language/platform, CPU/GPU/NPU/RAM/VRAM/storage, maintenance, separate
code/model/ data/plugin/dependency licenses, attribution, patents,
dependencies/SBOM, security risks, benchmark protocol/results, maturity, scores,
label and revalidation date. Unknown P0 values prevent aggregate scoring.

## Candidate source leads

These URLs are **unverified collection targets**, not evidence anchors, because
network collection was unavailable on `2026-09-20`.

| Evidence ID           | Candidate authority         | URL                                                                         | Claim to verify                                             | Status       |
| --------------------- | --------------------------- | --------------------------------------------------------------------------- | ----------------------------------------------------------- | ------------ |
| AV-LEAD-EBU-R128      | European Broadcasting Union | https://tech.ebu.ch/publications/r128                                       | Current loudness/LRA/true-peak requirements and version     | CAN_XAC_MINH |
| AV-LEAD-BLENDER-CLI   | Blender Foundation          | https://docs.blender.org/manual/en/latest/advanced/command_line/render.html | Background render, threads, device and long-render workflow | CAN_XAC_MINH |
| AV-LEAD-OPENUSD       | Alliance for OpenUSD/Pixar  | https://openusd.org/release/                                                | Scene composition scope and pinned specification            | CAN_XAC_MINH |
| AV-LEAD-ONNXRUNTIME   | Microsoft ONNX Runtime      | https://onnxruntime.ai/docs/execution-providers/                            | EP abstraction, CPU provider and version behavior           | CAN_XAC_MINH |
| AV-LEAD-PYTORCH-QUANT | PyTorch                     | https://pytorch.org/docs/stable/quantization.html                           | Current torchao/PT2E migration guidance                     | CAN_XAC_MINH |
| AV-LEAD-FFMPEG        | FFmpeg project              | https://ffmpeg.org/documentation.html                                       | Component/API coverage and build/license evidence           | CAN_XAC_MINH |
| AV-LEAD-WEBVTT        | W3C                         | https://www.w3.org/TR/webvtt1/                                              | Cue kinds, timing and conformance                           | CAN_XAC_MINH |
| AV-LEAD-TTML          | W3C                         | https://www.w3.org/TR/ttml2/                                                | Timed-text structure, styling and conformance               | CAN_XAC_MINH |

## Static collection gate

Archive the exact page/spec/repository revision, final URL, retrieved timestamp,
content hash, title/version/date and excerpt locator. For repositories, use a
read-only full-history mirror or a source manifest with full SHA and collection
time. Inspect only README, LICENSE/NOTICE, security policy, changelog,
manifests, lockfiles and workflows before approval. Do not resolve/install
dependencies or download binaries, weights, datasets, plugins or release assets.

## Dependency and license gate

Build the direct/transitive graph from pinned manifests and lockfiles without
installation. Record optional/runtime/build dependencies separately. Exact
license texts beat badges or README claims; codec patent exposure is a distinct
legal review and must not be inferred from the software license.
