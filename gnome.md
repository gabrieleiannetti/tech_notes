# GNOME 3 Specific

## Creation of Application Icons

### Icon Locations

User specific location: ~/.local/share/applications/
System-wide location: /usr/share/applications/

### Firefox Icon

cat firefox.desktop

```
[Desktop Entry]
Name=Firefox
Comment=Mozilla Firefox
Keywords=firefox;browser
Exec=/home/iannetti/apps/firefox/firefox
Terminal=false
Type=Application
Icon=/home/iannetti/apps/firefox/browser/icons/mozicon128.png
Categories=Network;
```


