# Changelog

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
