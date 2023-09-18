# gh-merge-upstream

## 1.0.1 / 2023-09-18
- Add installation instruction to [`README`](./README.md)
- `usage()`: use variable instead of hardcoded tool name
- `halt-error()`: print diagnostic only if there are still items in `$@`
- Add `-h | --help | --usage` into cmdline argument parser loop
- Workaround use of `insteadOf` GIT CLI config option by replacing `git remote get-url "${remote}"`
  with `git config --get remote."${remote}".url`

## 1.0.0 / 2023-09-16

Initial release.
