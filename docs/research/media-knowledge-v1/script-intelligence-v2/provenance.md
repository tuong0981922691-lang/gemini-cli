# Source Registry, Evidence Pack and provenance policy

## Required Source Record

`source_id`, canonical URL, organization/author, title, source class,
publication/update date, access timestamp, version/commit, excerpt locator,
claim IDs, license/terms, geography, language, declared bias/conflicts,
reliability score with rationale, freshness, archive hash and revalidation date
are mandatory. Unknown values are explicit and block aggregate scoring when they
concern license, provenance, factuality or safety.

## Evidence object

Each Evidence object contains `evidence_id`, `source_id`, immutable locator,
verbatim-hash (not necessarily stored text), bounded paraphrase, supports/
challenges relation, claim IDs, collector, timestamp, confidence and rights.
Copyrighted text is not bulk-ingested; quotations require purpose, minimum
length, locator and rights review.

## Evidence registry

| Evidence ID                 | Label               | Observation/requirement                                                                        | Source/version              | Confidence                | Status       |
| --------------------------- | ------------------- | ---------------------------------------------------------------------------------------------- | --------------------------- | ------------------------- | ------------ |
| E-REQUEST-V2                | SỰ THẬT ĐÃ XÁC MINH | The supplied brief requests Script Intelligence Mine v2 fields, phases and gates               | User request / 2026-09-20   | High for requirement only | DAT          |
| E-WORKSPACE-SCAN-20260920   | SỰ THẬT ĐÃ XÁC MINH | No requested DOCX was found in the accessible workspace scan                                   | Local `find` / 2026-09-20   | High, bounded to scan     | DAT          |
| E-COMETCHAT-ACCESS          | SỰ THẬT ĐÃ XÁC MINH | Mirror clone returned proxy HTTP 403 and browser gateway returned HTTP 401; no object acquired | Collection log / 2026-09-20 | High                      | DAT          |
| E-COMETCHAT-IDENTITY        | CHƯA BIẾT           | URL/owner are user-provided but canonical ownership is not independently verified              | User lead / 2026-09-20      | Low                       | CAN_XAC_MINH |
| E-SOURCE-PENDING-FOUNTAIN   | CHƯA BIẾT           | Official format specification/version not collected                                            | None                        | None                      | CAN_XAC_MINH |
| E-SOURCE-PENDING-JOURNALISM | CHƯA BIẾT           | Journalism ethics/correction assertions await primary policy sources                           | None                        | None                      | CAN_XAC_MINH |
| E-SOURCE-PENDING-LEARNING   | CHƯA BIẾT           | Learning-design assertions await primary research/standards                                    | None                        | None                      | CAN_XAC_MINH |

## CometChat candidate disposition

The complete failed-acquisition record is stored at
`../sources/cometchat-docs-mcp-source.json`. It is not a snapshot manifest.
Default branch, full SHA, commit date, release, license, languages,
capabilities, maintenance, security policy and dependencies remain unknown.
Required next input is a trusted Git bundle/mirror with refs and history, or
read-only access to the canonical GitHub repository/API. Static review must
precede any execution.

## Promotion policy

- `TINH_HOA`: canonical/versioned source, claim-level evidence, known rights,
  reproducible benchmark and zero P0 unknowns.
- `DAT`: bounded use with evidence and declared limitations; never an anchor.
- `CAN_XAC_MINH`: quarantine for missing/conflicting provenance or risk data.
- `LOAI_BO`: retained with decision owner, reason and evidence; never erased.
