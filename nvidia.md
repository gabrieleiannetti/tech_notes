# Manual Installation of NVIDIA Proprietary Graphics Card Driver

Check which graphics card driver is loaded by the Linux kernel:

* NVIDIA driver: `lsmod | grep nvidia`
* Nouveau driver: `lsmod | grep nouveau`

## Detect Graphic Card

The following installation steps were executed on Debian,
but the goal here is to install the `nvidia-detect` application.

The graphic card is detected by the NVIDIA detect application.

Update package repositories to install the proper package `/etc/apt/sources.list`:  
`deb http://httpredir.debian.org/debian/ stretch main contrib non-free`

Update repository references: `apt-get update`

Install the package: `nvidia-detect`

Run the NVIDIA detect application.

## Download Driver

The driver is downloaded from the official NVIDIA web page in the driver section.

Download the appropriate driver: `https://www.nvidia.com/Download/index.aspx?lang=en-us`

## Graphics Card Driver Installation

### Prerequistes

Install required packages for installing the driver first:
* `gcc`
* `make`
* `linux-headers-$(uname -r|sed 's/[^-]*-[^-]*-//')`

Make installer executable: `chmod 755 NVIDIA-Linux-x86_64-390.87.run`

Blacklist the nouveau driver `/etc/modprobe.d/disable-nouveau.conf`:  
```
blacklist nouveau
options nouveau modeset=0
```
> Important: Check that installed linux-headers match the same linux-image version:
> * `uname -a`
> * `dpkg -l | grep linux-headers`
> * `dpkg -l | grep linux-image`

Reboot is required to prevent the blacklisted nouveau driver from beeing loaded!

### Install the Driver

Open virtual console 1 by pressing: `<CTRL> + <ALT> + <F1>`

Log in...

Switch to run level 3 for non-graphical support: `sudo init 3`

Make the installer executable: `sudo ./chmod 755 NVIDIA-Linux-x86_64-390.87.run`

Execute the installer: `sudo ./NVIDIA-Linux-x86_64-390.87.run`

Choose the installer to configure the X server!

Reboot the machine: `sudo reboot`

### Uninstall the Driver

Open virtual console 1 by pressing: `<CTRL> + <ALT> + <F1>`

Log in...

Switch to run level 3 for non-graphical support: `sudo init 3`

Uninstall the driver: `sudo ./chmod 755 NVIDIA-Linux-x86_64-390.87.run --uninstall`

Remove the nouveau driver from the blacklist: `sudo rm /etc/modprobe.d/disable-nouveau.conf`:

Reboot the machine: `sudo reboot`
