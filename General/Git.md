# Git

## Learn more

- https://git-scm.com/docs

## Clone a repository

```
git clone some-url
[git remote add some-remote some-url]
```

For example:

```shell
git clone git@github.com:some-user/some-repository.git
git remote add upstream git@github.com:another-user/some-repository.git
```

## Create a feature branch

```
git checkout some-main-branch
git pull [some-remote some-main-branch]
[git push]
git checkout -b some-branch
```

For example:

```shell
git checkout main
git pull upstream main
git push
git checkout -b some-branch
```

## Check the local repository state

```shell
git status
```

## Save changes in the working directory to the staging area

```
git add [-p] some-paths
```

- `-p` to break into pieces.

## Save changes in the staging area to commits

```
git commit [-m "Some message"]
```

- Opens in default editor.
- Add commit message to top line with optional body below.
- Save file and exit to finish commit.
- `-m` for quick message.

## Save changes in the staging area temporarily

```
git stash
# Temporarily do something else
git stash list
git stash show
git stash apply
```

## Save changes in commits to remote repositories

```shell
git push
```

## Keep feature branches up to date with a target branch

```
git checkout some-branch
git fetch [some-remote some-main-branch]
git merge [some-remote/some-main-branch]
git push
```

For example:

```shell
git checkout some-branch
git fetch upstream main
git merge upstream/main
git push
```

## Show diff

```
git diff [--staged] [some-reference]
```

- Defaults to comparing with working directory.
- `--staged` for diff with staging area.
- `some-reference` for diff with a reference.

For example:

```shell
git diff
git diff --staged
git diff origin/some-main-branch
git diff some-branch..another-branch
git diff some-tag another-tag
```

## Undo changes in the working directory

```shell
git checkout some-paths
```

## Undo changes in the staging area back to the working directory

```shell
git reset HEAD some-paths
```

## Undo commits

```shell
git revert some-reference
```

## Find which author made changes to a file

```shell
git blame some-file
```

## Show commit history

```
git log [-#] [-p] [-S "some-search-pattern"] [--since="date"] [--until="date"] [--stat] [--oneline] [--graph] [-- some-paths]
```

- `-#` for number of results.
- `-p` for diffs.
- `-S` for specific matches.
- `--since="date"` for before a specific date.
- `--until="date"` for after a specific date.
- `date` for a date (like `yesterday`, `last week`, `30 minutes ago`, `01-01-2000`).
- `--stat` for insertions / deletions.
- `--oneline` for condensed formatting.
- `--graph` for a graphical representation.
- `-- some-paths` for specific paths.

## List tracked files

```shell
git ls-files
```

## Remove untracked files

```
git clean -dxf[n]
```

- `-n` for a preview.

## Find a search pattern across all tracked files in the repository

```shell
git grep some-search-pattern
```

## Find the commit that broke something

```
# Begin a bisect session
git bisect start

# Mark the current broken point
git bisect bad

# Mark when things were known to work
git bisect good some-reference

# Check for the broken change

# Mark if the current state is broken or not
git bisect bad/good

# Repeat checking / marking until the problem commit is found

# Cleanup
git bisect reset
```

## Add version tags

```
git tag vX.Y.Z
git push --tags
```

## List configuration

```
git config -l [--global]
```

- `--global` to include global configuration.
