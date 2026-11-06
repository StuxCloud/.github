# Changelog

All notable changes to Stux.Cloud's `.github` repository are documented here.

Since v26.10.23 this project uses [Date Versioning](https://datevers.ing) (`YY.MM.DD`, the UTC release date, with `-1`, `-2`… for later releases the same day); earlier releases used Semantic Versioning.

## v26.11.06-1

### Added

- An **Our Projects** table in `profile/README.md` listing every public Stux.Cloud repository: Stux.Cloud Status, the Region, Instance, Maintenance and Coming Soon Pages, the GitHub Pages Redirect, and the archived designs (Region Page v2, Instance Page v2 and v1, Maintenance Page v2, Coming Soon Page v2)
- **Regions** in the "Our Services" table, linking the region page and the region websites
- `.gitattributes`, so text files are checked out with LF line endings (CRLF for `.bat`) on every machine
- A `test` branch. Work happens there, and changes reach `main` only through a pull request from `test` that needs CI to pass and is reviewed and merged by Leo. Release commits and tags are made on `test`
- `.github/workflows/ci.yml`, which checks `VERSION.md` and the changelog on every push to `main` and `test` and on every pull request

### Changed

- The logos and icons in `profile/README.md`, `README.md` and the footers follow GitHub's light or dark theme, using each brand's `logo-light`/`logo-dark` and `icon-light`/`icon-dark` files. The Stuxedo icon comes from Stuxedo's media CDN instead of its GitHub avatar
- Stux.Cloud Status moved from "Our Services" to "Our Projects", and "Get Involved" now sits right after the projects
- `README.md` describes what's actually in this repository (the profile, the status and metrics workflows, the release scripts) instead of a generic list of template folders and files it doesn't have
- `commit.sh` and `commit.bat` suggest pushing just the new tag, since GitHub starts no workflows when more than three tags are pushed at once
- `CONTRIBUTING.md`'s closing note moved to the end, after the Versioning section
- The README's Versioning section and a new **Branches** section in `CONTRIBUTING.md` describe the `test` branch, and `commit.sh`/`commit.bat` suggest pushing to `test`

## v26.11.06

### Added

- **Status** in the "Our Services" table of `profile/README.md`, linking to the new [status.stux.cloud](https://status.stux.cloud)
- A **Service Status** section in `profile/README.md` with a live status badge and a status table for every Stux.Cloud site (group, status, uptime and response time), kept up to date hourly by the new `.github/workflows/status.yml` using GitHup's `readme` mode and the data in `StuxCloud/Status`

## v26.10.23

### Added

- `tests/version.sh`, which checks that `VERSION.md` is a valid Date Version, a real calendar date not in the future, and the same as the newest entry in this changelog

### Changed

- Switched from Semantic Versioning to [Date Versioning](https://datevers.ing): releases are numbered by their UTC release date as `YY.MM.DD`, with `-1`, `-2`… for later releases the same day. This release follows v1.0.8
- `commit.sh` and `commit.bat` refuse a `VERSION.md` that isn't a valid Date Version or is dated in the future (UTC), and warn when it's dated before today
- `README.md` and `CONTRIBUTING.md` describe Date Versioning and the release steps

## v1.0.8

### Added
- `profile/README.md` gained the "Our Services" table (Stuxedo) and a `legal@stux.cloud` contact line, matching the fuller template already used by Stux.Group's own profile.

## v1.0.7

### Added
- Stux.Cloud's first slogan, "Powering everything, quietly & securely!", added to `README.md` and `profile/README.md`. `profile/README.md`'s placeholder tagline previously read "Powered by Stuxedo" — backwards, since Stuxedo is a Stux.Cloud service, not the other way around.

## v1.0.6

### Fixed
- `README.md` and `profile/README.md`'s own Stux.Cloud header logo (separate from the Stux.Group brand icon already fixed in v1.0.5) still pointed at the old `media.stux.cloud/global/logo.png` host — corrected to `https://global.media.stux.cloud/logo.png`

## v1.0.5

### Fixed
- `README.md` and `profile/README.md`'s Stux.Group brand icon URL had a leftover duplicated `/global/` path segment (`global.media.stux.group/global/icon.png`) — corrected to `https://global.media.stux.group/icon.png`

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
