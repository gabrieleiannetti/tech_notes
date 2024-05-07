# ZSH/Oh-My-Zsh

## Installation

* [zsh](https://github.com/robbyrussell/oh-my-zsh/wiki/Installing-ZSH)
* [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)
* [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md#oh-my-zsh)

## Config

**~/.zshrc**

```bash
export ZSH=$HOME/.oh-my-zsh

ZSH_THEME="robbyrussell"

plugins=(
  git
  zsh-autosuggestions
)

source $ZSH/oh-my-zsh.sh

export ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE="fg=green,bold,underline"
bindkey '^ ' autosuggest-accept # bind `ctrl + space`

# Create a TMUX session on startup
if [ "$TMUX" = "" ]; then tmux; fi

# Change path to Golang workspace directory
export GOPATH=~/workspace/go

export PATH=$PATH:~/.local/bin/

alias l='ls -lthr'
```

The agnoster theme requires the **powerline-fonts**: https://github.com/powerline/fonts
