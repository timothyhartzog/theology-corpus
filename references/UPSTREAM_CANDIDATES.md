# Upstream Repository Candidates (Former Gitlinks)

Prior to `v2026.11.0`, `timothyhartzog/theology-corpus` recorded **30 gitlinks** (`160000` tree entries across **20 unique upstream commits**), of which only **11** were mapped in `.gitmodules`. As a result, `git submodule update --init` failed and unmapped text/lexicon directories cloned empty.

Per Prerequisite P2 of `THEOGRAPH_FIX_SPRINT_PLAN.md`, all 30 gitlinks and `.gitmodules` have been removed from `timothyhartzog/theology-corpus`. `ruralpeds/theograph` fetches external biblical, lexical, and linguistic repositories directly from upstream via `data/SOURCES.yaml` and `scripts/fetch-sources.sh`.

This file preserves the exact path, 40-character commit SHA, resolved upstream repository URL, fork URL, license/commercial-use notes, and `theograph` integration status for **all 30 former gitlinks** so nothing is lost and future phases (`THEOGRAPH_BUILD_PLAN.md` Phases 06, 07, 08, and 10) can pin upstream commits directly.

---

## Complete Inventory of All 30 Former Gitlinks

Sorted deterministically by former repository path (`git ls-files --stage | awk '$1 == "160000"'`):

| # | Former Path | Pinned Commit SHA (40-char) | Upstream Repository URL | `.gitmodules` | License & Commercial Status | `theograph` Status (`data/SOURCES.yaml` / Build Plan) |
|---|---|---|---|---|---|---|
| 1 | `data/stepbible` | `211dd7bf44ab01c8ab35cde61298b7f3d8e8e5b3` | https://github.com/STEPBible/STEPBible-Data | No (dup of #2) | `CC-BY-4.0` (`commercial_ok: true`) | Duplicate path; `SOURCES.yaml` pins `stepbible` (`b99716b0cddb648ddb95cc786a197180f2f97d48`) at `${CORPUS_PATH}/data/stepbible-data` |
| 2 | `data/stepbible-data` | `211dd7bf44ab01c8ab35cde61298b7f3d8e8e5b3` | https://github.com/STEPBible/STEPBible-Data | Yes | `CC-BY-4.0` (`commercial_ok: true`) | **Pinned in `SOURCES.yaml`** as `stepbible` (updated commit `b99716b0cddb648ddb95cc786a197180f2f97d48`) |
| 3 | `frameworks/openscriptures` | `da6ba3932b34287325f10e71ce34104e8a0ba03a` | https://github.com/openscriptures/openscriptures | No | Unspecified / legacy web framework (`commercial_ok: false` until verified) | Not used by `theograph` (archived legacy Django app; not a corpus dataset) |
| 4 | `frameworks/text-fabric` | `ed3a88c2cbf55daa526ee652531da762bbd38d3b` | https://github.com/annotation/text-fabric | No | `MIT` (`commercial_ok: true`; note ETCBC BHSA/DSS data corpora are `CC-BY-NC-4.0`) | **Candidate tooling (opt-in)**: Python library for reading opt-in ETCBC BHSA / DSS Text-Fabric datasets noted in `THEOGRAPH_BUILD_PLAN.md` §4 (Phase 07 uses MACULA by default instead of BHSA for open licensing) |
| 5 | `lexicons/greek/abbott-smith` | `8c00cb244761aa23659421a8cbbbf7a3b27b7d59` | https://github.com/translatable-exegetical-tools/Abbott-Smith | No | `CC-BY-SA-4.0` (`commercial_ok: true`) | **Pinned in `SOURCES.yaml`** as `abbott-smith` at this exact SHA (`8c00cb244761aa23659421a8cbbbf7a3b27b7d59`) |
| 6 | `lexicons/greek/greek-resources` | `dd5a2fd530ab3c6b748c174cec38966c356d8111` | https://github.com/openscriptures/GreekResources | No (dup of #7) | `CC-BY-4.0` scripts/mappings (`commercial_ok: true`; excludes restricted CCAT LXX text) | **Candidate helper for main-plan Phase 06** (Septuagint / Greek lexical utilities; duplicate path of #7) |
| 7 | `lexicons/greek/greek-resources-repo` | `dd5a2fd530ab3c6b748c174cec38966c356d8111` | https://github.com/openscriptures/GreekResources | Yes | `CC-BY-4.0` scripts/mappings (`commercial_ok: true`; excludes restricted CCAT LXX text) | **Candidate helper for main-plan Phase 06** (Septuagint / Greek lexical utilities) |
| 8 | `lexicons/greek/lsj-unicode` | `3f50db8db4ca63f7b22a2cd51af4471b6b3b0c73` | https://github.com/helmadik/LSJLogeion | No | `CC-BY-SA-4.0` (`commercial_ok: true`) | **Candidate for main-plan Phase 06** (Unicode Liddell-Scott-Jones Greek lexicon for LXX, Apostolic Fathers, Patristic Greek, and Second Temple Greek lemmas) |
| 9 | `lexicons/greek/perseus-lexica` | `934b055f530b5fd945e3344c2a9fe03c0d023dda` | https://github.com/PerseusDL/lexica | No (dup of #12) | `CC-BY-SA-4.0` (`commercial_ok: true`) | **Candidate for main-plan Phase 06** (Perseus Digital Library Greek & Latin lexica: LSJ, Middle Liddell, Autenrieth, Slater, Lewis & Short for Vulgate/Patristic lemmatization) |
| 10 | `lexicons/hebrew/bdb` | `21c9add13bc727d3a951361778e97e3ff7afd1ce` | https://github.com/openscriptures/HebrewLexicon | No (dup of #11) | `CC-BY-4.0` markup over Public-Domain BDB & Strong's (`commercial_ok: true`) | **Candidate for main-plan Phase 06 / Phase 08** (Brown-Driver-Briggs Hebrew & Aramaic Lexicon XML with Strong's and TWOT cross-links, complementing UBS SDBH) |
| 11 | `lexicons/hebrew/hebrew-lexicon` | `21c9add13bc727d3a951361778e97e3ff7afd1ce` | https://github.com/openscriptures/HebrewLexicon | Yes | `CC-BY-4.0` markup over Public-Domain BDB & Strong's (`commercial_ok: true`) | Duplicate path of #10 (`lexicons/hebrew/bdb`); **Candidate for main-plan Phase 06 / Phase 08** |
| 12 | `lexicons/lexica` | `934b055f530b5fd945e3344c2a9fe03c0d023dda` | https://github.com/PerseusDL/lexica | Yes | `CC-BY-SA-4.0` (`commercial_ok: true`) | Duplicate path of #9 (`lexicons/greek/perseus-lexica`); **Candidate for main-plan Phase 06** |
| 13 | `lexicons/strongs` | `0acd2f251c2d35ff8db2dece4e0593979d3ac223` | https://github.com/openscriptures/strongs | No | `Public-Domain` (`commercial_ok: true`) | **Pinned in `SOURCES.yaml`** as `strongs` at this exact SHA (`0acd2f251c2d35ff8db2dece4e0593979d3ac223`, path `${DATA_PATH}/lexicon`) |
| 14 | `references/awesome-bible` | `4349103e4957491237cc5d624d0b7f226e80c55f` | https://github.com/biblenerd/awesome-bible-developer-resources | No (dup of #15) | `CC0-1.0` (`commercial_ok: true`) | Reference bibliography only; not ingested by `theograph` (duplicate path of #15) |
| 15 | `references/awesome-bible-dev-resources` | `4349103e4957491237cc5d624d0b7f226e80c55f` | https://github.com/biblenerd/awesome-bible-developer-resources | Yes | `CC0-1.0` (`commercial_ok: true`) | Reference bibliography only; not ingested by `theograph` |
| 16 | `references/greek-mappings` | `4a76cbf24aec06dd8ad109b544ef9574741f75e6` | https://github.com/biblicalhumanities/greek-new-testament | No (dup of #22) | Mixed (`SBLGNT`, `Public-Domain` Nestle1904, `CC-BY-NC-SA-3.0` PROIEL transform) | Obsolete upstream (superseded by `Clear-Bible/macula-greek` in Phase 07; duplicate path of #22) |
| 17 | `references/proiel-treebank` | `8e388967a1335ed12335ddc655fe46993ee7d57a` | https://github.com/proiel/proiel-treebank | No | `CC-BY-NC-SA-3.0` / non-commercial (`commercial_ok: false`) | **Candidate opt-in source (`THEOGRAPH_BUILD_PLAN.md` §4)**: PROIEL dependency treebank (Greek NT, Latin Vulgate, Gothic, Classical Greek/Latin); opt-in only (`commercial_ok: false`), never bundled in release artifacts |
| 18 | `references/theographic-bible-metadata` | `2bd4da0d245c007a305602dd193de6606422e82b` | https://github.com/robertrouse/theographic-bible-metadata | Yes | `CC-BY-SA-4.0` (`commercial_ok: true`) | **Pinned in `SOURCES.yaml`** as `theographic` at this exact SHA (`2bd4da0d245c007a305602dd193de6606422e82b`, via fork `https://github.com/timothyhartzog/theographic-bible-metadata`, path `${DATA_PATH}/theographic`) |
| 19 | `references/theographic-web` | `c4fdea2406a264324af8f9417579ec95262a1a41` | https://github.com/robertrouse/theographic-web | Yes | `GPL-3.0` (`commercial_ok: true`, copyleft web UI) | Web application frontend for Theographic metadata; not ingested by `theograph` |
| 20 | `texts/greek-nt/byzantine` | `27a45ff1b7be6c17ccbfeac414f3f55732ae8e28` | https://github.com/byztxt/byzantine-majority-text | No | `Public-Domain` (`commercial_ok: true`) | **Pinned in `SOURCES.yaml`** as `byzantine` at this exact SHA (`27a45ff1b7be6c17ccbfeac414f3f55732ae8e28`) |
| 21 | `texts/greek-nt/byzantine-majority` | `27a45ff1b7be6c17ccbfeac414f3f55732ae8e28` | https://github.com/byztxt/byzantine-majority-text | Yes | `Public-Domain` (`commercial_ok: true`) | Duplicate path of #20 (`texts/greek-nt/byzantine`); **Pinned in `SOURCES.yaml`** as `byzantine` |
| 22 | `texts/greek-nt/greek-nt-resources` | `4a76cbf24aec06dd8ad109b544ef9574741f75e6` | https://github.com/biblicalhumanities/greek-new-testament | Yes | Mixed (`SBLGNT`, `Public-Domain` Nestle1904, `CC-BY-NC-SA-3.0` PROIEL transform) | Obsolete upstream (marked obsolete in upstream README; superseded by `Clear-Bible/macula-greek` in Phase 07) |
| 23 | `texts/greek-nt/macula` | `453876a98c049b08b54375918d04ead2a3d879e7` | https://github.com/Clear-Bible/macula-greek | No (dup of #24) | `CC-BY-4.0` (`commercial_ok: true`; includes Nestle1904 & SBLGNT lowfat trees) | **Candidate for main-plan Phase 07 (`macula-greek`)**: Greek NT syntax trees, clause/phrase roles, participant referents, and Louw-Nida domains |
| 24 | `texts/greek-nt/macula-greek-full` | `453876a98c049b08b54375918d04ead2a3d879e7` | https://github.com/Clear-Bible/macula-greek | Yes | `CC-BY-4.0` (`commercial_ok: true`; includes Nestle1904 & SBLGNT lowfat trees) | Duplicate path of #23; **Candidate for main-plan Phase 07 (`macula-greek`)** |
| 25 | `texts/greek-nt/nestle-1904` | `713f28a3b7d4d66132f5aa809fa223fe79762e5d` | https://github.com/biblicalhumanities/Nestle1904 | No | `Public-Domain` (`commercial_ok: true`) | **Pinned in `SOURCES.yaml`** as `nestle-1904` at this exact SHA (`713f28a3b7d4d66132f5aa809fa223fe79762e5d`) |
| 26 | `texts/greek-nt/opengnt` | `0029589cccd50bd48b1941aa041a956de6c29ac4` | https://github.com/eliranwong/OpenGNT | No | `CC-BY-NC-SA-4.0` (`commercial_ok: false`, non-commercial opt-in) | **Pinned in `SOURCES.yaml`** as `opengnt` at this exact SHA (`0029589cccd50bd48b1941aa041a956de6c29ac4`) |
| 27 | `texts/greek-nt/sblgnt` | `aaed91e57c8e4a8dc9a2383e129ca5e75fe6393d` | https://github.com/morphgnt/sblgnt | No | `CC-BY-SA-3.0` MorphGNT morphology + `SBLGNT-EULA` text (`commercial_ok: true` — verify both) | **`SOURCES.yaml` pins `sblgnt`** (`https://github.com/LogosBible/SBLGNT` @ `c4d241a9c1c479a55b989ba35a4976c1d0b8052c`); `morphgnt/sblgnt` @ `aaed91e57c8e4a8dc9a2383e129ca5e75fe6393d` is a **candidate for main-plan Phase 03 / Phase 10** (MorphGNT 7-column parse codes) |
| 28 | `texts/hebrew/macula` | `47db250bd55d0d8577f2a94fba114ef16c35b23c` | https://github.com/Clear-Bible/macula-hebrew | No (dup of #29) | `CC-BY-4.0` (`commercial_ok: true`; syntax over Public-Domain WLC) | **Candidate for main-plan Phase 07 (`macula-hebrew`)**: Hebrew/Aramaic WLC syntax trees, clause/phrase roles, participant referents, and SDBH lexical domains |
| 29 | `texts/hebrew/macula-hebrew-full` | `47db250bd55d0d8577f2a94fba114ef16c35b23c` | https://github.com/Clear-Bible/macula-hebrew | Yes | `CC-BY-4.0` (`commercial_ok: true`; syntax over Public-Domain WLC) | Duplicate path of #28; **Candidate for main-plan Phase 07 (`macula-hebrew`)** |
| 30 | `texts/hebrew/morphhb` | `3d15126fb1ef74867fc1434be1942e837932691f` | https://github.com/openscriptures/morphhb | No | `CC-BY-4.0` (`commercial_ok: true`) | **Pinned in `SOURCES.yaml`** as `morphhb` at this exact SHA (`3d15126fb1ef74867fc1434be1942e837932691f`) |

---

## Key Candidates for `THEOGRAPH_BUILD_PLAN.md` Phases 06 & 07

The following unpinned repositories from the table above are primary candidates when expanding `ruralpeds/theograph/data/SOURCES.yaml` in the main linguistic build plan:

### 1. MACULA Syntax Treebanks (Main-Plan Phase 07)
- **MACULA Greek (`macula-greek`)**
  - **Upstream:** `https://github.com/Clear-Bible/macula-greek` (fork: `https://github.com/timothyhartzog/macula-greek`)
  - **Pinned SHA:** `453876a98c049b08b54375918d04ead2a3d879e7`
  - **Former Paths:** `texts/greek-nt/macula`, `texts/greek-nt/macula-greek-full`
  - **License:** `CC-BY-4.0` (`commercial_ok: true`; verify underlying SBLGNT component notice in `LICENSE.md`)
  - **Role:** Lowfat XML clause/phrase syntax trees over Nestle 1904 and SBLGNT, syntactic roles, participant referents, and Louw-Nida semantic domain tags (`crates/theograph-syntax/src/macula.rs`).
- **MACULA Hebrew (`macula-hebrew`)**
  - **Upstream:** `https://github.com/Clear-Bible/macula-hebrew` (fork: `https://github.com/timothyhartzog/macula-hebrew`)
  - **Pinned SHA:** `47db250bd55d0d8577f2a94fba114ef16c35b23c`
  - **Former Paths:** `texts/hebrew/macula`, `texts/hebrew/macula-hebrew-full`
  - **License:** `CC-BY-4.0` (`commercial_ok: true`; over Public-Domain Westminster Leningrad Codex)
  - **Role:** Lowfat XML clause/phrase syntax trees over WLC, syntactic roles, participant referents, and SDBH (`sdbh` / `lexdomain`) annotations (`crates/theograph-syntax/src/macula.rs`).

### 2. Classical, Patristic & Biblical Lexica (Main-Plan Phase 06 & Phase 08)
- **LSJ Unicode (`lexicons/greek/lsj-unicode`)**
  - **Upstream:** `https://github.com/helmadik/LSJLogeion` (fork: `https://github.com/timothyhartzog/LSJLogeion`)
  - **Pinned SHA:** `3f50db8db4ca63f7b22a2cd51af4471b6b3b0c73`
  - **License:** `CC-BY-SA-4.0` (`commercial_ok: true`)
  - **Role:** Unicode Liddell-Scott-Jones Greek-English Lexicon (Logeion edition) for non-NT Greek lemmas across Septuagint, Apostolic Fathers, Patristic Greek, Josephus, and Philo in Phase 06.
- **Perseus Lexica (`lexicons/greek/perseus-lexica`, `lexicons/lexica`)**
  - **Upstream:** `https://github.com/PerseusDL/lexica` (fork: `https://github.com/timothyhartzog/lexica`)
  - **Pinned SHA:** `934b055f530b5fd945e3344c2a9fe03c0d023dda`
  - **License:** `CC-BY-SA-4.0` (`commercial_ok: true`)
  - **Role:** TEI XML Greek and Latin lexica (LSJ, Middle Liddell, Lewis & Short Latin Dictionary) supporting Greek and Clementine Vulgate Latin lemma glosses in Phase 06.
- **Open Scriptures Hebrew Lexicon / BDB (`lexicons/hebrew/bdb`, `lexicons/hebrew/hebrew-lexicon`)**
  - **Upstream:** `https://github.com/openscriptures/HebrewLexicon` (fork: `https://github.com/timothyhartzog/HebrewLexicon`)
  - **Pinned SHA:** `21c9add13bc727d3a951361778e97e3ff7afd1ce`
  - **License:** `CC-BY-4.0` markup over Public-Domain Brown-Driver-Briggs & Strong's (`commercial_ok: true`)
  - **Role:** Structured BDB Hebrew/Aramaic lexical definitions and Strong's mappings supplementing `strongs` and Phase 08 UBS SDBH domains.

### 3. Opt-In Treebank & Framework Candidates (`THEOGRAPH_BUILD_PLAN.md` §4)
- **PROIEL Treebank (`references/proiel-treebank`)**
  - **Upstream:** `https://github.com/proiel/proiel-treebank` (fork: `https://github.com/timothyhartzog/proiel-treebank`)
  - **Pinned SHA:** `8e388967a1335ed12335ddc655fe46993ee7d57a`
  - **License:** `CC-BY-NC-SA-3.0` (`commercial_ok: false` — non-commercial opt-in only)
  - **Role:** Dependency treebank for Greek NT, Latin Vulgate, and Classical texts; must retain `commercial_ok: false` and `status: opt-in` if added to `SOURCES.yaml`.
- **Text-Fabric (`frameworks/text-fabric`)**
  - **Upstream:** `https://github.com/annotation/text-fabric` (fork: `https://github.com/timothyhartzog/text-fabric`)
  - **Pinned SHA:** `ed3a88c2cbf55daa526ee652531da762bbd38d3b`
  - **License:** `MIT` (`commercial_ok: true` for the Python library; note ETCBC `bhsa` and `dss` corpora are `CC-BY-NC-4.0`, `commercial_ok: false`)
  - **Role:** Corpus reader framework if opt-in ETCBC BHSA or Dead Sea Scrolls datasets are enabled in future phases.

---

## Additional Repositories Previously Listed in `MANIFEST.md` (Never Added as Gitlinks)

For completeness, the legacy `MANIFEST.md` also named four upstream repositories that were never committed as gitlinks in `timothyhartzog/theology-corpus`:

| Upstream Repository | Legacy Planned Path | Notes |
|---|---|---|
| https://github.com/openscriptures/tsk | `references/tsk` | `theograph` ingests TSK via `tsk` entry in `data/SOURCES.yaml` (`${DATA_PATH}/cross_refs/tsk.csv`) |
| https://github.com/morphgnt/tischendorf-2.8 | `texts/greek-nt/tischendorf` | Tischendorf 8th edition Greek NT (`CC-BY-SA-3.0` / Public-Domain text); optional Phase 10 collation witness |
| https://github.com/unfoldingWord/hbo_uhb | `texts/hebrew/uhb` | unfoldingWord Hebrew Bible (`CC-BY-SA-4.0`) |
| https://github.com/unfoldingWord/el-x-koine_ugnt | `texts/greek-nt/ugnt` | unfoldingWord Greek New Testament (`CC-BY-SA-4.0`) |
| https://github.com/crosswire/sword | `frameworks/sword` | CrossWire SWORD C++ engine (`GPL-2.0`); not used by `theograph` |
