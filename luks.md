# Prerequistes

Install the following package: `cryptsetup`

# Mounting an Encrypted Device

```
1. cryptsetup open /dev/sdxx backup
2. mount /dev/mapper/backup /media/user/backup
```
