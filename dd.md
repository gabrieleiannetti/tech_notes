# DD

## Copy Image File

`sudo dd of=/dev/sdX if=image.iso bs=4M conv=fsync status=progress`

## Testing Sequential IO Write Performance on a Device

Useful to test sequential wirte speed on e.g. USB stick.
3 runs are done step by step...
(probably a fsync is required after each run,
since the performance gets slightly worse after each run?)

```bash
for i in {1..3}; do dd if=/dev/zero of=/run/media/user/usb_stick/test_$i.txt bs=1G count=1 oflag=direct; done
```
