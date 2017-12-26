# Fedora 27 Workstation Installation

## Upgrade System

```sudo dnf upgrade --refresh```

## Guide for Installation of Proprietary NVIDIA Graphics Card Driver

URL: https://www.if-not-true-then-false.com/2015/fedora-nvidia-guide/

## Installation of Spotify

URL: https://fedoraproject.org/wiki/Spotify

_Worked_:

```
dnf config-manager --add-repo=http://negativo17.org/repos/fedora-spotify.repo
dnf install spotify
```

## Installation of Misc Software

```sudo dnf install```

* gnome-tweak-tool
* htop
* keepassx
