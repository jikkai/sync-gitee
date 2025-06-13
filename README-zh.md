# Sync Gitee

一个允许将 GitHub 仓库同步到 Gitee 的 GitHub Action。

<div align="center">

[![][github-license-shield]][github-license-link]

</div>

## 使用方法

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

## 选项

- `repository`: 要同步到的 Gitee 仓库，格式为 `<username>/<repository>`。
- `username`: 你的 Gitee 用户名。
- `password`: 你的 Gitee 密码或个人访问令牌。
- `tags`: 是否同步标签。默认为 `true`。
- `branches`: 要同步的分支列表，以空格分隔。默认为 `main master`。

<!-- Links -->
[github-license-shield]: https://img.shields.io/github/license/jikkai/sync-gitee?style=flat-square
[github-license-link]: ./LICENSE
