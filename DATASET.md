# DATASET — Singapore Primary Mathematics Syllabus 2021 Dataset (P1-P6)

One-page datasheet for librarians, resource editors, data catalogues and researchers deciding whether to cite or list this dataset. Everything below is verifiable; nothing is aspirational.

## Identity

| Item | Value |
|---|---|
| Name | Singapore Primary Mathematics Syllabus 2021 Dataset (P1-P6) |
| Creators | PSLE Hero & BrainActive Labs (independent; see "Authority") |
| Version / Date | v1.0.1, released 2026-11-08 (data identical to v1.0.0, released 2026-11-07) |
| Records | 202 learning points — P1: 32, P2: 30, P3: 34, P4: 42, P5: 37, P6: 27 |
| Strands | Number and Algebra 118 · Measurement and Geometry 76 · Statistics 8 |
| Formats | CSV + JSON (identical records), UTF-8 |
| Canonical DOI | [10.5281/zenodo.24053661](https://doi.org/10.5281/zenodo.24053661) (Zenodo) |
| Mirror DOI | Kaggle, 10.34740/kaggle/dsv/21857026 |
| Repository | https://github.com/davidzbot/singapore-primary-math-syllabus (release tag `v1.0.1`) |
| Archive | Software Heritage snapshot (full visit 2026-11-08): `swh:1:snp:b69f2d689c3857a4d2b154b0190e154421eb5713` |
| Landing page | https://pslehero.org/singapore-math-syllabus.html#dataset |
| License | **CC BY-NC 4.0** ([SPDX `CC-BY-NC-4.0`](https://spdx.org/licenses/CC-BY-NC-4.0.html)) — see `LICENSE` and `NOTICE.md` |

## What it contains

Section 5 "Content by Level" (pp. 31–44) of MOE's **Mathematics Syllabus — Primary One to Six** (implementation from the 2021 Primary One cohort; edition **Updated October 2025**), machine-extracted (PyMuPDF) and manually reviewed row-by-row. Fields: syllabus version, edition, level, strand, sub-strand, topic, official item code, the learning point (`subtopic`), page-level `source_reference`, the official `source_url`, and `verification_status` (all `verified`). Full field dictionary: **`FIELDS.md`**. The Foundation syllabus (pp. 45–50) and MOE's descriptive/pedagogical prose are excluded by design.

## Provenance (source freeze, 2026-11-12)

| Item | Value |
|---|---|
| Official document | Ministry of Education (Singapore), *Mathematics Syllabus — Primary One to Six*, Updated October 2025 |
| Source file | `2021-Primary-Mathematics-Syllabus-P1-to-P6-Updated-October-2025.pdf` (as linked from moe.gov.sg; see README → Source and provenance) |
| Size / SHA-256 (recomputed 2026-11-12) | 806,004 bytes · `E8F77FE10D768E2AD5266DFC39A8821674BE7EB1C81BC545BA4B841B12AE70E1` |
| Reference use | Tracing every row to its page requires the official PDF; the SHA-256 lets you confirm you hold the identical file |

## Independent structural audit — 2026-11-12

Performed on the published v1.0.1 assets (CSV and JSON), not against the PDF:

- 202 rows; per-level and per-strand counts match documentation exactly; 0 duplicate rows; 0 empty cells (11 fields × 202 rows).
- CSV ↔ JSON record equivalence: **PASS** (all 202 records identical).
- Automated fragment probe against pp. 31–44 text: **199/202 pass**. The 3 misses are the documented SymbolMT font-private-glyph superscript items (`cm²/cm³`, `area/volume in square/cubic units`, P3/P5) — the same symbol items the build log records as manually verified at symbol level.
- This audit proves structural integrity and bulk page-level traceability. It is **not** a substitute for the compiler's row-by-row human review, and not an endorsement of MOE content.

## Authority and non-affiliation

PSLE Hero & BrainActive Labs is an independent Singapore primary-education platform. This dataset is an **independent compilation**. It is **not produced, endorsed, reviewed or approved by the Ministry of Education**, and it must not be cited as "MOE data" or "Ministry-approved". If any discrepancy exists, **the official MOE document prevails**. The official publication notice permits reproduction for personal and non-commercial use only; the compilation is licensed CC BY-NC 4.0 accordingly.

## License, in plain words

You may share and adapt this dataset for **non-commercial** purposes with attribution (commercial use would require rights beyond MOE's publication notice). Attribution string:

> Singapore Primary Mathematics Syllabus 2021 Dataset (P1-P6) by PSLE Hero, based on MOE's 2021 Primary Mathematics Syllabus (Updated October 2025), licensed CC BY-NC 4.0

Machine-readable licence: `LICENSE` (verbatim CC BY-NC 4.0 legal code, SPDX `CC-BY-NC-4.0`). Compilation vs underlying-rights split and attribution request: **`NOTICE.md`**. Do not describe this as "open data, unrestricted" — it is non-commercial.

## Citation

```text
PSLE Hero. (2026). Singapore Primary Mathematics Syllabus 2021 Dataset (P1-P6) (Version 1.0.1) [Data set].
https://doi.org/10.5281/zenodo.24053661
```

BibTeX and APA: see `README.md`. Suggest use of the DOI, not a file URL — the DOI resolves to the archived record.

## Corrections, errata, contact

Report errors to **pslehero@gmail.com** with the row `code` and page reference. All changes ship via semantic version bump + changelog entry (`CHANGELOG.md`); no silent edits. Next scheduled review: on any new MOE syllabus release (check https://www.moe.gov.sg/primary/curriculum/syllabus).

## What this dataset is not

Not exam papers, not answer keys, not a ranking/rating of schools, not MOE guidance, not legal advice about using syllabus facts. For teaching-time decisions, always use the official document.
