# Singapore Primary Mathematics Syllabus 2021 Dataset (P1–P6)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24053661.svg)](https://doi.org/10.5281/zenodo.24053661)
[![Kaggle](https://img.shields.io/badge/Kaggle-Dataset-20BEFF?logo=kaggle&logoColor=white)](https://www.kaggle.com/datasets/pslebot/singapore-primary-math-syllabus-2021-dataset)

**Version 1.0.1 · DOI [10.5281/zenodo.24053661](https://doi.org/10.5281/zenodo.24053661) · Independently compiled by PSLE Hero — not an official MOE dataset.**

An open, machine-readable dataset of the **MOE 2021 Primary Mathematics Syllabus (Primary One to Six), Updated October 2025**.
It is designed for teachers preparing materials, parents, tutors and developers building learning tools.

- 202 learning points across **P1–P6** (Standard Mathematics; see [Scope](#scope))
- Available as **CSV** and **JSON** (identical records)
- Every row carries a traceable **source reference** (page number in the official document)
- 100 % of published rows are marked **`verified`** against the official PDF

Landing page (with download links and methodology): <https://pslehero.org/singapore-math-syllabus.html#dataset>

## Scope

Included: the **Standard** 2021 Primary Mathematics syllabus, levels P1 to P6 — the three content strands **Number and Algebra** (118 rows), **Measurement and Geometry** (76 rows) and **Statistics** (8 rows).

Excluded: the **Foundation** Mathematics syllabus sections (pages 45–50 of the official document). Foundation Mathematics is a subset of the Standard syllabus for P5–P6; it can be reused by filtering and does not need separate records in this release.

Also excluded: MOE's descriptive aims, pedagogy, assessment guidance and examples. Only **facts** are captured: strand, sub-strand, topic, official item code and the learning-point text itself. No substantial MOE prose is reproduced.

## Source and provenance

- Official document: **MOE, Mathematics Syllabus – Primary One to Six**, implementation starting with the **2021 Primary One cohort**, **Updated October 2025**.
- The PDF is published by the Ministry of Education of Singapore and distributed through the official page <https://www.moe.gov.sg/primary/curriculum/syllabus>. Direct file (as linked by MOE on that page): <https://www.moe.gov.sg/api/media/92bff26d-b2b4-4535-b868-b8415c744b91/2021-Primary-Mathematics-Syllabus-P1-to-P6-Updated-October-2025.pdf>
- Extraction: Section 5 "Content by Level" (pages 31–44 for the Standard syllabus) was machine-extracted (PyMuPDF) and then **manually reviewed row by row** by the PSLE Hero Editorial Team against the official PDF, including symbol-level verification of algebraic notation (e.g. `a ± 3`, `a × 3 or 3a`, `a ÷ 3 or a/3`, `use of √, ³√`, superscript area/volume units (cm²/m²/cm³/m³) and `total value ÷ number of data`).
- Any row that could not be verified was excluded. **None were.**
- `verification_status` is `verified` for all 202 rows.

This is an independent compilation. It is **not produced, endorsed or approved by MOE**. If any discrepancy exists, the official MOE document prevails.

## Files

| File | Format | Records | Encoding |
|---|---|---|---|
| `singapore-primary-math-syllabus-2021.csv` | CSV (header row) | 202 | UTF-8 (no BOM) |
| `singapore-primary-math-syllabus-2021.json` | JSON (array of objects) | 202 | UTF-8 |

## Schema

| Field | Type | Description |
|---|---|---|
| `syllabus_version` | string | `"2021"` — the 2021 syllabus (updated October 2025) |
| `edition` | string | Document edition, e.g. `"Updated October 2025"` |
| `level` | string | `"P1"` … `"P6"` |
| `learning_area` | string | One of `Number and Algebra`, `Measurement and Geometry`, `Statistics` (the three content strands) |
| `sub_strand` | string | Official sub-strand, e.g. `Whole Numbers`, `Fractions`, `Money`, `Geometry`, `Area and Volume`, `Data Analysis` |
| `topic` | string | Official topic heading without the number prefix, e.g. `Numbers up to 100` |
| `code` | string | Official item code within the topic, e.g. `1.2` (scoped per level+topic) |
| `subtopic` | string | Learning point, preserving official terminology; bullet sub-details joined with `;` |
| `source_reference` | string | Traceable citation: document, section, page (e.g. `... Section 5 "Content by Level", p. 31`) |
| `source_url` | string | Official PDF URL used for extraction |
| `verification_status` | string | `verified` (all rows in v1.0.0) |

Field order in CSV is as above. JSON preserves the same keys.

## Record counts

| Level | Rows |
|---|---|
| P1 | 32 |
| P2 | 30 |
| P3 | 34 |
| P4 | 42 |
| P5 | 37 |
| P6 | 27 |
| **Total** | **202** |

## Verification methodology

1. Extract Section 5 pages of the official PDF (pages 31–44) with text extraction that preserves page markers.
2. Parse level / strand / sub-strand / topic / item rows with a deterministic parser (separating manual post-fixes only for glyphs lost in extraction, documented in this repository's history).
3. Manually review **every** generated row against the official document, page by page, including rendering checks for the three items whose symbols are stored as font-private glyphs.
4. Checks enforced in the build: row count, per-level counts, no duplicate keys, no empty required fields, no unverified rows published, CSV↔JSON equivalence.

## Licence and attribution

- The **facts** in this dataset (topic lists and structure) are published by the **Ministry of Education of Singapore**, © 2025 Curriculum Planning and Development Division. MOE's publication notice permits reproduction for personal and non-commercial use only. This dataset reproduces no MOE descriptive text or examples.
- The **compilation** (schema, curation, verification, packaging) is © PSLE Hero & BrainActive Labs and is licensed under the **Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)** licence.
  - ✔ Share and adapt for **non-commercial** purposes with attribution.
  - ✘ Commercial reuse requires MOE's own permission, since the underlying content is reproduced in reliance on MOE's non-commercial notice.
- **Attribution required**: `Singapore Primary Mathematics Syllabus 2021 Dataset (P1-P6) by PSLE Hero, based on MOE's 2021 Primary Mathematics Syllabus (Updated October 2025), licensed CC BY-NC 4.0`
- Full licence terms: <https://creativecommons.org/licenses/by-nc/4.0/legalcode> (and see `LICENSE`).

## Suggested citation

APA:
> PSLE Hero. (2026). *Singapore Primary Mathematics Syllabus 2021 dataset (P1–P6)* (Version 1.0.1) [Data set]. https://doi.org/10.5281/zenodo.24053661

BibTeX:
```bibtex
@dataset{pslehero_sgds2021,
  title   = {Singapore Primary Mathematics Syllabus 2021 Dataset (P1-P6)},
  author  = {{PSLE Hero}},
  year    = {2026},
  version = {1.0.1},
  doi     = {10.5281/zenodo.24053661},
  url     = {https://pslehero.org/singapore-math-syllabus.html#dataset}
}
```

## Version history

See `CHANGELOG.md`. Current version: **v1.0.1 (2026-11-08)**.

## Licence notice

This compilation is licensed under CC BY-NC 4.0. The official MOE document remains the authoritative source. PSLE Hero and this dataset are **not affiliated with, endorsed by, or approved by MOE**.
