# Vim

Content:  
* [commands](#commands)
* [config](#config)
* [building neovim from sources](#building-neovim-from-sources)
* [Useful Links](#useful-links)

## Commands

### Overview

| Command     | Description |
|:-----------:|:-----------:|
|    a        | Append text after the cursor. |
|    A        | Append text at the end of the line. |
|    b        | Move cursor [count] words backward. |
|    w        | Move cursor [count] words forward. |
|    n        | Search forward for the next occurrence. |
|    N        | Search backward for the previous occurrence. |
|    f {char} | Go to next {char} occurrence from left to right. |
|    ,        | Repeat latest f, t, F or T in opposite direction [count] times. |
|    ;        | Repeat latest f, t, F or T [count] times. |
|    .        | Repeat last change, with count replaced with [count]. |
|    u        | Undo [count] changes. |
|    $        | To the end of the line. |
|    *        | Search forward for the [count]'th occurrence of the word nearest to the cursor. |
|    #        | Same as '\*', but search backward. |
|    cw       | Delete to end of the word and switch into insert mode (cw = change word). |
|    daw      | Delete a word (including whitespace character). |

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

* VIM: __~/.vimrc__
* NeoVIM: __~/.config/nvim/init.vim__

```
" Show line number
set number

" Show current line
set cursorline

" Show vertical line at 120 character width
highlight ColorColumn ctermbg=grey
set colorcolumn=120

" Highlight search matches
set hlsearch

" Use 2 spaces for tabs
set tabstop=2 softtabstop=2 shiftwidth=2 expandtab

" Display indentation guides
set list listchars=tab:❘-,trail:·,extends:»,precedes:«,nbsp:×,eol:↵

highlight iCursor guifg=white guibg=steelblue
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

## Useful-Links

* [Use Vim macros to automate frequent tasks](https://www.redhat.com/sysadmin/use-vim-macros)
* [Sorting columns of text in Vim using sort](https://jordanelver.co.uk/blog/2014/03/12/sorting-columnds-of-text-in-vim-using-sort/)
