# Neovim

## Building from Sources

1. Automatically install all dependencies: `sudo apt-get build-dep neovim`
1. Clone repository: `git clone https://github.com/neovim/neovim`
1. Change directory: `cd neovim`
1. Show all tags: `git tag`
1. Checkout stable release: `git checkout stable`
1. Create/Change to BUILD directory: `mkdir BUILD && cd BUILD`
1. Configure: `cmake ..`
1. Build: `make`
1. Install: `sudo make install`
1. Check executable: `which nvim`

> Step 1 is Debian specific but comfortable for resolving all required project dependencies at once.

## Config

__~/.config/nvim/init.vim__

```
" Show line number
set number

" Show current line
set cursorline

" Show vertical line at 80 character width
highlight ColorColumn ctermbg=grey
set colorcolumn=80

" Highlight search matches
set hlsearch

" Use 4 spaces for tabs
set tabstop=4 softtabstop=4 shiftwidth=4

" Display indentation guides
set list listchars=tab:❘-,trail:·,extends:»,precedes:«,nbsp:×,space:.,eol:↵
```

## Commands

### Enabling and Disabling Options

Enable is ```set{OPTION}```.  
Disable is ```set no{OPTION}```.  

OPTION(S):

* List Chars: ```list```
* Line Numbers: ```nu```

### Search and Replace

* Replace each occurence of a whitespace with a new line: `%s/ /\r/g`

[Detailed documentation about search and replace](https://vim.fandom.com/wiki/Search_and_replace)
