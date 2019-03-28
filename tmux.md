# TMUX

## Free Book to Read

https://leanpub.com/the-tao-of-tmux/read

## Cheat Sheet

https://leanpub.com/the-tao-of-tmux/read#appendix-cheatsheets

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

### Automatic Resizing Multiple Panes

```
C-b M-1             # vertical split, all panes same width
C-b M-2             # horizontal split, all panes same height
C-b M-3             # horizontal split, main pane on top,
                      other panes on bottom, vertically split, all same width
C-b M-4             # vertical split, main pane left,
                      other panes right, horizontally split, all same height
C-b M-5             # tile, new panes on bottom, same height before same width
```

> Where M denotes the meta key, usually bound to ALT.

_Useful notes copied from [stackoverflow](https://superuser.com/questions/456775/how-to-auto-resize-panes-in-tmux), thanks to user n0rc!_
