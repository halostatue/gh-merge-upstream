# gh-merge-upstream

Uses the GitHub API to update your fork of a repository to the current state of
the parent repository.

In essence, this is a fancy wrapper around:

```sh
gh api repos/TARGET_REPO/merge-upstream -F branch=UPSTREAM_BRANCH
```

If there are insufficient permissions for your token, `gh api` will advise the
correct action to take.

## Installation

```sh
gh extension install halostatue/gh-merge-upstream
```

## Usage

`gh-merge-upstream` works best and easiest if you are in a local clone of the
target repository where `origin` points to your fork and `upstream` points to
the parent repository. In this case, `gh-merge-upstream` will discover the
target upstream branch and the target repo and apply everything automatically.

In other cases, the target repository and/or the upstream repository must be
specified.

### `TARGET_REPO` parameter

`gh-merge-upstream` takes one optional parameter, `TARGET_REPO`, which is either
a URL to the repository (`https://github.com/owner/repo`) or a shorthand
repository name (`owner/repo`). If unspecified, it will be determined from the
handling of the `origin` option, described below.

### `-b UPSTREAM_BRANCH`, `--branch UPSTREAM_BRANCH`

The name of the branch to use for updating your fork. Defaults to the 'upstream'
repository default branch.

### `-o NAME`, `--origin NAME`, `--mine NAME`

The name of the remote in the current git repo to use for discovering
`TARGET_REPO`. Defaults to `origin`.

### `-u NAME`, `--upstream NAME`, `--theirs NAME`

The name of the remote (`upstream`), shorthand repository name (`owner/repo`),
or repository URL (`https://github.com/owner/repo`) for the parent repository
and used only when `--branch` is not provided. Defaults `upstream` of the
current git repo.

## Contributors

- Austin Ziegler ([@halostatue](https://github.com/halostatue)) created gh-merge-upstream.
- George L. Yermulnik ([@yermulnik](https://github.com/yermulnik))
