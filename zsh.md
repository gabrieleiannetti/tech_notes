# ZSH/Oh-My-Zsh

## Installation

* Installing **zsh** and setting it as default shell: https://github.com/robbyrussell/oh-my-zsh/wiki/Installing-ZSH
* Installing **oh-my-zsh** framework: https://github.com/robbyrussell/oh-my-zsh

## Theme

Themes are listed [here](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes).

Favorite theme: agnoster

## Powerline Fonts

To render the used theme completley install the Powerline Fonts: https://github.com/powerline/fonts

### Additional Font Installation and Configuration

If just installing Powerline Fonts does not work, install the following packages as well:

* powerline
* fonts-inconsolata

> Specify **Inconsolata Medium** font type in Terminal settings.

## Config

Edit file: **~/.zshrc**

```
export ZSH=$HOME/.oh-my-zsh

ZSH_THEME="agnoster"

# Create a TMUX session on startup
if [ "$TMUX" = "" ]; then tmux; fi
```
