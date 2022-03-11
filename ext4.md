# ext4

Caution on device names e.g. LUKS encrypted devices might be opened at `/dev/mapper/XXX`.

Format device:  
`sudo mkfs.ext4 /dev/XXX`

Set label:  
`sudo e2label /dev/XXX label`
