# Modernization Plan

Small audit of this GitHub profile README repo (`README.md` + `LICENSE` only).

## Audit findings

### README.md

- **Badges (shields.io / Simple Icons)** — all badge URLs are well-formed and
  shields.io is alive, but three logo slugs reference icons that Simple Icons
  has since renamed or removed (checked statically, not fetched):
  - `logo=CSS3` — Simple Icons renamed `css3` to `css`; shields keeps an
    alias for now, so the badge still renders. Low risk.
  - `logo=microsoft-sql-server` — Microsoft brand icons were removed from
    Simple Icons; the badge renders but likely without its logo.
  - `logo=visual-studio-code` — the VS Code icon was removed from Simple
    Icons (brand-guideline removal); badge likely renders without its logo.

  These are cosmetic and rendering depends on shields.io alias behavior we
  can't verify offline, so they are **flagged, not changed**.
- **Markdown nits**:
  - Trailing space on the `🌐` list line.
  - A stray blank line splits the Tech Stack list between the 🛢 and 🔧
    items, making the last item render as a separate (loose) list.
- **Content/claims**: personal statements (learning Japanese, looking for
  Databricks help, etc.) are the owner's own words — intentionally left
  untouched.

### LICENSE

- Standard MIT, copyright 2024 Chris Lu. Fine as-is; no change needed
  (updating the year range is optional and not done).

### Other

- No `.gitignore` — not needed for a two-file docs-only repo. Skipped.
- No CI — added (see checklist).

## Checklist

- [x] Phase 1: audit + this plan
- [ ] Phase 2: fix trailing whitespace + stray blank line in README.md
      (no content/tone changes)
- [ ] Phase 3: minimal markdownlint CI (`.github/workflows/ci.yml` +
      permissive `.markdownlint-cli2.jsonc`), verified locally with Node 22
- [ ] Finish: update this file with Done vs Deferred, push branch
