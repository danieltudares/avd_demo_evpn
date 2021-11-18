# BC-OOBM1 Commands Output

## Table of Contents

- [show lldp neighbors](#show-lldp-neighbors)
- [show ip interface brief](#show-ip-interface-brief)
- [show interfaces description](#show-interfaces-description)
- [show version](#show-version)
- [show running-config](#show-running-config)
## show interfaces description

```
Interface                      Status         Protocol           Description
Et1                            up             up                 BC-CORE-PAN-FW-OOBM-01_Eth10
Et2                            up             up                 BC-CORE-PAN-FW-OOBM-02_Eth1
Et3                            up             up                 data_server_R2_1_Eth1
Et4                            up             up                 data_server_R2_2_Eth1
Et5                            up             up                 data_server_R3_1_Eth1
Et6                            up             up                 data_server_R3_2_Eth1
Et7                            up             up                 storage_server_R4_1_Eth1
Et8                            up             up                 storage_server_R4_2_Eth1
Et9                            up             up                 storage_server_R5_1_Eth1
Et10                           up             up                 
Et11                           up             up                 
Et12                           up             up                 
Et13                           up             up                 
Et14                           up             up                 
Et15                           up             up                 cvp_server_oobm1_Eth1
Et16                           up             up                 MLAG_PEER_BC-OOBM2_Ethernet16
Et17                           up             up                 MLAG_PEER_BC-OOBM2_Ethernet17
Ma1                            down           down               
Po1                            down           lowerlayerdown     BC-CORE-PAN-FW-OOBM-01_PortChannel-oobm-FW01
Po2                            down           lowerlayerdown     BC-CORE-PAN-FW-OOBM-02_PortChannel-oobm-FW02
Po3                            down           lowerlayerdown     data_server_R2_1_portchannel-oobm
Po4                            down           lowerlayerdown     data_server_R2_2_portchannel-oobm
Po5                            down           lowerlayerdown     data_server_R3_1_portchannel-oobm
Po6                            down           lowerlayerdown     data_server_R3_2_portchannel-oobm
Po7                            down           lowerlayerdown     storage_server_R4_1_portchannel-oobm
Po8                            down           lowerlayerdown     storage_server_R4_2_portchannel-oobm
Po9                            down           lowerlayerdown     storage_server_R5_1_portchannel-oobm
Po16                           up             up                 MLAG_PEER_BC-OOBM2_Po16
Vl100                          up             up                 oob_management
Vl4094                         up             up                 MLAG_PEER
```
## show ip interface brief

```
Address 
Interface       IP Address          Status      Protocol         MTU    Owner   
--------------- ------------------- ----------- ------------- --------- ------- 
Management1     unassigned          down        down            1500            
Vlan100         172.20.21.13/23     up          up              1500            
Vlan4094        10.255.252.0/31     up          up              1500
```
## show lldp neighbors

```
Last table change time   : 0:33:38 ago
Number of table inserts  : 2
Number of table deletes  : 0
Number of table drops    : 0
Number of table age-outs : 0

Port          Neighbor Device ID           Neighbor Port ID    TTL 
---------- ---------------------------- ---------------------- --- 
Et16          BC-OOBM2.tudareslab.io       Ethernet16          120 
Et17          BC-OOBM2.tudareslab.io       Ethernet17          120
```
## show running-config

```
! Command: show running-config
! device: BC-OOBM1 (vEOS-lab, EOS-4.26.2F)
!
! boot system flash:/vEOS-lab.swi
!
no aaa root
!
username admin privilege 15 role network-admin secret sha512 $6$LJcUms0WZ9UyskIF$b6jUZMJmruk95uA0GPood4z4Tgb2aHKqnRhm7HyHl3kjsgE6mA5.V3W/vwl16WeICFvWWz1vkU1zQET0CbILG0
username cvpadmin privilege 15 role network-admin secret sha512 $6$pWE0vYbIJTmV0ZWc$nIrbLNYS3pIgpFj9vuzkchwyA19betlJZjWR.KE95GHwOALliiUUAu92JUWg9jQ12Yd3.aTQmWf.gRe2VNo2Y.
!
daemon TerminAttr
   exec /usr/bin/TerminAttr -cvaddr=172.20.21.10:9910 -cvauth=key,arista -cvvrf=default -smashexcludes=ale,flexCounter,hardware,kni,pulse,strata -ingestexclude=/Sysdb/cell/1/agent,/Sysdb/cell/2/agent -taillogs
   no shutdown
!
vlan internal order ascending range 1006 1199
!
transceiver qsfp default-mode 4x10G
!
service routing protocols model multi-agent
!
hostname BC-OOBM1
ip name-server vrf default 172.20.20.6
dns domain tudareslab.io
!
spanning-tree mode mstp
no spanning-tree vlan-id 4094
spanning-tree mst 0 priority 4096
!
clock timezone America/Toronto
!
vlan 100
!
vlan 4094
   name MLAG_PEER
   trunk group MLAG
!
management api http-commands
   no shutdown
   !
   vrf default
      no shutdown
!
interface Port-Channel1
   description BC-CORE-PAN-FW-OOBM-01_PortChannel-oobm-FW01
   switchport access vlan 100
   mlag 1
!
interface Port-Channel2
   description BC-CORE-PAN-FW-OOBM-02_PortChannel-oobm-FW02
   switchport access vlan 100
   mlag 2
!
interface Port-Channel3
   description data_server_R2_1_portchannel-oobm
   switchport access vlan 100
   mlag 3
!
interface Port-Channel4
   description data_server_R2_2_portchannel-oobm
   switchport access vlan 100
   mlag 4
!
interface Port-Channel5
   description data_server_R3_1_portchannel-oobm
   switchport access vlan 100
   mlag 5
!
interface Port-Channel6
   description data_server_R3_2_portchannel-oobm
   switchport access vlan 100
   mlag 6
!
interface Port-Channel7
   description storage_server_R4_1_portchannel-oobm
   switchport access vlan 100
   mlag 7
!
interface Port-Channel8
   description storage_server_R4_2_portchannel-oobm
   switchport access vlan 100
   mlag 8
!
interface Port-Channel9
   description storage_server_R5_1_portchannel-oobm
   switchport access vlan 100
   mlag 9
!
interface Port-Channel16
   description MLAG_PEER_BC-OOBM2_Po16
   switchport trunk allowed vlan 2-4094
   switchport mode trunk
   switchport trunk group MLAG
!
interface Ethernet1
   description BC-CORE-PAN-FW-OOBM-01_Eth10
   no snmp trap link-change
   channel-group 1 mode active
!
interface Ethernet2
   description BC-CORE-PAN-FW-OOBM-02_Eth1
   no snmp trap link-change
   channel-group 2 mode active
!
interface Ethernet3
   description data_server_R2_1_Eth1
   no snmp trap link-change
   channel-group 3 mode active
!
interface Ethernet4
   description data_server_R2_2_Eth1
   no snmp trap link-change
   channel-group 4 mode active
!
interface Ethernet5
   description data_server_R3_1_Eth1
   no snmp trap link-change
   channel-group 5 mode active
!
interface Ethernet6
   description data_server_R3_2_Eth1
   no snmp trap link-change
   channel-group 6 mode active
!
interface Ethernet7
   description storage_server_R4_1_Eth1
   no snmp trap link-change
   channel-group 7 mode active
!
interface Ethernet8
   description storage_server_R4_2_Eth1
   no snmp trap link-change
   channel-group 8 mode active
!
interface Ethernet9
   description storage_server_R5_1_Eth1
   no snmp trap link-change
   channel-group 9 mode active
!
interface Ethernet10
!
interface Ethernet11
!
interface Ethernet12
!
interface Ethernet13
!
interface Ethernet14
!
interface Ethernet15
   description cvp_server_oobm1_Eth1
   switchport access vlan 100
   no snmp trap link-change
!
interface Ethernet16
   description MLAG_PEER_BC-OOBM2_Ethernet16
   channel-group 16 mode active
!
interface Ethernet17
   description MLAG_PEER_BC-OOBM2_Ethernet17
   channel-group 16 mode active
!
interface Management1
!
interface Vlan100
   description oob_management
   ip address 172.20.21.13/23
!
interface Vlan4094
   description MLAG_PEER
   no autostate
   ip address 10.255.252.0/31
!
ip routing
!
mlag configuration
   domain-id BC_OOBM
   local-interface Vlan4094
   peer-address 10.255.252.1
   peer-link Port-Channel16
   reload-delay mlag 300
   reload-delay non-mlag 330
!
ip route 0.0.0.0/0 172.20.20.1
!
ntp server 0.north-america.pool.ntp.org iburst
ntp server 1.north-america.pool.ntp.org iburst
!
end
```
## show version

```
Arista vEOS-lab
Hardware version: 
Serial number: AFF242C7D9303B18CC6DC32F14C0F3E2
Hardware MAC address: 5001.0035.8fcf
System MAC address: 5001.0035.8fcf

Software image version: 4.26.2F
Architecture: i686
Internal build version: 4.26.2F-23563874.4262F
Internal build ID: fa3a49f3-6093-4925-ad11-55fe15eac5ae
Image format version: 1.0

Uptime: 40 minutes
Total memory: 4002528 kB
Free memory: 2985304 kB
```
