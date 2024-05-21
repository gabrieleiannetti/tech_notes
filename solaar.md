# Solaar

[Solaar](https://github.com/pwr-Solaar/Solaar) is a Linux manager for many Logitech keyboards, mice, and other devices that connect wirelessly to a Unifying, Bolt, Lightspeed or Nano receiver as well as many Logitech devices that connect via a USB cable or Bluetooth.

## Config File

Config file should be located at: `/etc/xdg/autostart/solaar.desktop`

Execution of program should be set to hide window:  
```bash
$ grep 'hide' /etc/xdg/autostart/solaar.desktop
Exec=solaar --window=hide
```
