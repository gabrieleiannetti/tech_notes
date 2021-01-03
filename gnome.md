# GNOME 3

## Keyboard Shortcuts

https://wiki.gnome.org/Design/OS/KeyboardShortcuts

## Customization Apps

Install:  

* Extensions
* Tweaks

## Removal of Apps

* malcontent (Parental Controls)

## Deactivating Annoying Beep Sound for a Current Logged In User

```
gsettings set org.gnome.desktop.sound event-sounds false
```

## Font Settings

* Open Gnome Tweaks
* Open Fonts
    * Set **Hinting**: Full
    * Set **Antialiasing**: Subpixel
    * Set **Scaling Factor**: 1,25

## Creation of Application Icons

### Icon Locations

User specific location: ~/.local/share/applications/  
System-wide location: /usr/share/applications/  

### Freemind

freemind.desktop  

```
[Desktop Entry]
Name=Freemind
Comment=Freemind
Keywords=freemind;mindmap
Exec=/home/iannetti/apps/freemind-bin-1.0.1/freemind.sh
Terminal=false
Type=Application
Icon=/home/iannetti/apps/freemind-bin-1.0.1/images/76812-freemind_v0.4.png
Categories=Utility;
```

_The freemind icon file has been extracted from the freemindbrowser.jar application file._ 
