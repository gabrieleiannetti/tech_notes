# GIT notes

## Config

User specific config settings are saved in `~/.gitconfig`:  

```
[user]
    name = Gabriele Iannetti
    email = g.iannetti@gsi.de
[core]
    editor = vim
[log]
    decorate = auto
```

> Alternatively the command `git config` can also be used.

## Diff

Show differences of files in stagging area:
```
git diff --cached
```

## Log

Print out the ref names of any commits that are shown:
```
git log --decorate
```

Display all references that point to each commit:
```
git log --oneline
```

Show commit messages for a specific file:
```
git log file
```

Search in commit messages for a given string and print the proper log messages:
```
git log -S 'string'
```

Shows the history including change diffs of a file:
```
git log -p -- file
```

Overwrite author for last commit on current branch:
```
git commit --amend --author "Gabriele Iannetti <g.iannetti@gsi.de>" --no-edit
git push --force
```

## Push

Push branch to remote origin
```
git push -u origin <branch>
```

## Branch

Show already merged branches into master:
```
git branch --merged master
```

Show all branches not merged into master:
```
git branch --no-merged master
```

## Tag

Create a new tag with version number and a message:
```
git tag -a 1.0 -m "First stable release."
```

Push tag to remote repository:
```
git push origin 1.0
```

Delete local tag:
```
git tag -d 1.0
```

Delete a remote tag:
```
git push origin :1.0
```

List tags with commit message (default: 1 line):
```
git tag -n
```
