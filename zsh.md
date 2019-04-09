# ZSH/Oh-My-Zsh

## Installation

* Installing **zsh** and setting it as default shell: https://github.com/robbyrussell/oh-my-zsh/wiki/Installing-ZSH
* Installing **oh-my-zsh** framework: https://github.com/robbyrussell/oh-my-zsh

## Config

File: **~/.zshrc**

```
export ZSH=$HOME/.oh-my-zsh

ZSH_THEME="agnoster"

# Create a TMUX session on startup
if [ "$TMUX" = "" ]; then tmux; fi
```

The agnoster theme requires the **powerline-fonts**: https://github.com/powerline/fonts
