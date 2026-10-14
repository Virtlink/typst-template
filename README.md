# Typst Project Template

The canonical document source is `src/main.typ`; builds write `dist/main.pdf`.

## Build

```shell
mise run build
```

To rebuild on changes:

```shell
mise run watch
```

## Dependency updates

Renovate runs weekly at Saturday 06:00 UTC and can be started manually on either
platform after credentials are configured.

### GitHub

Create a GitHub App with Commit statuses, Contents, Pull requests, and Workflows
read/write permissions, plus Metadata read-only. Enable **Allow GitHub Actions to
create and approve pull requests** in the repository Actions settings. Add the App
client ID and private key as the `APP_CLIENT_ID` and `APP_PRIVATE_KEY` Actions
secrets.

### GitLab

Add a masked `RENOVATE_TOKEN` with `api` scope whose owner can merge into the
protected default branch. A masked, read-only `RENOVATE_GITHUB_COM_TOKEN` is
optional but recommended for GitHub-hosted presets and changelogs. Create a
Saturday 06:00 UTC pipeline schedule on the default branch and set its
`RENOVATE=true` variable.
