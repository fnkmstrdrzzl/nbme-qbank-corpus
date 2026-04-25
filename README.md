# nbme-qbank-corpus

Mehlman pointer-phrase reference data for the [nbme-qbank](https://github.com/fnkmstrdrzzl/nbme-qbank) app's Language Gap analytics feature.

## Contents

- `manifest.json` — file index consumed by the app's corpus refresh feature
- `HY_*.json` — per-PDF pointer-phrase extractions

## Updating the corpus

```bash
# After ingesting a new HY PDF and producing HY_Subject.json:
cp /path/to/HY_Subject.json .
python3 /path/to/qbank/mehlman_manifest_generate.py --dir . --out manifest.json
git add . && git commit -m "Add HY_Subject" && git push
```

The app fetches files via `https://raw.githubusercontent.com/fnkmstrdrzzl/nbme-qbank-corpus/main/<filename>`.
