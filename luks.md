# Prerequistes

Install the following package: `cryptsetup`

# Mount an Encrypted Device

## Check New Device First

Check plugged in device first: `sudo dmesg`

Should output something e.g. `sdc`

## Open/Mount Device

```
1. sudo cryptsetup open /dev/sdc1 usb_stick
2. sudo mount /dev/mapper/usb_stick /media/user/usb_stick
```
> Use the first partition of the device e.g. sdc1 not the device sdc itself!

# Umount/Close an Encrypted Device

```
1. sudo umount /media/user/usb_stick
2. sudo cryptsetup close usb_stick
```

# Check Status of Encrypted Device

```
sudo cryptsetup status usb_stick
```
