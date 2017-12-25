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

Update Repository References: 
```
apt-get update
```

## Adding User to Sudo Group

```
apt-get install sudo
apt-get install adduser
adduser gabriele sudo
```


## Installing NVIDIA Geforce 660GTX Graphics Card

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