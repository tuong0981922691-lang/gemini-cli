# Script compiler and canonical object model

## Pipeline

`TopicBrief → ResearchQuestion → SourceRecord → Claim → Evidence → ThesisAngle → BeatSheet → SceneCard → Narration/Dialogue → OnScreenText → ShotIntent → AudioIntent → CitationCue → QCRule → RevisionDecision`

Every object requires: UUID, object type, schema version, content version,
parent IDs, author/agent ID, created/updated timestamps, claim label,
confidence, rights status, language, duration estimate, workflow status and
immutable provenance links. This is a design requirement, not a verified claim.
`[GIẢ ĐỊNH; E-REQUEST-V2]`

## Compile gates

1. A material factual `Claim` without supporting Evidence cannot compile into
   factual narration, dialogue, title, thumbnail or on-screen text.
2. A `SceneCard` without exactly one primary function is rejected.
3. Narration outside the declared duration tolerance returns `REVISE_DURATION`.
4. Every `ShotIntent` traces to a scene and beat; decorative shots are marked
   non-evidentiary and cannot imply unproven events.
5. Caption cues link to spoken or intentionally non-speech audio; chapter and
   descriptive metadata share the same timebase.
6. Rights `unknown`, material contradiction, missing attribution or failed
   safety gate blocks publication; human override requires identity, rationale,
   expiry and audit event.

## Canonical script envelope

```json
{
  "schema_version": "2.0.0",
  "script_id": "00000000-0000-4000-8000-000000000001",
  "version": "0.1.0",
  "language": "vi-VN",
  "status": "DRAFT",
  "rights_status": "ORIGINAL_SELF_CREATED",
  "duration_target_ms": 180000,
  "source_record_ids": ["SRC-EXAMPLE-001"],
  "claims": [],
  "beats": [],
  "scenes": [],
  "timed_tracks": {
    "caption": [],
    "subtitle": [],
    "description": [],
    "chapter": [],
    "metadata": []
  },
  "qc_results": [],
  "revision_decisions": []
}
```

The example contains no external story, dialogue or character and is released
only as project documentation metadata.

## Adapter boundaries

- Plain text: lossy review projection; stable IDs emitted as comments/sidecar.
- DOCX: review projection with styles/comments; canonical JSON remains source of
  truth until a revision-locking specification is selected.
- JSON: lossless canonical interchange after schema validation.
- Fountain: candidate early screenplay interchange. Its exact parser behavior
  and limits remain `CHƯA BIẾT` until an official specification is acquired and
  versioned (`E-SOURCE-PENDING-FOUNTAIN`).

No format is declared production-lock capable in this phase.
