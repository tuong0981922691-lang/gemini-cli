# Benchmark and evaluation protocol v2.0.0

**Status: protocol only. No result exists.** Any score column is forbidden until
the corpus, systems and reviewers are versioned and the run is reproducible.

## Corpus design

- 36 core briefs: 12 genre families × three complexity levels.
- Factorial views across five durations, three platforms and three audience
  groups. This yields 1,620 evaluation conditions if fully crossed; a
  preregistered fractional design may be used when budget is known.
- Gold annotations: thesis, beat, scene function, claim/evidence, hook/payoff,
  duration, visualizability, voiceability, rights/safety and error taxonomy.
- Four systems: baseline template, AI zero-shot, AI retrieval-grounded and
  human-edited. Pin model/prompt/retrieval corpus/configuration.
- At least three blinded reviewers per item; report agreement statistic selected
  before inspection, confidence interval, disagreement adjudication and reviewer
  conflicts.

## Measures and fail-fast thresholds

Measure factual precision/recall, unsupported material claim rate, structural
completeness, coherence, novelty, Vietnamese readability, estimated/actual
duration error, visual coverage, caption suitability, revision distance, human
edit minutes, preregistered retention proxy and safety/rights failures.

Fail-fast: factuality `<7/10` for factual content; safety/rights `<8/10`;
unsupported material claims `>0`; serious continuity contradiction; or missing
provenance. Other numeric thresholds remain `CHƯA BIẾT` until the pilot
distribution and board risk tolerance are available.

## Weighted rubric

| Dimension                  | Weight |
| -------------------------- | -----: |
| Factuality                 |    15% |
| Coherence                  |    12% |
| Audience fit               |    10% |
| Genre fidelity             |     8% |
| Originality                |     8% |
| Tension/attention          |     8% |
| Clarity                    |     8% |
| Visualizability            |     7% |
| Voiceability               |     6% |
| Editability                |     5% |
| Accessibility/localization |     4% |
| Safety/rights              |     5% |
| Production efficiency      |     4% |

Weighted score is calculated only after fail-fast gates pass. Sensitivity runs
each weight at ±20%, renormalizes all weights, and reports rank reversals,
winner stability and criteria driving instability. This weighting is a user
requirement (`E-REQUEST-V2`), not validated empirical importance.

## Bias analysis

Stratify errors by genre, duration, platform, audience, language variety, speech
rate, disability/accessibility mode, factual risk and production style. Audit
reviewer familiarity, prestige bias, verbosity preference and whether retention
proxies reward sensationalism. Do not equate audience metrics with social or
editorial value.
