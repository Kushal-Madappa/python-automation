# python-automation

Small, focused Python utilities and automation scripts. Each script lives in
its own folder with a README, a `requirements.txt` if needed, and a usage
example.

Planned scripts:
- `bulk_renamer/` -- pattern-based file renaming with dry-run support
- `pdf_merger/` -- merge / split PDFs from a folder
- `csv_cleaner/` -- normalize messy CSVs (encoding, headers, types)
- `web_scraper/` -- polite scraper with requests + BeautifulSoup

> Each utility will ship with: usage docs, example input/output, and tests.

## Status

| Script           | Status   | Notes                                  |
| ---------------- | -------- | -------------------------------------- |
| `bulk_renamer`   | planned  | first pickup — designed for dry-run    |
| `pdf_merger`     | planned  | uses `pypdf`                           |
| `csv_cleaner`    | planned  | encoding sniff + header normalization  |
| `web_scraper`    | planned  | rate-limited; `robots.txt` respected   |

**Next pickup:** `bulk_renamer` — a CLI that previews renames before
applying them. The first commit will land the dry-run skeleton and a
test fixture; the second will wire up the actual rename pass behind a
`--apply` flag.

---

### Log

- **2026-05-25** — Locked `bulk_renamer` as the first concrete pickup. The
  dry-run-first design (preview every rename before any file moves) sets
  the safety pattern the rest of the utilities should inherit: any
  destructive utility in this repo should default to dry-run and require
  an explicit `--apply` flag to actually mutate state.
