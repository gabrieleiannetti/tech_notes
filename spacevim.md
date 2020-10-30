# Spacevim

## Resolving Dependency to vimproc\_linux64.so

Probably the build process of spacevim should have created it  
when `make` command is available on the system already.

Otherwise make sure to have installed the `make` command.  

Fixing it manually:  

```bash
  cd ~/.SpaceVim/bundle/vimproc.vim/
  make
```
