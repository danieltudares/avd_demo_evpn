# BC-DATALEAF6
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
- [Virtual Source NAT](#virtual-source-nat)
  - [Virtual Source NAT Summary](#virtual-source-nat-summary)
  - [Virtual Source NAT Configuration](#virtual-source-nat-configuration)
- [Quality Of Service](#quality-of-service)

<!-- toc -->
# Management

## Management Interfaces

### Management Interfaces Summary

#### IPv4

| Management Interface | description | Type | VRF | IP Address | Gateway |
| -------------------- | ----------- | ---- | --- | ---------- | ------- |
| Management1 | oob_management | oob | mgmt | 172.20.21.106/23 | 172.20.20.1 |

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
   ip address 172.20.21.106/23
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
| BC_DATA_RACK3 | Vlan4094 | 10.255.252.8 | Port-Channel12 |

Dual primary detection is disabled.

## MLAG Device Configuration

```eos
!
mlag configuration
   domain-id BC_DATA_RACK3
   local-interface Vlan4094
   peer-address 10.255.252.8
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
| 110 | BC_BLUE_ZONE_A_1 | - |
| 111 | BC_BLUE_ZONE_A_2 | - |
| 112 | BC_BLUE_ZONE_A_3 | - |
| 120 | BC_BLUE_ZONE_B_1 | - |
| 121 | BC_BLUE_ZONE_B_2 | - |
| 160 | BC_VMOTION | - |
| 161 | BC_NFS | - |
| 210 | BC_RED_ZONE_A_1 | - |
| 211 | BC_RED_ZONE_A_2 | - |
| 250 | BC_RED_ZONE_B_1 | - |
| 251 | BC_RED_ZONE_B_2 | - |
| 3009 | MLAG_iBGP_BC_BLUE_ZONE_A | LEAF_PEER_L3 |
| 3010 | MLAG_iBGP_BC_BLUE_ZONE_B | LEAF_PEER_L3 |
| 3019 | MLAG_iBGP_BC_RED_ZONE_A | LEAF_PEER_L3 |
| 3020 | MLAG_iBGP_BC_RED_ZONE_B | LEAF_PEER_L3 |
| 4093 | LEAF_PEER_L3 | LEAF_PEER_L3 |
| 4094 | MLAG_PEER | MLAG |

## VLANs Device Configuration

```eos
!
vlan 110
   name BC_BLUE_ZONE_A_1
!
vlan 111
   name BC_BLUE_ZONE_A_2
!
vlan 112
   name BC_BLUE_ZONE_A_3
!
vlan 120
   name BC_BLUE_ZONE_B_1
!
vlan 121
   name BC_BLUE_ZONE_B_2
!
vlan 160
   name BC_VMOTION
!
vlan 161
   name BC_NFS
!
vlan 210
   name BC_RED_ZONE_A_1
!
vlan 211
   name BC_RED_ZONE_A_2
!
vlan 250
   name BC_RED_ZONE_B_1
!
vlan 251
   name BC_RED_ZONE_B_2
!
vlan 3009
   name MLAG_iBGP_BC_BLUE_ZONE_A
   trunk group LEAF_PEER_L3
!
vlan 3010
   name MLAG_iBGP_BC_BLUE_ZONE_B
   trunk group LEAF_PEER_L3
!
vlan 3019
   name MLAG_iBGP_BC_RED_ZONE_A
   trunk group LEAF_PEER_L3
!
vlan 3020
   name MLAG_iBGP_BC_RED_ZONE_B
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
| Ethernet3 | data_server_1_Eth4 | *trunk | *110,111,112 | *110 | *- | 3 |
| Ethernet4 | data_server_1_Eth6 | *access | *- | *- | *- | 4 |
| Ethernet5 | data_server_2_Eth4 | *trunk | *110,111,112 | *110 | *- | 5 |
| Ethernet6 | data_server_2_Eth6 | *access | *- | *- | *- | 6 |
| Ethernet12 | MLAG_PEER_BC-DATALEAF5_Ethernet12 | *trunk | *2-4094 | *- | *['LEAF_PEER_L3', 'MLAG'] | 12 |
| Ethernet13 | MLAG_PEER_BC-DATALEAF5_Ethernet13 | *trunk | *2-4094 | *- | *['LEAF_PEER_L3', 'MLAG'] | 12 |

*Inherited from Port-Channel Interface

#### IPv4

| Interface | Description | Type | Channel Group | IP Address | VRF |  MTU | Shutdown | ACL In | ACL Out |
| --------- | ----------- | -----| ------------- | ---------- | ----| ---- | -------- | ------ | ------- |
| Ethernet1 | P2P_LINK_TO_BC-SPINE1_Ethernet6 | routed | - | 172.31.255.21/31 | default | 1500 | false | - | - |
| Ethernet2 | P2P_LINK_TO_BC-SPINE2_Ethernet6 | routed | - | 172.31.255.23/31 | default | 1500 | false | - | - |

### Ethernet Interfaces Device Configuration

```eos
!
interface Ethernet1
   description P2P_LINK_TO_BC-SPINE1_Ethernet6
   no shutdown
   mtu 1500
   no switchport
   ip address 172.31.255.21/31
!
interface Ethernet2
   description P2P_LINK_TO_BC-SPINE2_Ethernet6
   no shutdown
   mtu 1500
   no switchport
   ip address 172.31.255.23/31
!
interface Ethernet3
   description data_server_1_Eth4
   no shutdown
   channel-group 3 mode active
   no snmp trap link-change

!
interface Ethernet4
   description data_server_1_Eth6
   no shutdown
   channel-group 4 mode active
!
interface Ethernet5
   description data_server_2_Eth4
   no shutdown
   channel-group 5 mode active
   no snmp trap link-change

!
interface Ethernet6
   description data_server_2_Eth6
   no shutdown
   channel-group 6 mode active
!
interface Ethernet12
   description MLAG_PEER_BC-DATALEAF5_Ethernet12
   no shutdown
   channel-group 12 mode active
!
interface Ethernet13
   description MLAG_PEER_BC-DATALEAF5_Ethernet13
   no shutdown
   channel-group 12 mode active
```

## Port-Channel Interfaces

### Port-Channel Interfaces Summary

#### L2

| Interface | Description | Type | Mode | VLANs | Native VLAN | Trunk Group | LACP Fallback Timeout | LACP Fallback Mode | MLAG ID | EVPN ESI |
| --------- | ----------- | ---- | ---- | ----- | ----------- | ------------| --------------------- | ------------------ | ------- | -------- |
| Port-Channel3 | data_server_1_portchannel-tenant_blue_zoneA | switched | trunk | 110,111,112 | 110 | - | - | - | 3 | - |
| Port-Channel4 | data_server_1_portchannel-tenant_blue_zoneB | switched | access | - | - | - | - | - | 4 | - |
| Port-Channel5 | data_server_2_portchannel-tenant_blue_zoneA | switched | trunk | 110,111,112 | 110 | - | - | - | 5 | - |
| Port-Channel6 | data_server_2_portchannel-tenant_blue_zoneB | switched | access | - | - | - | - | - | 6 | - |
| Port-Channel12 | MLAG_PEER_BC-DATALEAF5_Po12 | switched | trunk | 2-4094 | - | ['LEAF_PEER_L3', 'MLAG'] | - | - | - | - |

### Port-Channel Interfaces Device Configuration

```eos
!
interface Port-Channel3
   description data_server_1_portchannel-tenant_blue_zoneA
   no shutdown
   switchport
   switchport trunk allowed vlan 110,111,112
   switchport trunk native vlan 110
   switchport mode trunk
   mlag 3
!
interface Port-Channel4
   description data_server_1_portchannel-tenant_blue_zoneB
   no shutdown
   switchport
   mlag 4
!
interface Port-Channel5
   description data_server_2_portchannel-tenant_blue_zoneA
   no shutdown
   switchport
   switchport trunk allowed vlan 110,111,112
   switchport trunk native vlan 110
   switchport mode trunk
   mlag 5
!
interface Port-Channel6
   description data_server_2_portchannel-tenant_blue_zoneB
   no shutdown
   switchport
   mlag 6
!
interface Port-Channel12
   description MLAG_PEER_BC-DATALEAF5_Po12
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
| Loopback0 | EVPN_Overlay_Peering | default | 10.200.1.6/32 |
| Loopback1 | VTEP_VXLAN_Tunnel_Source | default | 192.168.254.5/32 |
| Loopback100 | BC_BLUE_ZONE_A_VTEP_DIAGNOSTICS | BC_BLUE_ZONE_A | 10.255.1.6/32 |

#### IPv6

| Interface | Description | VRF | IPv6 Address |
| --------- | ----------- | --- | ------------ |
| Loopback0 | EVPN_Overlay_Peering | default | - |
| Loopback1 | VTEP_VXLAN_Tunnel_Source | default | - |
| Loopback100 | BC_BLUE_ZONE_A_VTEP_DIAGNOSTICS | BC_BLUE_ZONE_A | - |


### Loopback Interfaces Device Configuration

```eos
!
interface Loopback0
   description EVPN_Overlay_Peering
   no shutdown
   ip address 10.200.1.6/32
!
interface Loopback1
   description VTEP_VXLAN_Tunnel_Source
   no shutdown
   ip address 192.168.254.5/32
!
interface Loopback100
   description BC_BLUE_ZONE_A_VTEP_DIAGNOSTICS
   no shutdown
   vrf BC_BLUE_ZONE_A
   ip address 10.255.1.6/32
```

## VLAN Interfaces

### VLAN Interfaces Summary

| Interface | Description | VRF |  MTU | Shutdown |
| --------- | ----------- | --- | ---- | -------- |
| Vlan110 |  BC_BLUE_ZONE_A_1  |  BC_BLUE_ZONE_A  |  -  |  false  |
| Vlan111 |  BC_BLUE_ZONE_A_2  |  BC_BLUE_ZONE_A  |  -  |  false  |
| Vlan112 |  BC_BLUE_ZONE_A_3  |  BC_BLUE_ZONE_A  |  -  |  false  |
| Vlan120 |  BC_BLUE_ZONE_B_1  |  BC_BLUE_ZONE_B  |  -  |  false  |
| Vlan121 |  BC_BLUE_ZONE_B_2  |  BC_BLUE_ZONE_B  |  -  |  false  |
| Vlan210 |  BC_RED_ZONE_A_1  |  BC_RED_ZONE_A  |  -  |  false  |
| Vlan211 |  BC_RED_ZONE_A_2  |  BC_RED_ZONE_A  |  -  |  false  |
| Vlan250 |  BC_RED_ZONE_B_1  |  BC_RED_ZONE_B  |  -  |  false  |
| Vlan251 |  BC_RED_ZONE_B_2  |  BC_RED_ZONE_B  |  -  |  false  |
| Vlan3009 |  MLAG_PEER_L3_iBGP: vrf BC_BLUE_ZONE_A  |  BC_BLUE_ZONE_A  |  1500  |  false  |
| Vlan3010 |  MLAG_PEER_L3_iBGP: vrf BC_BLUE_ZONE_B  |  BC_BLUE_ZONE_B  |  1500  |  false  |
| Vlan3019 |  MLAG_PEER_L3_iBGP: vrf BC_RED_ZONE_A  |  BC_RED_ZONE_A  |  1500  |  false  |
| Vlan3020 |  MLAG_PEER_L3_iBGP: vrf BC_RED_ZONE_B  |  BC_RED_ZONE_B  |  1500  |  false  |
| Vlan4093 |  MLAG_PEER_L3_PEERING  |  default  |  1500  |  false  |
| Vlan4094 |  MLAG_PEER  |  default  |  1500  |  false  |

#### IPv4

| Interface | VRF | IP Address | IP Address Virtual | IP Router Virtual Address | VRRP | ACL In | ACL Out |
| --------- | --- | ---------- | ------------------ | ------------------------- | ---- | ------ | ------- |
| Vlan110 |  BC_BLUE_ZONE_A  |  -  |  10.1.10.1/24  |  -  |  -  |  leaf_acl  |  -  |
| Vlan111 |  BC_BLUE_ZONE_A  |  -  |  10.1.11.1/24  |  -  |  -  |  -  |  -  |
| Vlan112 |  BC_BLUE_ZONE_A  |  -  |  10.1.12.1/24  |  -  |  -  |  -  |  -  |
| Vlan120 |  BC_BLUE_ZONE_B  |  -  |  10.1.20.1/24  |  -  |  -  |  -  |  -  |
| Vlan121 |  BC_BLUE_ZONE_B  |  -  |  10.1.21.1/24  |  -  |  -  |  -  |  -  |
| Vlan210 |  BC_RED_ZONE_A  |  -  |  10.2.10.1/24  |  -  |  -  |  -  |  -  |
| Vlan211 |  BC_RED_ZONE_A  |  -  |  10.2.11.1/24  |  -  |  -  |  -  |  -  |
| Vlan250 |  BC_RED_ZONE_B  |  -  |  10.2.50.1/24  |  -  |  -  |  -  |  -  |
| Vlan251 |  BC_RED_ZONE_B  |  -  |  10.2.51.1/24  |  -  |  -  |  -  |  -  |
| Vlan3009 |  BC_BLUE_ZONE_A  |  10.255.251.9/31  |  -  |  -  |  -  |  -  |  -  |
| Vlan3010 |  BC_BLUE_ZONE_B  |  10.255.251.9/31  |  -  |  -  |  -  |  -  |  -  |
| Vlan3019 |  BC_RED_ZONE_A  |  10.255.251.9/31  |  -  |  -  |  -  |  -  |  -  |
| Vlan3020 |  BC_RED_ZONE_B  |  10.255.251.9/31  |  -  |  -  |  -  |  -  |  -  |
| Vlan4093 |  default  |  10.255.251.9/31  |  -  |  -  |  -  |  -  |  -  |
| Vlan4094 |  default  |  10.255.252.9/31  |  -  |  -  |  -  |  -  |  -  |


### VLAN Interfaces Device Configuration

```eos
!
interface Vlan110
   description BC_BLUE_ZONE_A_1
   no shutdown
   vrf BC_BLUE_ZONE_A
   ip address virtual 10.1.10.1/24
   ip access-group leaf_acl in
!
interface Vlan111
   description BC_BLUE_ZONE_A_2
   no shutdown
   vrf BC_BLUE_ZONE_A
   ip address virtual 10.1.11.1/24
!
interface Vlan112
   description BC_BLUE_ZONE_A_3
   no shutdown
   vrf BC_BLUE_ZONE_A
   ip address virtual 10.1.12.1/24
!
interface Vlan120
   description BC_BLUE_ZONE_B_1
   no shutdown
   vrf BC_BLUE_ZONE_B
   ip address virtual 10.1.20.1/24
!
interface Vlan121
   description BC_BLUE_ZONE_B_2
   no shutdown
   vrf BC_BLUE_ZONE_B
   ip address virtual 10.1.21.1/24
!
interface Vlan210
   description BC_RED_ZONE_A_1
   no shutdown
   vrf BC_RED_ZONE_A
   ip address virtual 10.2.10.1/24
!
interface Vlan211
   description BC_RED_ZONE_A_2
   no shutdown
   vrf BC_RED_ZONE_A
   ip address virtual 10.2.11.1/24
!
interface Vlan250
   description BC_RED_ZONE_B_1
   no shutdown
   vrf BC_RED_ZONE_B
   ip address virtual 10.2.50.1/24
!
interface Vlan251
   description BC_RED_ZONE_B_2
   no shutdown
   vrf BC_RED_ZONE_B
   ip address virtual 10.2.51.1/24
!
interface Vlan3009
   description MLAG_PEER_L3_iBGP: vrf BC_BLUE_ZONE_A
   no shutdown
   mtu 1500
   vrf BC_BLUE_ZONE_A
   ip address 10.255.251.9/31
!
interface Vlan3010
   description MLAG_PEER_L3_iBGP: vrf BC_BLUE_ZONE_B
   no shutdown
   mtu 1500
   vrf BC_BLUE_ZONE_B
   ip address 10.255.251.9/31
!
interface Vlan3019
   description MLAG_PEER_L3_iBGP: vrf BC_RED_ZONE_A
   no shutdown
   mtu 1500
   vrf BC_RED_ZONE_A
   ip address 10.255.251.9/31
!
interface Vlan3020
   description MLAG_PEER_L3_iBGP: vrf BC_RED_ZONE_B
   no shutdown
   mtu 1500
   vrf BC_RED_ZONE_B
   ip address 10.255.251.9/31
!
interface Vlan4093
   description MLAG_PEER_L3_PEERING
   no shutdown
   mtu 1500
   ip address 10.255.251.9/31
!
interface Vlan4094
   description MLAG_PEER
   no shutdown
   mtu 1500
   no autostate
   ip address 10.255.252.9/31
```

## VXLAN Interface

### VXLAN Interface Summary

#### Source Interface: Loopback1

#### UDP port: 4789

#### EVPN MLAG Shared Router MAC : mlag-system-id

#### VLAN to VNI and Flood List Mappings

| VLAN | VNI | Flood List |
| ---- | --- | ---------- |
| 110 | 10110 | - |
| 111 | 10111 | - |
| 112 | 10112 | - |
| 120 | 10120 | - |
| 121 | 10121 | - |
| 160 | 50160 | - |
| 161 | 10161 | - |
| 210 | 20210 | - |
| 211 | 20211 | - |
| 250 | 20250 | - |
| 251 | 20251 | - |

#### VRF to VNI Mappings

| VLAN | VNI |
| ---- | --- |
| BC_BLUE_ZONE_A | 10 |
| BC_BLUE_ZONE_B | 11 |
| BC_RED_ZONE_A | 20 |
| BC_RED_ZONE_B | 21 |

### VXLAN Interface Device Configuration

```eos
!
interface Vxlan1
   description BC-DATALEAF6_VTEP
   vxlan source-interface Loopback1
   vxlan virtual-router encapsulation mac-address mlag-system-id
   vxlan udp-port 4789
   vxlan vlan 110 vni 10110
   vxlan vlan 111 vni 10111
   vxlan vlan 112 vni 10112
   vxlan vlan 120 vni 10120
   vxlan vlan 121 vni 10121
   vxlan vlan 160 vni 50160
   vxlan vlan 161 vni 10161
   vxlan vlan 210 vni 20210
   vxlan vlan 211 vni 20211
   vxlan vlan 250 vni 20250
   vxlan vlan 251 vni 20251
   vxlan vrf BC_BLUE_ZONE_A vni 10
   vxlan vrf BC_BLUE_ZONE_B vni 11
   vxlan vrf BC_RED_ZONE_A vni 20
   vxlan vrf BC_RED_ZONE_B vni 21
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
| default | true|| BC_BLUE_ZONE_A | true |
| BC_BLUE_ZONE_B | true |
| BC_RED_ZONE_A | true |
| BC_RED_ZONE_B | true |
| mgmt | false |

### IP Routing Device Configuration

```eos
!
ip routing
ip routing vrf BC_BLUE_ZONE_A
ip routing vrf BC_BLUE_ZONE_B
ip routing vrf BC_RED_ZONE_A
ip routing vrf BC_RED_ZONE_B
no ip routing vrf mgmt
```
## IPv6 Routing

### IPv6 Routing Summary

| VRF | Routing Enabled |
| --- | --------------- |
| default | false || BC_BLUE_ZONE_A | false |
| BC_BLUE_ZONE_B | false |
| BC_RED_ZONE_A | false |
| BC_RED_ZONE_B | false |
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
| 65103|  10.200.1.6 |

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
| Remote AS | 65103 |
| Next-hop self | True |
| Send community | all |
| Maximum routes | 12000 |

### BGP Neighbors

| Neighbor | Remote AS | VRF | Send-community | Maximum-routes |
| -------- | --------- | --- | -------------- | -------------- |
| 10.200.0.1 | 65001 | default | Inherited from peer group EVPN-OVERLAY-PEERS | Inherited from peer group EVPN-OVERLAY-PEERS |
| 10.200.0.2 | 65001 | default | Inherited from peer group EVPN-OVERLAY-PEERS | Inherited from peer group EVPN-OVERLAY-PEERS |
| 10.255.251.8 | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER | default | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER |
| 172.31.255.20 | 65001 | default | Inherited from peer group IPv4-UNDERLAY-PEERS | Inherited from peer group IPv4-UNDERLAY-PEERS |
| 172.31.255.22 | 65001 | default | Inherited from peer group IPv4-UNDERLAY-PEERS | Inherited from peer group IPv4-UNDERLAY-PEERS |
| 10.255.251.8 | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER | BC_BLUE_ZONE_A | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER |
| 10.255.251.8 | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER | BC_BLUE_ZONE_B | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER |
| 10.255.251.8 | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER | BC_RED_ZONE_A | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER |
| 10.255.251.8 | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER | BC_RED_ZONE_B | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER | Inherited from peer group MLAG-IPv4-UNDERLAY-PEER |

### Router BGP EVPN Address Family

#### Router BGP EVPN MAC-VRFs

##### VLAN aware bundles

| VLAN Aware Bundle | Route-Distinguisher | Both Route-Target | Import Route Target | Export Route-Target | Redistribute | VLANs |
| ----------------- | ------------------- | ----------------- | ------------------- | ------------------- | ------------ | ----- |
| BC_BLUE_ZONE_A | 10.200.1.6:10 | 10:10 | - | - | learned | 110-112 |
| BC_BLUE_ZONE_B | 10.200.1.6:11 | 11:11 | - | - | learned | 120-121 |
| BC_NFS | 10.200.1.6:10161 | 10161:10161 | - | - | learned | 161 |
| BC_RED_ZONE_A | 10.200.1.6:20 | 20:20 | - | - | learned | 210-211 |
| BC_RED_ZONE_B | 10.200.1.6:21 | 21:21 | - | - | learned | 250-251 |
| BC_VMOTION | 10.200.1.6:50160 | 50160:50160 | - | - | learned | 160 |

#### Router BGP EVPN VRFs

| VRF | Route-Distinguisher | Redistribute |
| --- | ------------------- | ------------ |
| BC_BLUE_ZONE_A | 10.200.1.6:10 | connected |
| BC_BLUE_ZONE_B | 10.200.1.6:11 | connected |
| BC_RED_ZONE_A | 10.200.1.6:20 | connected |
| BC_RED_ZONE_B | 10.200.1.6:21 | connected |

### Router BGP Device Configuration

```eos
!
router bgp 65103
   router-id 10.200.1.6
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
   neighbor MLAG-IPv4-UNDERLAY-PEER remote-as 65103
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
   neighbor 10.255.251.8 peer group MLAG-IPv4-UNDERLAY-PEER
   neighbor 10.255.251.8 description BC-DATALEAF5
   neighbor 172.31.255.20 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.31.255.20 remote-as 65001
   neighbor 172.31.255.20 description BC-SPINE1_Ethernet6
   neighbor 172.31.255.22 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.31.255.22 remote-as 65001
   neighbor 172.31.255.22 description BC-SPINE2_Ethernet6
   redistribute connected route-map RM-CONN-2-BGP
   !
   vlan-aware-bundle BC_BLUE_ZONE_A
      rd 10.200.1.6:10
      route-target both 10:10
      redistribute learned
      vlan 110-112
   !
   vlan-aware-bundle BC_BLUE_ZONE_B
      rd 10.200.1.6:11
      route-target both 11:11
      redistribute learned
      vlan 120-121
   !
   vlan-aware-bundle BC_NFS
      rd 10.200.1.6:10161
      route-target both 10161:10161
      redistribute learned
      vlan 161
   !
   vlan-aware-bundle BC_RED_ZONE_A
      rd 10.200.1.6:20
      route-target both 20:20
      redistribute learned
      vlan 210-211
   !
   vlan-aware-bundle BC_RED_ZONE_B
      rd 10.200.1.6:21
      route-target both 21:21
      redistribute learned
      vlan 250-251
   !
   vlan-aware-bundle BC_VMOTION
      rd 10.200.1.6:50160
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
   vrf BC_BLUE_ZONE_A
      rd 10.200.1.6:10
      route-target import evpn 10:10
      route-target export evpn 10:10
      router-id 10.200.1.6
      neighbor 10.255.251.8 peer group MLAG-IPv4-UNDERLAY-PEER
      redistribute connected
   !
   vrf BC_BLUE_ZONE_B
      rd 10.200.1.6:11
      route-target import evpn 11:11
      route-target export evpn 11:11
      router-id 10.200.1.6
      neighbor 10.255.251.8 peer group MLAG-IPv4-UNDERLAY-PEER
      redistribute connected
   !
   vrf BC_RED_ZONE_A
      rd 10.200.1.6:20
      route-target import evpn 20:20
      route-target export evpn 20:20
      router-id 10.200.1.6
      neighbor 10.255.251.8 peer group MLAG-IPv4-UNDERLAY-PEER
      redistribute connected
   !
   vrf BC_RED_ZONE_B
      rd 10.200.1.6:21
      route-target import evpn 21:21
      route-target export evpn 21:21
      router-id 10.200.1.6
      neighbor 10.255.251.8 peer group MLAG-IPv4-UNDERLAY-PEER
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
| BC_BLUE_ZONE_A | enabled |
| BC_BLUE_ZONE_B | enabled |
| BC_RED_ZONE_A | enabled |
| BC_RED_ZONE_B | enabled |
| mgmt | disabled |

## VRF Instances Device Configuration

```eos
!
vrf instance BC_BLUE_ZONE_A
!
vrf instance BC_BLUE_ZONE_B
!
vrf instance BC_RED_ZONE_A
!
vrf instance BC_RED_ZONE_B
!
vrf instance mgmt
```

# Virtual Source NAT

## Virtual Source NAT Summary

| Source NAT VRF | Source NAT IP Address |
| -------------- | --------------------- |
| BC_BLUE_ZONE_A | 10.255.1.6 |

## Virtual Source NAT Configuration

```eos
!
ip address virtual source-nat vrf BC_BLUE_ZONE_A address 10.255.1.6
```

# Quality Of Service
