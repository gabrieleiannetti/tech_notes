# Prerequistes

Install the following package: `cryptsetup`

# Mounting an Encrypted Device

## Check New Device First

Check plugged in device first: `sudo dmesg`

Should output something e.g. `sdc`

## Open/Mount Device

!!! Use the first partition of the device e.g. sdc1 not sdc !!!

```
1. sudo cryptsetup open /dev/sdc1 usb_stick
2. sudo mount /dev/mapper/usb_stick /media/user/usb_stick
```

# Check Status of Encrypted Device

```
sudo cryptsetup status usb_stick
```

# Umount/Close Device

```
1. sudo umount /media/user/usb_stick
2. sudo cryptsetup close usb_stick
```
