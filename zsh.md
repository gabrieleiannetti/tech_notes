# ZSH/Oh-My-Zsh

## Installation

* Installing **zsh** and setting it as default shell: https://github.com/robbyrussell/oh-my-zsh/wiki/Installing-ZSH
* Installing **oh-my-zsh** framework: https://github.com/robbyrussell/oh-my-zsh

#### Additional Font Installation and Configuration

Install inconsolata fonts and use it in the terminal.

## Config

File: **~/.zshrc**

```
export ZSH=$HOME/.oh-my-zsh

ZSH_THEME="robbyrussell"

# Create a TMUX session on startup
if [ "$TMUX" = "" ]; then tmux; fi
```
