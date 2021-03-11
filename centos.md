# CentOS

## Updates

Exclude kernel from updating:  
`yum -y --exclude=kernel\* update`

## Deactivate Services for Testing System Installations

`systemctl disable firewalld`
