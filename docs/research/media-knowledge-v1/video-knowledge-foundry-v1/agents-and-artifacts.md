# Agent and artifact contracts

## Common agent envelope

Every agent declares owner, purpose, risk class, allowed tools/data/network,
versioned input/output schemas, token/compute/money budget, timeout, retry
policy, idempotency key, checkpoint format, evaluation set, forbidden actions
and escalation target. Tool use is deny-by-default. Agents cannot approve their
own high-risk output or widen rights/consent.

| Agent                 | Primary input/output              | Allowlist boundary                  | Mandatory escalation                |
| --------------------- | --------------------------------- | ----------------------------------- | ----------------------------------- |
| Orchestrator          | workflow plan/status              | scheduling, registry, audit         | policy conflict or exhausted budget |
| Research              | brief → source leads/claims       | approved search/read-only ingest    | identity/provenance uncertainty     |
| Script                | claims → script/beat revisions    | promoted knowledge only             | unsupported material claim          |
| Fact-check            | claims/evidence → verdict         | source snapshots and counter-search | contradiction or stale anchor       |
| Storyboard            | script → boards/shot intents      | rights-cleared asset catalog        | implied unproven reconstruction     |
| Voice Director        | script/consent → voice plan       | approved voice profiles             | missing/revoked consent             |
| Sound Designer        | scenes → audio plan               | licensed audio catalog              | rights or loudness-profile gap      |
| 2D Artist             | style/scenes → 2D plan/assets     | approved design/render adapters     | font/reference rights gap           |
| 3D Technical Director | scenes/assets → scene/render plan | validated 3D adapters               | interchange/resource uncertainty    |
| Editor                | plans/assets → timeline           | non-destructive edit adapters       | lineage mismatch                    |
| Render Planner        | timeline → jobs/capacity          | scheduler and approved workers      | tier budget cannot meet deadline    |
| QC                    | outputs → QC report               | read-only analyzers/test fixtures   | P0 failure                          |
| Rights                | manifests → rights decision       | registry/legal hold workflow        | unknown jurisdiction/term/consent   |
| Cost                  | job plan → estimate/variance      | approved rate cards/telemetry       | cap breach                          |

## Artifact envelope

Every artifact has UUID, type, schema/content version, hash, parent hashes,
creator, timestamps, status, language, rights/consent refs, evidence refs,
confidence, compatibility, approval events and retention/legal-hold status.

| Artifact            | Minimum content                                                     |
| ------------------- | ------------------------------------------------------------------- |
| Creative brief      | topic, audience, platform, objective, duration, risk, budget        |
| Evidence pack       | claims, supporting/challenging evidence, locators, freshness        |
| Script              | beats/scenes, factual claim links, timing and accessibility intent  |
| Storyboard          | frame intent, scene/shot linkage, evidentiary/reconstruction label  |
| Shot plan           | framing, movement, duration, asset and production constraints       |
| Voice plan          | profile/consent, pronunciation, prosody, timing and fallback        |
| Audio plan          | cues, sources/rights, mix routing and delivery profile              |
| Visual/3D plan      | style, color, assets, scene graph, interchange and render settings  |
| Asset manifest      | hashes, versions, dependencies, rights and validation               |
| Timeline            | rational timebase, tracks, transitions, captions and source lineage |
| Render job          | input hashes, worker requirements, seed, outputs and retries        |
| QC report           | rules/results, measurements, failures, override/auditor             |
| Rights manifest     | license/consent/territory/term/attribution and legal hold           |
| Publication package | approved master, derivatives, metadata, QC/rights and rollback      |
