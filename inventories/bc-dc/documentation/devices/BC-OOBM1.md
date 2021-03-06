# BC-OOBM1
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
  - [VLAN Interfaces](#vlan-interfaces)
- [Routing](#routing)
  - [Service Routing Protocols Model](#service-routing-protocols-model)
  - [IP Routing](#ip-routing)
  - [IPv6 Routing](#ipv6-routing)
  - [Static Routes](#static-routes)
- [Multicast](#multicast)
  - [IP IGMP Snooping](#ip-igmp-snooping)
- [Filters](#filters)
- [ACL](#acl)
- [VRF Instances](#vrf-instances)
  - [VRF Instances Summary](#vrf-instances-summary)
  - [VRF Instances Device Configuration](#vrf-instances-device-configuration)
- [Quality Of Service](#quality-of-service)
- [EOS CLI](#eos-cli)

<!-- toc -->
# Management

## Management Interfaces

### Management Interfaces Summary

#### IPv4

| Management Interface | description | Type | VRF | IP Address | Gateway |
| -------------------- | ----------- | ---- | --- | ---------- | ------- |
| vlan100 | oob_management | oob | default | 172.20.21.13/23 | 172.20.20.1 |

#### IPv6

| Management Interface | description | Type | VRF | IPv6 Address | IPv6 Gateway |
| -------------------- | ----------- | ---- | --- | ------------ | ------------ |
| vlan100 | oob_management | oob | default | -  | - |

### Management Interfaces Device Configuration

```eos
!
interface vlan100
   description oob_management
   no shutdown
   ip address 172.20.21.13/23
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
| 172.20.20.6 | default |

### Name Servers Device Configuration

```eos
ip name-server vrf default 172.20.20.6
```

## NTP

### NTP Summary

#### NTP Servers

| Server | VRF | Preferred | Burst | iBurst | Version | Min Poll | Max Poll | Local-interface | Key |
| ------ | --- | --------- | ----- | ------ | ------- | -------- | -------- | --------------- | --- |
| time.google.com | default | - | - | True | - | - | - | - | - |

### NTP Device Configuration

```eos
!
ntp server time.google.com iburst
```

## Management API HTTP

### Management API HTTP Summary

| HTTP | HTTPS |
| ---------- | ---------- |
| default | true |

### Management API VRF Access

| VRF Name | IPv4 ACL | IPv6 ACL |
| -------- | -------- | -------- |
| default | - | - |


### Management API HTTP Configuration

```eos
!
management api http-commands
   protocol https
   no shutdown
   !
   vrf default
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
| gzip | 172.20.21.10:9910 | default | key,arista | ale,flexCounter,hardware,kni,pulse,strata | /Sysdb/cell/1/agent,/Sysdb/cell/2/agent | False |

### TerminAttr Daemon Device Configuration

```eos
!
daemon TerminAttr
   exec /usr/bin/TerminAttr -cvaddr=172.20.21.10:9910 -cvauth=key,arista -cvvrf=default -smashexcludes=ale,flexCounter,hardware,kni,pulse,strata -ingestexclude=/Sysdb/cell/1/agent,/Sysdb/cell/2/agent -taillogs
   no shutdown
```

# MLAG

## MLAG Summary

| Domain-id | Local-interface | Peer-address | Peer-link |
| --------- | --------------- | ------------ | --------- |
| BC_OOBM | Vlan4094 | 10.255.252.1 | Port-Channel16 |

Dual primary detection is disabled.

## MLAG Device Configuration

```eos
!
mlag configuration
   domain-id BC_OOBM
   local-interface Vlan4094
   peer-address 10.255.252.1
   peer-link Port-Channel16
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

Spanning Tree disabled for VLANs: **4094**

## Spanning Tree Device Configuration

```eos
!
spanning-tree mode mstp
no spanning-tree vlan-id 4094
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
| 4094 | MLAG_PEER | MLAG |

## VLANs Device Configuration

```eos
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
| Ethernet1 | BC-CORE-PAN-FW-OOBM-01_Eth10 | *access | *100 | *- | *- | 1 |
| Ethernet2 | BC-CORE-PAN-FW-OOBM-02_Eth1 | *access | *100 | *- | *- | 2 |
| Ethernet3 | data_server_R2_1_Eth1 | *access | *100 | *- | *- | 3 |
| Ethernet4 | data_server_R2_2_Eth1 | *access | *100 | *- | *- | 4 |
| Ethernet5 | data_server_R3_1_Eth1 | *access | *100 | *- | *- | 5 |
| Ethernet6 | data_server_R3_2_Eth1 | *access | *100 | *- | *- | 6 |
| Ethernet7 | storage_server_R4_1_Eth1 | *access | *100 | *- | *- | 7 |
| Ethernet8 | storage_server_R4_2_Eth1 | *access | *100 | *- | *- | 8 |
| Ethernet9 | storage_server_R5_1_Eth1 | *access | *100 | *- | *- | 9 |
| Ethernet15 |  cvp_server_oobm1_Eth1 | access | 100 | - | - | - |
| Ethernet16 | MLAG_PEER_BC-OOBM2_Ethernet16 | *trunk | *2-4094 | *- | *['MLAG'] | 16 |
| Ethernet17 | MLAG_PEER_BC-OOBM2_Ethernet17 | *trunk | *2-4094 | *- | *['MLAG'] | 16 |

*Inherited from Port-Channel Interface

### Ethernet Interfaces Device Configuration

```eos
!
interface Ethernet1
   description BC-CORE-PAN-FW-OOBM-01_Eth10
   no shutdown
   channel-group 1 mode active
   no snmp trap link-change

!
interface Ethernet2
   description BC-CORE-PAN-FW-OOBM-02_Eth1
   no shutdown
   channel-group 2 mode active
   no snmp trap link-change

!
interface Ethernet3
   description data_server_R2_1_Eth1
   no shutdown
   channel-group 3 mode active
   no snmp trap link-change

!
interface Ethernet4
   description data_server_R2_2_Eth1
   no shutdown
   channel-group 4 mode active
   no snmp trap link-change

!
interface Ethernet5
   description data_server_R3_1_Eth1
   no shutdown
   channel-group 5 mode active
   no snmp trap link-change

!
interface Ethernet6
   description data_server_R3_2_Eth1
   no shutdown
   channel-group 6 mode active
   no snmp trap link-change

!
interface Ethernet7
   description storage_server_R4_1_Eth1
   no shutdown
   channel-group 7 mode active
   no snmp trap link-change

!
interface Ethernet8
   description storage_server_R4_2_Eth1
   no shutdown
   channel-group 8 mode active
   no snmp trap link-change

!
interface Ethernet9
   description storage_server_R5_1_Eth1
   no shutdown
   channel-group 9 mode active
   no snmp trap link-change

!
interface Ethernet15
   description cvp_server_oobm1_Eth1
   no shutdown
   switchport
   switchport access vlan 100
   switchport mode access
   no snmp trap link-change

!
interface Ethernet16
   description MLAG_PEER_BC-OOBM2_Ethernet16
   no shutdown
   channel-group 16 mode active
!
interface Ethernet17
   description MLAG_PEER_BC-OOBM2_Ethernet17
   no shutdown
   channel-group 16 mode active
```

## Port-Channel Interfaces

### Port-Channel Interfaces Summary

#### L2

| Interface | Description | Type | Mode | VLANs | Native VLAN | Trunk Group | LACP Fallback Timeout | LACP Fallback Mode | MLAG ID | EVPN ESI |
| --------- | ----------- | ---- | ---- | ----- | ----------- | ------------| --------------------- | ------------------ | ------- | -------- |
| Port-Channel1 | BC-CORE-PAN-FW-OOBM-01_PortChannel-oobm-FW01 | switched | access | 100 | - | - | - | - | 1 | - |
| Port-Channel2 | BC-CORE-PAN-FW-OOBM-02_PortChannel-oobm-FW02 | switched | access | 100 | - | - | - | - | 2 | - |
| Port-Channel3 | data_server_R2_1_portchannel-oobm | switched | access | 100 | - | - | - | - | 3 | - |
| Port-Channel4 | data_server_R2_2_portchannel-oobm | switched | access | 100 | - | - | - | - | 4 | - |
| Port-Channel5 | data_server_R3_1_portchannel-oobm | switched | access | 100 | - | - | - | - | 5 | - |
| Port-Channel6 | data_server_R3_2_portchannel-oobm | switched | access | 100 | - | - | - | - | 6 | - |
| Port-Channel7 | storage_server_R4_1_portchannel-oobm | switched | access | 100 | - | - | - | - | 7 | - |
| Port-Channel8 | storage_server_R4_2_portchannel-oobm | switched | access | 100 | - | - | - | - | 8 | - |
| Port-Channel9 | storage_server_R5_1_portchannel-oobm | switched | access | 100 | - | - | - | - | 9 | - |
| Port-Channel16 | MLAG_PEER_BC-OOBM2_Po16 | switched | trunk | 2-4094 | - | ['MLAG'] | - | - | - | - |

### Port-Channel Interfaces Device Configuration

```eos
!
interface Port-Channel1
   description BC-CORE-PAN-FW-OOBM-01_PortChannel-oobm-FW01
   no shutdown
   switchport
   switchport access vlan 100
   mlag 1
!
interface Port-Channel2
   description BC-CORE-PAN-FW-OOBM-02_PortChannel-oobm-FW02
   no shutdown
   switchport
   switchport access vlan 100
   mlag 2
!
interface Port-Channel3
   description data_server_R2_1_portchannel-oobm
   no shutdown
   switchport
   switchport access vlan 100
   mlag 3
!
interface Port-Channel4
   description data_server_R2_2_portchannel-oobm
   no shutdown
   switchport
   switchport access vlan 100
   mlag 4
!
interface Port-Channel5
   description data_server_R3_1_portchannel-oobm
   no shutdown
   switchport
   switchport access vlan 100
   mlag 5
!
interface Port-Channel6
   description data_server_R3_2_portchannel-oobm
   no shutdown
   switchport
   switchport access vlan 100
   mlag 6
!
interface Port-Channel7
   description storage_server_R4_1_portchannel-oobm
   no shutdown
   switchport
   switchport access vlan 100
   mlag 7
!
interface Port-Channel8
   description storage_server_R4_2_portchannel-oobm
   no shutdown
   switchport
   switchport access vlan 100
   mlag 8
!
interface Port-Channel9
   description storage_server_R5_1_portchannel-oobm
   no shutdown
   switchport
   switchport access vlan 100
   mlag 9
!
interface Port-Channel16
   description MLAG_PEER_BC-OOBM2_Po16
   no shutdown
   switchport
   switchport trunk allowed vlan 2-4094
   switchport mode trunk
   switchport trunk group MLAG
```

## VLAN Interfaces

### VLAN Interfaces Summary

| Interface | Description | VRF |  MTU | Shutdown |
| --------- | ----------- | --- | ---- | -------- |
| Vlan4094 |  MLAG_PEER  |  default  |  1500  |  false  |

#### IPv4

| Interface | VRF | IP Address | IP Address Virtual | IP Router Virtual Address | VRRP | ACL In | ACL Out |
| --------- | --- | ---------- | ------------------ | ------------------------- | ---- | ------ | ------- |
| Vlan4094 |  default  |  10.255.252.0/31  |  -  |  -  |  -  |  -  |  -  |


### VLAN Interfaces Device Configuration

```eos
!
interface Vlan4094
   description MLAG_PEER
   no shutdown
   mtu 1500
   no autostate
   ip address 10.255.252.0/31
```

# Routing
## Service Routing Protocols Model

Multi agent routing protocol model enabled

```eos
!
service routing protocols model multi-agent
```

## IP Routing

### IP Routing Summary

| VRF | Routing Enabled |
| --- | --------------- |
| default | true|| default | false |

### IP Routing Device Configuration

```eos
!
ip routing
```
## IPv6 Routing

### IPv6 Routing Summary

| VRF | Routing Enabled |
| --- | --------------- |
| default | false || default | false |


## Static Routes

### Static Routes Summary

| VRF | Destination Prefix | Next Hop IP             | Exit interface      | Administrative Distance       | Tag               | Route Name                    | Metric         |
| --- | ------------------ | ----------------------- | ------------------- | ----------------------------- | ----------------- | ----------------------------- | -------------- |
| default  | 0.0.0.0/0 |  172.20.20.1  |  -  |  1  |  -  |  -  |  - |

### Static Routes Device Configuration

```eos
!
ip route 0.0.0.0/0 172.20.20.1
```

# Multicast

## IP IGMP Snooping

### IP IGMP Snooping Summary

IGMP snooping is globally enabled.


### IP IGMP Snooping Device Configuration

```eos
```

# Filters

# ACL

# VRF Instances

## VRF Instances Summary

| VRF Name | IP Routing |
| -------- | ---------- |
| default | disabled |

## VRF Instances Device Configuration

```eos
```

# Quality Of Service

# EOS CLI

```eos
!
vlan 100

```
