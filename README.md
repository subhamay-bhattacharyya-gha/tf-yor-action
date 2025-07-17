# Yor Git Metadata Tagging Action

![Release](https://github.com/subhamay-bhattacharyya-gha/tf-yor-action/actions/workflows/release.yaml/badge.svg)&nbsp;![Commit Activity](https://img.shields.io/github/commit-activity/t/subhamay-bhattacharyya-gha/tf-yor-action)&nbsp;![Last Commit](https://img.shields.io/github/last-commit/subhamay-bhattacharyya-gha/tf-yor-action)&nbsp;![Release Date](https://img.shields.io/github/release-date/subhamay-bhattacharyya-gha/tf-yor-action)&nbsp;![Repo Size](https://img.shields.io/github/repo-size/subhamay-bhattacharyya-gha/tf-yor-action)&nbsp;![File Count](https://img.shields.io/github/directory-file-count/subhamay-bhattacharyya-gha/tf-yor-action)&nbsp;![Issues](https://img.shields.io/github/issues/subhamay-bhattacharyya-gha/tf-yor-action)&nbsp;![Top Language](https://img.shields.io/github/languages/top/subhamay-bhattacharyya-gha/tf-yor-action)&nbsp;![Custom Endpoint](https://img.shields.io/endpoint?url=https://gist.githubusercontent.com/bsubhamay/77f93a02120fa5702a93fe6060128580/raw/tf-yor-action.json?)

A GitHub Composite Action to tag Terraform files with [Yor](https://github.com/bridgecrewio/yor) Git metadata and optionally commit those changes back to the repository.

---

## 🛠️ Action Name

**Yor Git Metadata Tagging**

### 📌 Description

This GitHub Action runs [Yor](https://github.com/bridgecrewio/yor) to automatically tag Terraform files with Git metadata such as author, commit, and timestamp information. You can specify a release tag to checkout and optionally commit changes.

---

## 📥 Inputs

| Name             | Description                                                                                  | Required | Default     |
|------------------|----------------------------------------------------------------------------------------------|----------|-------------|
| `terraform-dir`  | Relative path to the directory containing Terraform configuration files.                     | No       | `tf`        |
| `release-tag`    | Git release tag to check out. If omitted, defaults to the current branch.                    | No       | `""`        |
| `commit-changes` | Whether to commit the changes made by Yor. Accepts `true` or `false`.                        | No       | `true`      |
| `github-token`   | GitHub token used to authenticate Yor's Git operations and avoid rate limits.                | No       | `${{ github.token }}` |

---

## 🚀 Example Usage

```yaml
name: Tag Terraform with Yor

on:
  push:
    branches:
      - main
      - feature/**

jobs:
  tag-with-yor:
    runs-on: ubuntu-latest
    steps:
      - name: Run Yor Git Metadata Tagging
        uses: subhamay-bhattacharyya-gha/tf-yor-action@v1
        with:
          terraform-dir: infrastructure
          release-tag: v1.2.3
          commit-changes: true
          github-token: ${{ secrets.GITHUB_TOKEN }}

```

## License

MIT
