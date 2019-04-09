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

## Adding User to Sudoers

First install required package: `apt-get install sudo`

Add new USER to sudoers file `/etc/sudoers`:  

```
root ALL=(ALL:ALL) ALL
USER ALL=(ALL:ALL) ALL
```


## Installing NVIDIA Proprietary Graphics Card Driver

Check which graphics card driver is loaded by the Linux kernel:

* NVIDIA driver: `lsmod | grep nvidia`
* Mouveau driver: `lsmod | grep nouveau`

### Detect Graphic Card

The graphic card is detected by the NVIDIA detect application.

Update package repositories to install the proper package `/etc/apt/sources.list`:  
```
deb http://httpredir.debian.org/debian/ stretch main contrib non-free
```

Update repository references: `apt-get update`

Install the package: `nvidia-detect`

Run the NVIDIA detect application.

### Download Driver

The driver is downloaded from the official NVIDIA web page in the driver section.

Download the appropriate driver: `https://www.nvidia.com/Download/index.aspx?lang=en-us`

### Graphics Card Driver Installation

#### Prerequistes

Install required packages for installing the driver first:  
* `gcc`
* `make`
* `linux-headers-$(uname -r|sed 's/[^-]*-[^-]*-//')`

Make driver installer executable: `chmod 755 NVIDIA-Linux-x86_64-390.87.run`  

Blacklist the nouveau driver `/etc/modprobe.d/disable-nouveau.conf`:  
```
blacklist nouveau
options nouveau modeset=0
```

> Important: Check that installed linux-headers match the same linux-image version:
> * `dpkg -l | grep linux-headers` 
> * `dpkg -l | grep linux-image`

Reboot: `sudo reboot`

#### Install the Driver

Open virtual console 1 by pressing: `<CTRL> + <ALT> + <F1>`  

Log in...  

Switch to run level 3 for non-graphical support: `sudo init 3`  

Install the driver: `sudo ./chmod 755 NVIDIA-Linux-x86_64-390.87.run`

Reboot: `sudo reboot`

#### Uninstall the Driver

Uninstall the driver: `sudo ./chmod 755 NVIDIA-Linux-x86_64-390.87.run --uninstall`

Remove the nouveau driver from the blacklist: `sudo rm /etc/modprobe.d/disable-nouveau.conf`:  

Reboot: `sudo reboot`

## Installing Packages from Backport

Installation of packages from backport is deactivated by default.
To install packages manually do:
```
apt-get -t stretch-backports install "package"
```

List of all available packages from backport:
_https://packages.debian.org/stretch-backports/allpackages_
