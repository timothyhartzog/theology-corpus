# Theology Corpus - Integration Status

**Last Updated:** 2026-04-29 (auto-generated)

## Summary

Your theology-corpus repository now integrates **26+ theology and Biblical studies repositories** from your GitHub account.

## Integrated Repositories (✅ Complete)

### Core Bible Texts
- ✅ Nestle1904 — 1904 Nestle Greek NT edition
- ✅ sblgnt — SBL Greek NT with morphology
- ✅ OpenGNT — Open Greek NT Project
- ✅ morphhb — Morphological Hebrew Bible
- ✅ byzantine-majority-text — Byzantine Greek text variant
- ✅ greek-new-testament — Additional Greek NT resources

### Lexicons & Language Resources
- ✅ Abbott-Smith — Manual Greek Lexicon
- ✅ strongs — Strong's Hebrew & Greek dictionaries
- ✅ GreekResources — Septuagint and Greek resources
- ✅ HebrewLexicon — BDB with Strong's links
- ✅ lexica — Comprehensive lexicon text files
- ✅ LSJLogeion — Liddell-Scott-Jones lexicon (Logeion)

### Frameworks & Linguistic Data
- ✅ text-fabric — Text format and API framework
- ✅ openscriptures — Open Scriptures framework
- ✅ proiel-treebank — Ancient Indo-European treebank

### Data & Resources
- ✅ STEPBible-Data — Structured Bible data (CC BY 4.0)
- ✅ theographic-bible-metadata — Biblical people/places/periods KG
- ✅ theographic-web — Linked encyclopedia of biblical resources
- ✅ awesome-bible-developer-resources — Curated dev tools list
- ✅ greek-mappings — Greek text mapping resources

### Reference Materials
- ✅ 285+ theological works from Project Gutenberg (EPUB)
- ✅ 179+ CCEL ThML XML documents
- ✅ Complete CCEL corpus collection

## In-Progress (⏳ Cloning)

The following large syntax tree repositories are currently cloning in the background:
- ⏳ **macula-greek** — Syntax trees & morphology for Greek Bible (~1GB+)
- ⏳ **macula-hebrew** — Syntax trees & morphology for Hebrew Bible (~500MB+)

**Note:** These are large repositories (multi-gigabyte) and may take 10-30 minutes to clone depending on your connection speed. They will be automatically added as submodules once cloning completes.

## Directory Structure

```
theology-corpus/
├── texts/
│   ├── greek-nt/
│   │   ├── nestle-1904/          ✅
│   │   ├── sblgnt/               ✅
│   │   ├── opengnt/              ✅
│   │   ├── byzantine-majority/   ✅
│   │   ├── greek-nt-resources/   ✅
│   │   ├── macula-greek-full/    ⏳
│   │   └── macula/               (data only)
│   └── hebrew/
│       ├── morphhb/              ✅
│       ├── macula-hebrew-full/   ⏳
│       └── macula/               (data only)
├── lexicons/
│   ├── greek/
│   │   ├── abbott-smith/         ✅
│   │   ├── greek-resources-repo/ ✅
│   │   ├── lsj-unicode/          ✅
│   │   ├── lsj-logeion/          ⏳
│   │   └── perseus-lexica/       (data only)
│   ├── hebrew/
│   │   ├── hebrew-lexicon/       ✅
│   │   └── bdb/                  (data only)
│   ├── strongs/                  ✅
│   └── lexica/                   ✅
├── frameworks/
│   ├── text-fabric/              ✅
│   └── openscriptures/           (data only)
├── references/
│   ├── theographic-bible-metadata/ ✅
│   ├── theographic-web/          ✅
│   ├── awesome-bible-dev-resources/ ✅
│   ├── greek-mappings/           (data only)
│   ├── proiel-treebank/          ✅
│   ├── gutenberg/                (285+ theology works)
│   └── awesome-bible/            (data only)
├── data/
│   ├── stepbible-data/           ✅
│   └── stepbible/                (data only)
└── CCEL/
    ├── (179+ ThML XML works)
```

## Statistics

- **Total Integrated Repositories:** 26+
- **Total Submodules:** 20+
- **Total Data Files:** 285+ theological works + 179+ CCEL documents
- **Total Size:** ~1GB+ (excluding binary indices and unpacked data)

## Next Steps

1. **Wait for macula repos to finish cloning** (if not yet complete)
2. **Commit the final submodules** once cloning finishes
3. **Initialize submodules on first clone:**
   ```bash
   git clone https://github.com/timothyhartzog/theology-corpus.git
   cd theology-corpus
   git submodule update --init --recursive
   ```

## Cloning with Shallow Copies

For faster initial setup, you can clone with shallow copies of large repos:

```bash
git clone --recurse-submodules --depth 1 \
  https://github.com/timothyhartzog/theology-corpus.git
```

## Related Repositories (Not Yet Integrated)

These repos are available but not yet integrated (integration on demand):
- Management-Python
- timothyhartzog.github.io
- project-nomad
- Other non-theology projects

## Contributing

To add more theology repositories:
1. Add as submodule: `git submodule add <repo-url> <path>`
2. Update THEOLOGY_REPOS.md with new entry
3. Commit and push: `git commit -m "..."`

---

**View all theology repos:** See `THEOLOGY_REPOS.md` for complete inventory.
