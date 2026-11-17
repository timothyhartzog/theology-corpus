# Theology Corpus Manifest

**Repository:** `https://github.com/timothyhartzog/theology-corpus`
**Release:** `v2026.11.0` (2026-11-17)
**Primary Consumer:** [`ruralpeds/theograph`](https://github.com/ruralpeds/theograph)

---

## Overview

`timothyhartzog/theology-corpus` stores curated Christian theological texts in two collections (`references/ccel/` and `references/gutenberg/`) together with a deterministic, checksummed file manifest (`references/MANIFEST.tsv`) and an archive of upstream biblical/lexical repository pins (`references/UPSTREAM_CANDIDATES.md`).

All Git submodules and unmapped gitlinks (`160000` tree entries) previously present in this repository were removed in `v2026.11.0`. Upstream biblical editions, lexicons, and syntax treebanks are **not** stored here; instead, `ruralpeds/theograph` fetches them directly from their canonical upstream repositories at immutable commit SHAs declared in `data/SOURCES.yaml` via `scripts/fetch-sources.sh`.

---

## Repository Contents

```
theology-corpus/
├── MANIFEST.md                        # Repository overview, collection counts, and licensing terms
├── INTEGRATION_STATUS.md              # Architecture and integration contract with ruralpeds/theograph
├── THEOLOGY_REPOS.md                  # Legacy fork inventory (superseded by references/UPSTREAM_CANDIDATES.md)
└── references/
    ├── MANIFEST.tsv                   # Deterministic UTF-8 TSV manifest (367 files: bytes, sha256, URLs, licenses)
    ├── UPSTREAM_CANDIDATES.md         # Archive of all 30 former gitlinks, 40-char SHAs, URLs, and licenses
    ├── ccel/
    │   └── authors/<author>/<work>.xml  # 179 CCEL Theological Markup Language (ThML) XML editions
    └── gutenberg/
        └── <Author_Folder>/pg<id>.epub  # 188 Project Gutenberg EPUB editions
```

### Collection Summary (`references/MANIFEST.tsv`)

| Collection Slug | Directory | Format | File Count | Total Bytes | Size (MiB) |
|---|---|---|---:|---:|---:|
| `ccel-thml` | `references/ccel/` | ThML XML (`.xml`) | 179 | 526,548,552 | 502.16 |
| `gutenberg-epub` | `references/gutenberg/` | EPUB (`.epub`) | 188 | 119,984,100 | 114.43 |
| **Total** | | | **367** | **646,532,652** | **616.58** |

Every file across both collections is indexed in `references/MANIFEST.tsv` (sorted deterministically by `path`) with columns:

```
path	bytes	sha256	collection	source_url	license_note
```

---

## Licensing and Terms of Use

> **Important:** `timothyhartzog/theology-corpus` is a **public** GitHub repository. Downstream users and automated pipelines (including `ruralpeds/theograph`) must respect the distinct terms governing each collection below.

### 1. Christian Classics Ethereal Library (`ccel-thml` — `references/ccel/`)

- **Manifest license string:**
  `Public-Domain-US text; CCEL ThML markup non-commercial/educational per CCEL terms (verify per-work status)`
- **Underlying texts vs. CCEL ThML editions:**
  - Most underlying historical works distributed by the Christian Classics Ethereal Library (`https://ccel.org`) are in the **public domain in the United States** (as reflected in `<DC.Rights>` headers within individual files, though a small number of CCEL-hosted works carry separate publisher copyrights by permission and copyright status varies outside the US).
  - However, the **electronic ThML editions themselves**—including CCEL's Theological Markup Language (`ThML`) XML tagging, `<scripRef>` scripture-reference encoding, editorial descriptions (`CCEL Staff` notes in `<generalInfo>`), formatting, and site metadata (`<!-- Copyright Christian Classics Ethereal Library -->`)—are copyrighted by the Christian Classics Ethereal Library.
- **Permitted and restricted uses under CCEL's published policy (`https://ccel.org/about/copyright.html`):**
  - CCEL permits free **personal, educational, and non-profit / non-commercial** use of its electronic editions.
  - **Commercial use or commercial redistribution** of CCEL's ThML markup and electronic editions **requires prior written permission from CCEL** (or stripping/replacing CCEL-specific markup and editorial additions after verifying the underlying print source is in the public domain).
  - Because this repository is public, `ruralpeds/theograph` tracks `ccel-thml` with `license_verified: false` / non-commercial safeguards until per-work rights and distribution terms are explicitly verified.

### 2. Project Gutenberg (`gutenberg-epub` — `references/gutenberg/`)

- **Manifest license string:**
  `Public-Domain-US + Project Gutenberg License`
- **Terms (`https://www.gutenberg.org/policy/license.html`):**
  - The 188 theological EPUBs in `references/gutenberg/` (`pg<id>.epub`, sourced from `https://www.gutenberg.org/ebooks/<id>`) are works in the **United States public domain** packaged under the **Project Gutenberg License**.
  - Under the Project Gutenberg License, redistribution that retains the "Project Gutenberg" trademark/headers is subject to Project Gutenberg's license conditions (royalty/reporting rules apply to commercial redistribution under the Project Gutenberg name unless the Project Gutenberg trademark and boilerplate headers/footers are stripped to leave pure public-domain text).
  - Users outside the United States must verify copyright status in their jurisdiction before copying or redistributing.

---

## Sparse Checkout Usage (`ruralpeds/theograph`)

Consumers do not need a full working-tree clone of repository history and never run `git submodule`. To fetch only the collections and manifest at the pinned release commit:

```bash
git clone --filter=blob:none --no-checkout https://github.com/timothyhartzog/theology-corpus
cd theology-corpus
git sparse-checkout set references/ccel references/gutenberg references/MANIFEST.tsv
git checkout v2026.11.0
```

For the upstream biblical texts, lexicons, and syntax datasets used alongside this repository (`morphhb`, `nestle-1904`, `sblgnt`, `byzantine`, `stepbible`, `opengnt`, `strongs`, `abbott-smith`, `theographic`, MACULA, LSJ, BDB, Perseus, PROIEL, etc.), see [`references/UPSTREAM_CANDIDATES.md`](references/UPSTREAM_CANDIDATES.md) and `data/SOURCES.yaml` in [`ruralpeds/theograph`](https://github.com/ruralpeds/theograph).
