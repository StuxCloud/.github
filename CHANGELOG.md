# Changelog

All notable changes to Stux.Cloud's `.github` repository are documented here.

## v1.0.4

### Changed
- `CONTRIBUTING.md` and `profile/README.md`'s general contact address changed from `contact@stux.cloud` to `hello@stux.cloud`, matching the convention used across other Stux.Group brand repos

## v1.0.3

### Changed
- `README.md` and `profile/README.md`'s footer/brand-attribution block updated to the new two-line format (Built & Maintained by Stux.Cloud, Hosted by Stuxedo / Stux.Cloud is a part of the Stux.Group brand of businesses), replacing the older single-line disclaimer and, in `README.md`, the redundant separate "Made by Stux.Cloud" line

## v1.0.2

### Added
- The Stux.Group icon now appears inline next to the "part of the Stux.Group Brand of Companies" line in `README.md` and `profile/README.md`, alongside the existing Stux.Cloud logo

## v1.0.1

### Fixed
- `generateMetrics.yml`'s `setup` job created the `metrics` branch by branching off `main`'s current commit, so
  it wasn't actually an orphan branch — it carried the whole repo history and file tree instead of starting
  empty. Now creates a true root commit (via the git empty-tree hash, no parents) and points `metrics` at that,
  so the branch only ever holds what the `gh-metrics/metrics` action commits to it. The already-created (wrong)
  `metrics` branch needs to be deleted so the next run recreates it correctly and regenerates the SVGs

## v1.0.0

### Added
- `VERSION.md` and `CHANGELOG.md`, and a `commit.sh`/`commit.bat` pair that reads the version from `VERSION.md` and tags the release accordingly
