# TMUX

## Free Book to Read

https://leanpub.com/the-tao-of-tmux/read

## Cheat Sheet

* https://leanpub.com/the-tao-of-tmux/read#appendix-cheatsheets
* https://gist.github.com/andreyvit/2921703

## Best Pactices and Cntrol Commands

In the following with __prefix__ the default key combinatiob of __ctrl + b__ is meant.

### Listining of Key Bindings

__tmux list-keys__ or __prefix + ?__ 

### Copy and Paste

1. Enter copy/view mode: __prefix + [__ 
1. Navigate to start position with arrow keys.
1. Start text selection: __ctrl + space__
1. Navigate to end position with arrow keys.
1. Copy text into clipboard: __ctrl__ + __w__
1. For pasting press: __prefix__ + __]__

## Config

**~/.tmux.conf**  

    bind '"' split-window -c "#{pane_current_path}"
    bind % split-window -h -c "#{pane_current_path}"
    bind c new-window -c "#{pane_current_path}"
