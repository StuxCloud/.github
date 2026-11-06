<p align="center">
  <picture><source media="(prefers-color-scheme: dark)" srcset="https://global.media.stux.cloud/logo-light.png"><source media="(prefers-color-scheme: light)" srcset="https://global.media.stux.cloud/logo-dark.png"><img src="https://global.media.stux.cloud/logo-dark.png" height="100" alt="Stux.Cloud Logo"></picture>
</p>

# Stux.Cloud GitHub Configuration

### *Powering everything, quietly & securely!*

The central repository for Stux.Cloud's GitHub organization: its public profile and the org-wide defaults.

## What's in it

| Path | What it does |
| ---- | ------------ |
| `profile/README.md` | The public org profile shown at [github.com/StuxCloud](https://github.com/StuxCloud): services, projects, the live service status table, contact details and activity |
| `CONTRIBUTING.md` | Contributing guidelines, which GitHub uses for any Stux.Cloud repository that has none of its own |
| `.github/workflows/status.yml` | Refreshes the profile's **Service Status** table hourly with [GitHup](https://githup.stux.group)'s `readme` mode, from the data in [StuxCloud/Status](https://github.com/StuxCloud/Status) ([status.stux.cloud](https://status.stux.cloud)) |
| `.github/workflows/generateMetrics.yml` | Builds the profile's activity image daily into the `metrics` branch (needs the `METRICS_TOKEN` secret) |
| `commit.sh` / `commit.bat` | Commit and tag a release, using the version in `VERSION.md` |
| `tests/version.sh` | Checks `VERSION.md` and the changelog |

## How it works

GitHub shows `profile/README.md` on the organization's page, and uses the community health files here (such as `CONTRIBUTING.md`) for any public Stux.Cloud repository that doesn't have its own.

The status table in the profile sits between the `<!-- githup:start -->` and `<!-- githup:end -->` markers and is written by the workflow. Don't edit inside them.

## Contributing

We welcome contributions! Please refer to our [Contributing Guidelines](CONTRIBUTING.md) for details on how to participate in improving our organization's standards.

## Versioning

This project uses [Date Versioning](https://datevers.ing): each release is numbered by its UTC release date as `YY.MM.DD` (for example `26.10.23`), with `-1`, `-2`… for later releases the same day. See [CHANGELOG.md](CHANGELOG.md) for what changed in each release.

## License

This project is open source and available for use and modification.

---

*Built & Maintained by <picture><source media="(prefers-color-scheme: dark)" srcset="https://global.media.stux.cloud/icon-light.png"><source media="(prefers-color-scheme: light)" srcset="https://global.media.stux.cloud/icon-dark.png"><img src="https://global.media.stux.cloud/icon-dark.png" height="14" alt="Stux.Cloud" valign="middle"></picture> [Stux.Cloud](https://github.com/StuxCloud), Hosted by <picture><source media="(prefers-color-scheme: dark)" srcset="https://global.media.stuxedo.com/icon-light.png"><source media="(prefers-color-scheme: light)" srcset="https://global.media.stuxedo.com/icon-dark.png"><img src="https://global.media.stuxedo.com/icon-dark.png" height="14" alt="Stuxedo" valign="middle"></picture> [Stuxedo](https://stuxedo.com).  
Stux.Cloud is a part of the <picture><source media="(prefers-color-scheme: dark)" srcset="https://global.media.stux.group/icon-light.png"><source media="(prefers-color-scheme: light)" srcset="https://global.media.stux.group/icon-dark.png"><img src="https://global.media.stux.group/icon-dark.png" height="14" alt="Stux.Group" valign="middle"></picture> Stux.Group brand of businesses.*
