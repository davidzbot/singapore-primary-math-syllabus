# Changelog

## Unreleased — 2026-11-12 (documentation and licensing only; no release, no new DOI)

No data changes, no schema changes, no row changes. Deliberately **not** tagged or released on GitHub, so no additional Zenodo DOI is minted; DOI 10.5281/zenodo.24053661 remains canonical for v1.0.0/v1.0.1.

- Adds `DATASET.md` — one-page citation/provenance datasheet (identity, source freeze, structural audit, license, citation, contact)
- Adds `FIELDS.md` — field dictionary: types, enum domains (13 sub-strands; levels P1–P6; strands 118/76/8), null rules, code scoping (`per level+topic`), observed ranges (max subtopic 224 chars; page refs 31–44), CSV/JSON format notes
- Adds `NOTICE.md` — attribution, compilation vs underlying-rights split, MOE publication notice; `LICENSE` replaced with the verbatim CC BY-NC 4.0 legal code (SPDX `CC-BY-NC-4.0`) so the licence is machine-detectable (previous custom summary moved to NOTICE.md)
- Source freeze recorded (2026-11-12): official MOE PDF `2021-Primary-Mathematics-Syllabus-P1-to-P6-Updated-October-2025.pdf`, 806,004 bytes, SHA-256 `E8F77FE10D768E2AD5266DFC39A8821674BE7EB1C81BC545BA4B841B12AE70E1`
- Independent structural audit (2026-11-12, outside the build): 202/202 rows; per-level/per-strand counts match; 0 duplicates; 0 empty cells; CSV↔JSON record equivalence PASS; 199/202 automated text probes against pp. 31–44; the 3 misses are the documented SymbolMT font-private-glyph superscript items (cm²/cm³), previously manually verified
- `README.md` unchanged except for pointer links to the new files

## v1.0.1 — 2026-11-08

Data unchanged; packaging and citation release that mints the Zenodo DOI via the GitHub-Zenodo integration.

- Adds `CITATION.cff` (drives the GitHub "Cite this repository" widget) and `.zenodo.json` (creators, license, keywords, `isIdenticalTo` related-identifier to the landing page)
- Publishes release assets (CSV/JSON) for archiving
- Minted Zenodo DOI [10.5281/zenodo.24053661](https://doi.org/10.5281/zenodo.24053661) (repository zip, license CC BY-NC 4.0, creators PSLE Hero & BrainActive Labs, isIdenticalTo -> pslehero.org dataset page)
- No changes to any learning point, row count, schema or licence

## v1.0.0 — 2026-11-07

Initial release.

- 202 rows, Standard Mathematics P1–P6
  - P1: 32 · P2: 30 · P3: 34 · P4: 42 · P5: 37 · P6: 27
- Learning areas: Number and Algebra (118) · Measurement and Geometry (76) · Statistics (8)
- Based on **MOE 2021 Primary Mathematics Syllabus (Primary One to Six), Updated October 2025** (implementation starting with the 2021 Primary One cohort), Section 5 "Content by Level" (pp. 31–44)
- Extraction via PyMuPDF; **100% of rows manually verified** against the official PDF, including symbol-level checks for:
  - algebraic notation on p. 43 (`a ± 3`; `a × 3 or 3a`; `a ÷ 3 or a/3`)
  - volume root notation on p. 44 (`use of √, ³√`)
  - superscript area/volume units (`cm²`, `m²`, `cm³`, `m³`)
  - Statistics item 1.1, p. 44 (`total value ÷ number of data`)
- Schema v1: `syllabus_version, edition, level, learning_area, sub_strand, topic, code, subtopic, source_reference, source_url, verification_status`
- Excluded: Foundation Mathematics (official document pp. 45–50) — a subset of the Standard syllabus
- Normalizations (documented, not substantive): sub-strand names normalized to Title Case; bullet sub-details joined with `;`; superscript units written with Unicode superscript glyphs; font-private glyph codepoints (SymbolMT) mapped to visible characters (`±`, `×`, `÷`)
- Licence: CC BY-NC 4.0 (compilation); underlying syllabus content © MOE Curriculum Planning and Development Division
