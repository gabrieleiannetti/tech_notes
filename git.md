# GIT notes

## Config

Set username:
```
git config --global user.name "Gabriele Iannetti"
```

Set email:
```
git config --global user.email "g.iannetti@gsi.de"
```

Set default text editor:
```
git config --global core.editor vi
```

Alternatively create or edit the gitconfig file directly:

_cat ~/.gitconfig_

```
[user]
	name = Gabriele Iannetti
	email = g.iannetti@gsi.de
[core]
	editor = vi
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

> Hint: Add parameter --patch/-p to git log to get more detailed information what changed within a commit.


## Push

Push branch to remote origin
```
git push -u origin <branch>
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

