# GRUB

Disabling GRUB boot menu completely.  

Edit `/etc/default/grub`:  

```
...
GRUB_TIMEOUT=0
GRUB_TIMEOUT_STYLE=hidden
GRUB_DISABLE_OS_PROBER=true
```

Since another OS is installed on another disk, the parameter **GRUB_DISABLE_OS_PROBER=true** is required to hide the menu on start.  

Execute `sudo update-grub` generate new grub config file.
