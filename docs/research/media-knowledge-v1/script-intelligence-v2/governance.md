# Governance, risk and roadmap

## Automated QC rule contract

Each rule requires ID/version, scope, input/output, deterministic test where
possible, severity, threshold, evidence IDs, false-positive risk, repair, owner,
human override policy and audit retention. Required families: claim– evidence
coverage, contradiction, chronology, entity continuity, tense/POV,
repetition/cliché, duration, subtitle load, pronunciation, numbers/dates,
on-screen mismatch, title/content mismatch, hook/payoff, CTA, sensitive claims,
license and attribution.

## Initial risk register

Deal Breaker Index (DBI) is a provisional 0–100 prioritization hypothesis, not
measured risk. All rows are `GIẢ ĐỊNH / E-REQUEST-V2`.

| Rank | Risk                                      | DBI | Owner                 | Prevent / detect / correct                                          | Residual  |
| ---: | ----------------------------------------- | --: | --------------------- | ------------------------------------------------------------------- | --------- |
|    1 | Defamation/unsupported material claim     | 100 | Editorial + Legal     | Evidence gate/right of reply / claim audit / retract-correct        | CHƯA BIẾT |
|    2 | Harmful instruction or safety omission    |  98 | Safety owner          | Scope/version/warning / expert review / unpublish-update            | CHƯA BIẾT |
|    3 | Copyright/plagiarism/unauthorized persona |  95 | Rights lead           | Original-only policy / similarity+rights review / replace-remediate | CHƯA BIẾT |
|    4 | Misleading reconstruction/synthetic media |  92 | Standards lead        | Persistent label/provenance / frame audit / relabel-remove          | CHƯA BIẾT |
|    5 | Privacy/customer-data misuse              |  90 | Privacy lead          | Minimization/consent / access audit / delete-notify                 | CHƯA BIẾT |
|    6 | Hallucination/stale news                  |  88 | Fact-check lead       | Retrieval/version gate / freshness scan / correction log            | CHƯA BIẾT |
|    7 | Hidden advertising/conflict               |  82 | Commercial standards  | Disclosure / conflict audit / correct disclosure                    | CHƯA BIẾT |
|    8 | Bias/cultural error/manipulation          |  78 | Inclusion + Editorial | diverse review / stratified metrics / revise-stop                   | CHƯA BIẾT |

## Technology Build/Buy/Integrate gate

Evaluate research, LLM, retrieval, screenplay parsing/editing, grammar/style,
fact-checking, graph, storyboard, localization, subtitle and analytics tools.
Weights: quality 20%; evidence/provenance 15%; controllability 10%;
interoperability 10%; Vietnamese 10%; privacy 10%; license 8%; maintenance 7%;
cost 5%; performance 5%. Do not score a tool while provenance, license, privacy
or security is unknown; do not use stars, popularity or marketing demos as
capability evidence.

## P0/P1/P2 backlog and timeline

| Horizon      | Priority                                                                                                           | Exit evidence                             |
| ------------ | ------------------------------------------------------------------------------------------------------------------ | ----------------------------------------- |
| 0–30 days    | P0: approve charter; acquire DOCX and canonical sources; verify repository snapshots; lock schemas and risk owners | Signed decisions, hashes, source records  |
| 31–60 days   | P0: complete five high-risk Genre Cards; claim/evidence and rights gates; benchmark preregistration                | Reviewed cards, rules and frozen protocol |
| 61–90 days   | P1: 36-brief corpus, reviewer training and pilot; adjudicate thresholds                                            | Versioned corpus and pilot report         |
| Months 4–6   | P1: complete remaining cards/pattern evidence; adapters and tool matrix                                            | Coverage and interoperability report      |
| Months 7–9   | P2: sandbox-approved integrations; local/hybrid/cloud architecture                                                 | Security, performance and cost evidence   |
| Months 10–12 | P2: controlled rollout and feedback loop with consent/leakage controls                                             | Audit, rollback drill and board review    |

## Decisions requiring board approval

Charter assumptions; budget/deadline; canonical source list; acceptable quote
policy; risk appetite/DBI; publication authority; right-of-reply procedure;
benchmark sampling and retention proxy; reviewer compensation/conflicts;
customer-data consent; tool sandbox/network policy; license counsel sign-off;
and promotion from quarantine.

## Five final self-checks

1. **Missing data:** DOCX, canonical repository metadata/content, primary
   narrative sources, completed Genre Cards, corpus, reviewers and all results.
2. **Assumptions:** audience/platform/duration baseline, ontology design,
   patterns, weights, DBI and roadmap capacity.
3. **Low confidence:** CometChat identity/capabilities, external technical
   assertions, effectiveness thresholds and commercial/tool decisions.
4. **CEO/showrunner/editor objection:** this is governance scaffolding, not
   proof of creative or business value; it lacks tested examples and cost.
5. **Board-ready?** No. It needs signed charter decisions, immutable source
   packs, legal/security review, completed P0 cards and reproducible benchmark
   results before an architecture or procurement decision.
