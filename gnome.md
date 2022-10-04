# GNOME 3

## Keyboard Shortcuts

https://wiki.gnome.org/Design/OS/KeyboardShortcuts

## Customization Apps

* gnome-tweaks

## Removal of Apps

* malcontent (Parental Controls)

## Deactivating Annoying Beep Sound for a Current Logged In User

```
gsettings set org.gnome.desktop.sound event-sounds false
```

## Deactivate Search and Indexing

Navigate to Gnome Settings **Settings->Search** and deactivate search function.

Afterwards the already created cache of the tracker application can also  
be deleted:  

```bash
$ du -sh ~/.cache/tracker
3,7M    /home/gia/.cache/tracker

$ du -sh ~/.cache/tracker3 
17M     /home/gia/.cache/tracker3

rm -rf ~/.cache/tracker/*
rm -rf ~/.cache/tracker3/*
```

The tracker process should also be offline:  `ps aux | grep tracker`

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
