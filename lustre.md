# Lustre Notes

## Installing the Lustre client on Kronos

Unmounting the Lustre mount point before installation:  
`umount -lf /lustre/nyx`

Update package repository:  
`apt update`  

Search pakets for Lustre:  
`apt search lustre`  

Query APT cache for Lustre client modules.
We are looking for the Lustre client in version 2.10 located currently in the jessie-testing repository:  
`apt-cache policy lustre-client-modules-3.16.0-4-amd64`  

lustre-client-modules-3.16.0-4-amd64:  
```
  Installed: 2.10.0-38-g86421e7-dirty-1
  Candidate: 2.10.0-38-g86421e7-dirty-1
  Version table:
 *** 2.10.0-38-g86421e7-dirty-1 0
        400 http://mirror.gsi.de/distrib/gsi-repository/ jessie-testing/main amd64 Packages
        100 /var/lib/dpkg/status
     2.6.92-6 0
        500 http://mirror.gsi.de/distrib/gsi-repository/ jessie/main amd64 Packages
```

Install Lustre client modules from jessie-testing repository:  
`apt install -t jessie-testing lustre-client-modules-3.16.0-4-amd64`

Install Lustre client utils from jessie-testing repository:  
`apt install -t jessie-testing lustre-client-utils`

List installed lustre packages:  
`dpkg -l | grep lustre`

## Changelog Related

Checking set changelogs on a MDT:  
`lctl get_param mdd.*.changelog_mask`

Setting the changelog mask in Lustre version 2.5:  
`lctl set_param mdd.*.changelog_mask "MARK CREAT MKDIR HLINK SLINK MKNOD UNLNK RMDIR RENME RNMTO OPEN CLOSE LYOUT TRUNC SATTR XATTR HSM MTIME CTIME"`

## Working with Target Disk Information

Viewing Lustre target disk information of an OST:  
`tunefs.lustre --dryrun osspool2/ost2`
