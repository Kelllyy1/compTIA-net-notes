Steps to configure the switch

enable
configure terminal
hostname Switch1

1. Create two VLANs
```
vlan 10
name HR
exit 
```
```
vlan 20
 name IT
exit
```

2. Assign access ports
```
interface FastEthernet1/0/1
 switchport mode access
 switchport access vlan 10
exit
```
```
interface FastEthernet0/2
 switchport mode access
 switchport access vlan 20
exit
```

3. Configure trunk port to router
```
interface FastEthernet0/24
 switchport mode trunk
exit
```

4. Save configurations
```
end
write memory
```

~Switch successfully configured~