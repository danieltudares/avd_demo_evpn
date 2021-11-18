# BC-BORDERLEAF1 Commands Output

## Table of Contents

- [show lldp neighbors](#show-lldp-neighbors)
- [show ip interface brief](#show-ip-interface-brief)
- [show interfaces description](#show-interfaces-description)
- [show version](#show-version)
- [show running-config](#show-running-config)
## show interfaces description

```
Interface                      Status         Protocol           Description
Et1                            up             up                 P2P_LINK_TO_BC-SPINE1_Ethernet1
Et2                            up             up                 P2P_LINK_TO_BC-SPINE2_Ethernet1
Et3                            up             up                 BC-CORE-PAN-FW-01_Eth1
Et4                            up             up                 BC-CORE-PAN-FW-01_Eth3
Et5                            up             up                 BC-CORE-PAN-FW-02_Eth1
Et6                            up             up                 BC-CORE-PAN-FW-02_Eth3
Et7                            up             up                 
Et8                            up             up                 
Et9                            up             up                 
Et10                           up             up                 
Et11                           up             up                 
Et12                           up             up                 MLAG_PEER_BC-BORDERLEAF2_Ethernet12
Et13                           up             up                 MLAG_PEER_BC-BORDERLEAF2_Ethernet13
Lo0                            up             up                 EVPN_Overlay_Peering
Lo1                            up             up                 VTEP_VXLAN_Tunnel_Source
Ma1                            up             up                 oob_management
Po3                            down           lowerlayerdown     BC-CORE-PAN-FW-01_PortChannel-inside
Po4                            down           lowerlayerdown     BC-CORE-PAN-FW-01_PortChannel-outside
Po5                            down           lowerlayerdown     BC-CORE-PAN-FW-02_PortChannel-inside
Po6                            down           lowerlayerdown     BC-CORE-PAN-FW-02_PortChannel-outside
Po12                           up             up                 MLAG_PEER_BC-BORDERLEAF2_Po12
Vl1194                         up             up                 
Vl1195                         up             up                 
Vl1196                         up             up                 
Vl1197                         up             up                 
Vl1198                         up             up                 
Vl1199                         up             up                 
Vl4093                         up             up                 MLAG_PEER_L3_PEERING
Vl4094                         up             up                 MLAG_PEER
Vx1                            up             up                 BC-BORDERLEAF1_VTEP
```
## show ip interface brief

```
Address 
Interface       IP Address           Status     Protocol         MTU    Owner   
--------------- -------------------- ---------- ------------ ---------- ------- 
Ethernet1       172.31.255.1/31      up         up              1500            
Ethernet2       172.31.255.3/31      up         up              1500            
Ethernet7       unassigned           up         up              1500            
Ethernet8       unassigned           up         up              1500            
Ethernet9       unassigned           up         up              1500            
Ethernet10      unassigned           up         up              1500            
Ethernet11      unassigned           up         up              1500            
Loopback0       10.200.1.1/32        up         up             65535            
Loopback1       192.168.254.1/32     up         up             65535            
Management1     172.20.21.101/23     up         up              1500            
Vlan1194        unassigned           up         up              9164            
Vlan1195        unassigned           up         up              9164            
Vlan1196        unassigned           up         up              9164            
Vlan1197        unassigned           up         up              9164            
Vlan1198        unassigned           up         up              9164            
Vlan1199        unassigned           up         up              9164            
Vlan4093        10.255.251.0/31      up         up              1500            
Vlan4094        10.255.252.0/31      up         up              1500
```
## show lldp neighbors

```
Last table change time   : 2:31:23 ago
Number of table inserts  : 4
Number of table deletes  : 0
Number of table drops    : 0
Number of table age-outs : 0

Port          Neighbor Device ID                 Neighbor Port ID    TTL 
---------- ---------------------------------- ---------------------- --- 
Et1           BC-SPINE1.tudareslab.io            Ethernet1           120 
Et2           BC-SPINE2.tudareslab.io            Ethernet1           120 
Et12          BC-BORDERLEAF2.tudareslab.io       Ethernet12          120 
Et13          BC-BORDERLEAF2.tudareslab.io       Ethernet13          120
```
## show running-config

```
! Command: show running-config
! device: BC-BORDERLEAF1 (vEOS-lab, EOS-4.26.2F)
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
hostname BC-BORDERLEAF1
ip name-server vrf mgmt 172.20.20.6
dns domain tudareslab.io
!
spanning-tree mode mstp
no spanning-tree vlan-id 4093-4094
spanning-tree mst 0 priority 4096
!
clock timezone America/Toronto
!
vlan 160
   name BC_VMOTION
!
vlan 161
   name BC_NFS
!
vlan 4093
   name LEAF_PEER_L3
   trunk group LEAF_PEER_L3
!
vlan 4094
   name MLAG_PEER
   trunk group MLAG
!
vrf instance mgmt
!
management api http-commands
   no shutdown
   !
   vrf mgmt
      no shutdown
!
interface Port-Channel3
   description BC-CORE-PAN-FW-01_PortChannel-inside
   switchport trunk allowed vlan 1000-1010
   switchport mode trunk
   switchport
   mlag 3
!
interface Port-Channel4
   description BC-CORE-PAN-FW-01_PortChannel-outside
   switchport trunk allowed vlan 2000
   switchport mode trunk
   switchport
   mlag 4
!
interface Port-Channel5
   description BC-CORE-PAN-FW-02_PortChannel-inside
   switchport trunk allowed vlan 1000-1010
   switchport mode trunk
   switchport
   mlag 5
!
interface Port-Channel6
   description BC-CORE-PAN-FW-02_PortChannel-outside
   switchport trunk allowed vlan 2000
   switchport mode trunk
   switchport
   mlag 6
!
interface Port-Channel12
   description MLAG_PEER_BC-BORDERLEAF2_Po12
   switchport trunk allowed vlan 2-4094
   switchport mode trunk
   switchport trunk group LEAF_PEER_L3
   switchport trunk group MLAG
   switchport
!
interface Ethernet1
   description P2P_LINK_TO_BC-SPINE1_Ethernet1
   no switchport
   ip address 172.31.255.1/31
!
interface Ethernet2
   description P2P_LINK_TO_BC-SPINE2_Ethernet1
   no switchport
   ip address 172.31.255.3/31
!
interface Ethernet3
   description BC-CORE-PAN-FW-01_Eth1
   no switchport
   channel-group 3 mode active
!
interface Ethernet4
   description BC-CORE-PAN-FW-01_Eth3
   no switchport
   channel-group 4 mode active
!
interface Ethernet5
   description BC-CORE-PAN-FW-02_Eth1
   no switchport
   channel-group 5 mode active
!
interface Ethernet6
   description BC-CORE-PAN-FW-02_Eth3
   no switchport
   channel-group 6 mode active
!
interface Ethernet7
   no switchport
!
interface Ethernet8
   no switchport
!
interface Ethernet9
   no switchport
!
interface Ethernet10
   no switchport
!
interface Ethernet11
   no switchport
!
interface Ethernet12
   description MLAG_PEER_BC-BORDERLEAF2_Ethernet12
   no switchport
   channel-group 12 mode active
!
interface Ethernet13
   description MLAG_PEER_BC-BORDERLEAF2_Ethernet13
   no switchport
   channel-group 12 mode active
!
interface Loopback0
   description EVPN_Overlay_Peering
   ip address 10.200.1.1/32
!
interface Loopback1
   description VTEP_VXLAN_Tunnel_Source
   ip address 192.168.254.1/32
!
interface Management1
   description oob_management
   vrf mgmt
   ip address 172.20.21.101/23
!
interface Vlan4093
   description MLAG_PEER_L3_PEERING
   ip address 10.255.251.0/31
!
interface Vlan4094
   description MLAG_PEER
   no autostate
   ip address 10.255.252.0/31
!
interface Vxlan1
   description BC-BORDERLEAF1_VTEP
   vxlan source-interface Loopback1
   vxlan virtual-router encapsulation mac-address mlag-system-id
   vxlan udp-port 4789
   vxlan vlan 160 vni 50160
   vxlan vlan 161 vni 10161
!
ip virtual-router mac-address 00:dc:00:00:00:0a
!
ip access-list leaf_acl
   10 permit icmp any any
   12 deny tcp any 192.168.255.0/24 eq telnet
   20 permit ip any any
!
ip routing
no ip routing vrf mgmt
!
ip prefix-list PL-LOOPBACKS-EVPN-OVERLAY
   seq 10 permit 10.200.1.0/24 eq 32
   seq 20 permit 192.168.254.0/24 eq 32
!
mlag configuration
   domain-id BC_BORDER_RACK1
   local-interface Vlan4094
   peer-address 10.255.252.1
   peer-link Port-Channel12
   reload-delay mlag 300
   reload-delay non-mlag 330
!
ip route vrf mgmt 0.0.0.0/0 172.20.20.1
!
ntp server vrf mgmt 0.north-america.pool.ntp.org iburst
ntp server vrf mgmt 1.north-america.pool.ntp.org iburst
!
route-map RM-CONN-2-BGP permit 10
   match ip address prefix-list PL-LOOPBACKS-EVPN-OVERLAY
!
route-map RM-MLAG-PEER-IN permit 10
   description Make routes learned over MLAG Peer-link less preferred on spines to ensure optimal routing
   set origin incomplete
!
router bfd
   multihop interval 1200 min-rx 1200 multiplier 3
!
router bgp 65101
   router-id 10.200.1.1
   maximum-paths 6 ecmp 6
   neighbor EVPN-OVERLAY-PEERS peer group
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
   neighbor MLAG-IPv4-UNDERLAY-PEER peer group
   neighbor MLAG-IPv4-UNDERLAY-PEER remote-as 65101
   neighbor MLAG-IPv4-UNDERLAY-PEER next-hop-self
   neighbor MLAG-IPv4-UNDERLAY-PEER route-map RM-MLAG-PEER-IN in
   neighbor MLAG-IPv4-UNDERLAY-PEER password 7 4b21pAdCvWeAqpcKDFMdWw==
   neighbor MLAG-IPv4-UNDERLAY-PEER send-community
   neighbor MLAG-IPv4-UNDERLAY-PEER maximum-routes 12000
   neighbor 10.200.0.1 peer group EVPN-OVERLAY-PEERS
   neighbor 10.200.0.1 remote-as 65001
   neighbor 10.200.0.1 description BC-SPINE1
   neighbor 10.200.0.2 peer group EVPN-OVERLAY-PEERS
   neighbor 10.200.0.2 remote-as 65001
   neighbor 10.200.0.2 description BC-SPINE2
   neighbor 10.255.251.1 peer group MLAG-IPv4-UNDERLAY-PEER
   neighbor 10.255.251.1 description BC-BORDERLEAF2
   neighbor 172.31.255.0 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.31.255.0 remote-as 65001
   neighbor 172.31.255.0 description BC-SPINE1_Ethernet1
   neighbor 172.31.255.2 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.31.255.2 remote-as 65001
   neighbor 172.31.255.2 description BC-SPINE2_Ethernet1
   redistribute connected route-map RM-CONN-2-BGP
   !
   vlan-aware-bundle BC_NFS
      rd 10.200.1.1:10161
      route-target both 10161:10161
      redistribute learned
      vlan 161
   !
   vlan-aware-bundle BC_VMOTION
      rd 10.200.1.1:50160
      route-target both 50160:50160
      redistribute learned
      vlan 160
   !
   address-family evpn
      neighbor EVPN-OVERLAY-PEERS activate
   !
   address-family ipv4
      no neighbor EVPN-OVERLAY-PEERS activate
      neighbor IPv4-UNDERLAY-PEERS activate
      neighbor MLAG-IPv4-UNDERLAY-PEER activate
!
end
```
## show version

```
Arista vEOS-lab
Hardware version: 
Serial number: 9D1799705A18B3453F1E6AB010F2F34B
Hardware MAC address: 5001.00c4.29f0
System MAC address: 5001.00c4.29f0

Software image version: 4.26.2F
Architecture: i686
Internal build version: 4.26.2F-23563874.4262F
Internal build ID: fa3a49f3-6093-4925-ad11-55fe15eac5ae
Image format version: 1.0

Uptime: 2 hours and 34 minutes
Total memory: 4002528 kB
Free memory: 2961568 kB
```
