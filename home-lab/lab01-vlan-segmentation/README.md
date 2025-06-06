# VLAN Segmentation & Trunking
So the goal for this lab is to properly configure 1 physical router and 1 physical switch. Two VLANs are created and segmented using the switches, and then they are connected together using the router.

## Some Key Features
* Create VLAN 10 and VLAN 20 on a managed switch
* Assign switchports to the correct VLANs
* Configure trunking between the switch and router
* Configure router subinterfaces with dot1Q encapsulation
* Assign correct IP addressing to devices in each VLAN
* Successfully ping VLAN 10 gateway from VLAN 10 host
* Successfully ping VLAN 20 gateway from VLAN 20 host
* Successfully ping across VLANs via router
* Foundation for NAT/DHCP for future labs

## Overview
### 1. Configure the switch
Following the configs/switch_config.md


### 2. Configure the router:
Following the configs/router_config.md


### 3. Connect the devices
I connected my switch's FastEthernet1/0/24 (set as trunking), to my router's GigabitEthernet0.0 port

Physically connected:
- Switch fa0/24 → Router fa0/0


### 4. Confirming that the interfaces and subinterfaces are up
Running
    ```show ip interface brief```
        on the router and then the switch to make sure the correct interfaces are in the up status.

### 5. Testing vlans & routing

Physically connected:
- PC #1 to Switch fa0/1
- PC #2 to Switch fa0/2

<br>Plugged my PC1 into the switch's FastEthernet1/0/1
<br>Plugged my PC2 into the switch's FastEthernet1/0/2
<br>Manually configured the ip addresses for the devices, with a default gateway of the router.
<br>Pinged the devices