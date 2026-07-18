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
- [x] Phase 2: fix trailing whitespace + stray blank line in README.md
      (no content/tone changes)
- [x] Phase 3: minimal markdownlint CI (`.github/workflows/ci.yml` +
      permissive `.markdownlint-cli2.jsonc`), verified locally with Node 22
- [x] Finish: update this file with Done vs Deferred, push branch

## Done vs Deferred

### Done

- Audit of README.md and LICENSE (this document).
- README whitespace fixes: removed a trailing space and a stray blank line
  that split the Tech Stack list. Content, wording, and tone untouched.
- Minimal CI: `.github/workflows/ci.yml` runs `npx --yes markdownlint-cli2`
  on Node 22; `.markdownlint-cli2.jsonc` disables only MD013 (line length)
  and MD041 (first-line heading). Verified locally: 0 issues in 2 files.

### Deferred

- Badge logo slugs (`CSS3`, `microsoft-sql-server`, `visual-studio-code`)
  reference Simple Icons that were renamed/removed. Rendering depends on
  shields.io alias behavior that couldn't be verified offline — left as-is;
  owner can swap slugs if a logo stops showing.
- LICENSE copyright year update — optional, owner's call.
- `.gitignore` — not useful for a two-file docs repo.

## Summary (PR-style)

Modernizes the profile README repo with a light touch: adds this audit
plan, fixes two markdown whitespace nits in `README.md` (no content
changes), and adds a tiny markdownlint CI workflow with a permissive
config that passes against the current files.
