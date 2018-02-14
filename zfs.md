# OpenZFS

## Working with ZPools

Make ZPool mountable:  
`zfs set canmount=on osspool0/ost0`

Mount ZPool:  
`zfs mount osspool0/ost0`

Umount ZPool:  
`zfs umount osspool2/ost2`

Deactivate automount(?) for ZPool:  
`zfs canmount=off osspool2/ost2`
