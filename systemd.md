# systemd

## systemctl

Reload the systemd manager configuration:  
`systemctl daemon-reload`

List all units installed in the file system:  
`systemctl list-unit-files`

List all enabled units installed in the file system:  
`systemctl list-unit-files --state=enabled`
