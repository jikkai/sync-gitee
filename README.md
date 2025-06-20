# Sync Gitee

This action allows you to sync your GitHub repository to Gitee.

<div align="center">

[![][github-license-shield]][github-license-link]

</div>

## Usage

```yaml
name: 🔮 Sync Mirror

on:
  push:
    branches:
      - main

jobs:
  sync:
    runs-on: ubuntu-latest
    steps:
      - name: Sync Gitee
        uses: jikkai/sync-gitee@v1
        with:
          repository: <username>/<repository>
          username: ${{ secrets.GITEE_USERNAME }}
          password: ${{ secrets.GITEE_PASSWORD }}
          tags: true
          branches: main
```

## Options

- `repository`: The Gitee repository to sync to, in the format `<username>/<repository>`.
- `username`: Your Gitee username.
- `password`: Your Gitee password or personal access token.
- `tags`: Whether to sync tags. Defaults to `true`.
- `branches`: A space-separated list of branches to sync. Defaults to `main master`.

<!-- Links -->
[github-license-shield]: https://img.shields.io/github/license/jikkai/sync-gitee?style=flat-square
[github-license-link]: ./LICENSE
