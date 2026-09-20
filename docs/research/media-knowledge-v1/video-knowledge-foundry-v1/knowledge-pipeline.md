# Ingest, evidence and retrieval design

## Ingest state machine

```text
DISCOVERED
  → CANONICAL_IDENTITY_CHECKED
  → SNAPSHOTTED_IMMUTABLY
  → PARSED_OR_OCR_REVIEW
  → CLAIMS_EXTRACTED
  → ENTITIES_LINKED
  → DEDUPED
  → CONTRADICTIONS_MAPPED
  → LICENSE_SECURITY_REVIEWED
  → HUMAN_REVIEWED
  → INDEXED
  → DAT | TINH_HOA
```

Any failed identity, snapshot, license, security, parser-confidence or review
gate routes to `CAN_XAC_MINH`. Rejected material routes to `LOAI_BO` with
reason, evidence and approver. Quarantine indexes are physically/logically
excluded from production retrieval and architecture-anchor queries.

## Ingest controls

- Discovery stores leads only; canonical ownership requires authoritative
  cross-link or repository/registry metadata.
- Snapshot stores original bytes/Git objects, source manifest, hash, timestamp
  and acquisition tool version. OCR output never replaces the original.
- Parsing retains page/section/line/time locators and parser confidence.
- Claim extraction separates source assertion from Foundry endorsement.
- Entity linking is reversible and records ambiguous candidates.
- Dedup uses exact hash, normalized fingerprint and semantic candidates; a human
  resolves material near-duplicates.
- Contradiction records both sides, time validity and scope instead of selecting
  a winner silently.
- License/security scans produce evidence, not automatic legal conclusions.

## Hybrid retrieval

```text
query → policy/domain planner → temporal/license/hardware filters
      → lexical + vector + graph traversals
      → counter-evidence branch → reranker
      → claim-level context pack → citation validator → answer
```

The query planner selects indexes and budgets by domain and risk. Context units
are Claim–Evidence bundles, not arbitrary text chunks. Packing preserves
supporting and challenging evidence, effective dates, license constraints and
hardware applicability. A material answer without valid locators fails closed.

## Retrieval evaluation

Create a versioned, rights-cleared gold set stratified by domain, risk, time,
language, hardware tier and positive/counter-evidence cases. Measure Recall@K,
Precision@K, nDCG, citation correctness, answer faithfulness, contradiction
coverage, filter compliance and stale-source rate. Report confidence intervals,
zero-result rate and failures; do not tune on the held-out test set.

Confidence calibration compares declared answer confidence with adjudicated
correctness. Calibration never substitutes for citations or expert review.
