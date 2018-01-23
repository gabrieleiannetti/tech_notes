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

### Pycharm Icon
```
[Desktop Entry]
Name=Pycharm
Comment=Python Pycharm IDE
Keywords=python;development;ide
Exec=/home/iannetti/apps/pycharm-community/bin/pycharm.sh
Terminal=false
Type=Application
Icon=/home/iannetti/apps/pycharm-community/bin/pycharm.png
Categories=Development;

```
