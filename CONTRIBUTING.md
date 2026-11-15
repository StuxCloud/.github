# Contributing to Stux.Cloud

Thank you for your interest in contributing to Stux.Cloud projects! We welcome contributions from everyone and appreciate your effort in helping us improve.

## Getting Started

1. **Fork the repository** you want to contribute to.
2. **Clone your fork** locally and create a new branch for your changes.
3. **Make your changes**, ensuring they follow the guidelines below.
4. **Submit a pull request** with a clear description of what you've changed and why.

## Code of Conduct

By participating in any Stux.Cloud project, you agree to uphold our community standards. We expect all contributors to be respectful, constructive, and inclusive in all interactions.

## How to Contribute

### Reporting Bugs

- Check existing issues to avoid duplicates before opening a new one.
- Provide a clear title and description, steps to reproduce, and the expected vs. actual behaviour.
- Include your environment details (OS, language/runtime version, etc.) where relevant.

### Suggesting Features

- Open an issue with the label `enhancement` and describe your idea clearly.
- Explain the problem it solves and any alternatives you've considered.

### Submitting Pull Requests

- Keep pull requests focused — one change or fix per PR.
- Write clear, descriptive commit messages.
- Update documentation if your change affects behaviour or usage.
- Ensure your changes do not break existing functionality.
- Link any related issues in your pull request description.

## Style Guidelines

- Follow the coding conventions already present in the repository.
- Keep code clean, readable, and well-structured.
- Avoid introducing unnecessary dependencies.

## Questions

If you have any questions, feel free to reach out at [hello@stux.cloud](mailto:hello@stux.cloud) or open a discussion in the relevant repository.

## Branches and going live

- **`main` is what's live.** Nothing is pushed to it directly: it only changes when a pull request from `staging` is merged. Merging into `main` updates the organization profile.
- **`staging` is the last check before live.** It only changes when a pull request from `test` is merged. There's no staging deployment, so this is where CI and a final review happen.
- **Work happens on `test`**, or on a feature branch off `test` that's merged back into it. Releases are made on `test` too; `commit.sh` / `commit.bat` refuse to run on `staging` or `main`.
- **Going live:** push `test` with its tag (`git push origin test --tags`), open a pull request into staging (`gh pr create --base staging --head test`), then once it's merged open one from staging into main (`gh pr create --base main --head staging`). Each needs CI to pass and is reviewed and merged by Leo.
- **The bot writes to `main`.** The **Service status** workflow commits the profile's status table straight to `main` as `github-actions[bot]` every hour. Start new work from an up-to-date `test` (`git merge origin/main` into it) so the pull requests stay clean.

## Versioning

This project uses [Date Versioning](https://datevers.ing). To release:

1. Add a `## vYY.MM.DD` entry at the top of `CHANGELOG.md`, with its sections in this order: Added, Changed, Fixed, Removed, Security, Deprecated.
2. Set `VERSION.md` to the same bare version (no `v`): today's **UTC** date as `YY.MM.DD`, or `YY.MM.DD-1`, `-2`… for later releases the same UTC day. Never a future date. Use UTC, not local time: just after midnight in the UK it is still the previous day in UTC.
3. Run `bash tests/version.sh`.
4. Run `./commit.sh` (or `commit.bat` on Windows). It checks the version, commits and tags `vYY.MM.DD`, and never pushes.
5. Push `test` with its tag (`git push origin test --tags`) and open a pull request into `staging` (`gh pr create --base staging --head test`). Once it is merged, open one from `staging` into `main` (`gh pr create --base main --head staging`).

---

We appreciate every contribution, no matter how small. Thank you for helping make Stux.Cloud better!

*Stux.Cloud is a part of the [Stux.Group](https://github.com/StuxGroup) brand of businesses.*
