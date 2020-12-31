# Manjaro Linux

## Overview of the Package Manager

[Pacman Overview](https://wiki.manjaro.org/index.php?title=Pacman_Overview)

## Installing Packages

* **host** command: `sudo pacman -S bind`

## Removing Packages

* If using NVIDIA driver drop the Radeon related packages and vice versa...
* manjaro-hello

## Installation and Configuration of Graphics Card

### Overview

* [Configuration of Graphics Card](https://wiki.manjaro.org/Configure_Graphics_Cards)
* [NVIDIA Graphics Card Driver](https://wiki.manjaro.org/index.php?title=Configure_NVIDIA_(non-free)_settings_and_load_them_on_Startup)

### Snippets

Show Graphic card(s) information:  
```inxi -G```

List appropriate drivers available:  
```mhwd -l```

List installed driver configs:  
```mhwd -li```

Install video-nvidia-450xx driver:  
```sudo mhwd -i pci video-nvidia-450xx```

Force reinstallation of video-nvidia-450xx driver:  
```sudo mhwd -f -i pci video-nvidia-450xx```

Removing installed video driver:  
```sudo mhwd -r pci video-nvidia-455xx```

## Installing Printer

Printer relevant modules e.g. CUPS might be not installed/activated on Manjaro.  
Therefore it is necessary to installed the requirements.  

Follow notes at:  
https://wiki.manjaro.org/index.php?title=Printing

