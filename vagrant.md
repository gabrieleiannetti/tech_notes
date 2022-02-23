# Vagrant

## SSH-CONFIG

Get ssh-config from the virtual machine:  

`vagrant ssh-config VM > ssh-config`

## SCP

Copy FILE to home directory of user vagrant to VM:  

`scp -F ssh-config FILE vagrant@VM:~/`
