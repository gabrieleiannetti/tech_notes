# TMUX

## Free Book to Read

https://leanpub.com/the-tao-of-tmux/read

## Best Pactices and Cntrol Commands

In the following with __prefix__ the default key combinatiob of __ctrl + b__ is meant.

### Listining of Key Bindings

__tmux list-keys__ or __prefix + ?__ 

### Copy and Paste

Instructions are originally taken from this post on [unix.stackexchange.com](https://unix.stackexchange.com/questions/58763/copy-text-from-one-tmux-pane-to-another-using-vim).

1. Enter copy mode: __prefix__ + __[__.
2. Navigate to start position with arrow keys.
3. Switch layout: __prefix__ + __space__ key.
4. Navigate to end position with arrow keys.
5. Copy text into clipboard: __ctrl__ + __w__.
6. For pasting press __ctrl__ + __]__ then.
