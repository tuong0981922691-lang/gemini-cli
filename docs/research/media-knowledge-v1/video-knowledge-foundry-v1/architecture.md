# Target architecture, dataflow and deployment

## Desktop-first reference architecture

```text
Local UI
  │ approvals / edits / status
Local Orchestrator ── Policy + Budget + Audit
  ├── Metadata DB ── lexical index ── vector index ── knowledge graph adapter
  ├── Content-addressed object/artifact store
  ├── Local worker pool ── model-runtime adapter
  │                    ├── media-backend adapter
  │                    └── 3D-render adapter
  └── Optional cloud connector ── approved remote GPU/service adapters
```

Names such as Blender, FFmpeg or a model runtime are candidate adapter
implementations, not architectural dependencies. Quarantined MCP candidates are
not connected to the orchestrator. Every adapter declares capability,
permissions, input/output schema, idempotency, timeout, cost and fallback.

## Brief-to-publication dataflow

```text
CreativeBrief → ResearchPlan → EvidencePack → ApprovedClaims
→ Script → Storyboard → Shot/Voice/Audio/Visual Plans → AssetManifest
→ Timeline → RenderJobs → QCReport + RightsManifest
→ Human Release Approval → PublicationPackage → Platform Adapter
```

Each arrow validates the incoming artifact contract and emits a new immutable
revision with parent hashes. Rework creates a branch and RevisionDecision; it
does not mutate approved history.

## Deployment modes

| Mode           | Local guarantees                                                 | Optional remote work                          | Degraded behavior                             |
| -------------- | ---------------------------------------------------------------- | --------------------------------------------- | --------------------------------------------- |
| Offline        | metadata, artifacts, lexical search, approved local models/tools | none                                          | queue freshness checks and cloud-only nodes   |
| Hybrid         | offline guarantees plus encrypted connector                      | approved elastic render/inference/publication | fall back/queue; never bypass policy          |
| Cloud-assisted | local control plane and approval/audit remain authoritative      | compute/index replica/service adapters        | revoke connector and resume local checkpoints |

Secrets live outside artifacts and prompts, are scoped per adapter and never
enter logs. Network is deny-by-default; remote data transfer requires rights,
residency, cost and redaction checks.

## Storage and recovery

Metadata and event logs use transactional backup; object storage uses hashes,
versioning and replication; indexes are rebuildable. Recovery tests restore a
publication’s evidence, rights, timeline, source assets and render lineage—not
only its final video. RPO/RTO remain business decisions, not invented values.
