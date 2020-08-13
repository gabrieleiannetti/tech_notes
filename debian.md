# Debian Installation

## Package Repositories

Package repository list `/etc/apt/sources.list`:

```
deb http://deb.debian.org/debian buster main contrib non-free
deb-src http://deb.debian.org/debian buster main contrib non-free

deb http://deb.debian.org/debian-security/ buster/updates main contrib non-free
deb-src http://deb.debian.org/debian-security/ buster/updates main contrib non-free

deb http://deb.debian.org/debian buster-updates main contrib non-free
deb-src http://deb.debian.org/debian buster-updates main contrib non-free

deb http://deb.debian.org/debian buster-backports main contrib non-free
deb-src http://deb.debian.org/debian buster-backports main contrib non-free
```

Update repository references: `apt-get update`

## Sudoers

First install required package: `apt-get install sudo`

Add new USER to sudoers file `/etc/sudoers`:  

```
root ALL=(ALL:ALL) ALL
USER ALL=(ALL:ALL) ALL
```

## Firefox

* `sudo apt install -t unstable firefox`
* `sudo apt purge firefox-esr`
