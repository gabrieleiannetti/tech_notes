# Network

## ip - show / manipulate routing, devices, policy routing and tunnels

**Show Link Status:**  
```ip link show```  

**Show IP Address:**  
```ip addr show```  

## nmcli - command-line tool for controlling NetworkManager

**Readable output for humans:**  
```nmcli -p```  

**Show all connection profiles:**  
```
$ nmcli connection show

    NAME  UUID                                  TYPE      DEVICE
    eth0  0f53c41e-e3d1-4610-ae68-67114604368c  ethernet  eth0
```  

**Show details for specific connection:**  
```$ nmcli connection show 0f53c41e-e3d1-4610-ae68-67114604368c```   


**Print DHCP related options for specific connection:**  
```
$ nmcli connection show 0f53c41e-e3d1-4610-ae68-67114604368c | grep dhcp

    DHCP4.OPTION[1]:                        broadcast_address = 10.1.1.255
    DHCP4.OPTION[2]:                        dhcp_lease_time = 3600
    DHCP4.OPTION[3]:                        dhcp_message_type = 5
    DHCP4.OPTION[4]:                        dhcp_rebinding_time = 2962
    DHCP4.OPTION[5]:                        dhcp_renewal_time = 1612
    DHCP4.OPTION[6]:                        dhcp_server_identifier = 10.1.1.1
    DHCP4.OPTION[7]:                        domain_name = devops.test
    DHCP4.OPTION[8]:                        domain_name_servers = 10.1.1.1
    DHCP4.OPTION[9]:                        expiry = 1596022877
    DHCP4.OPTION[10]:                       ip_address = 10.1.1.231
    DHCP4.OPTION[11]:                       network_number = 10.1.1.0
    DHCP4.OPTION[12]:                       next_server = 10.1.1.1
    DHCP4.OPTION[13]:                       requested_broadcast_address = 1
    DHCP4.OPTION[14]:                       requested_classless_static_routes = 1
    DHCP4.OPTION[15]:                       requested_domain_name = 1
    DHCP4.OPTION[16]:                       requested_domain_name_servers = 1
    DHCP4.OPTION[17]:                       requested_domain_search = 1
    DHCP4.OPTION[18]:                       requested_host_name = 1
    DHCP4.OPTION[19]:                       requested_interface_mtu = 1
    DHCP4.OPTION[20]:                       requested_ms_classless_static_routes = 1
    DHCP4.OPTION[21]:                       requested_nis_domain = 1
    DHCP4.OPTION[22]:                       requested_nis_servers = 1
    DHCP4.OPTION[23]:                       requested_ntp_servers = 1
    DHCP4.OPTION[24]:                       requested_rfc3442_classless_static_routes = 1
    DHCP4.OPTION[25]:                       requested_root_path = 1
    DHCP4.OPTION[26]:                       requested_routers = 1
    DHCP4.OPTION[27]:                       requested_static_routes = 1
    DHCP4.OPTION[28]:                       requested_subnet_mask = 1
    DHCP4.OPTION[29]:                       requested_time_offset = 1
    DHCP4.OPTION[30]:                       requested_wpad = 1
    DHCP4.OPTION[31]:                       routers = 10.1.1.1
    DHCP4.OPTION[32]:                       subnet_mask = 255.255.255.0
```
