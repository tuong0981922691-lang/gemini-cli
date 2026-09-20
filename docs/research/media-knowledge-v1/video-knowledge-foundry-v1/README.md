# Video Knowledge Foundry v1

## Board memo

**Decision status: CONDITIONAL — NOT BOARD-READY.** This package integrates the
versioned designs from Script Intelligence Mine v2 and Audio–Visual–3D
Technology Mine v1 into a vendor-neutral target architecture. Those inputs are
treated as unverified design records, not facts or production endorsements.
`[SUY LUẬN; evidence: VKF-INPUT-SIM-V2, VKF-INPUT-AV3D-V1; confidence: medium]`

The recommended decision is to authorize a 90-day evidence-and-prototype phase,
not production procurement. The phase should freeze schemas, acquire canonical
sources, populate a rights-cleared test corpus, validate offline/degraded paths
and measure CPU tiers. No quarantined repository or model is an architecture
anchor. `[GIẢ ĐỊNH; evidence: VKF-REQ-20260920; confidence: medium]`

The source report **“BÁO CÁO KIỂM ĐỊNH TRI THỨC.docx”**, official source packs,
benchmarks, business data and legal opinions remain unavailable. Therefore no
technology, five-year return, EBITDA, jurisdictional penalty or production
readiness is asserted.
`[SỰ THẬT ĐÃ XÁC MINH for workspace availability; evidence: VKF-WORKSPACE-SCAN-20260920; confidence: high]`

## Deliverables

- [Unified domain ontology and registry contract](ontology-and-registry.md)
- [Ingest, evidence and retrieval design](knowledge-pipeline.md)
- [Target architecture, dataflow and deployment](architecture.md)
- [Agent and artifact contracts](agents-and-artifacts.md)
- [CPU scheduler and capacity model](scheduler-and-capacity.md)
- [Stage gates, technology matrix and end-to-end corpus](quality-and-tests.md)
- [Risk, cost, roadmap and board decisions](governance-and-roadmap.md)

## Non-negotiable gates

Every artifact has a content hash and lineage. Every material factual output has
claim-level citations and counter-evidence retrieval. License, consent,
provenance, malicious behavior, reproducibility and minimum quality are P0
fail-fast gates. Human approval follows risk, not agent confidence.

## Input revisions

| Evidence ID              | Input                             | Version/status           | Permitted use                                |
| ------------------------ | --------------------------------- | ------------------------ | -------------------------------------------- |
| VKF-INPUT-SIM-V2         | `script-intelligence-v2`          | design v2; unbenchmarked | schema and research hypothesis               |
| VKF-INPUT-AV3D-V1        | `audio-visual-3d-v1`              | design v1; unbenchmarked | capability and benchmark hypothesis          |
| VKF-INPUT-KR-V1          | `knowledge-registry.schema.json`  | schema 1.0.0             | migration input, not complete Foundry schema |
| VKF-INPUT-MCP-CANDIDATES | GLIF, CometChat, OpusClip records | `CAN_XAC_MINH`           | quarantine testing only; never an anchor     |
