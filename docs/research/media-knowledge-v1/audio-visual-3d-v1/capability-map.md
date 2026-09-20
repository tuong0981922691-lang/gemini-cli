# Capability map and detailed taxonomy

All taxonomy entries are design requirements from `AV-REQ-20260920`, version
`1.0.0`, accessed `2026-09-20`, confidence high for scope and **CHƯA BIẾT** for
implementation effectiveness until evidence and benchmarks exist.

## Voice and speech

| Layer                | Capabilities                                                                                    | Required output/QC                                              |
| -------------------- | ----------------------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| Text front end       | language/locale detection, normalization, tokenization, abbreviation/number/date expansion      | normalized text plus reversible spans                           |
| Linguistic           | G2P, phoneme inventory, syllable/stress/tone, pronunciation lexicon, code-switching             | phoneme sequence, confidence, lexicon version                   |
| Expressive planning  | prosody, emotion/style, pause/breath, emphasis, rate, pitch and energy controls                 | explicit control track; no inferred identity claim              |
| Synthesis/adaptation | acoustic generation, vocoder, multilingual synthesis, consented speaker adaptation              | audio plus model/voice/consent provenance                       |
| Transformation       | voice conversion and enhancement                                                                | blocked unless identity rights and anti-impersonation gate pass |
| Timing               | forced alignment, dubbing, lip/segment constraints                                              | word/phoneme timestamps and alignment residual                  |
| Safety               | consent receipt, allowed purpose, expiry/revocation, watermark/disclosure, impersonation review | auditable authorization or hard reject                          |

Metrics must record method and uncertainty: listening-test MOS; intelligibility
task score; pronunciation error by token/phoneme; absolute and percentile
alignment error in milliseconds; real-time factor
(`processing seconds / audio seconds`); peak/steady RAM; model and working-set
bytes; and cold-start latency. MOS is invalid without test design, listener
count, scale anchors, confidence interval and audio-set version.

## Audio and sound

1. **Capture and repair:** device/channel/sample format, gain, room tone, clock,
   clipping; denoise, dereverb, de-click/de-plosive and restoration.
2. **Separation and design:** source separation, Foley/SFX, ambience, music
   selection/generation, provenance and sync.
3. **Mix:** spatialization, routing, EQ, compression, de-essing, limiting,
   ducking and automation.
4. **Delivery:** loudness normalization, Loudness Range, true peak, codec-aware
   QC and channel-specific mastering profiles.

The supplied `−23 LUFS` EBU R 128 statement is a candidate broadcast baseline,
not a universal delivery preset. It remains `CAN_XAC_MINH` until the official
recommendation/version is archived. Every distribution channel requires a
separate versioned profile; no web/social value may be inferred from broadcast.
`[CHƯA BIẾT; AV-LEAD-EBU-R128]`

## 2D graphics

- Raster/vector formats; resolution, bit depth, alpha, premultiplication and
  matte edges.
- Typography, layout/grid, iconography, infographic, chart-as-image and
  accessibility alternatives.
- Color space/profile/transfer, working/display transforms and export intent.
- Drawing/painting, procedural graphics, compositing and template variables.
- Motion graphics, easing, keyframes, safe area, subtitle styling and readable
  contrast.
- Grease Pencil is a candidate capability name only until its exact supported
  Blender release and behavior are verified.

## 3D and scene interchange

| Stage    | Capability                                              | Validation focus                                              |
| -------- | ------------------------------------------------------- | ------------------------------------------------------------- |
| Author   | modeling, sculpting, retopology, UV                     | topology, scale, units, manifold policy                       |
| Surface  | PBR material, texture authoring/baking                  | channels, color spaces, resolution, rights                    |
| Deform   | rigging, skinning, animation, mocap                     | hierarchy, weights, frame rate, consent                       |
| Layout   | camera, lighting, particles, simulation, geometry nodes | determinism, seeds, cache/version                             |
| Render   | renderer/device, sampling, denoise, passes/AOV          | frame time, memory, quality, resume                           |
| Finish   | compositing, image-sequence ingest, editorial output    | alpha/color/timebase/QC                                       |
| Exchange | USD, glTF, Alembic                                      | feature-loss matrix, units, axes, material/animation fidelity |
| Scale    | LOD, asset validation, queue/render farm                | package integrity, retry, ownership                           |

OpenUSD is evaluated as a **candidate** scene-description/composition layer for
multi-tool assets, geometry, shading, lighting and physics. Those capabilities
must be verified against a pinned official specification and each application’s
support matrix; “USD support” alone is not interoperability evidence.
`[CHƯA BIẾT; AV-LEAD-OPENUSD]`

## Media backend and timed text

Backend stages are probe → decode → color/scale/filter → subtitle/composite →
encode → mux → structural/perceptual QC. Image sequences are first-class inputs
and outputs. Each build record stores configure flags, enabled codec/muxer/
demuxer/filter/resampler/scaler/library features, exact license texts and a
separate codec-patent review. `[GIẢ ĐỊNH; AV-REQ-20260920]`

The canonical timed-text model covers cues, speaker, language, role, style,
reading load, safe area, translation lineage, accessibility purpose and
timebase. WebVTT and TTML are adapters, not the canonical store. The brief’s
statement that WebVTT covers captions, subtitles, descriptions, chapters and
metadata is `CAN_XAC_MINH` pending a pinned W3C source.
`[CHƯA BIẾT; AV-LEAD-WEBVTT]`
