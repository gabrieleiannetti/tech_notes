# ZSH/Oh-My-Zsh

## Installation

* Installing **zsh** and setting it as default shell: https://github.com/robbyrussell/oh-my-zsh/wiki/Installing-ZSH
* Installing **oh-my-zsh** framework: https://github.com/robbyrussell/oh-my-zsh

## Theme

Themes are listed [here](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes).

Favorite theme: agnoster

Installation of Powerline Fonts on Debian:  
```
sudo apt-get install fonts-powerline
```
 
Powerline Fonts project page on [GitHub](https://github.com/powerline/fonts).

## Config

Edit file: **~/.zshrc**

```
export ZSH=$HOME/.oh-my-zsh

ZSH_THEME="agnoster"

# Create a TMUX session on startup
if [ "$TMUX" = "" ]; then tmux; fi
```
