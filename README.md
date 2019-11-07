### Comunicación entre VLANS 

## Para switch

enable
configure terminal

vtp mode server
vtp domain nombre_server
vtp password 1234

vlan 100
name nombre_vlan
exit

interface fastethernet 0/1
sw mode trunk

interface fastethernet 0/2
sw mode trunk


show vtp status
show vlan

/// cliente

enable
configure terminal
vtp domain nombre_server
vtp mode client
vtp password 1234


//conect con el switch
interface fastethernet 0/2  
sw mode trunk

// conect con el PC
interface fastethernet 0/1
sw access vlan 200
exit


## Para Router

interface fastEthernet 0/0.10
encapsulation dot1Q 10
ip address 10.0.0.1 255.0.0.0
no shutdown 


interface fastEthernet 0/0.20
encapsulation dot1Q 20
ip address 10.0.0.1 255.0.0.0
no shutdown 

interface fastEthernet 0/0
no shutdown
