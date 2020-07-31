# Creating a FAT32 USB Stick

Check that the device has been connected and recognized by the kernel:  

```sudo dmesg -wH```

    ...
    [ +18,618209] usb 6-1: USB disconnect, device number 5
    [  +2,638411] usb 6-1: new SuperSpeed Gen 1 USB device number 6 using xhci_hcd
    [  +0,030761] usb 6-1: New USB device found, idVendor=0951, idProduct=16a2, bcdDevice= 1.00
    [  +0,000006] usb 6-1: New USB device strings: Mfr=1, Product=2, SerialNumber=3
    [  +0,000003] usb 6-1: Product: DTR30G2
    [  +0,000003] usb 6-1: Manufacturer: Kingston
    [  +0,000003] usb 6-1: SerialNumber: 0018F30BFF7DBF7081315F44
    [  +0,001228] usb-storage 6-1:1.0: USB Mass Storage device detected
    [  +0,000396] scsi host6: usb-storage 6-1:1.0
    [  +1,002032] scsi 6:0:0:0: Direct-Access     Kingston DTR30G2          PMAP PQ: 0 ANSI: 6
    [  +0,316519] sd 6:0:0:0: [sdc] 120979456 512-byte logical blocks: (61.9 GB/57.7 GiB)
    [  +0,000877] sd 6:0:0:0: [sdc] Write Protect is off
    [  +0,000005] sd 6:0:0:0: [sdc] Mode Sense: 23 00 00 00
    [  +0,000839] sd 6:0:0:0: [sdc] No Caching mode page found
    [  +0,000004] sd 6:0:0:0: [sdc] Assuming drive cache: write through
    [  +0,030718]  sdc: sdc1
    [  +0,002467] sd 6:0:0:0: [sdc] Attached SCSI removable disk

Create new FAT32 "W95 FAT32 (LBA)" partition table if it does not exist already:  

```sudo fdisk /dev/sdc1```

    Command (m for help): n                                                        
    Partition type                                                                 
       p   primary (0 primary, 0 extended, 4 free)                                 
       e   extended (container for logical partitions)                             
    Select (default p): p                                                          
    Partition number (1-4, default 1):                                             
    First sector (2048-120977407, default 2048):                                   
    Last sector, +/-sectors or +/-size{K,M,G,T,P} (2048-120977407, default 120977407):
                                                                                   
    Created a new partition 1 of type 'Linux' and of size 57,7 GiB.                
                                                                                   
    Command (m for help): t                                                        
    Selected partition 1                                                           
    Hex code (type L to list all codes): L                                         
                                                                                   
     0  Empty           24  NEC DOS         81  Minix / old Lin bf  Solaris        
     1  FAT12           27  Hidden NTFS Win 82  Linux swap / So c1  DRDOS/sec (FAT-
     2  XENIX root      39  Plan 9          83  Linux           c4  DRDOS/sec (FAT-
     3  XENIX usr       3c  PartitionMagic  84  OS/2 hidden or  c6  DRDOS/sec (FAT-
     4  FAT16 <32M      40  Venix 80286     85  Linux extended  c7  Syrinx         
     5  Extended        41  PPC PReP Boot   86  NTFS volume set da  Non-FS data    
     6  FAT16           42  SFS             87  NTFS volume set db  CP/M / CTOS / .
     7  HPFS/NTFS/exFAT 4d  QNX4.x          88  Linux plaintext de  Dell Utility   
     8  AIX             4e  QNX4.x 2nd part 8e  Linux LVM       df  BootIt         
     9  AIX bootable    4f  QNX4.x 3rd part 93  Amoeba          e1  DOS access     
     a  OS/2 Boot Manag 50  OnTrack DM      94  Amoeba BBT      e3  DOS R/O        
     b  W95 FAT32       51  OnTrack DM6 Aux 9f  BSD/OS          e4  SpeedStor      
     c  W95 FAT32 (LBA) 52  CP/M            a0  IBM Thinkpad hi ea  Linux extended 
     e  W95 FAT16 (LBA) 53  OnTrack DM6 Aux a5  FreeBSD         eb  BeOS fs        
     f  W95 Ext'd (LBA) 54  OnTrackDM6      a6  OpenBSD         ee  GPT            
    10  OPUS            55  EZ-Drive        a7  NeXTSTEP        ef  EFI (FAT-12/16/
    11  Hidden FAT12    56  Golden Bow      a8  Darwin UFS      f0  Linux/PA-RISC b
    12  Compaq diagnost 5c  Priam Edisk     a9  NetBSD          f1  SpeedStor      
    14  Hidden FAT16 <3 61  SpeedStor       ab  Darwin boot     f4  SpeedStor      
    16  Hidden FAT16    63  GNU HURD or Sys af  HFS / HFS+      f2  DOS secondary  
    17  Hidden HPFS/NTF 64  Novell Netware  b7  BSDI fs         fb  VMware VMFS    
    18  AST SmartSleep  65  Novell Netware  b8  BSDI swap       fc  VMware VMKCORE 
    1b  Hidden W95 FAT3 70  DiskSecure Mult bb  Boot Wizard hid fd  Linux raid auto
    1c  Hidden W95 FAT3 75  PC/IX           bc  Acronis FAT32 L fe  LANstep        
    1e  Hidden W95 FAT1 80  Old Minix       be  Solaris boot    ff  BBT            
    Hex code (type L to list all codes): c
    Changed type of partition 'Linux' to 'W95 FAT32 (LBA)'.

    Command (m for help): p
    Disk /dev/sdc1: 57,7 GiB, 61940432896 bytes, 120977408 sectors
    Units: sectors of 1 * 512 = 512 bytes
    Sector size (logical/physical): 512 bytes / 512 bytes
    I/O size (minimum/optimal): 512 bytes / 512 bytes
    Disklabel type: dos
    Disk identifier: 0xb8e740a7
    
    Device      Boot Start       End   Sectors  Size Id Type
    /dev/sdc1p1       2048 120977407 120975360 57,7G  c W95 FAT32 (LBA)
    
    Command (m for help): w
    The partition table has been altered.
    Syncing disks.

Check created partition:  

```sudo  fdisk -l```

    ...
    Disk /dev/sdc: 57,7 GiB, 61941481472 bytes, 120979456 sectors
    Disk model: DTR30G2         
    Units: sectors of 1 * 512 = 512 bytes
    Sector size (logical/physical): 512 bytes / 512 bytes
    I/O size (minimum/optimal): 512 bytes / 512 bytes
    Disklabel type: dos
    Disk identifier: 0x00000000
    
    Device     Boot Start       End   Sectors  Size Id Type
    /dev/sdc1        2048 120979455 120977408 57,7G  c W95 FAT32 (LBA)

Format partition with FAT32:  

```sudo mkdosfs -F 32 -I /dev/sdc1```

Set volume name for the filesystem:  

```sudo mkfs.vfat /dev/sdc1 -n king```

