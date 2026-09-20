# Six-layer ontology and controlled vocabulary

## Node contract

Every node MUST contain: `id`, Vietnamese/English names, operational definition,
objective, inputs, outputs, `parent_ids`, `child_ids`, `compatible_with`,
`conflicts_with`, use/do-not-use conditions, duration fit, pacing, evidence
level, visual/audio treatment, risks, metrics, original example, anti-pattern,
source IDs, confidence and semantic version. Empty required knowledge is
represented as `unknown`, never omitted.

Stable ID grammar: `SIM.<layer>.<slug>.v<major>`, where layer is `GEN`, `SUB`,
`INT`, `PAT`, `SCN` or `AVT`. Patch/minor changes do not alter identity; a
breaking semantic change creates a new major ID and `supersedes` relation.
`[SUY LUẬN; E-REQUEST-V2]`

## Six layers

| Layer             | Controlled meaning           | Input                 | Output                  | Invariant                   |
| ----------------- | ---------------------------- | --------------------- | ----------------------- | --------------------------- |
| Genre             | Editorial contract family    | Topic + audience      | Eligible subgenres      | Not a platform or mood      |
| Subgenre          | Operational production form  | Genre + promise       | Genre Card              | Has acceptance criteria     |
| Audience Intent   | Observable viewer job        | Persona + context     | Desired outcome         | Not presumed emotion        |
| Narrative Pattern | Ordered information strategy | Thesis + evidence     | Beat constraints        | Has failure conditions      |
| Scene Function    | Reason a scene exists        | Beat + state change   | Scene outcome           | Functionless scene rejected |
| AV Treatment      | Perceptual realization       | Scene intent + rights | Shot/audio/text intents | Traceable to scene          |

## Genre and subgenre coverage matrix

Every entry is `GIẢ ĐỊNH / CAN_XAC_MINH / E-REQUEST-V2` until its Genre Card has
official or primary evidence and benchmark results.

| Genre ID | Genre                              | Required subgenres                                                                                     |
| -------- | ---------------------------------- | ------------------------------------------------------------------------------------------------------ |
| GEN-NEWS | Tin tức–thời sự / News             | breaking; explainer; digest; live recap; policy analysis; fact-check; correction/update                |
| GEN-DOC  | Tài liệu–điều tra / Documentary    | event; profile; history; science; nature; business; multi-source investigation; labeled reconstruction |
| GEN-EDU  | Giáo dục / Education               | microlearning; lecture; concept explainer; case-based; problem–solution; quiz; recap                   |
| GEN-HOW  | Hướng dẫn / How-to                 | onboarding; software task; installation; troubleshooting; maintenance; safety procedure; before/after  |
| GEN-REV  | Review–so sánh / Review            | single review; benchmark; buyer guide; head-to-head; long-term; myth-busting                           |
| GEN-ARG  | Tranh luận / Argument              | debate; cross-examination; steelman; adversarial; Socratic; courtroom reasoning                        |
| GEN-PHI  | Triết lý / Philosophy              | premise; paradox; thought experiment; analogy; counterexample; synthesis; reflection                   |
| GEN-MYS  | Bí ẩn an toàn / Safe mystery       | mystery; investigation; suspense; uncertainty; folklore retelling; reveal                              |
| GEN-MKT  | Marketing–doanh nghiệp / Corporate | brand story; launch; testimonial; case study; pitch; recruitment; internal communication               |
| GEN-INT  | Phỏng vấn–podcast hình / Interview | expert; profile; panel; roundtable; Q&A; solo commentary                                               |
| GEN-ENT  | Giải trí / Entertainment           | clean comedy; challenge; analytical reaction; listicle; countdown; original parody                     |
| GEN-SER  | Series                             | episodic; serialized; anthology; recurring format; season arc; responsible cliffhanger                 |

## Genre Card contract

A card must specify audience promise/JTBD, cognitive/emotional journey, central
question, thesis/viewpoint, source burden, structure and beats, hook/stakes/
escalation/reveal/turn/climax/resolution/CTA, narrator and character functions,
dialogue/sentence/scene rhythm, information density, duration, visual/B-roll/
graphics/text/audio grammar, title relationship, accessibility/localization,
complexity/cost, failure/repair and measurable acceptance criteria.

No card is complete in this package. P0 cards are news, investigation, safety
procedure, benchmark review and testimonial because error can create elevated
factual, safety, reputational or disclosure risk. `[SUY LUẬN; E-REQUEST-V2]`

## Controlled terms

| Term            | Operational definition                                                    | Exclusion                              |
| --------------- | ------------------------------------------------------------------------- | -------------------------------------- |
| Material claim  | Claim that can alter safety, reputation, rights, money or a key decision  | Purely disclosed fiction               |
| Evidence        | Immutable source observation supporting or challenging a claim            | URL without locator/version            |
| Hook            | Opening device with a declared promise                                    | Misleading omission or false certainty |
| Beat            | Smallest planned narrative state change                                   | Formatting-only paragraph              |
| Scene function  | Testable contribution to viewer/narrative state                           | “Looks interesting”                    |
| Payoff          | Resolution of a registered promise                                        | Unrelated surprise                     |
| Reconstruction  | Recreated event representation explicitly labeled as such                 | Unlabeled fabricated footage           |
| Originality     | Distance from protected expression plus attributable independent creation | Mere synonym replacement               |
| Retention proxy | Predeclared measurable correlate, not actual viewer value                 | Universal quality score                |
