# Debian Installation

## Adding User to Sudoers

First install required package: `apt-get install sudo`

Add new USER to sudoers file `/etc/sudoers`:  

```
root ALL=(ALL:ALL) ALL
USER ALL=(ALL:ALL) ALL
```

# Debian Stretch Installation

## Package Repositories

Package repository list `/etc/apt/sources.list`:

```
deb  http://deb.debian.org/debian stretch main contrib non-free
deb-src  http://deb.debian.org/debian stretch main contrib non-free

deb  http://deb.debian.org/debian stretch-updates main contrib non-free
deb-src  http://deb.debian.org/debian stretch-updates main contrib non-free

deb http://security.debian.org/ stretch/updates main contrib non-free
deb-src http://security.debian.org/ stretch/updates main contrib non-free

deb http://ftp.debian.org/debian stretch-backports main
```

Update repository references: `apt-get update`

## Installing Packages from Stretch-Backport

Installation of packages from backport is deactivated by default.
To install packages manually do:
```
apt-get -t stretch-backports install "package"
```

List of all available packages from backport:
_https://packages.debian.org/stretch-backports/allpackages_
