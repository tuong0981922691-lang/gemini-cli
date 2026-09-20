# Taxonomy công nghệ truyền thông v1

Mỗi nút lá là một năng lực có thể tạo một hoặc nhiều Knowledge Record; tên sản
phẩm không thay thế taxonomy. Các chiều cắt ngang bắt buộc gồm provenance,
version, platform/hardware, license, patent, privacy, security, quality,
performance, maturity, cost và operating mode (`local`, `hybrid`, `cloud`).

## 1. Media foundation

- **Container và pipeline:** probe, demux, decode, filter, encode, mux,
  transcode; trim; concatenate; stream/seek; batch và render queue.
- **Timeline:** track/layer, clip, transition, keyframe, proxy, cache, preview,
  conform, relink và export.
- **Video processing:** resize/crop, deinterlace, denoise, stabilization,
  tracking, optical flow, compositing, effects và quality control.
- **Color và geometry:** color space/transfer/matrix/range, ICC, LUT, HDR
  metadata/tone mapping, bit depth/chroma, pixel/sample aspect ratio,
  resolution/orientation và CFR/VFR/time base.
- **Codec families:** H.264/AVC, H.265/HEVC, AV1, VP9, ProRes và lossless/
  mezzanine codecs. Theo dõi riêng implementation license và patent obligation.
- **Framework/API:** FFmpeg/libav\*, GStreamer, OpenCV, VapourSynth, Media
  Foundation; tách CLI, library, binding và hardware acceleration backend.
- **Delivery:** subtitles/captions, metadata, thumbnails, HLS/DASH, packaging,
  encryption/DRM interface, validation và archival.

## 2. Image

- Generate; edit; inpaint/outpaint; guided/control generation.
- Detection, segmentation, matting, background/object removal và compositing.
- OCR/document layout; super-resolution; restoration; denoise; deblur; color
  correction và quality assessment.
- Character/object/style identity consistency và reference conditioning.
- Raster/vector/RAW formats, alpha, ICC, EXIF/XMP, C2PA/Content Credentials.

## 3. Audio, speech và language

- Capture/resample/channel mapping; denoise, dereverb, source separation,
  enhancement, loudness, dynamics, mixing và mastering.
- ASR, TTS, speech translation, VAD, diarization, alignment, punctuation,
  subtitle timing và domain lexicon.
- Speaker/voice consent, biometric/privacy handling và anti-impersonation.
- Metrics: WER/CER, DER, alignment error, intelligibility, MOS methodology,
  LUFS/true peak và real-time factor.

## 4. Generative and understanding AI

- Text-to-video, image-to-video, video-to-video, interpolation và extension.
- Motion/camera/keyframe control; spatial and temporal consistency; identity
  preservation; editability và provenance/watermarking.
- Shot/scene/boundary detection, classification, tracking, captioning, search,
  question answering, moderation và summarization.
- Model lifecycle: research, experimental, production candidate, production;
  architecture, weights, tokenizer/encoder, adapter, quantization và runtime.
- Resource envelope: CPU/GPU/NPU, RAM/VRAM/storage, precision, throughput,
  latency, input/output limits and quality/performance curve.

## 5. Agents, automation và integrations

- Roles: orchestrator, research, media, video and Microsoft 365 agents.
- Protocol/surface: tool calling, MCP client/server, plugin, extension, skill,
  API, webhook, queue và scheduled workflow.
- State: session, durable memory, artifact store, knowledge retrieval and human
  approval checkpoints.
- Controls: least privilege, capability declaration, input/output validation,
  credential isolation, network/filesystem/subprocess boundary and audit log.
- Reliability: tracing, metrics, evaluation, guardrails, idempotency, timeout,
  retry, compensation, checkpoint/resume and failure recovery.
- Placement: deterministic/local-sensitive work versus elastic/cloud work;
  offline and degraded-mode behavior.

## 6. Knowledge platform

- Domain taxonomy/ontology, entity/relationship model and controlled vocabulary.
- Ingest, normalization, claim extraction, chunking and passage provenance.
- Embedding, lexical/full-text, hybrid retrieval, reranking, vector database,
  knowledge graph and grounded generation.
- Deduplication, contradiction detection, blacklist, quarantine, promotion,
  expiry/revalidation and immutable evidence store.
- Fixed evaluation: corpus snapshot, question set, relevance judgments,
  precision/recall/nDCG, citation correctness and answer faithfulness.

## 7. Compute and deployment

- OS/runtime: Windows 11, Windows ML, ONNX Runtime and execution providers;
  container/VM/native packaging.
- Vendors/backends: NVIDIA/CUDA, AMD/DirectML or supported backend,
  Intel/OpenVINO and Qualcomm-supported NPU runtime.
- Hardware tiers: minimum, recommended and professional; CPU-only fallback;
  memory/storage bandwidth; driver/runtime compatibility.
- Modes: offline, local-network, hybrid and cloud; update, rollback, backup,
  observability, SLO/capacity and cost controls.

## 8. Governance, legal and security

- Separate licenses for source, binary, model weights, training/evaluation data,
  documentation, plugin and every direct/transitive dependency.
- Attribution, notice, source-offer, copyleft/linking, redistribution,
  commercial-use and field-of-use obligations.
- Codec/algorithm patents, pools, territories, expiry and distribution/use case.
- Privacy, personal/biometric data, retention, deletion, residency and consent.
- Supply chain: canonical owner, signed tag/commit, hash, SBOM, provenance,
  secret/dependency/code scanning, advisories and coordinated disclosure.
- Content authenticity: C2PA/Content Credentials, disclosure, moderation and
  copyright/training-data evidence.

## 9. Business and operations

- Build/buy/integrate decision; product fit; API stability; lock-in; migration.
- Pricing, quota, egress, license support, maintenance health and vendor SLA.
- Incident response, disaster recovery, supportability, accessibility,
  localization and lifecycle/end-of-support.
