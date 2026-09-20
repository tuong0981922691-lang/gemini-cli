# Preset and scene/asset schemas

## Common envelope

Every preset, asset, scene and timed-text object requires UUID, schema/content
version, parent IDs, author/agent, created/updated time, language, rights and
consent references, source/evidence IDs, confidence, lifecycle status, software/
model compatibility and a content hash.

## Voice preset

Fields: locale, normalization/G2P/lexicon versions, approved speaker identity
token (never raw biometric identity), consent scope/expiry/revocation, rate,
pitch, energy, style, emphasis/pause/breath tracks, model/vocoder hashes,
precision/provider, sample format, loudness target, anti-impersonation controls
and measured MOS/intelligibility/pronunciation/alignment/RTF/RAM/cold-start.

## Audio delivery preset

Fields: channel/layout, sample rate/format, dialogue reference, integrated
loudness target/tolerance, range, true-peak ceiling, EQ/dynamics/ducking chain,
codec/container, distribution channel, measurement-tool version and QC evidence.
No “universal platform preset” is allowed.

## 2D/motion preset

Fields: canvas/resolution/aspect/pixel aspect, frame rate/timebase, working and
output color/profile, alpha mode, safe areas, typography assets/licenses,
subtitle style, motion/easing policy, template parameters and export formats.

## Scene and asset record

Fields: units/up axis, frame range/rate, asset graph and variants, geometry/LOD,
UV, material/shader/texture channels and color spaces, skeleton/animation/mocap
rights, cameras/lights, simulation/particle caches and seeds, interchange format
and feature-loss report, renderer/device/samples/passes, resource estimates,
dependencies, validation results and per-frame output manifest.

## Timed-text object

Fields: track purpose (`caption`, `subtitle`, `description`, `chapter`,
`metadata`), cue UUID, start/end on rational timebase, source narration ID,
speaker/role, language, text, style class, line/character/reading-rate measures,
safe-area placement, sound/non-speech semantics, translation parent/version,
translator/reviewer, accessibility review, rights and adapter-specific payload.

## Example status lifecycle

`DRAFT → STATIC_REVIEWED → BENCHMARK_CANDIDATE → SANDBOX_APPROVED → DAT → TINH_HOA`;
any provenance, consent, license, regression or security failure moves the
object to `CAN_XAC_MINH`. `LOAI_BO` retains reason, evidence and approver.
