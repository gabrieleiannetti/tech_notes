# Neovim

## Building from Sources

1. sudo apt-get build-dep neovim
1. git clone https://github.com/neovim/neovim
1. cd neovim
1. git branch -a
1. git checkout release-0.3
1. mkdir BUILD && cd BUILD
1. cmake ..
1. make
1. sudo make install
1. which nvim

## Config

_~/.config/nvim/init.vim_

``
" Show line number
set number

" Use 4 spaces for tabs
set tabstop=4 softtabstop=4 shiftwidth=4

" Display indentation guides
set list listchars=tab:❘-,trail:·,extends:»,precedes:«,nbsp:×
``
