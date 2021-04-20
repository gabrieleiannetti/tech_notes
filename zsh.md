# ZSH/Oh-My-Zsh

## Installation

* Installing **zsh** and setting it as default shell: https://github.com/robbyrussell/oh-my-zsh/wiki/Installing-ZSH
* Installing **oh-my-zsh** framework: https://github.com/robbyrussell/oh-my-zsh

## Config

**~/.zshrc**

```bash
export ZSH=$HOME/.oh-my-zsh

ZSH_THEME="robbyrussell"

plugins=(git)

source $ZSH/oh-my-zsh.sh

# Create a TMUX session on startup
if [ "$TMUX" = "" ]; then tmux; fi

# Change path to Go lang workspace directory
export GOPATH=~/workspace/go
```

The agnoster theme requires the **powerline-fonts**: https://github.com/powerline/fonts
