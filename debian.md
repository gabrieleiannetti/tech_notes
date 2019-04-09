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

Update Repository References: `apt-get update`

## Adding User to Sudoers

First install required package: `apt-get install sudo`

Edit sudoers file `/etc/sudoers`:  

```
  root     ALL=(ALL:ALL) ALL  
  gabriele ALL=(ALL:ALL) ALL
```


## Installing NVIDIA Proprietary Graphics Card Driver

Notes taken from URL:
_https://wiki.debian.org/NvidiaGraphicsDrivers_

Add "contrib" and "non-free" components to /etc/apt/sources.list:
```
deb http://httpredir.debian.org/debian/ stretch main contrib non-free
```

Update the List of Available Packages:
```
apt update
```

Install the Appropriate Linux-Headers and Kernel Module Packages:
```
apt install linux-headers-$(uname -r|sed 's/[^-]*-[^-]*-//') nvidia-driver
```

Finnally do a reboot of the maschine.

## Installing Packages from Backport

Installation of packages from backport is deactivated by default.
To install packages manually do:
```
apt-get -t stretch-backports install "package"
```

List of all available packages from backport:
_https://packages.debian.org/stretch-backports/allpackages_
