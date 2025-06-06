Steps to configure the router

Clearing the current settings for the GigabitEthernet port:
```
configure terminal
default interface GigabitEthernet0/0
no interface GigabitEthernet0/0.2
no interface GigabitEthernet0/0.100
```

Once reset, configure router-on-a-stick setup:
For sub-interface 1
````
interface GigabitEthernet0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0
exit
````
For sub-interface 2
```
interface GigabitEthernet0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0
exit
```
For default port
```
interface GigabitEthernet0/0
 no shutdown
exit
exit
write memory
```