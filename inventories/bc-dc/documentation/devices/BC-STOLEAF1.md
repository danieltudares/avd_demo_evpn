# BC-STOLEAF1
# Table of Contents
<!-- toc -->

- [Management](#management)
  - [Management Interfaces](#management-interfaces)
  - [DNS Domain](#dns-domain)
  - [Name Servers](#name-servers)
  - [NTP](#ntp)
  - [Management API HTTP](#management-api-http)
- [Authentication](#authentication)
  - [Local Users](#local-users)
- [Monitoring](#monitoring)
  - [TerminAttr Daemon](#terminattr-daemon)
- [MLAG](#mlag)
  - [MLAG Summary](#mlag-summary)
  - [MLAG Device Configuration](#mlag-device-configuration)
- [Spanning Tree](#spanning-tree)
  - [Spanning Tree Summary](#spanning-tree-summary)
  - [Spanning Tree Device Configuration](#spanning-tree-device-configuration)
- [Internal VLAN Allocation Policy](#internal-vlan-allocation-policy)
  - [Internal VLAN Allocation Policy Summary](#internal-vlan-allocation-policy-summary)
  - [Internal VLAN Allocation Policy Configuration](#internal-vlan-allocation-policy-configuration)
- [VLANs](#vlans)
  - [VLANs Summary](#vlans-summary)
  - [VLANs Device Configuration](#vlans-device-configuration)
- [Interfaces](#interfaces)
  - [Ethernet Interfaces](#ethernet-interfaces)
  - [Port-Channel Interfaces](#port-channel-interfaces)
  - [Loopback Interfaces](#loopback-interfaces)
  - [VLAN Interfaces](#vlan-interfaces)
  - [VXLAN Interface](#vxlan-interface)
- [Routing](#routing)
  - [Service Routing Protocols Model](#service-routing-protocols-model)
  - [Virtual Router MAC Address](#virtual-router-mac-address)
  - [IP Routing](#ip-routing)
  - [IPv6 Routing](#ipv6-routing)
  - [Static Routes](#static-routes)
  - [Router BGP](#router-bgp)
- [BFD](#bfd)
  - [Router BFD](#router-bfd)
- [Multicast](#multicast)
  - [IP IGMP Snooping](#ip-igmp-snooping)
- [Filters](#filters)
  - [Prefix-lists](#prefix-lists)
  - [Route-maps](#route-maps)
- [ACL](#acl)
  - [Extended Access-lists](#extended-access-lists)
- [VRF Instances](#vrf-instances)
  - [VRF Instances Summary](#vrf-instances-summary)
  - [VRF Instances Device Configuration](#vrf-instances-device-configuration)
- [Quality Of Service](#quality-of-service)

<!-- toc -->
# Management

## Management Interfaces

### Management Interfaces Summary

#### IPv4

| Management Interface | description | Type | VRF | IP Address | Gateway |
| -------------------- | ----------- | ---- | --- | ---------- | ------- |
| Management1 | oob_management | oob | mgmt | 172.20.21.111/23 | 172.20.20.1 |

#### IPv6

| Management Interface | description | Type | VRF | IPv6 Address | IPv6 Gateway |
| -------------------- | ----------- | ---- | --- | ------------ | ------------ |
| Management1 | oob_management | oob | mgmt | -  | - |

### Management Interfaces Device Configuration

```eos
!
interface Management1
   description oob_management
   no shutdown
   vrf mgmt
   ip address 172.20.21.111/23
```

## DNS Domain

### DNS domain: tudareslab.io

### DNS Domain Device Configuration

```eos
!
dns domain tudareslab.io
!
```

## Name Servers

### Name Servers Summary

| Name Server | Source VRF |
| ----------- | ---------- |
| 172.20.20.6 | mgmt |

### Name Servers Device Configuration

```eos
ip name-server vrf mgmt 172.20.20.6
```

## NTP

### NTP Summary

#### NTP Servers

| Server | VRF | Preferred | Burst | iBurst | Version | Min Poll | Max Poll | Local-interface | Key |
| ------ | --- | --------- | ----- | ------ | ------- | -------- | -------- | --------------- | --- |
| time.google.com | mgmt | - | - | True | - | - | - | - | - |

### NTP Device Configuration

```eos
!
ntp server vrf mgmt time.google.com iburst
```

## Management API HTTP

### Management API HTTP Summary

| HTTP | HTTPS |
| ---------- | ---------- |
| default | true |

### Management API VRF Access

| VRF Name | IPv4 ACL | IPv6 ACL |
| -------- | -------- | -------- |
| mgmt | - | - |


### Management API HTTP Configuration

```eos
!
management api http-commands
   protocol https
   no shutdown
   !
   vrf mgmt
      no shutdown
```

# Authentication

## Local Users

### Local Users Summary

| User | Privilege | Role |
| ---- | --------- | ---- |
| admin | 15 | network-admin |
| cvpadmin | 15 | network-admin |

### Local Users Device Configuration

```eos
!
username admin privilege 15 role network-admin secret sha512 $6$LJcUms0WZ9UyskIF$b6jUZMJmruk95uA0GPood4z4Tgb2aHKqnRhm7HyHl3kjsgE6mA5.V3W/vwl16WeICFvWWz1vkU1zQET0CbILG0
username cvpadmin privilege 15 role network-admin secret sha512 $6$pWE0vYbIJTmV0ZWc$nIrbLNYS3pIgpFj9vuzkchwyA19betlJZjWR.KE95GHwOALliiUUAu92JUWg9jQ12Yd3.aTQmWf.gRe2VNo2Y.
```

# Monitoring

## TerminAttr Daemon

### TerminAttr Daemon Summary

| CV Compression | CloudVision Servers | VRF | Authentication | Smash Excludes | Ingest Exclude | Bypass AAA |
| -------------- | ------------------- | --- | -------------- | -------------- | -------------- | ---------- |
| gzip | 172.20.21.10:9910 | mgmt | key,arista | ale,flexCounter,hardware,kni,pulse,strata | /Sysdb/cell/1/agent,/Sysdb/cell/2/agent | False |

### TerminAttr Daemon Device Configuration

```eos
!
daemon TerminAttr
   exec /usr/bin/TerminAttr -cvaddr=172.20.21.10:9910 -cvauth=key,arista -cvvrf=mgmt -smashexcludes=ale,flexCounter,hardware,kni,pulse,strata -ingestexclude=/Sysdb/cell/1/agent,/Sysdb/cell/2/agent -taillogs
   no shutdown
```

# MLAG

## MLAG Summary

| Domain-id | Local-interface | Peer-address | Peer-link |
| --------- | --------------- | ------------ | --------- |
| BC_STO_RACK1 | Vlan4094 | 10.255.252.13 | Port-Channel12 |

Dual primary detection is disabled.

## MLAG Device Configuration

```eos
!
mlag configuration
   domain-id BC_STO_RACK1
   local-interface Vlan4094
   peer-address 10.255.252.13
   peer-link Port-Channel12
   reload-delay mlag 300
   reload-delay non-mlag 330
```

# Spanning Tree

## Spanning Tree Summary

STP mode: **mstp**

### MSTP Instance and Priority

| Instance(s) | Priority |
| -------- | -------- |
| 0 | 4096 |

### Global Spanning-Tree Settings

Spanning Tree disabled for VLANs: **4093-4094**

## Spanning Tree Device Configuration

```eos
!
spanning-tree mode mstp
no spanning-tree vlan-id 4093-4094
spanning-tree mst 0 priority 4096
```

# Internal VLAN Allocation Policy

## Internal VLAN Allocation Policy Summary

| Policy Allocation | Range Beginning | Range Ending |
| ------------------| --------------- | ------------ |
| ascending | 1006 | 1199 |

## Internal VLAN Allocation Policy Configuration

```eos
!
vlan internal order ascending range 1006 1199
```

# VLANs

## VLANs Summary

| VLAN ID | Name | Trunk Groups |
| ------- | ---- | ------------ |
| 310 | BC_STO_ZONE_A_1 | - |
| 311 | BC_STO_ZONE_A_2 | - |
| 350 | BC_STO_ZONE_B_1 | - |
| 351 | BC_STO_ZONE_B_2 | - |
| 3029 | MLAG_iBGP_BC_STO_ZONE_A | LEAF_PEER_L3 |
| 3030 | MLAG_iBGP_BC_STO_ZONE_B | LEAF_PEER_L3 |
| 4093 | LEAF_PEER_L3 | LEAF_PEER_L3 |
| 4094 | MLAG_PEER | MLAG |

## VLANs Device Configuration

```eos
!
vlan 310
   name BC_STO_ZONE_A_1
!
vlan 311
   name BC_STO_ZONE_A_2
!
vlan 350
   name BC_STO_ZONE_B_1
!
vlan 351
   name BC_STO_ZONE_B_2
!
vlan 3029
   name MLAG_iBGP_BC_STO_ZONE_A
   trunk group LEAF_PEER_L3
!
vlan 3030
   name MLAG_iBGP_BC_STO_ZONE_B
   trunk group LEAF_PEER_L3
!
vlan 4093
   name LEAF_PEER_L3
   trunk group LEAF_PEER_L3
!
vlan 4094
   name MLAG_PEER
   trunk group MLAG
```

# Interfaces

## Ethernet Interfaces

### Ethernet Interfaces Summary

#### L2

| Interface | Description | Mode | VLANs | Native VLAN | Trunk Group | Channel-Group |
| --------- | ----------- | ---- | ----- | ----------- | ----------- | ------------- |
| Ethernet3 | storage_server_1_Eth3 | *trunk | *310,311 | *310 | *- | 3 |
| Ethernet4 | storage_server_1_Eth5 | *access | *- | *- | *- | 4 |
| Ethernet5 | storage_server_2_Eth3 | *trunk | *310,311 | *310 | *- | 5 |
| Ethernet6 | storage_server_2_Eth5 | *access | *- | *- | *- | 6 |
| Ethernet12 | MLAG_PEER_BC-STOLEAF2_Ethernet12 | *trunk | *2-4094 | *- | *['LEAF_PEER_L3', 'MLAG'] | 12 |
| Ethernet13 | MLAG_PEER_BC-STOLEAF2_Ethernet13 | *trunk | *2-4094 | *- | *['LEAF_PEER_L3', 'MLAG'] | 12 |

*Inherited from Port-Channel Interface

#### IPv4

| Interface | Description | Type | Channel Group | IP Address | VRF |  MTU | Shutdown | ACL In | ACL Out |
| --------- | ----------- | -----| ------------- | ---------- | ----| ---- | -------- | ------ | ------- |
| Ethernet1 | P2P_LINK_TO_BC-SPINE1_Ethernet7 | routed | - | 172.31.255.25/31 | default | 1500 | false | - | - |
| Ethernet2 | P2P_LINK_TO_BC-SPINE2_Ethernet7 | routed | - | 172.31.255.27/31 | default | 1500 | false | - | - |

### Ethernet Interfaces Device Configuration

```eos
!
interface Ethernet1
   description P2P_LINK_TO_BC-SPINE1_Ethernet7
   no shutdown
   mtu 1500
   no switchport
   ip address 172.31.255.25/31
!
interface Ethernet2
   description P2P_LINK_TO_BC-SPINE2_Ethernet7
   no shutdown
   mtu 1500
   no switchport
   ip address 172.31.255.27/31
!
interface Ethernet3
   description storage_server_1_Eth3
   no shutdown
   channel-group 3 mode active
   no snmp trap link-change

!
interface Ethernet4
   description storage_server_1_Eth5
   no shutdown
   channel-group 4 mode active
!
interface Ethernet5
   description storage_server_2_Eth3
   no shutdown
   channel-group 5 mode active
   no snmp trap link-change

!
interface Ethernet6
   description storage_server_2_Eth5
   no shutdown
   channel-group 6 mode active
!
interface Ethernet12
   description MLAG_PEER_BC-STOLEAF2_Ethernet12
   no shutdown
   channel-group 12 mode active
!
interface Ethernet13
   description MLAG_PEER_BC-STOLEAF2_Ethernet13
   no shutdown
   channel-group 12 mode active
```

## Port-Channel Interfaces

### Port-Channel Interfaces Summary

#### L2

| Interface | Description | Type | Mode | VLANs | Native VLAN | Trunk Group | LACP Fallback Timeout | LACP Fallback Mode | MLAG ID | EVPN ESI |
| --------- | ----------- | ---- | ---- | ----- | ----------- | ------------| --------------------- | ------------------ | ------- | -------- |
| Port-Channel3 | storage_server_1_portchannel-storage_zoneA | switched | trunk | 310,311 | 310 | - | - | - | 3 | - |
| Port-Channel4 | storage_server_1_portchannel-storage_zoneB | switched | access | - | - | - | - | - | 4 | - |
| Port-Channel5 | storage_server_2_portchannel-storage_zoneA | switched | trunk | 310,311 | 310 | - | - | - | 5 | - |
| Port-Channel6 | storage_server_2_portchannel-storage_zoneB | switched | access | - | - | - | - | - | 6 | - |
| Port-Channel12 | MLAG_PEER_BC-STOLEAF2_Po12 | switched | trunk | 2-4094 | - | ['LEAF_PEER_L3', 'MLAG'] | - | - | - | - |

### Port-Channel Interfaces Device Configuration

```eos
!
interface Port-Channel3
   description storage_server_1_portchannel-storage_zoneA
   no shutdown
   switchport
   switchport trunk allowed vlan 310,311
   switchport trunk native vlan 310
   switchport mode trunk
   mlag 3
!
interface Port-Channel4
   description storage_server_1_portchannel-storage_zoneB
   no shutdown
   switchport
   mlag 4
!
interface Port-Channel5
   description storage_server_2_portchannel-storage_zoneA
   no shutdown
   switchport
   switchport trunk allowed vlan 310,311
   switchport trunk native vlan 310
   switchport mode trunk
   mlag 5
!
interface Port-Channel6
   description storage_server_2_portchannel-storage_zoneB
   no shutdown
   switchport
   mlag 6
!
interface Port-Channel12
   description MLAG_PEER_BC-STOLEAF2_Po12
   no shutdown
   switchport
   switchport trunk allowed vlan 2-4094
   switchport mode trunk
   switchport trunk group LEAF_PEER_L3
   switchport trunk group MLAG
```

## Loopback Interfaces

### Loopback Interfaces Summary

#### IPv4

| Interface | Description | VRF | IP Address |
| --------- | ----------- | --- | ---------- |
| Loopback0 | EVPN_Overlay_Peering | default | 10.200.1.7/32 |
| Loopback1 | VTEP_VXLAN_Tunnel_Source | default | 192.168.254.7/32 |

#### IPv6

| Interface | Description | VRF | IPv6 Address |
| --------- | ----------- | --- | ------------ |
| Loopback0 | EVPN_Overlay_Peering | default | - |
| Loopback1 | VTEP_VXLAN_Tunnel_Source | default | - |


### Loopback Interfaces Device Configuration

```eos
!
interface Loopback0
   description EVPN_Overlay_Peering
   no shutdown
   ip address 10.200.1.7/32
!
interface Loopback1
   description VTEP_VXLAN_Tunnel_Source
   no shutdown
   ip address 192.168.254.7/32
```

## VLAN Interfaces

### VLAN Interfaces Summary

| Interface | Description | VRF |  MTU | Shutdown |
| --------- | ----------- | --- | ---- | -------- |
| Vlan310 |  BC_STO_ZONE_A_1  |  BC_STO_ZONE_A  |  -  |  false  |
| Vlan311 |  BC_STO_ZONE_A_2  |  BC_STO_ZONE_A  |  -  |  false  |
| Vlan350 |  BC_STO_ZONE_B_1  |  BC_STO_ZONE_B  |  -  |  false  |
| Vlan351 |  BC_STO_ZONE_B_2  |  BC_STO_ZONE_B  |  -  |  false  |
| Vlan3029 |  MLAG_PEER_L3_iBGP: vrf BC_STO_ZONE_A  |  BC_STO_ZONE_A  |  1500  |  false  |
| Vlan3030 |  MLAG_PEER_L3_iBGP: vrf BC_STO_ZONE_B  |  BC_STO_ZONE_B  |  1500  |  false  |
| Vlan4093 |  MLAG_PEER_L3_PEERING  |  default  |  1500  |  false  |
| Vlan4094 |  MLAG_PEER  |  default  |  1500  |  false  |

#### IPv4

| Interface | VRF | IP Address | IP Address Virtual | IP Router Virtual Address | VRRP | ACL In | ACL Out |
| --------- | --- | ---------- | ------------------ | ------------------------- | ---- | ------ | ------- |
| Vlan310 |  BC_STO_ZONE_A  |  -  |  10.3.10.1/24  |  -  |  -  |  -  |  -  |
| Vlan311 |  BC_STO_ZONE_A  |  -  |  10.3.11.1/24  |  -  |  -  |  -  |  -  |
| Vlan350 |  BC_STO_ZONE_B  |  -  |  10.3.50.1/24  |  -  |  -  |  -  |  -  |
| Vlan351 |  BC_STO_ZONE_B  |  -  |  10.3.51.1/24  |  -  |  -  |  -  |  -  |
| Vlan3029 |  BC_STO_ZONE_A  |  10.255.251.12/31  |  -  |  -  |  -  |  -  |  -  |
| Vlan3030 |  BC_STO_ZONE_B  |  10.255.251.12/31  |  -  |  -  |  -  |  -  |  -  |
| Vlan4093 |  default  |  10.255.251.12/31  |  -  |  -  |  -  |  -  |  -  |
| Vlan4094 |  default  |  10.255.252.12/31  |  -  |  -  |  -  |  -  |  -  |


### VLAN Interfaces Device Configuration

```eos
!
interface Vlan310
   description BC_STO_ZONE_A_1
   no shutdown
   vrf BC_STO_ZONE_A
   ip address virtual 10.3.10.1/24
!
interface Vlan311
   description BC_STO_ZONE_A_2
   no shutdown
   vrf BC_STO_ZONE_A
   ip address virtual 10.3.11.1/24
!
interface Vlan350
   description BC_STO_ZONE_B_1
   no shutdown
   vrf BC_STO_ZONE_B
   ip address virtual 10.3.50.1/24
!
interface Vlan351
   description BC_STO_ZONE_B_2
   no shutdown
   vrf BC_STO_ZONE_B
   ip address virtual 10.3.51.1/24
!
interface Vlan3029
   description MLAG_PEER_L3_iBGP: vrf BC_STO_ZONE_A
   no shutdown
   mtu 1500
   vrf BC_STO_ZONE_A
   ip address 10.255.251.12/31
!
interface Vlan3030
   description MLAG_PEER_L3_iBGP: vrf BC_STO_ZONE_B
   no shutdown
   mtu 1500
   vrf BC_STO_ZONE_B
   ip address 10.255.251.12/31
!
interface Vlan4093
   description MLAG_PEER_L3_PEERING
   no shutdown
   mtu 1500
   ip address 10.255.251.12/31
!
interface Vlan4094
   description MLAG_PEER
   no shutdown
   mtu 1500
   no autostate
   ip address 10.255.252.12/31
```

## VXLAN Interface

### VXLAN Interface Summary

#### Source Interface: Loopback1

#### UDP port: 4789

#### EVPN MLAG Shared Router MAC : mlag-system-id

#### VLAN to VNI and Flood List Mappings

| VLAN | VNI | Flood List |
| ---- | --- | ---------- |
| 310 | 30310 | - |
| 311 | 30311 | - |
| 350 | 30350 | - |
| 351 | 30351 | - |

#### VRF to VNI Mappings

| VLAN | VNI |
| ---- | --- |
| BC_STO_ZONE_A | 30 |
| BC_STO_ZONE_B | 31 |

### VXLAN Interface Device Configuration

```eos
!
interface Vxlan1
   description BC-STOLEAF1_VTEP
   vxlan source-interface Loopback1
   vxlan virtual-router encapsulation mac-address mlag-system-id
   vxlan udp-port 4789
   vxlan vlan 310 vni 30310
   vxlan vlan 311 vni 30311
   vxlan vlan 350 vni 30350
   vxlan vlan 351 vni 30351
   vxlan vrf BC_STO_ZONE_A vni 30
   vxlan vrf BC_STO_ZONE_B vni 31
```

# Routing
## Service Routing Protocols Model

Multi agent routing protocol model enabled

```eos
!
service routing protocols model multi-agent
```

## Virtual Router MAC Address

### Virtual Router MAC Address Summary

#### Virtual Router MAC Address: 00:dc:00:00:00:0a

### Virtual Router MAC Address Configuration

```eos
!
ip virtual-router mac-address 00:dc:00:00:00:0a
```

## IP Routing

### IP Routing Summary

| VRF | Routing Enabled |
| --- | --------------- |
| default | true|| BC_STO_ZONE_A | true |
| BC_STO_ZONE_B | true |
| mgmt | false |

### IP Routing Device Configuration

```eos
!
ip routing
ip routing vrf BC_STO_ZONE_A
ip routing vrf BC_STO_ZONE_B
no ip routing vrf mgmt
```
## IPv6 Routing

### IPv6 Routing Summary

| VRF | Routing Enabled |
| --- | --------------- |
| default | false || BC_STO_ZONE_A | false |
| BC_STO_ZONE_B | false |
| mgmt | false |


## Static Routes

### Static Routes Summary

| VRF | Destination Prefix | Next Hop IP             | Exit interface      | Administrative Distance       | Tag               | Route Name                    | Metric         |
| --- | ------------------ | ----------------------- | ------------------- | ----------------------------- | ----------------- | ----------------------------- | -------------- |
| mgmt  | 0.0.0.0/0 |  172.20.20.1  |  -  |  1  |  -  |  -  |  - |

### Static Routes Device Configuration

```eos
!
ip route vrf mgmt 0.0.0.0/0 172.20.20.1
```

## Router BGP

### Router BGP Summary

| BGP AS | Router ID |
| ------ | --------- |
| 65104|  10.200.1.7 |

| BGP Tuning |
| ---------- |
| maximum-paths 6 ecmp 6 |

### Router BGP Peer Groups

#### EVPN-OVERLAY-PEERS

| Settings | Value |
| -------- | ----- |
| Address Family | evpn |
| Source | Loopback0 |
| Bfd | true |
| Ebgp multihop | 3 |
| Send community | all |
| Maximum routes | 0 (no limit) |

#### IPv4-UNDERLAY-PEERS

| Settings | Value |
| -------- | ----- |
| Address Family | ipv4 |
| Send community | all |
| Maximum routes | 12000 |

#### MLAG-IPv4-UNDERLAY-PEER

| Settings | Value |
| -------- | ----- |
| Address Family | ipv4 |
| Remote AS | 65104 |
| Next-hop self | True |
| Send community | all |
| Maximum routes | 12000 |

### BGP Neighbors

| Neighbor | Remote AS | VRF | Send-community | Maximum-routes |
| -------- | --------- | --- | -------------- | -------------- |
| 10.200.0.1 | 65001 | default | Inherited from peer group EVPN-OVERLAY-PEERS | Inherited from peer group EVPN-OVERLAY-PEERS |
| 10.200.0.2 | 65001 | default | Inherited from peer group EVPN-OVERLAY-PEERS | Inherited from peer group EVPN-OVERLAY-PEERS |
| 10.255.251.13 | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER | default | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER |
| 172.31.255.24 | 65001 | default | Inherited from peer group IPv4-UNDERLAY-PEERS | Inherited from peer group IPv4-UNDERLAY-PEERS |
| 172.31.255.26 | 65001 | default | Inherited from peer group IPv4-UNDERLAY-PEERS | Inherited from peer group IPv4-UNDERLAY-PEERS |
| 10.255.251.13 | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER | BC_STO_ZONE_A | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER |
| 10.255.251.13 | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER | BC_STO_ZONE_B | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER |

### Router BGP EVPN Address Family

#### Router BGP EVPN MAC-VRFs

##### VLAN aware bundles

| VLAN Aware Bundle | Route-Distinguisher | Both Route-Target | Import Route Target | Export Route-Target | Redistribute | VLANs |
| ----------------- | ------------------- | ----------------- | ------------------- | ------------------- | ------------ | ----- |
| BC_STO_ZONE_A | 10.200.1.7:30 | 30:30 | - | - | learned | 310-311 |
| BC_STO_ZONE_B | 10.200.1.7:31 | 31:31 | - | - | learned | 350-351 |

#### Router BGP EVPN VRFs

| VRF | Route-Distinguisher | Redistribute |
| --- | ------------------- | ------------ |
| BC_STO_ZONE_A | 10.200.1.7:30 | connected |
| BC_STO_ZONE_B | 10.200.1.7:31 | connected |

### Router BGP Device Configuration

```eos
!
router bgp 65104
   router-id 10.200.1.7
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
   neighbor MLAG-IPv4-UNDERLAY-PEER remote-as 65104
   neighbor MLAG-IPv4-UNDERLAY-PEER next-hop-self
   neighbor MLAG-IPv4-UNDERLAY-PEER password 7 4b21pAdCvWeAqpcKDFMdWw==
   neighbor MLAG-IPv4-UNDERLAY-PEER send-community
   neighbor MLAG-IPv4-UNDERLAY-PEER maximum-routes 12000
   neighbor MLAG-IPv4-UNDERLAY-PEER route-map RM-MLAG-PEER-IN in
   neighbor 10.200.0.1 peer group EVPN-OVERLAY-PEERS
   neighbor 10.200.0.1 remote-as 65001
   neighbor 10.200.0.1 description BC-SPINE1
   neighbor 10.200.0.2 peer group EVPN-OVERLAY-PEERS
   neighbor 10.200.0.2 remote-as 65001
   neighbor 10.200.0.2 description BC-SPINE2
   neighbor 10.255.251.13 peer group MLAG-IPv4-UNDERLAY-PEER
   neighbor 10.255.251.13 description BC-STOLEAF2
   neighbor 172.31.255.24 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.31.255.24 remote-as 65001
   neighbor 172.31.255.24 description BC-SPINE1_Ethernet7
   neighbor 172.31.255.26 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.31.255.26 remote-as 65001
   neighbor 172.31.255.26 description BC-SPINE2_Ethernet7
   redistribute connected route-map RM-CONN-2-BGP
   !
   vlan-aware-bundle BC_STO_ZONE_A
      rd 10.200.1.7:30
      route-target both 30:30
      redistribute learned
      vlan 310-311
   !
   vlan-aware-bundle BC_STO_ZONE_B
      rd 10.200.1.7:31
      route-target both 31:31
      redistribute learned
      vlan 350-351
   !
   address-family evpn
      neighbor EVPN-OVERLAY-PEERS activate
   !
   address-family ipv4
      no neighbor EVPN-OVERLAY-PEERS activate
      neighbor IPv4-UNDERLAY-PEERS activate
      neighbor MLAG-IPv4-UNDERLAY-PEER activate
   !
   vrf BC_STO_ZONE_A
      rd 10.200.1.7:30
      route-target import evpn 30:30
      route-target export evpn 30:30
      router-id 10.200.1.7
      neighbor 10.255.251.13 peer group MLAG-IPv4-UNDERLAY-PEER
      redistribute connected
   !
   vrf BC_STO_ZONE_B
      rd 10.200.1.7:31
      route-target import evpn 31:31
      route-target export evpn 31:31
      router-id 10.200.1.7
      neighbor 10.255.251.13 peer group MLAG-IPv4-UNDERLAY-PEER
      redistribute connected
```

# BFD

## Router BFD

### Router BFD Multihop Summary

| Interval | Minimum RX | Multiplier |
| -------- | ---------- | ---------- |
| 1200 | 1200 | 3 |

### Router BFD Device Configuration

```eos
!
router bfd
   multihop interval 1200 min-rx 1200 multiplier 3
```

# Multicast

## IP IGMP Snooping

### IP IGMP Snooping Summary

IGMP snooping is globally enabled.


### IP IGMP Snooping Device Configuration

```eos
```

# Filters

## Prefix-lists

### Prefix-lists Summary

#### PL-LOOPBACKS-EVPN-OVERLAY

| Sequence | Action |
| -------- | ------ |
| 10 | permit 10.200.1.0/24 eq 32 |
| 20 | permit 192.168.254.0/24 eq 32 |

### Prefix-lists Device Configuration

```eos
!
ip prefix-list PL-LOOPBACKS-EVPN-OVERLAY
   seq 10 permit 10.200.1.0/24 eq 32
   seq 20 permit 192.168.254.0/24 eq 32
```

## Route-maps

### Route-maps Summary

#### RM-CONN-2-BGP

| Sequence | Type | Match and/or Set |
| -------- | ---- | ---------------- |
| 10 | permit | match ip address prefix-list PL-LOOPBACKS-EVPN-OVERLAY |

#### RM-MLAG-PEER-IN

| Sequence | Type | Match and/or Set |
| -------- | ---- | ---------------- |
| 10 | permit | set origin incomplete |

### Route-maps Device Configuration

```eos
!
route-map RM-CONN-2-BGP permit 10
   match ip address prefix-list PL-LOOPBACKS-EVPN-OVERLAY
!
route-map RM-MLAG-PEER-IN permit 10
   description Make routes learned over MLAG Peer-link less preferred on spines to ensure optimal routing
   set origin incomplete
```

# ACL

## Extended Access-lists

### Extended Access-lists Summary

#### leaf_acl

| Sequence | Action |
| -------- | ------ |
| 10 | permit icmp any any |
| 12 | deny tcp any 192.168.255.0 0.0.0.255 eq telnet |
| 20 | permit ip any any |

### Extended Access-lists Device Configuration

```eos
!
ip access-list leaf_acl
   10 permit icmp any any
   12 deny tcp any 192.168.255.0 0.0.0.255 eq telnet
   20 permit ip any any
```

# VRF Instances

## VRF Instances Summary

| VRF Name | IP Routing |
| -------- | ---------- |
| BC_STO_ZONE_A | enabled |
| BC_STO_ZONE_B | enabled |
| mgmt | disabled |

## VRF Instances Device Configuration

```eos
!
vrf instance BC_STO_ZONE_A
!
vrf instance BC_STO_ZONE_B
!
vrf instance mgmt
```

# Quality Of Service
