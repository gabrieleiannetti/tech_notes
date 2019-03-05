# ZSH/Oh-My-Zsh

## Installation

* Installing **zsh** and setting it as default shell: https://github.com/robbyrussell/oh-my-zsh/wiki/Installing-ZSH
* Installing **oh-my-zsh** framework: https://github.com/robbyrussell/oh-my-zsh

## Theme

Themes are listed [here](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes).

Favorite theme: agnoster

### Fonts

> Rewrite this section as required steps... Create a fonts section!!!

#### Powerline Fonts

To render the used theme completley install the Powerline Fonts: https://github.com/powerline/fonts

#### Additional Font Installation and Configuration

If just installing Powerline Fonts does not work e.g. broken rendering in Debian Buster (Soft Release), install the following packages as well and **Inconsolata Medium** font type in Terminal settings:

* powerline
* fonts-inconsolata

## Config

Edit file: **~/.zshrc**

```
export ZSH=$HOME/.oh-my-zsh

ZSH_THEME="agnoster"

# Create a TMUX session on startup
if [ "$TMUX" = "" ]; then tmux; fi
```
