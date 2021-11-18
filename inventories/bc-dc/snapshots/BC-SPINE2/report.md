# BC-SPINE2 Commands Output

## Table of Contents

- [show lldp neighbors](#show-lldp-neighbors)
- [show ip interface brief](#show-ip-interface-brief)
- [show interfaces description](#show-interfaces-description)
- [show version](#show-version)
- [show running-config](#show-running-config)
## show interfaces description

```
Interface                      Status         Protocol           Description
Et1                            up             up                 P2P_LINK_TO_BC-BORDERLEAF1_Ethernet2
Et2                            up             up                 P2P_LINK_TO_BC-BORDERLEAF2_Ethernet2
Et3                            up             up                 P2P_LINK_TO_BC-DATALEAF3_Ethernet2
Et4                            up             up                 P2P_LINK_TO_BC-DATALEAF4_Ethernet2
Et5                            up             up                 P2P_LINK_TO_BC-DATALEAF5_Ethernet2
Et6                            up             up                 P2P_LINK_TO_BC-DATALEAF6_Ethernet2
Et7                            up             up                 P2P_LINK_TO_BC-STOLEAF1_Ethernet2
Et8                            up             up                 P2P_LINK_TO_BC-STOLEAF2_Ethernet2
Et9                            up             up                 P2P_LINK_TO_BC-STOLEAF3_Ethernet2
Et10                           up             up                 P2P_LINK_TO_BC-STOLEAF4_Ethernet2
Et11                           up             up                 
Et12                           up             up                 
Et13                           up             up                 
Et14                           up             up                 
Et15                           up             up                 
Et16                           up             up                 
Et17                           up             up                 
Et18                           up             up                 
Et19                           up             up                 
Et20                           up             up                 
Et21                           up             up                 
Et22                           up             up                 
Et23                           up             up                 
Lo0                            up             up                 EVPN_Overlay_Peering
Ma1                            up             up                 oob_management
```
## show ip interface brief

```
Address 
Interface       IP Address           Status     Protocol         MTU    Owner   
--------------- -------------------- ---------- ------------ ---------- ------- 
Ethernet1       172.31.255.2/31      up         up              1500            
Ethernet2       172.31.255.6/31      up         up              1500            
Ethernet3       172.31.255.10/31     up         up              1500            
Ethernet4       172.31.255.14/31     up         up              1500            
Ethernet5       172.31.255.18/31     up         up              1500            
Ethernet6       172.31.255.22/31     up         up              1500            
Ethernet7       172.31.255.26/31     up         up              1500            
Ethernet8       172.31.255.30/31     up         up              1500            
Ethernet9       172.31.255.34/31     up         up              1500            
Ethernet10      172.31.255.38/31     up         up              1500            
Ethernet11      unassigned           up         up              1500            
Ethernet12      unassigned           up         up              1500            
Ethernet13      unassigned           up         up              1500            
Ethernet14      unassigned           up         up              1500            
Ethernet15      unassigned           up         up              1500            
Ethernet16      unassigned           up         up              1500            
Ethernet17      unassigned           up         up              1500            
Ethernet18      unassigned           up         up              1500            
Ethernet19      unassigned           up         up              1500            
Ethernet20      unassigned           up         up              1500            
Ethernet21      unassigned           up         up              1500            
Ethernet22      unassigned           up         up              1500            
Ethernet23      unassigned           up         up              1500            
Loopback0       10.200.0.2/32        up         up             65535            
Management1     172.20.21.12/23      up         up              1500
```
## show lldp neighbors

```
Last table change time   : 2:31:19 ago
Number of table inserts  : 10
Number of table deletes  : 0
Number of table drops    : 0
Number of table age-outs : 0

Port          Neighbor Device ID                 Neighbor Port ID    TTL 
---------- ---------------------------------- ---------------------- --- 
Et1           BC-BORDERLEAF1.tudareslab.io       Ethernet2           120 
Et2           BC-BORDERLEAF2.tudareslab.io       Ethernet2           120 
Et3           BC-DATALEAF3.tudareslab.io         Ethernet2           120 
Et4           BC-DATALEAF4.tudareslab.io         Ethernet2           120 
Et5           BC-DATALEAF5.tudareslab.io         Ethernet2           120 
Et6           BC-DATALEAF6.tudareslab.io         Ethernet2           120 
Et7           BC-STOLEAF1.tudareslab.io          Ethernet2           120 
Et8           BC-STOLEAF2.tudareslab.io          Ethernet2           120 
Et9           BC-STOLEAF3.tudareslab.io          Ethernet2           120 
Et10          BC-STOLEAF4.tudareslab.io          Ethernet2           120
```
## show running-config

```
! Command: show running-config
! device: BC-SPINE2 (vEOS-lab, EOS-4.26.2F)
!
! boot system flash:/vEOS-lab.swi
!
no aaa root
!
username admin privilege 15 role network-admin secret sha512 $6$LJcUms0WZ9UyskIF$b6jUZMJmruk95uA0GPood4z4Tgb2aHKqnRhm7HyHl3kjsgE6mA5.V3W/vwl16WeICFvWWz1vkU1zQET0CbILG0
username cvpadmin privilege 15 role network-admin secret sha512 $6$pWE0vYbIJTmV0ZWc$nIrbLNYS3pIgpFj9vuzkchwyA19betlJZjWR.KE95GHwOALliiUUAu92JUWg9jQ12Yd3.aTQmWf.gRe2VNo2Y.
!
daemon TerminAttr
   exec /usr/bin/TerminAttr -cvaddr=172.20.21.10:9910 -cvauth=key,arista -cvvrf=mgmt -smashexcludes=ale,flexCounter,hardware,kni,pulse,strata -ingestexclude=/Sysdb/cell/1/agent,/Sysdb/cell/2/agent -taillogs
   no shutdown
!
switchport default mode routed
!
vlan internal order ascending range 1006 1199
!
transceiver qsfp default-mode 4x10G
!
service routing protocols model multi-agent
!
hostname BC-SPINE2
ip name-server vrf mgmt 172.20.20.6
dns domain tudareslab.io
!
spanning-tree mode none
!
clock timezone America/Toronto
!
vrf instance mgmt
!
management api http-commands
   no shutdown
   !
   vrf mgmt
      no shutdown
!
interface Ethernet1
   description P2P_LINK_TO_BC-BORDERLEAF1_Ethernet2
   no switchport
   ip address 172.31.255.2/31
!
interface Ethernet2
   description P2P_LINK_TO_BC-BORDERLEAF2_Ethernet2
   no switchport
   ip address 172.31.255.6/31
!
interface Ethernet3
   description P2P_LINK_TO_BC-DATALEAF3_Ethernet2
   no switchport
   ip address 172.31.255.10/31
!
interface Ethernet4
   description P2P_LINK_TO_BC-DATALEAF4_Ethernet2
   no switchport
   ip address 172.31.255.14/31
!
interface Ethernet5
   description P2P_LINK_TO_BC-DATALEAF5_Ethernet2
   no switchport
   ip address 172.31.255.18/31
!
interface Ethernet6
   description P2P_LINK_TO_BC-DATALEAF6_Ethernet2
   no switchport
   ip address 172.31.255.22/31
!
interface Ethernet7
   description P2P_LINK_TO_BC-STOLEAF1_Ethernet2
   no switchport
   ip address 172.31.255.26/31
!
interface Ethernet8
   description P2P_LINK_TO_BC-STOLEAF2_Ethernet2
   no switchport
   ip address 172.31.255.30/31
!
interface Ethernet9
   description P2P_LINK_TO_BC-STOLEAF3_Ethernet2
   no switchport
   ip address 172.31.255.34/31
!
interface Ethernet10
   description P2P_LINK_TO_BC-STOLEAF4_Ethernet2
   no switchport
   ip address 172.31.255.38/31
!
interface Ethernet11
   no switchport
!
interface Ethernet12
   no switchport
!
interface Ethernet13
   no switchport
!
interface Ethernet14
   no switchport
!
interface Ethernet15
   no switchport
!
interface Ethernet16
   no switchport
!
interface Ethernet17
   no switchport
!
interface Ethernet18
   no switchport
!
interface Ethernet19
   no switchport
!
interface Ethernet20
   no switchport
!
interface Ethernet21
   no switchport
!
interface Ethernet22
   no switchport
!
interface Ethernet23
   no switchport
!
interface Loopback0
   description EVPN_Overlay_Peering
   ip address 10.200.0.2/32
!
interface Management1
   description oob_management
   vrf mgmt
   ip address 172.20.21.12/23
!
ip routing
no ip routing vrf mgmt
!
ip prefix-list PL-LOOPBACKS-EVPN-OVERLAY
   seq 10 permit 10.200.0.0/24 eq 32
!
ip route vrf mgmt 0.0.0.0/0 172.20.20.1
!
ntp server vrf mgmt 0.north-america.pool.ntp.org iburst
ntp server vrf mgmt 1.north-america.pool.ntp.org iburst
!
route-map RM-CONN-2-BGP permit 10
   match ip address prefix-list PL-LOOPBACKS-EVPN-OVERLAY
!
router bfd
   multihop interval 1200 min-rx 1200 multiplier 3
!
router bgp 65001
   router-id 10.200.0.2
   maximum-paths 6 ecmp 6
   neighbor EVPN-OVERLAY-PEERS peer group
   neighbor EVPN-OVERLAY-PEERS next-hop-unchanged
   neighbor EVPN-OVERLAY-PEERS update-source Loopback0
   neighbor EVPN-OVERLAY-PEERS bfd
   neighbor EVPN-OVERLAY-PEERS ebgp-multihop 3
   neighbor EVPN-OVERLAY-PEERS password 7 q+VNViP5i4rVjW1cxFv2wA==
   neighbor EVPN-OVERLAY-PEERS send-community
   neighbor EVPN-OVERLAY-PEERS maximum-routes 0
   neighbor IPv4-UNDERLAY-PEERS peer group
   neighbor IPv4-UNDERLAY-PEERS password 7 AQQvKeimxJu+uGQ/yYvv9w==
   neighbor IPv4-UNDERLAY-PEERS send-community
   neighbor IPv4-UNDERLAY-PEERS maximum-routes 12000
   neighbor 10.200.1.1 peer group EVPN-OVERLAY-PEERS
   neighbor 10.200.1.1 remote-as 65101
   neighbor 10.200.1.1 description BC-BORDERLEAF1
   neighbor 10.200.1.2 peer group EVPN-OVERLAY-PEERS
   neighbor 10.200.1.2 remote-as 65101
   neighbor 10.200.1.2 description BC-BORDERLEAF2
   neighbor 10.200.1.3 peer group EVPN-OVERLAY-PEERS
   neighbor 10.200.1.3 remote-as 65102
   neighbor 10.200.1.3 description BC-DATALEAF3
   neighbor 10.200.1.4 peer group EVPN-OVERLAY-PEERS
   neighbor 10.200.1.4 remote-as 65102
   neighbor 10.200.1.4 description BC-DATALEAF4
   neighbor 10.200.1.5 peer group EVPN-OVERLAY-PEERS
   neighbor 10.200.1.5 remote-as 65103
   neighbor 10.200.1.5 description BC-DATALEAF5
   neighbor 10.200.1.6 peer group EVPN-OVERLAY-PEERS
   neighbor 10.200.1.6 remote-as 65103
   neighbor 10.200.1.6 description BC-DATALEAF6
   neighbor 10.200.1.7 peer group EVPN-OVERLAY-PEERS
   neighbor 10.200.1.7 remote-as 65104
   neighbor 10.200.1.7 description BC-STOLEAF1
   neighbor 10.200.1.8 peer group EVPN-OVERLAY-PEERS
   neighbor 10.200.1.8 remote-as 65104
   neighbor 10.200.1.8 description BC-STOLEAF2
   neighbor 10.200.1.9 peer group EVPN-OVERLAY-PEERS
   neighbor 10.200.1.9 remote-as 65105
   neighbor 10.200.1.9 description BC-STOLEAF3
   neighbor 10.200.1.10 peer group EVPN-OVERLAY-PEERS
   neighbor 10.200.1.10 remote-as 65105
   neighbor 10.200.1.10 description BC-STOLEAF4
   neighbor 172.31.255.3 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.31.255.3 remote-as 65101
   neighbor 172.31.255.3 description BC-BORDERLEAF1_Ethernet2
   neighbor 172.31.255.7 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.31.255.7 remote-as 65101
   neighbor 172.31.255.7 description BC-BORDERLEAF2_Ethernet2
   neighbor 172.31.255.11 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.31.255.11 remote-as 65102
   neighbor 172.31.255.11 description BC-DATALEAF3_Ethernet2
   neighbor 172.31.255.15 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.31.255.15 remote-as 65102
   neighbor 172.31.255.15 description BC-DATALEAF4_Ethernet2
   neighbor 172.31.255.19 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.31.255.19 remote-as 65103
   neighbor 172.31.255.19 description BC-DATALEAF5_Ethernet2
   neighbor 172.31.255.23 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.31.255.23 remote-as 65103
   neighbor 172.31.255.23 description BC-DATALEAF6_Ethernet2
   neighbor 172.31.255.27 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.31.255.27 remote-as 65104
   neighbor 172.31.255.27 description BC-STOLEAF1_Ethernet2
   neighbor 172.31.255.31 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.31.255.31 remote-as 65104
   neighbor 172.31.255.31 description BC-STOLEAF2_Ethernet2
   neighbor 172.31.255.35 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.31.255.35 remote-as 65105
   neighbor 172.31.255.35 description BC-STOLEAF3_Ethernet2
   neighbor 172.31.255.39 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.31.255.39 remote-as 65105
   neighbor 172.31.255.39 description BC-STOLEAF4_Ethernet2
   redistribute connected route-map RM-CONN-2-BGP
   !
   address-family evpn
      neighbor EVPN-OVERLAY-PEERS activate
   !
   address-family ipv4
      no neighbor EVPN-OVERLAY-PEERS activate
      neighbor IPv4-UNDERLAY-PEERS activate
!
end
```
## show version

```
Arista vEOS-lab
Hardware version: 
Serial number: 9950509487C5DFE4046FA1B8E55792D8
Hardware MAC address: 5001.0080.9a64
System MAC address: 5001.0080.9a64

Software image version: 4.26.2F
Architecture: i686
Internal build version: 4.26.2F-23563874.4262F
Internal build ID: fa3a49f3-6093-4925-ad11-55fe15eac5ae
Image format version: 1.0

Uptime: 2 hours and 34 minutes
Total memory: 4002528 kB
Free memory: 3009040 kB
```
