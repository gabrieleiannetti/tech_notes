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

