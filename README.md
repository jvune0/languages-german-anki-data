# anki-data

Vocabulary card files and word log for the German Anki card generator.

## ⚠️ Clone name matters

This repo **must** be cloned as `anki-data/`, as a sibling of the config repo — regardless of what either repo is named on GitHub:

```
<parent>/
  anki-instructions/   ← config repo (CLAUDE.md, setup.sh, …)
  anki-data/           ← this repo  ← clone it exactly here
```

The `setup.sh` in the config repo looks for `../anki-data/` relative to itself. A different folder name will break the symlinks.

```bash
git clone <config-repo-url> anki-instructions
git clone <this-repo-url>   anki-data
cd anki-instructions
bash setup.sh
```

For a brand-new machine with no existing data, use `--init` instead:

```bash
git clone <config-repo-url> anki-instructions
cd anki-instructions
bash setup.sh --init   # creates a fresh anki-data/ next to this folder
```

## Contents

```
cards/
  words_log.csv          # master log of every word added, across all weeks
  week_<YYYY>-W<WW>/
    <word>_<YYYYMMDD>.csv
    _all.csv             # weekly bundle imported into AnkiDroid
```
