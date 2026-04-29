# Theology Corpus - All Related Repositories

Complete inventory of theology and biblical studies repositories from timothyhartzog's GitHub, with integration status.

## Greek New Testament

| Repository | Purpose | Status | Path |
|------------|---------|--------|------|
| [macula-greek](https://github.com/timothyhartzog/macula-greek) | Syntax trees, morphology, linguistic annotations for Greek Bible | ⏳ Partial | `texts/greek-nt/macula-greek` |
| [byzantine-majority-text](https://github.com/timothyhartzog/byzantine-majority-text) | Byzantine Majority text with morphology & Strong's | ⏳ TODO | `texts/greek-nt/byzantine-majority` |
| [greek-new-testament](https://github.com/timothyhartzog/greek-new-testament) | Greek NT texts and resources | ⏳ TODO | `texts/greek-nt/greek-nt-repo` |
| [Nestle1904](https://github.com/timothyhartzog/Nestle1904) | 1904 Nestle edition with morphology | ✅ READY | `texts/greek-nt/nestle-1904` |
| [sblgnt](https://github.com/timothyhartzog/sblgnt) | SBL Greek NT with morphological tagging | ✅ READY | `texts/greek-nt/sblgnt` |
| [OpenGNT](https://github.com/timothyhartzog/OpenGNT) | Open Greek NT Project (NA28/NA27 equivalent) | ✅ READY | `texts/greek-nt/opengnt` |

## Hebrew Bible

| Repository | Purpose | Status | Path |
|------------|---------|--------|------|
| [macula-hebrew](https://github.com/timothyhartzog/macula-hebrew) | Syntax trees, morphology for Hebrew Bible | ⏳ Partial | `texts/hebrew/macula-hebrew` |
| [morphhb](https://github.com/timothyhartzog/morphhb) | Morphological Hebrew Bible (Open Scriptures) | ✅ READY | `texts/hebrew/morphhb` |

## Lexicons & Language Resources

| Repository | Purpose | Status | Path |
|------------|---------|--------|------|
| [Abbott-Smith](https://github.com/timothyhartzog/Abbott-Smith) | Abbott-Smith's Manual Greek Lexicon | ✅ READY | `lexicons/greek/abbott-smith` |
| [LSJLogeion](https://github.com/timothyhartzog/LSJLogeion) | Liddell-Scott-Jones Lexicon (Logeion edition) | ⏳ TODO | `lexicons/greek/lsj-logeion` |
| [GreekResources](https://github.com/timothyhartzog/GreekResources) | Resources for Greek texts (Septuagint focused) | ⏳ TODO | `lexicons/greek/greek-resources-repo` |
| [strongs](https://github.com/timothyhartzog/strongs) | Strong's Dictionaries (Hebrew & Greek) | ✅ READY | `lexicons/strongs` |
| [HebrewLexicon](https://github.com/timothyhartzog/HebrewLexicon) | BDB outline with Strong's & Gesenius links | ⏳ TODO | `lexicons/hebrew/hebrew-lexicon` |
| [lexica](https://github.com/timothyhartzog/lexica) | Repository for lexicon text files | ⏳ TODO | `lexicons/lexica` |

## Frameworks & Linguistic Data

| Repository | Purpose | Status | Path |
|------------|---------|--------|------|
| [text-fabric](https://github.com/timothyhartzog/text-fabric) | File format & API for annotated text | ✅ READY | `frameworks/text-fabric` |
| [openscriptures](https://github.com/timothyhartzog/openscriptures) | Open Scriptures framework | ✅ READY | `frameworks/openscriptures` |
| [proiel-treebank](https://github.com/timothyhartzog/proiel-treebank) | PROIEL treebank of ancient Indo-European | ✅ READY | `references/proiel-treebank` |

## Data & Metadata

| Repository | Purpose | Status | Path |
|------------|---------|--------|------|
| [STEPBible-Data](https://github.com/timothyhartzog/STEPBible-Data) | STEP Bible data (CC BY 4.0) | ⏳ TODO | `data/stepbible-data` |
| [theographic-bible-metadata](https://github.com/timothyhartzog/theographic-bible-metadata) | Knowledge graph: biblical people, places, periods | ✅ READY | `references/theographic-bible-metadata` |
| [theographic-web](https://github.com/timothyhartzog/theographic-web) | Linked encyclopedia of biblical resources | ✅ READY | `references/theographic-web` |

## Resource Collections & References

| Repository | Purpose | Status | Path |
|------------|---------|--------|------|
| [awesome-bible-developer-resources](https://github.com/timothyhartzog/awesome-bible-developer-resources) | Curated list of resources for biblical texts & tools | ⏳ TODO | `references/awesome-bible-dev-resources` |
| [greek-mappings](https://github.com/timothyhartzog/greek-mappings) | Greek text mapping resources | ✅ READY | `references/greek-mappings` |

## Status Legend
- ✅ READY: Already integrated or ready to add
- ⏳ TODO: Planned for integration
- ⏳ Partial: Partially cloned or added

## Integration Notes

### Already Integrated
The corpus already contains:
- 179 CCEL ThML XML works (360MB+)
- 285+ theological works from Project Gutenberg
- Greek lexicons: Abbott-Smith, LSJ Unicode, Perseus Lexica
- Hebrew lexicons: BDB, Strong's
- Multiple Greek NT versions with morphology
- Hebrew Bible with morphology
- Text-Fabric framework
- PROIEL treebank
- Theographic metadata & web resources

### Remaining to Add
To complete full integration, the following repos should be added as submodules:
1. `macula-greek` & `macula-hebrew` - Large syntax tree repos
2. `GreekResources`, `HebrewLexicon` - Additional lexicon resources
3. `STEPBible-Data` - STEP Bible structured data
4. `LSJLogeion` - LSJ from Logeion project
5. `byzantine-majority-text` - Byzantine text variant
6. `greek-new-testament` - Additional Greek NT resources
7. `awesome-bible-developer-resources` - Developer tools list

### Performance Notes
Some repos (especially macula-greek, macula-hebrew) are large and clone slowly. Consider cloning on demand or using shallow clones for faster integration.
