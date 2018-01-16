# My Private Desktop Installation

OS: Debian Stretch

## Package Repositories

Location of Source Repository List: 

```
/etc/apt/sources.list
```

Content of the Source Repository List:

```
deb  http://deb.debian.org/debian stretch main contrib non-free
deb-src  http://deb.debian.org/debian stretch main contrib non-free

deb  http://deb.debian.org/debian stretch-updates main contrib non-free
deb-src  http://deb.debian.org/debian stretch-updates main contrib non-free

deb http://security.debian.org/ stretch/updates main contrib non-free
deb-src http://security.debian.org/ stretch/updates main contrib non-free
```

Adding Backports for Strech:
```
deb http://ftp.debian.org/debian stretch-backports main
```

Update Repository References: 
```
apt-get update
```

## Adding User to Sudoers

First install required package:
```
apt-get install sudo
```

_cat /etc/sudoers_

```
# User privilege specification
root	 ALL=(ALL:ALL) ALL
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

Since installing packages from backports is deactivated by default run the following command to install a package from the backport:
```
apt-get -t stretch-backports install "package"
```

List of all available packages from backport:
_https://packages.debian.org/stretch-backports/allpackages_
