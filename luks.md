# LUKS

## Prerequistes

Install the following package: `cryptsetup`

## Check Device Name First

Check plugged in device first: `sudo dmesg`

Should output something e.g. `sdX`

## Create an Encrypted Device

`sudo cryptsetup --type luks2 luksFormat /dev/sdX`

## Mount Encrypted Device

### Open Device

`sudo cryptsetup open /dev/sdX device_name`

### Close an Encrypted Device

`sudo cryptsetup close device_name`

## Check Status of Encrypted Device

`sudo cryptsetup status device_name`
