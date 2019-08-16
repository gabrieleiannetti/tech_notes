# Vim

Content:  
* [commands](#commands)
* [config](#config)
* [building neovim from sources](#building-neovim-from-sources)

## Commands

### Overview

| Command     | Description |
|:-----------:|:-----------:|
|    a        | Append text after the cursor |
|    A        | Append text at the end of the line |
|    f {char} | Go to next {char} occurrence from left to right |
|    ;        | Repeat latest f, t, F or T [count] times |
|    .        | Repeat last change, with count replaced with [count] |
|    $        | To the end of the line |


### Enabling and Disabling Options

Enable is ```set{OPTION}```.  
Disable is ```set no{OPTION}```.  

OPTION(S):

* List Chars: ```list```
* Line Numbers: ```nu```

### Search and Replace

#### Global

* Replace each occurence of a whitespace with a new line: `:%s/ /\r/g`
* Replace text within visual mode: `:%s/\%Vold_text/new_text/g`
* Replace whole text: `:%s/\<old_text\>/new_text/g`

[Detailed documentation about search and replace](https://vim.fandom.com/wiki/Search_and_replace)

#### Visual Mode Selection-based

Select text where to search and replace.  
Add whitespaces at end of each selected line: `:'<,'>s/$/  /`  

Explenation:  
> * `:'<,'>` initializes the command for visual mode selection
> * `s` means subsitute
> * `$` regular expression for end of the line or word

### Execute Command with Regular Expression

Delete each empty line: `:g/^$/d`

### Indention

Indention is triggered by the `>` character from normal and visual mode.  

Examples in normal mode:  

* Indent current line once in normal mode: `>>`
* Indent all remaining lines from current cursor position to EOF: `>G`

A selected text in visual mode can also be indented by pressing the `>` symbol.

For more information see the help: `:h >`

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

## Building Neovim from Sources

1. Install build dependencies: 
  * On Debian automatically with build-dep: `sudo apt-get build-dep neovim`
  * Otherwise manually with package list:  
  ```
  cmake autoconf g++ pkg-config autopoint build-essential debhelper dh-autoreconf gperf libacl1-dev libuv1-dev libjemalloc-dev  libluajit-5.1-dev libnss-wrapper libtermkey-dev libunibilium-dev libvterm-dev libvterm0 libyaml-dev lua-bitop lua-busted lua-cliargs lua-coxpcall lua-dkjson lua-inifile lua-lpeg lua-luassert lua-luv lua-mediator lua-mpack lua-nvim lua-penlight lua-say lua-term lua-yaml libmsgpack-dev luajit lua-system lua-filesystem
  ```
1. Clone repository: `git clone https://github.com/neovim/neovim`
1. Change directory: `cd neovim`
1. Show all tags: `git tag`
1. Checkout stable release: `git checkout stable`
1. Create/Change to BUILD directory: `mkdir BUILD && cd BUILD`
1. Configure: `cmake ..`
1. Build: `make`
1. Install: `sudo make install`
1. Check executable: `which nvim`
