# Theology Corpus — Integration Status

**Last Updated:** 2026-11-17 (`v2026.11.0`)
**Status:** Repaired — zero gitlinks/submodules; checksummed CCEL & Project Gutenberg collections ready for sparse-checkout import by [`ruralpeds/theograph`](https://github.com/ruralpeds/theograph).

---

## What Changed in `v2026.11.0`

Prior to `v2026.11.0`, this repository contained **30 gitlinks** (`160000` tree entries), only **11** of which were registered in `.gitmodules`. Running `git submodule update --init` failed, and cloning left unmapped text and lexicon directories (`texts/hebrew/morphhb`, `texts/greek-nt/sblgnt`, `texts/greek-nt/nestle-1904`, `texts/greek-nt/byzantine`, `texts/greek-nt/opengnt`, `lexicons/greek/abbott-smith`, etc.) empty.

In `v2026.11.0` (Prerequisite P2 of `THEOGRAPH_FIX_SPRINT_PLAN.md`):

1. **Archived all 30 former gitlinks** in [`references/UPSTREAM_CANDIDATES.md`](references/UPSTREAM_CANDIDATES.md) with their exact former paths, 40-character commit SHAs, canonical upstream GitHub URLs, license notes, and `theograph` integration status.
2. **Removed all 30 gitlinks and `.gitmodules`** (`git ls-files --stage | awk '$1 == "160000"'` is now empty).
3. **Generated [`references/MANIFEST.tsv`](references/MANIFEST.tsv)** recording exact byte sizes, SHA-256 checksums, collection identifiers, canonical source URLs, and license notes for all **367** files stored in this repository.
4. **Documented CCEL and Project Gutenberg license boundaries** for public-repository hosting and downstream ingestion.

---

## What Is Stored in `timothyhartzog/theology-corpus`

Only the files unique to this repository are stored here:

| Path | Description | Count / Size |
|---|---|---|
| `references/ccel/authors/<author>/<work>.xml` | CCEL Theological Markup Language (ThML) XML editions | 179 files (526,548,552 bytes / 502.16 MiB) |
| `references/gutenberg/<Author>/pg<id>.epub` | Project Gutenberg theological EPUB editions | 188 files (119,984,100 bytes / 114.43 MiB) |
| `references/MANIFEST.tsv` | Deterministic UTF-8 TSV manifest (`path`, `bytes`, `sha256`, `collection`, `source_url`, `license_note`) | 367 file rows + 1 header row |
| `references/UPSTREAM_CANDIDATES.md` | Complete record of all 30 removed gitlinks and candidate pins for `theograph` Phases 06/07 | 30 former gitlinks (20 unique commits) |

---

## How `ruralpeds/theograph` Integrates With This Repository

`ruralpeds/theograph` uses `data/SOURCES.yaml` + `scripts/fetch-sources.sh` as the **single source of truth** for all external data:

1. **Direct Upstream Fetching for Biblical & Lexical Repos:**
   `ruralpeds/theograph` does **not** rely on submodules inside `theology-corpus`. Instead, `data/SOURCES.yaml` pins each upstream biblical text and lexicon repository directly at the same immutable commit SHAs (`openscriptures/morphhb` @ `3d15126fb1...`, `biblicalhumanities/Nestle1904` @ `713f28a3b7...`, `LogosBible/SBLGNT` @ `c4d241a9c1...`, `byztxt/byzantine-majority-text` @ `27a45ff1b7...`, `STEPBible/STEPBible-Data` @ `b99716b0cd...`, `eliranwong/OpenGNT` @ `0029589ccc...`, `openscriptures/strongs` @ `0acd2f251c...`, `translatable-exegetical-tools/Abbott-Smith` @ `8c00cb2447...`, and `theographic-bible-metadata` @ `2bd4da0d24...`).
   Additional upstream repos formerly linked here—including `Clear-Bible/macula-greek`, `Clear-Bible/macula-hebrew`, `helmadik/LSJLogeion` (`lsj-unicode`), `PerseusDL/lexica` (`perseus-lexica`), `openscriptures/HebrewLexicon` (`bdb`), `annotation/text-fabric`, and `proiel/proiel-treebank`—are cataloged with their exact 40-char SHAs in [`references/UPSTREAM_CANDIDATES.md`](references/UPSTREAM_CANDIDATES.md) for `THEOGRAPH_BUILD_PLAN.md` Phases 06 and 07.

2. **Sparse Checkout of `theology-corpus` (`ccel-thml` and `gutenberg-epub`):**
   `scripts/fetch-sources.sh` fetches `timothyhartzog/theology-corpus` at the pinned commit for `v2026.11.0` into `${CORPUS_PATH}` using sparse checkout (`references/ccel`, `references/gutenberg`, `references/MANIFEST.tsv`), and then populates upstream biblical/lexical checkouts alongside it without gitlink conflicts.

---

## Licensing Notes for Public Hosting & Downstream Redistribution

- **`ccel-thml` (`references/ccel/`):**
  `Public-Domain-US text; CCEL ThML markup non-commercial/educational per CCEL terms (verify per-work status)`
  While most underlying historical works in CCEL are in the US public domain, CCEL claims copyright in its electronic ThML editions, `<scripRef>` markup, and staff descriptions (`https://ccel.org/about/copyright.html`). Personal, educational, and non-commercial use is permitted free of charge; **commercial redistribution of CCEL's ThML markup requires permission from CCEL** (and individual files should be checked for any third-party publisher copyright notices). Note that `timothyhartzog/theology-corpus` is a public repository.
- **`gutenberg-epub` (`references/gutenberg/`):**
  `Public-Domain-US + Project Gutenberg License`
  Underlying texts are in the US public domain; redistribution bearing the Project Gutenberg name/headers is governed by the Project Gutenberg License (`https://www.gutenberg.org/policy/license.html`).
