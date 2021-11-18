# BC_FABRIC_1

# Table of Contents
<!-- toc -->

- [Fabric Switches and Management IP](#fabric-switches-and-management-ip)
  - [Fabric Switches with inband Management IP](#fabric-switches-with-inband-management-ip)
- [Fabric Topology](#fabric-topology)
- [Fabric IP Allocation](#fabric-ip-allocation)
  - [Fabric Point-To-Point Links](#fabric-point-to-point-links)
  - [Point-To-Point Links Node Allocation](#point-to-point-links-node-allocation)
  - [Loopback Interfaces (BGP EVPN Peering)](#loopback-interfaces-bgp-evpn-peering)
  - [Loopback0 Interfaces Node Allocation](#loopback0-interfaces-node-allocation)
  - [VTEP Loopback VXLAN Tunnel Source Interfaces (VTEPs Only)](#vtep-loopback-vxlan-tunnel-source-interfaces-vteps-only)
  - [VTEP Loopback Node allocation](#vtep-loopback-node-allocation)

<!-- toc -->
# Fabric Switches and Management IP

| POD | Type | Node | Management IP | Platform | Provisioned in CloudVision |
| --- | ---- | ---- | ------------- | -------- | -------------------------- |
| BC_FABRIC_1 | l3leaf | BC-BORDERLEAF1 | 172.20.21.101/23 | vEOS-LAB | Provisioned |
| BC_FABRIC_1 | l3leaf | BC-BORDERLEAF2 | 172.20.21.102/23 | vEOS-LAB | Provisioned |
| BC_FABRIC_1 | l3leaf | BC-DATALEAF3 | 172.20.21.103/23 | vEOS-LAB | Provisioned |
| BC_FABRIC_1 | l3leaf | BC-DATALEAF4 | 172.20.21.104/23 | vEOS-LAB | Provisioned |
| BC_FABRIC_1 | l3leaf | BC-DATALEAF5 | 172.20.21.105/23 | vEOS-LAB | Provisioned |
| BC_FABRIC_1 | l3leaf | BC-DATALEAF6 | 172.20.21.106/23 | vEOS-LAB | Provisioned |
| BC_FABRIC_1 | l2leaf | BC-OOBM1 | 172.20.21.13/23 | vEOS-LAB | Provisioned |
| BC_FABRIC_1 | l2leaf | BC-OOBM2 | 172.20.21.14/23 | vEOS-LAB | Provisioned |
| BC_FABRIC_1 | spine | BC-SPINE1 | 172.20.21.11/23 | vEOS-LAB | Provisioned |
| BC_FABRIC_1 | spine | BC-SPINE2 | 172.20.21.12/23 | vEOS-LAB | Provisioned |
| BC_FABRIC_1 | l3leaf | BC-STOLEAF1 | 172.20.21.111/23 | vEOS-LAB | Provisioned |
| BC_FABRIC_1 | l3leaf | BC-STOLEAF2 | 172.20.21.112/23 | vEOS-LAB | Provisioned |
| BC_FABRIC_1 | l3leaf | BC-STOLEAF3 | 172.20.21.113/23 | vEOS-LAB | Provisioned |
| BC_FABRIC_1 | l3leaf | BC-STOLEAF4 | 172.20.21.114/23 | vEOS-LAB | Provisioned |

> Provision status is based on Ansible inventory declaration and do not represent real status from CloudVision.

## Fabric Switches with inband Management IP
| POD | Type | Node | Management IP | Inband Interface |
| --- | ---- | ---- | ------------- | ---------------- |

# Fabric Topology

| Type | Node | Node Interface | Peer Type | Peer Node | Peer Interface |
| ---- | ---- | -------------- | --------- | ----------| -------------- |
| l3leaf | BC-BORDERLEAF1 | Ethernet1 | spine | BC-SPINE1 | Ethernet1 |
| l3leaf | BC-BORDERLEAF1 | Ethernet2 | spine | BC-SPINE2 | Ethernet1 |
| l3leaf | BC-BORDERLEAF1 | Ethernet12 | mlag_peer | BC-BORDERLEAF2 | Ethernet12 |
| l3leaf | BC-BORDERLEAF1 | Ethernet13 | mlag_peer | BC-BORDERLEAF2 | Ethernet13 |
| l3leaf | BC-BORDERLEAF2 | Ethernet1 | spine | BC-SPINE1 | Ethernet2 |
| l3leaf | BC-BORDERLEAF2 | Ethernet2 | spine | BC-SPINE2 | Ethernet2 |
| l3leaf | BC-DATALEAF3 | Ethernet1 | spine | BC-SPINE1 | Ethernet3 |
| l3leaf | BC-DATALEAF3 | Ethernet2 | spine | BC-SPINE2 | Ethernet3 |
| l3leaf | BC-DATALEAF3 | Ethernet12 | mlag_peer | BC-DATALEAF4 | Ethernet12 |
| l3leaf | BC-DATALEAF3 | Ethernet13 | mlag_peer | BC-DATALEAF4 | Ethernet13 |
| l3leaf | BC-DATALEAF4 | Ethernet1 | spine | BC-SPINE1 | Ethernet4 |
| l3leaf | BC-DATALEAF4 | Ethernet2 | spine | BC-SPINE2 | Ethernet4 |
| l3leaf | BC-DATALEAF5 | Ethernet1 | spine | BC-SPINE1 | Ethernet5 |
| l3leaf | BC-DATALEAF5 | Ethernet2 | spine | BC-SPINE2 | Ethernet5 |
| l3leaf | BC-DATALEAF5 | Ethernet12 | mlag_peer | BC-DATALEAF6 | Ethernet12 |
| l3leaf | BC-DATALEAF5 | Ethernet13 | mlag_peer | BC-DATALEAF6 | Ethernet13 |
| l3leaf | BC-DATALEAF6 | Ethernet1 | spine | BC-SPINE1 | Ethernet6 |
| l3leaf | BC-DATALEAF6 | Ethernet2 | spine | BC-SPINE2 | Ethernet6 |
| l2leaf | BC-OOBM1 | Ethernet16 | mlag_peer | BC-OOBM2 | Ethernet16 |
| l2leaf | BC-OOBM1 | Ethernet17 | mlag_peer | BC-OOBM2 | Ethernet17 |
| spine | BC-SPINE1 | Ethernet7 | l3leaf | BC-STOLEAF1 | Ethernet1 |
| spine | BC-SPINE1 | Ethernet8 | l3leaf | BC-STOLEAF2 | Ethernet1 |
| spine | BC-SPINE1 | Ethernet9 | l3leaf | BC-STOLEAF3 | Ethernet1 |
| spine | BC-SPINE1 | Ethernet10 | l3leaf | BC-STOLEAF4 | Ethernet1 |
| spine | BC-SPINE2 | Ethernet7 | l3leaf | BC-STOLEAF1 | Ethernet2 |
| spine | BC-SPINE2 | Ethernet8 | l3leaf | BC-STOLEAF2 | Ethernet2 |
| spine | BC-SPINE2 | Ethernet9 | l3leaf | BC-STOLEAF3 | Ethernet2 |
| spine | BC-SPINE2 | Ethernet10 | l3leaf | BC-STOLEAF4 | Ethernet2 |
| l3leaf | BC-STOLEAF1 | Ethernet12 | mlag_peer | BC-STOLEAF2 | Ethernet12 |
| l3leaf | BC-STOLEAF1 | Ethernet13 | mlag_peer | BC-STOLEAF2 | Ethernet13 |
| l3leaf | BC-STOLEAF3 | Ethernet12 | mlag_peer | BC-STOLEAF4 | Ethernet12 |
| l3leaf | BC-STOLEAF3 | Ethernet13 | mlag_peer | BC-STOLEAF4 | Ethernet13 |

# Fabric IP Allocation

## Fabric Point-To-Point Links

| Uplink IPv4 Pool | Available Addresses | Assigned addresses | Assigned Address % |
| ---------------- | ------------------- | ------------------ | ------------------ |
| 172.31.255.0/24 | 256 | 40 | 15.63 % |

## Point-To-Point Links Node Allocation

| Node | Node Interface | Node IP Address | Peer Node | Peer Interface | Peer IP Address |
| ---- | -------------- | --------------- | --------- | -------------- | --------------- |
| BC-BORDERLEAF1 | Ethernet1 | 172.31.255.1/31 | BC-SPINE1 | Ethernet1 | 172.31.255.0/31 |
| BC-BORDERLEAF1 | Ethernet2 | 172.31.255.3/31 | BC-SPINE2 | Ethernet1 | 172.31.255.2/31 |
| BC-BORDERLEAF2 | Ethernet1 | 172.31.255.5/31 | BC-SPINE1 | Ethernet2 | 172.31.255.4/31 |
| BC-BORDERLEAF2 | Ethernet2 | 172.31.255.7/31 | BC-SPINE2 | Ethernet2 | 172.31.255.6/31 |
| BC-DATALEAF3 | Ethernet1 | 172.31.255.9/31 | BC-SPINE1 | Ethernet3 | 172.31.255.8/31 |
| BC-DATALEAF3 | Ethernet2 | 172.31.255.11/31 | BC-SPINE2 | Ethernet3 | 172.31.255.10/31 |
| BC-DATALEAF4 | Ethernet1 | 172.31.255.13/31 | BC-SPINE1 | Ethernet4 | 172.31.255.12/31 |
| BC-DATALEAF4 | Ethernet2 | 172.31.255.15/31 | BC-SPINE2 | Ethernet4 | 172.31.255.14/31 |
| BC-DATALEAF5 | Ethernet1 | 172.31.255.17/31 | BC-SPINE1 | Ethernet5 | 172.31.255.16/31 |
| BC-DATALEAF5 | Ethernet2 | 172.31.255.19/31 | BC-SPINE2 | Ethernet5 | 172.31.255.18/31 |
| BC-DATALEAF6 | Ethernet1 | 172.31.255.21/31 | BC-SPINE1 | Ethernet6 | 172.31.255.20/31 |
| BC-DATALEAF6 | Ethernet2 | 172.31.255.23/31 | BC-SPINE2 | Ethernet6 | 172.31.255.22/31 |
| BC-SPINE1 | Ethernet7 | 172.31.255.24/31 | BC-STOLEAF1 | Ethernet1 | 172.31.255.25/31 |
| BC-SPINE1 | Ethernet8 | 172.31.255.28/31 | BC-STOLEAF2 | Ethernet1 | 172.31.255.29/31 |
| BC-SPINE1 | Ethernet9 | 172.31.255.32/31 | BC-STOLEAF3 | Ethernet1 | 172.31.255.33/31 |
| BC-SPINE1 | Ethernet10 | 172.31.255.36/31 | BC-STOLEAF4 | Ethernet1 | 172.31.255.37/31 |
| BC-SPINE2 | Ethernet7 | 172.31.255.26/31 | BC-STOLEAF1 | Ethernet2 | 172.31.255.27/31 |
| BC-SPINE2 | Ethernet8 | 172.31.255.30/31 | BC-STOLEAF2 | Ethernet2 | 172.31.255.31/31 |
| BC-SPINE2 | Ethernet9 | 172.31.255.34/31 | BC-STOLEAF3 | Ethernet2 | 172.31.255.35/31 |
| BC-SPINE2 | Ethernet10 | 172.31.255.38/31 | BC-STOLEAF4 | Ethernet2 | 172.31.255.39/31 |

## Loopback Interfaces (BGP EVPN Peering)

| Loopback Pool | Available Addresses | Assigned addresses | Assigned Address % |
| ------------- | ------------------- | ------------------ | ------------------ |
| 10.200.0.0/24 | 256 | 2 | 0.79 % |
| 10.200.1.0/24 | 256 | 10 | 3.91 % |

## Loopback0 Interfaces Node Allocation

| POD | Node | Loopback0 |
| --- | ---- | --------- |
| BC_FABRIC_1 | BC-BORDERLEAF1 | 10.200.1.1/32 |
| BC_FABRIC_1 | BC-BORDERLEAF2 | 10.200.1.2/32 |
| BC_FABRIC_1 | BC-DATALEAF3 | 10.200.1.3/32 |
| BC_FABRIC_1 | BC-DATALEAF4 | 10.200.1.4/32 |
| BC_FABRIC_1 | BC-DATALEAF5 | 10.200.1.5/32 |
| BC_FABRIC_1 | BC-DATALEAF6 | 10.200.1.6/32 |
| BC_FABRIC_1 | BC-SPINE1 | 10.200.0.1/32 |
| BC_FABRIC_1 | BC-SPINE2 | 10.200.0.2/32 |
| BC_FABRIC_1 | BC-STOLEAF1 | 10.200.1.7/32 |
| BC_FABRIC_1 | BC-STOLEAF2 | 10.200.1.8/32 |
| BC_FABRIC_1 | BC-STOLEAF3 | 10.200.1.9/32 |
| BC_FABRIC_1 | BC-STOLEAF4 | 10.200.1.10/32 |

## VTEP Loopback VXLAN Tunnel Source Interfaces (VTEPs Only)

| VTEP Loopback Pool | Available Addresses | Assigned addresses | Assigned Address % |
| --------------------- | ------------------- | ------------------ | ------------------ |
| 192.168.254.0/24 | 256 | 10 | 3.91 % |

## VTEP Loopback Node allocation

| POD | Node | Loopback1 |
| --- | ---- | --------- |
| BC_FABRIC_1 | BC-BORDERLEAF1 | 192.168.254.1/32 |
| BC_FABRIC_1 | BC-BORDERLEAF2 | 192.168.254.1/32 |
| BC_FABRIC_1 | BC-DATALEAF3 | 192.168.254.3/32 |
| BC_FABRIC_1 | BC-DATALEAF4 | 192.168.254.3/32 |
| BC_FABRIC_1 | BC-DATALEAF5 | 192.168.254.5/32 |
| BC_FABRIC_1 | BC-DATALEAF6 | 192.168.254.5/32 |
| BC_FABRIC_1 | BC-STOLEAF1 | 192.168.254.7/32 |
| BC_FABRIC_1 | BC-STOLEAF2 | 192.168.254.7/32 |
| BC_FABRIC_1 | BC-STOLEAF3 | 192.168.254.9/32 |
| BC_FABRIC_1 | BC-STOLEAF4 | 192.168.254.9/32 |
