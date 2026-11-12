# Field Dictionary — Singapore Primary Mathematics Syllabus 2021 Dataset (P1-P6)

**File covered:** `singapore-primary-math-syllabus-2021.csv` (and the identical JSON array in `singapore-primary-math-syllabus-2021.json`)
**Format:** CSV with header row, UTF-8 (no BOM), fields quoted per RFC 4180 when they contain commas. JSON: one object per row, same keys, all values are JSON strings.
**Rows (data, excluding header):** 202
**Audited:** 2026-11-12 (structural audit — row counts, per-level counts, enum inventory, uniqueness, empty-cell scan, CSV↔JSON record equivalence — all pass)

> Types below are as observed in the published data (all JSON values are strings; CSV has no quoting of types). `code` is **not** a number — always treat it as an opaque string.

| # | Field | Type | Null? | Observed domain | Description & notes |
|---|---|---|---|---|---|
| 1 | `syllabus_version` | string | never | `2021` (only) | The syllabus cohort year. Constant in v1.0.0/v1.0.1. |
| 2 | `edition` | string | never | `Updated October 2025` (only) | Edition of the official source document used. |
| 3 | `level` | string (enum) | never | `P1` … `P6` | Level. Per-level row counts: P1 32, P2 30, P3 34, P4 42, P5 37, P6 27 (total 202). |
| 4 | `learning_area` | string (enum) | never | `Number and Algebra` \| `Measurement and Geometry` \| `Statistics` | The three content strands. Row counts: 118 / 76 / 8. |
| 5 | `sub_strand` | string (enum, 13) | never | `Algebra`, `Area and Volume`, `Data Analysis`, `Data Representation and Interpretation`, `Decimals`, `Fractions`, `Geometry`, `Measurement`, `Money`, `Percentage`, `Rate`, `Ratio`, `Whole Numbers` | Official sub-strand, normalized to Title Case. |
| 6 | `topic` | string | never | 42 distinct values, e.g. `Numbers up to 100`, `Addition and Subtraction`, `Multiplication and Division`, `Money`, `Length`, `Time`, `2D Shapes`, `Data Analysis` | Official topic heading with the numeric prefix removed. |
| 7 | `code` | string | never | `^[0-9]+\.[0-9]+$` (e.g. `1.1`, `2.5`) | Official item code scoped **per level + topic** — codes restart under each topic. Uniqueness constraint is on `(level, learning_area, sub_strand, topic, code, subtopic)`, never on `code` alone. |
| 8 | `subtopic` | string | never | Free text; max observed length 224 chars; 23 rows contain `;` | The learning point. Bullet sub-details from the official document are joined with `;`. Superscript units are written with Unicode superscript glyphs (`cm²`, `m²`, `cm³`, `m³`, `^s` where applicable). |
| 9 | `source_reference` | string | never | 14 distinct values (one per page 31–44), e.g. `MOE 2021 Primary Mathematics Syllabus (Primary One to Six), Updated October 2025, Section 5 "Content by Level", p. 35` | Page-level provenance into the official document. Pages referenced: 31–44 inclusive. |
| 10 | `source_url` | string (URL) | never | 1 distinct value (the official MOE PDF) | The exact official PDF used for extraction (see README → Source and provenance). SHA-256 of that PDF: see `DATASET.md`. |
| 11 | `verification_status` | string (enum) | never | `verified` (only value in v1.0.0/v1.0.1) | Row was manually checked against the official PDF by the PSLE Hero Editorial Team (see README → Verification methodology). No `unverified` row is published. |

## Hard constraints (enforced in the build; independently re-checked 2026-11-12)

- Row count == 202; per-level counts as above; per-strand counts as above.
- No empty/null cells in any of the 11 fields (202 × 11 = 2,222 non-empty cells).
- Duplicate detection across `(level, topic, code, subtopic)` → 0 duplicates.
- CSV ↔ JSON equivalence: all 202 records identical (multiset comparison, all fields).
- `source_url` is single-valued; `verification_status` is single-valued (`verified`).

## What is deliberately NOT in the data

- **Foundation Mathematics** sections (pp. 45–50 of the official document) — excluded as a subset of Standard Mathematics.
- MOE's descriptive aims, pedagogy, assessment guidance, examples and glossaries — only syllabus *facts* are captured.
- Any product identifiers, prices, or marketing copy.

## Encoding and tooling notes

- CSV is UTF-8 without BOM; JSON is UTF-8. Parse with an RFC 4180-compliant parser.
- Mathematical symbols were written with Unicode glyphs; the source PDF stores three symbol items as
  font-private (SymbolMT) codepoints, which extraction maps manually — see `CHANGELOG.md` (v1.0.0)
  and `DATASET.md` (audit results) for the affected rows and the automated-probe outcome.
