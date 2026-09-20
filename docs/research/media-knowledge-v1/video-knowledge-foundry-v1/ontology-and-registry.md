# Unified ontology and registry contract

## Entity model

All relationships are versioned edges with `valid_from`, `valid_to`, evidence
IDs, confidence and author. Minimum cardinalities use `1`; optional is `0..1`;
collections use `0..*` or `1..*`.

| Entity           | Required relationships                | Cardinality/invariant                                               |
| ---------------- | ------------------------------------- | ------------------------------------------------------------------- |
| Topic            | audience, research questions          | `Audience 1..*`; immutable topic revision                           |
| Audience         | needs, platform context               | may inherit approved segment; no inferred sensitive trait           |
| Genre            | subgenre/pattern constraints          | `NarrativePattern 0..*`; versioned editorial contract               |
| NarrativePattern | compatible genres, scene functions    | cannot claim universal applicability                                |
| Claim            | evidence and script use               | material factual claim requires supporting `Evidence 1..*`          |
| Evidence         | source snapshot and locator           | exactly one immutable source revision; may support/challenge claims |
| ScriptBeat       | claim/pattern and scenes              | parent script `1`; `Scene 1..*` for compiled beats                  |
| Scene            | beat, function and shots              | primary function exactly `1`; `Shot 1..*` when production-ready     |
| Shot             | scene, assets and AV intent           | parent scene exactly `1`; evidentiary status explicit               |
| VoiceProfile     | consent/rights and delivery profile   | active consent `1` for identifiable voice                           |
| AudioCue         | scene/time range and asset            | rational time range; overlap policy explicit                        |
| VisualStyle      | color/type/composition rules          | rights-cleared references only                                      |
| Asset            | rights, hash, versions                | `Rights 1..*`; immutable binary hash                                |
| Rights           | subject, territory/use/term           | no inheritance beyond explicitly compatible scope                   |
| Model            | weights/data/code licenses            | separate records; runtime compatibility `0..*`                      |
| Tool             | release/build/dependencies            | adapter-facing; exact version/hash required for execution           |
| WorkflowNode     | input/output contracts and tool/model | deterministic idempotency key                                       |
| Benchmark        | fixture/config/result bundle          | result cannot outlive its pinned environment without stale flag     |
| QualityRule      | artifact scope and severity           | owner and human override policy required                            |
| PlatformProfile  | delivery/accessibility constraints    | version/date/territory required                                     |
| Publication      | approved package and platform profile | rights/QC/approval manifests exactly `1` each                       |

## Inheritance and composition

Use inheritance only for stable semantic “is-a” relations, such as specialized
Asset or QualityRule types. Capabilities, platform support, rights and licenses
use composition, never inheritance. A child cannot broaden consent or license.
Ontology breaking changes mint a new major entity ID and a `supersedes` edge;
content changes mint a revision linked to the stable entity ID.

## Provenance and versioning

Every entity and edge includes UUID, stable ID, schema/content versions, content
hash, parent/superseded IDs, creator/agent, timestamps, source/evidence IDs,
claim label (`VERIFIED`, `INFERENCE`, `ASSUMPTION`, `UNKNOWN`), confidence,
rights, workflow state and revalidation date. Event history is append-only;
promotion never overwrites quarantine evidence.

## Foundry Knowledge Record

Required groups:

1. **Identity:** stable ID, revision, names, domain and owner.
2. **Function:** problem, inputs/outputs, capabilities, compatibility and
   failure modes.
3. **Source:** canonical URL/owner, release/full commit/content hashes,
   snapshot, access time and excerpt locators.
4. **Rights:** code, binary, model weight, training/evaluation data, plugin,
   direct/transitive dependency licenses; attribution, consent and patents.
5. **Runtime:** platforms, CPU/GPU/NPU, RAM/VRAM/storage, offline/degraded mode.
6. **Assurance:** CPU benchmark bundle, quality, security, privacy, cost,
   maturity, evidence, confidence, final label and revalidation.

Unknown license, provenance, consent, security or material quality fields are
represented explicitly and prevent aggregate scoring or promotion.
