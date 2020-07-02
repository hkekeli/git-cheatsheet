# git-cheatsheet

A designer's git cheatsheet.

I wrote this cheatsheet while learning to use git. It has served as a personal reference many times so I'm making it available here.

## Commands included:

- [Git log](#git-log)
- [Git commit](#git-commit)
- [Git stash](#git-stash)
- [Git reset](#git-reset)

## Branches

  - [Delete branch](#delete-branch)
  - [Rename branch](#rename-branch)

## Scenarios
- [Amending commits](#amending-commits)
- [Squashing commits](#squashing-commits)
- [Solving merge conflicts](#solving-merge-conflicts)
- [Tracked the wrong files?](#accidentally-tracked-the-wrong-files)

### Git log

`git log` see all recent updates

### Git commit
    `git commit -m "your commit message here"`

### Amending commits

  Amending small updates to previous commit:

  1. Make necessary updates
  2. `git add -A`
  3. `git commit --amend --no-edit` (adds update to your latest commit)
  4. `git push --force`


Amend a commit without opening vim(text editor):

    `git commit --amend --no-edit`

### Git stash

`git stash`

`git stash list` (displays list)

`git stash apply` (applies most recent stash)

`git stash apply stash@{n}` (stash specific version)

`git stash clear` (clears all)


### Delete branch

On local

`git branch -D branchname`

On remote

`git branch -dr origin/branchname`

### Rename branch

`git branch -m oldname newname`

### Git reset

`git reset --hard HEAD^` (rewinds changes)

**Reset author date**: `git commit --amend --date=now`

**Reset author date w/o opening vim**:`git commit --amend --no-edit --date=now`

**Reset author of the last commit**:`git commit --amend --reset-author --no-edit`



## Solving Merge conflicts

In case of merge conflict:

1. Fix conflict
2. `git add`
3. `git rebase --continue` (No need to commit again)


## Squashing Commits

1. `Git rebase -i branchname`
2. Pick any line and [squash] anything you want to apply to the first line.
3. Esc + :wq
4. Edit commit message
5. Esc + :wq

## Accidentally tracked the wrong files?

`git rm -r --cached filename`
