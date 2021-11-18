
# Validate State Report

**Table of Contents:**

- [Validate State Report](validate-state-report)
  - [Test Results Summary](#test-results-summary)
  - [Failed Test Results Summary](#failed-test-results-summary)
  - [All Test Results](#all-test-results)

## Test Results Summary

### Summary Totals

| Total Tests | Total Tests Passed | Total Tests Failed |
| ----------- | ------------------ | ------------------ |
| 848 | 794 | 54 |

### Summary Totals Devices Under Tests

| DUT | Total Tests | Tests Passed | Tests Failed | Categories Failed |
| --- | ----------- | ------------ | ------------ | ----------------- |
| BC-BORDERLEAF1 |  57 | 53 | 4 | Interface State |
| BC-BORDERLEAF2 |  57 | 53 | 4 | Interface State |
| BC-DATALEAF3 |  71 | 67 | 4 | Interface State |
| BC-DATALEAF4 |  71 | 67 | 4 | Interface State |
| BC-DATALEAF5 |  71 | 67 | 4 | Interface State |
| BC-DATALEAF6 |  71 | 67 | 4 | Interface State |
| BC-OOBM1 |  27 | 18 | 9 | Interface State |
| BC-OOBM2 |  27 | 18 | 9 | Interface State |
| BC-SPINE1 |  73 | 73 | 0 | - |
| BC-SPINE2 |  73 | 73 | 0 | - |
| BC-STOLEAF1 |  63 | 59 | 4 | Interface State |
| BC-STOLEAF2 |  63 | 59 | 4 | Interface State |
| BC-STOLEAF3 |  62 | 60 | 2 | Interface State |
| BC-STOLEAF4 |  62 | 60 | 2 | Interface State |

### Summary Totals Per Category

| Test Category | Total Tests | Tests Passed | Tests Failed |
| ------------- | ----------- | ------------ | ------------ |
| NTP |  14 | 14 | 0 |
| Interface State |  326 | 272 | 54 |
| LLDP Topology |  64 | 64 | 0 |
| MLAG |  12 | 12 | 0 |
| IP Reachability |  40 | 40 | 0 |
| BGP |  102 | 102 | 0 |
| Routing Table |  170 | 170 | 0 |
| Loopback0 Reachability |  120 | 120 | 0 |

## Failed Test Results Summary

| Test ID | Node | Test Category | Test Description | Test | Test Result | Failure Reason |
| ------- | ---- | ------------- | ---------------- | ---- | ----------- | -------------- |
| 136 | BC-BORDERLEAF1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - BC-CORE-PAN-FW-01_PortChannel-inside | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 137 | BC-BORDERLEAF1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - BC-CORE-PAN-FW-01_PortChannel-outside | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 138 | BC-BORDERLEAF1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - BC-CORE-PAN-FW-02_PortChannel-inside | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 139 | BC-BORDERLEAF1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - BC-CORE-PAN-FW-02_PortChannel-outside | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 141 | BC-BORDERLEAF2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - BC-CORE-PAN-FW-01_PortChannel-inside | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 142 | BC-BORDERLEAF2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - BC-CORE-PAN-FW-01_PortChannel-outside | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 143 | BC-BORDERLEAF2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - BC-CORE-PAN-FW-02_PortChannel-inside | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 144 | BC-BORDERLEAF2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - BC-CORE-PAN-FW-02_PortChannel-outside | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 146 | BC-DATALEAF3 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - data_server_1_portchannel-tenant_blue_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 147 | BC-DATALEAF3 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - data_server_1_portchannel-tenant_blue_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 148 | BC-DATALEAF3 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - data_server_2_portchannel-tenant_blue_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 149 | BC-DATALEAF3 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - data_server_2_portchannel-tenant_blue_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 151 | BC-DATALEAF4 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - data_server_1_portchannel-tenant_blue_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 152 | BC-DATALEAF4 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - data_server_1_portchannel-tenant_blue_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 153 | BC-DATALEAF4 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - data_server_2_portchannel-tenant_blue_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 154 | BC-DATALEAF4 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - data_server_2_portchannel-tenant_blue_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 156 | BC-DATALEAF5 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - data_server_1_portchannel-tenant_blue_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 157 | BC-DATALEAF5 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - data_server_1_portchannel-tenant_blue_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 158 | BC-DATALEAF5 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - data_server_2_portchannel-tenant_blue_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 159 | BC-DATALEAF5 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - data_server_2_portchannel-tenant_blue_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 161 | BC-DATALEAF6 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - data_server_1_portchannel-tenant_blue_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 162 | BC-DATALEAF6 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - data_server_1_portchannel-tenant_blue_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 163 | BC-DATALEAF6 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - data_server_2_portchannel-tenant_blue_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 164 | BC-DATALEAF6 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - data_server_2_portchannel-tenant_blue_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 166 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - data_server_R2_1_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 167 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - data_server_R2_2_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 168 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - data_server_R3_1_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 169 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - data_server_R3_2_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 170 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel7 - storage_server_R4_1_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 171 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel8 - storage_server_R4_2_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 172 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel9 - storage_server_R5_1_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 173 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel1 - BC-CORE-PAN-FW-OOBM-01_PortChannel-oobm-FW01 | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 174 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel2 - BC-CORE-PAN-FW-OOBM-02_PortChannel-oobm-FW02 | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 176 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - data_server_R2_1_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 177 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - data_server_R2_2_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 178 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - data_server_R3_1_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 179 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - data_server_R3_2_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 180 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel7 - storage_server_R4_1_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 181 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel8 - storage_server_R4_2_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 182 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel9 - storage_server_R5_1_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 183 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel1 - BC-CORE-PAN-FW-OOBM-01_PortChannel-oobm-FW01 | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 184 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel2 - BC-CORE-PAN-FW-OOBM-02_PortChannel-oobm-FW02 | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 186 | BC-STOLEAF1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - storage_server_1_portchannel-storage_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 187 | BC-STOLEAF1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - storage_server_1_portchannel-storage_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 188 | BC-STOLEAF1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - storage_server_2_portchannel-storage_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 189 | BC-STOLEAF1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - storage_server_2_portchannel-storage_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 191 | BC-STOLEAF2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - storage_server_1_portchannel-storage_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 192 | BC-STOLEAF2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - storage_server_1_portchannel-storage_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 193 | BC-STOLEAF2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - storage_server_2_portchannel-storage_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 194 | BC-STOLEAF2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - storage_server_2_portchannel-storage_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 196 | BC-STOLEAF3 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - storage_server_1_portchannel-storage_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 197 | BC-STOLEAF3 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - storage_server_1_portchannel-storage_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 199 | BC-STOLEAF4 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - storage_server_1_portchannel-storage_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 200 | BC-STOLEAF4 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - storage_server_1_portchannel-storage_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |

## All Test Results

| Test ID | Node | Test Category | Test Description | Test | Test Result | Failure Reason |
| ------- | ---- | ------------- | ---------------- | ---- | ----------- | -------------- |
| 1 | BC-BORDERLEAF1 | NTP | Synchronised with NTP server | NTP | PASS |  |
| 2 | BC-BORDERLEAF2 | NTP | Synchronised with NTP server | NTP | PASS |  |
| 3 | BC-DATALEAF3 | NTP | Synchronised with NTP server | NTP | PASS |  |
| 4 | BC-DATALEAF4 | NTP | Synchronised with NTP server | NTP | PASS |  |
| 5 | BC-DATALEAF5 | NTP | Synchronised with NTP server | NTP | PASS |  |
| 6 | BC-DATALEAF6 | NTP | Synchronised with NTP server | NTP | PASS |  |
| 7 | BC-OOBM1 | NTP | Synchronised with NTP server | NTP | PASS |  |
| 8 | BC-OOBM2 | NTP | Synchronised with NTP server | NTP | PASS |  |
| 9 | BC-SPINE1 | NTP | Synchronised with NTP server | NTP | PASS |  |
| 10 | BC-SPINE2 | NTP | Synchronised with NTP server | NTP | PASS |  |
| 11 | BC-STOLEAF1 | NTP | Synchronised with NTP server | NTP | PASS |  |
| 12 | BC-STOLEAF2 | NTP | Synchronised with NTP server | NTP | PASS |  |
| 13 | BC-STOLEAF3 | NTP | Synchronised with NTP server | NTP | PASS |  |
| 14 | BC-STOLEAF4 | NTP | Synchronised with NTP server | NTP | PASS |  |
| 15 | BC-BORDERLEAF1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet12 - MLAG_PEER_BC-BORDERLEAF2_Ethernet12 | PASS |  |
| 16 | BC-BORDERLEAF1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet13 - MLAG_PEER_BC-BORDERLEAF2_Ethernet13 | PASS |  |
| 17 | BC-BORDERLEAF1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_BC-SPINE1_Ethernet1 | PASS |  |
| 18 | BC-BORDERLEAF1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_BC-SPINE2_Ethernet1 | PASS |  |
| 19 | BC-BORDERLEAF1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - BC-CORE-PAN-FW-01_Eth1 | PASS |  |
| 20 | BC-BORDERLEAF1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - BC-CORE-PAN-FW-01_Eth3 | PASS |  |
| 21 | BC-BORDERLEAF1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet5 - BC-CORE-PAN-FW-02_Eth1 | PASS |  |
| 22 | BC-BORDERLEAF1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet6 - BC-CORE-PAN-FW-02_Eth3 | PASS |  |
| 23 | BC-BORDERLEAF2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet12 - MLAG_PEER_BC-BORDERLEAF1_Ethernet12 | PASS |  |
| 24 | BC-BORDERLEAF2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet13 - MLAG_PEER_BC-BORDERLEAF1_Ethernet13 | PASS |  |
| 25 | BC-BORDERLEAF2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_BC-SPINE1_Ethernet2 | PASS |  |
| 26 | BC-BORDERLEAF2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_BC-SPINE2_Ethernet2 | PASS |  |
| 27 | BC-BORDERLEAF2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - BC-CORE-PAN-FW-01_Eth2 | PASS |  |
| 28 | BC-BORDERLEAF2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - BC-CORE-PAN-FW-01_Eth4 | PASS |  |
| 29 | BC-BORDERLEAF2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet5 - BC-CORE-PAN-FW-02_Eth2 | PASS |  |
| 30 | BC-BORDERLEAF2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet6 - BC-CORE-PAN-FW-02_Eth4 | PASS |  |
| 31 | BC-DATALEAF3 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet12 - MLAG_PEER_BC-DATALEAF4_Ethernet12 | PASS |  |
| 32 | BC-DATALEAF3 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet13 - MLAG_PEER_BC-DATALEAF4_Ethernet13 | PASS |  |
| 33 | BC-DATALEAF3 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_BC-SPINE1_Ethernet3 | PASS |  |
| 34 | BC-DATALEAF3 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_BC-SPINE2_Ethernet3 | PASS |  |
| 35 | BC-DATALEAF3 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - data_server_1_Eth3 | PASS |  |
| 36 | BC-DATALEAF3 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - data_server_1_Eth5 | PASS |  |
| 37 | BC-DATALEAF3 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet5 - data_server_2_Eth3 | PASS |  |
| 38 | BC-DATALEAF3 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet6 - data_server_2_Eth5 | PASS |  |
| 39 | BC-DATALEAF4 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet12 - MLAG_PEER_BC-DATALEAF3_Ethernet12 | PASS |  |
| 40 | BC-DATALEAF4 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet13 - MLAG_PEER_BC-DATALEAF3_Ethernet13 | PASS |  |
| 41 | BC-DATALEAF4 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_BC-SPINE1_Ethernet4 | PASS |  |
| 42 | BC-DATALEAF4 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_BC-SPINE2_Ethernet4 | PASS |  |
| 43 | BC-DATALEAF4 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - data_server_1_Eth4 | PASS |  |
| 44 | BC-DATALEAF4 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - data_server_1_Eth6 | PASS |  |
| 45 | BC-DATALEAF4 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet5 - data_server_2_Eth4 | PASS |  |
| 46 | BC-DATALEAF4 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet6 - data_server_2_Eth6 | PASS |  |
| 47 | BC-DATALEAF5 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet12 - MLAG_PEER_BC-DATALEAF6_Ethernet12 | PASS |  |
| 48 | BC-DATALEAF5 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet13 - MLAG_PEER_BC-DATALEAF6_Ethernet13 | PASS |  |
| 49 | BC-DATALEAF5 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_BC-SPINE1_Ethernet5 | PASS |  |
| 50 | BC-DATALEAF5 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_BC-SPINE2_Ethernet5 | PASS |  |
| 51 | BC-DATALEAF5 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - data_server_1_Eth3 | PASS |  |
| 52 | BC-DATALEAF5 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - data_server_1_Eth5 | PASS |  |
| 53 | BC-DATALEAF5 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet5 - data_server_2_Eth3 | PASS |  |
| 54 | BC-DATALEAF5 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet6 - data_server_2_Eth5 | PASS |  |
| 55 | BC-DATALEAF6 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet12 - MLAG_PEER_BC-DATALEAF5_Ethernet12 | PASS |  |
| 56 | BC-DATALEAF6 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet13 - MLAG_PEER_BC-DATALEAF5_Ethernet13 | PASS |  |
| 57 | BC-DATALEAF6 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_BC-SPINE1_Ethernet6 | PASS |  |
| 58 | BC-DATALEAF6 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_BC-SPINE2_Ethernet6 | PASS |  |
| 59 | BC-DATALEAF6 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - data_server_1_Eth4 | PASS |  |
| 60 | BC-DATALEAF6 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - data_server_1_Eth6 | PASS |  |
| 61 | BC-DATALEAF6 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet5 - data_server_2_Eth4 | PASS |  |
| 62 | BC-DATALEAF6 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet6 - data_server_2_Eth6 | PASS |  |
| 63 | BC-OOBM1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet16 - MLAG_PEER_BC-OOBM2_Ethernet16 | PASS |  |
| 64 | BC-OOBM1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet17 - MLAG_PEER_BC-OOBM2_Ethernet17 | PASS |  |
| 65 | BC-OOBM1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet15 - cvp_server_oobm1_Eth1 | PASS |  |
| 66 | BC-OOBM1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - data_server_R2_1_Eth1 | PASS |  |
| 67 | BC-OOBM1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - data_server_R2_2_Eth1 | PASS |  |
| 68 | BC-OOBM1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet5 - data_server_R3_1_Eth1 | PASS |  |
| 69 | BC-OOBM1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet6 - data_server_R3_2_Eth1 | PASS |  |
| 70 | BC-OOBM1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet7 - storage_server_R4_1_Eth1 | PASS |  |
| 71 | BC-OOBM1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet8 - storage_server_R4_2_Eth1 | PASS |  |
| 72 | BC-OOBM1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet9 - storage_server_R5_1_Eth1 | PASS |  |
| 73 | BC-OOBM1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - BC-CORE-PAN-FW-OOBM-01_Eth10 | PASS |  |
| 74 | BC-OOBM1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - BC-CORE-PAN-FW-OOBM-02_Eth1 | PASS |  |
| 75 | BC-OOBM2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet16 - MLAG_PEER_BC-OOBM1_Ethernet16 | PASS |  |
| 76 | BC-OOBM2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet17 - MLAG_PEER_BC-OOBM1_Ethernet17 | PASS |  |
| 77 | BC-OOBM2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet15 - cvp_server_oobm2_Eth2 | PASS |  |
| 78 | BC-OOBM2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - data_server_R2_1_Eth2 | PASS |  |
| 79 | BC-OOBM2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - data_server_R2_2_Eth2 | PASS |  |
| 80 | BC-OOBM2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet5 - data_server_R3_1_Eth2 | PASS |  |
| 81 | BC-OOBM2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet6 - data_server_R3_2_Eth2 | PASS |  |
| 82 | BC-OOBM2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet7 - storage_server_R4_1_Eth2 | PASS |  |
| 83 | BC-OOBM2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet8 - storage_server_R4_2_Eth2 | PASS |  |
| 84 | BC-OOBM2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet9 - storage_server_R5_1_Eth2 | PASS |  |
| 85 | BC-OOBM2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - BC-CORE-PAN-FW-OOBM-01_Eth11 | PASS |  |
| 86 | BC-OOBM2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - BC-CORE-PAN-FW-OOBM-02_Eth2 | PASS |  |
| 87 | BC-SPINE1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_BC-BORDERLEAF1_Ethernet1 | PASS |  |
| 88 | BC-SPINE1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_BC-BORDERLEAF2_Ethernet1 | PASS |  |
| 89 | BC-SPINE1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - P2P_LINK_TO_BC-DATALEAF3_Ethernet1 | PASS |  |
| 90 | BC-SPINE1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - P2P_LINK_TO_BC-DATALEAF4_Ethernet1 | PASS |  |
| 91 | BC-SPINE1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet5 - P2P_LINK_TO_BC-DATALEAF5_Ethernet1 | PASS |  |
| 92 | BC-SPINE1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet6 - P2P_LINK_TO_BC-DATALEAF6_Ethernet1 | PASS |  |
| 93 | BC-SPINE1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet7 - P2P_LINK_TO_BC-STOLEAF1_Ethernet1 | PASS |  |
| 94 | BC-SPINE1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet8 - P2P_LINK_TO_BC-STOLEAF2_Ethernet1 | PASS |  |
| 95 | BC-SPINE1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet9 - P2P_LINK_TO_BC-STOLEAF3_Ethernet1 | PASS |  |
| 96 | BC-SPINE1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet10 - P2P_LINK_TO_BC-STOLEAF4_Ethernet1 | PASS |  |
| 97 | BC-SPINE2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_BC-BORDERLEAF1_Ethernet2 | PASS |  |
| 98 | BC-SPINE2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_BC-BORDERLEAF2_Ethernet2 | PASS |  |
| 99 | BC-SPINE2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - P2P_LINK_TO_BC-DATALEAF3_Ethernet2 | PASS |  |
| 100 | BC-SPINE2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - P2P_LINK_TO_BC-DATALEAF4_Ethernet2 | PASS |  |
| 101 | BC-SPINE2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet5 - P2P_LINK_TO_BC-DATALEAF5_Ethernet2 | PASS |  |
| 102 | BC-SPINE2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet6 - P2P_LINK_TO_BC-DATALEAF6_Ethernet2 | PASS |  |
| 103 | BC-SPINE2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet7 - P2P_LINK_TO_BC-STOLEAF1_Ethernet2 | PASS |  |
| 104 | BC-SPINE2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet8 - P2P_LINK_TO_BC-STOLEAF2_Ethernet2 | PASS |  |
| 105 | BC-SPINE2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet9 - P2P_LINK_TO_BC-STOLEAF3_Ethernet2 | PASS |  |
| 106 | BC-SPINE2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet10 - P2P_LINK_TO_BC-STOLEAF4_Ethernet2 | PASS |  |
| 107 | BC-STOLEAF1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet12 - MLAG_PEER_BC-STOLEAF2_Ethernet12 | PASS |  |
| 108 | BC-STOLEAF1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet13 - MLAG_PEER_BC-STOLEAF2_Ethernet13 | PASS |  |
| 109 | BC-STOLEAF1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_BC-SPINE1_Ethernet7 | PASS |  |
| 110 | BC-STOLEAF1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_BC-SPINE2_Ethernet7 | PASS |  |
| 111 | BC-STOLEAF1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - storage_server_1_Eth3 | PASS |  |
| 112 | BC-STOLEAF1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - storage_server_1_Eth5 | PASS |  |
| 113 | BC-STOLEAF1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet5 - storage_server_2_Eth3 | PASS |  |
| 114 | BC-STOLEAF1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet6 - storage_server_2_Eth5 | PASS |  |
| 115 | BC-STOLEAF2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet12 - MLAG_PEER_BC-STOLEAF1_Ethernet12 | PASS |  |
| 116 | BC-STOLEAF2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet13 - MLAG_PEER_BC-STOLEAF1_Ethernet13 | PASS |  |
| 117 | BC-STOLEAF2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_BC-SPINE1_Ethernet8 | PASS |  |
| 118 | BC-STOLEAF2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_BC-SPINE2_Ethernet8 | PASS |  |
| 119 | BC-STOLEAF2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - storage_server_1_Eth4 | PASS |  |
| 120 | BC-STOLEAF2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - storage_server_1_Eth6 | PASS |  |
| 121 | BC-STOLEAF2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet5 - storage_server_2_Eth4 | PASS |  |
| 122 | BC-STOLEAF2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet6 - storage_server_2_Eth6 | PASS |  |
| 123 | BC-STOLEAF3 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet12 - MLAG_PEER_BC-STOLEAF4_Ethernet12 | PASS |  |
| 124 | BC-STOLEAF3 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet13 - MLAG_PEER_BC-STOLEAF4_Ethernet13 | PASS |  |
| 125 | BC-STOLEAF3 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_BC-SPINE1_Ethernet9 | PASS |  |
| 126 | BC-STOLEAF3 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_BC-SPINE2_Ethernet9 | PASS |  |
| 127 | BC-STOLEAF3 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - storage_server_1_Eth3 | PASS |  |
| 128 | BC-STOLEAF3 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - storage_server_1_Eth5 | PASS |  |
| 129 | BC-STOLEAF4 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet12 - MLAG_PEER_BC-STOLEAF3_Ethernet12 | PASS |  |
| 130 | BC-STOLEAF4 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet13 - MLAG_PEER_BC-STOLEAF3_Ethernet13 | PASS |  |
| 131 | BC-STOLEAF4 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1 - P2P_LINK_TO_BC-SPINE1_Ethernet10 | PASS |  |
| 132 | BC-STOLEAF4 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2 - P2P_LINK_TO_BC-SPINE2_Ethernet10 | PASS |  |
| 133 | BC-STOLEAF4 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3 - storage_server_1_Eth4 | PASS |  |
| 134 | BC-STOLEAF4 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4 - storage_server_1_Eth6 | PASS |  |
| 135 | BC-BORDERLEAF1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel12 - MLAG_PEER_BC-BORDERLEAF2_Po12 | PASS |  |
| 136 | BC-BORDERLEAF1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - BC-CORE-PAN-FW-01_PortChannel-inside | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 137 | BC-BORDERLEAF1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - BC-CORE-PAN-FW-01_PortChannel-outside | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 138 | BC-BORDERLEAF1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - BC-CORE-PAN-FW-02_PortChannel-inside | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 139 | BC-BORDERLEAF1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - BC-CORE-PAN-FW-02_PortChannel-outside | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 140 | BC-BORDERLEAF2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel12 - MLAG_PEER_BC-BORDERLEAF1_Po12 | PASS |  |
| 141 | BC-BORDERLEAF2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - BC-CORE-PAN-FW-01_PortChannel-inside | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 142 | BC-BORDERLEAF2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - BC-CORE-PAN-FW-01_PortChannel-outside | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 143 | BC-BORDERLEAF2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - BC-CORE-PAN-FW-02_PortChannel-inside | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 144 | BC-BORDERLEAF2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - BC-CORE-PAN-FW-02_PortChannel-outside | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 145 | BC-DATALEAF3 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel12 - MLAG_PEER_BC-DATALEAF4_Po12 | PASS |  |
| 146 | BC-DATALEAF3 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - data_server_1_portchannel-tenant_blue_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 147 | BC-DATALEAF3 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - data_server_1_portchannel-tenant_blue_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 148 | BC-DATALEAF3 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - data_server_2_portchannel-tenant_blue_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 149 | BC-DATALEAF3 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - data_server_2_portchannel-tenant_blue_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 150 | BC-DATALEAF4 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel12 - MLAG_PEER_BC-DATALEAF3_Po12 | PASS |  |
| 151 | BC-DATALEAF4 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - data_server_1_portchannel-tenant_blue_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 152 | BC-DATALEAF4 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - data_server_1_portchannel-tenant_blue_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 153 | BC-DATALEAF4 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - data_server_2_portchannel-tenant_blue_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 154 | BC-DATALEAF4 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - data_server_2_portchannel-tenant_blue_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 155 | BC-DATALEAF5 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel12 - MLAG_PEER_BC-DATALEAF6_Po12 | PASS |  |
| 156 | BC-DATALEAF5 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - data_server_1_portchannel-tenant_blue_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 157 | BC-DATALEAF5 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - data_server_1_portchannel-tenant_blue_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 158 | BC-DATALEAF5 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - data_server_2_portchannel-tenant_blue_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 159 | BC-DATALEAF5 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - data_server_2_portchannel-tenant_blue_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 160 | BC-DATALEAF6 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel12 - MLAG_PEER_BC-DATALEAF5_Po12 | PASS |  |
| 161 | BC-DATALEAF6 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - data_server_1_portchannel-tenant_blue_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 162 | BC-DATALEAF6 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - data_server_1_portchannel-tenant_blue_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 163 | BC-DATALEAF6 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - data_server_2_portchannel-tenant_blue_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 164 | BC-DATALEAF6 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - data_server_2_portchannel-tenant_blue_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 165 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel16 - MLAG_PEER_BC-OOBM2_Po16 | PASS |  |
| 166 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - data_server_R2_1_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 167 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - data_server_R2_2_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 168 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - data_server_R3_1_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 169 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - data_server_R3_2_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 170 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel7 - storage_server_R4_1_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 171 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel8 - storage_server_R4_2_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 172 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel9 - storage_server_R5_1_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 173 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel1 - BC-CORE-PAN-FW-OOBM-01_PortChannel-oobm-FW01 | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 174 | BC-OOBM1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel2 - BC-CORE-PAN-FW-OOBM-02_PortChannel-oobm-FW02 | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 175 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel16 - MLAG_PEER_BC-OOBM1_Po16 | PASS |  |
| 176 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - data_server_R2_1_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 177 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - data_server_R2_2_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 178 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - data_server_R3_1_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 179 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - data_server_R3_2_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 180 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel7 - storage_server_R4_1_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 181 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel8 - storage_server_R4_2_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 182 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel9 - storage_server_R5_1_portchannel-oobm | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 183 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel1 - BC-CORE-PAN-FW-OOBM-01_PortChannel-oobm-FW01 | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 184 | BC-OOBM2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel2 - BC-CORE-PAN-FW-OOBM-02_PortChannel-oobm-FW02 | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 185 | BC-STOLEAF1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel12 - MLAG_PEER_BC-STOLEAF2_Po12 | PASS |  |
| 186 | BC-STOLEAF1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - storage_server_1_portchannel-storage_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 187 | BC-STOLEAF1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - storage_server_1_portchannel-storage_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 188 | BC-STOLEAF1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - storage_server_2_portchannel-storage_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 189 | BC-STOLEAF1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - storage_server_2_portchannel-storage_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 190 | BC-STOLEAF2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel12 - MLAG_PEER_BC-STOLEAF1_Po12 | PASS |  |
| 191 | BC-STOLEAF2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - storage_server_1_portchannel-storage_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 192 | BC-STOLEAF2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - storage_server_1_portchannel-storage_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 193 | BC-STOLEAF2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel5 - storage_server_2_portchannel-storage_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 194 | BC-STOLEAF2 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel6 - storage_server_2_portchannel-storage_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 195 | BC-STOLEAF3 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel12 - MLAG_PEER_BC-STOLEAF4_Po12 | PASS |  |
| 196 | BC-STOLEAF3 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - storage_server_1_portchannel-storage_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 197 | BC-STOLEAF3 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - storage_server_1_portchannel-storage_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 198 | BC-STOLEAF4 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel12 - MLAG_PEER_BC-STOLEAF3_Po12 | PASS |  |
| 199 | BC-STOLEAF4 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel3 - storage_server_1_portchannel-storage_zoneA | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 200 | BC-STOLEAF4 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel4 - storage_server_1_portchannel-storage_zoneB | FAIL | interface status: down - line protocol status: lowerLayerDown |
| 201 | BC-BORDERLEAF1 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4093 - MLAG_PEER_L3_PEERING | PASS |  |
| 202 | BC-BORDERLEAF1 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS |  |
| 203 | BC-BORDERLEAF2 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4093 - MLAG_PEER_L3_PEERING | PASS |  |
| 204 | BC-BORDERLEAF2 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS |  |
| 205 | BC-DATALEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4093 - MLAG_PEER_L3_PEERING | PASS |  |
| 206 | BC-DATALEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS |  |
| 207 | BC-DATALEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan110 - BC_BLUE_ZONE_A_1 | PASS |  |
| 208 | BC-DATALEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan111 - BC_BLUE_ZONE_A_2 | PASS |  |
| 209 | BC-DATALEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan112 - BC_BLUE_ZONE_A_3 | PASS |  |
| 210 | BC-DATALEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3009 - MLAG_PEER_L3_iBGP: vrf BC_BLUE_ZONE_A | PASS |  |
| 211 | BC-DATALEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan120 - BC_BLUE_ZONE_B_1 | PASS |  |
| 212 | BC-DATALEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan121 - BC_BLUE_ZONE_B_2 | PASS |  |
| 213 | BC-DATALEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3010 - MLAG_PEER_L3_iBGP: vrf BC_BLUE_ZONE_B | PASS |  |
| 214 | BC-DATALEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan210 - BC_RED_ZONE_A_1 | PASS |  |
| 215 | BC-DATALEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan211 - BC_RED_ZONE_A_2 | PASS |  |
| 216 | BC-DATALEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3019 - MLAG_PEER_L3_iBGP: vrf BC_RED_ZONE_A | PASS |  |
| 217 | BC-DATALEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan250 - BC_RED_ZONE_B_1 | PASS |  |
| 218 | BC-DATALEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan251 - BC_RED_ZONE_B_2 | PASS |  |
| 219 | BC-DATALEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3020 - MLAG_PEER_L3_iBGP: vrf BC_RED_ZONE_B | PASS |  |
| 220 | BC-DATALEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4093 - MLAG_PEER_L3_PEERING | PASS |  |
| 221 | BC-DATALEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS |  |
| 222 | BC-DATALEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan110 - BC_BLUE_ZONE_A_1 | PASS |  |
| 223 | BC-DATALEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan111 - BC_BLUE_ZONE_A_2 | PASS |  |
| 224 | BC-DATALEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan112 - BC_BLUE_ZONE_A_3 | PASS |  |
| 225 | BC-DATALEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3009 - MLAG_PEER_L3_iBGP: vrf BC_BLUE_ZONE_A | PASS |  |
| 226 | BC-DATALEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan120 - BC_BLUE_ZONE_B_1 | PASS |  |
| 227 | BC-DATALEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan121 - BC_BLUE_ZONE_B_2 | PASS |  |
| 228 | BC-DATALEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3010 - MLAG_PEER_L3_iBGP: vrf BC_BLUE_ZONE_B | PASS |  |
| 229 | BC-DATALEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan210 - BC_RED_ZONE_A_1 | PASS |  |
| 230 | BC-DATALEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan211 - BC_RED_ZONE_A_2 | PASS |  |
| 231 | BC-DATALEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3019 - MLAG_PEER_L3_iBGP: vrf BC_RED_ZONE_A | PASS |  |
| 232 | BC-DATALEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan250 - BC_RED_ZONE_B_1 | PASS |  |
| 233 | BC-DATALEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan251 - BC_RED_ZONE_B_2 | PASS |  |
| 234 | BC-DATALEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3020 - MLAG_PEER_L3_iBGP: vrf BC_RED_ZONE_B | PASS |  |
| 235 | BC-DATALEAF5 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4093 - MLAG_PEER_L3_PEERING | PASS |  |
| 236 | BC-DATALEAF5 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS |  |
| 237 | BC-DATALEAF5 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan110 - BC_BLUE_ZONE_A_1 | PASS |  |
| 238 | BC-DATALEAF5 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan111 - BC_BLUE_ZONE_A_2 | PASS |  |
| 239 | BC-DATALEAF5 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan112 - BC_BLUE_ZONE_A_3 | PASS |  |
| 240 | BC-DATALEAF5 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3009 - MLAG_PEER_L3_iBGP: vrf BC_BLUE_ZONE_A | PASS |  |
| 241 | BC-DATALEAF5 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan120 - BC_BLUE_ZONE_B_1 | PASS |  |
| 242 | BC-DATALEAF5 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan121 - BC_BLUE_ZONE_B_2 | PASS |  |
| 243 | BC-DATALEAF5 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3010 - MLAG_PEER_L3_iBGP: vrf BC_BLUE_ZONE_B | PASS |  |
| 244 | BC-DATALEAF5 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan210 - BC_RED_ZONE_A_1 | PASS |  |
| 245 | BC-DATALEAF5 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan211 - BC_RED_ZONE_A_2 | PASS |  |
| 246 | BC-DATALEAF5 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3019 - MLAG_PEER_L3_iBGP: vrf BC_RED_ZONE_A | PASS |  |
| 247 | BC-DATALEAF5 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan250 - BC_RED_ZONE_B_1 | PASS |  |
| 248 | BC-DATALEAF5 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan251 - BC_RED_ZONE_B_2 | PASS |  |
| 249 | BC-DATALEAF5 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3020 - MLAG_PEER_L3_iBGP: vrf BC_RED_ZONE_B | PASS |  |
| 250 | BC-DATALEAF6 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4093 - MLAG_PEER_L3_PEERING | PASS |  |
| 251 | BC-DATALEAF6 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS |  |
| 252 | BC-DATALEAF6 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan110 - BC_BLUE_ZONE_A_1 | PASS |  |
| 253 | BC-DATALEAF6 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan111 - BC_BLUE_ZONE_A_2 | PASS |  |
| 254 | BC-DATALEAF6 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan112 - BC_BLUE_ZONE_A_3 | PASS |  |
| 255 | BC-DATALEAF6 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3009 - MLAG_PEER_L3_iBGP: vrf BC_BLUE_ZONE_A | PASS |  |
| 256 | BC-DATALEAF6 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan120 - BC_BLUE_ZONE_B_1 | PASS |  |
| 257 | BC-DATALEAF6 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan121 - BC_BLUE_ZONE_B_2 | PASS |  |
| 258 | BC-DATALEAF6 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3010 - MLAG_PEER_L3_iBGP: vrf BC_BLUE_ZONE_B | PASS |  |
| 259 | BC-DATALEAF6 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan210 - BC_RED_ZONE_A_1 | PASS |  |
| 260 | BC-DATALEAF6 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan211 - BC_RED_ZONE_A_2 | PASS |  |
| 261 | BC-DATALEAF6 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3019 - MLAG_PEER_L3_iBGP: vrf BC_RED_ZONE_A | PASS |  |
| 262 | BC-DATALEAF6 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan250 - BC_RED_ZONE_B_1 | PASS |  |
| 263 | BC-DATALEAF6 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan251 - BC_RED_ZONE_B_2 | PASS |  |
| 264 | BC-DATALEAF6 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3020 - MLAG_PEER_L3_iBGP: vrf BC_RED_ZONE_B | PASS |  |
| 265 | BC-OOBM1 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS |  |
| 266 | BC-OOBM2 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS |  |
| 267 | BC-STOLEAF1 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4093 - MLAG_PEER_L3_PEERING | PASS |  |
| 268 | BC-STOLEAF1 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS |  |
| 269 | BC-STOLEAF1 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan310 - BC_STO_ZONE_A_1 | PASS |  |
| 270 | BC-STOLEAF1 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan311 - BC_STO_ZONE_A_2 | PASS |  |
| 271 | BC-STOLEAF1 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3029 - MLAG_PEER_L3_iBGP: vrf BC_STO_ZONE_A | PASS |  |
| 272 | BC-STOLEAF1 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan350 - BC_STO_ZONE_B_1 | PASS |  |
| 273 | BC-STOLEAF1 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan351 - BC_STO_ZONE_B_2 | PASS |  |
| 274 | BC-STOLEAF1 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3030 - MLAG_PEER_L3_iBGP: vrf BC_STO_ZONE_B | PASS |  |
| 275 | BC-STOLEAF2 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4093 - MLAG_PEER_L3_PEERING | PASS |  |
| 276 | BC-STOLEAF2 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS |  |
| 277 | BC-STOLEAF2 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan310 - BC_STO_ZONE_A_1 | PASS |  |
| 278 | BC-STOLEAF2 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan311 - BC_STO_ZONE_A_2 | PASS |  |
| 279 | BC-STOLEAF2 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3029 - MLAG_PEER_L3_iBGP: vrf BC_STO_ZONE_A | PASS |  |
| 280 | BC-STOLEAF2 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan350 - BC_STO_ZONE_B_1 | PASS |  |
| 281 | BC-STOLEAF2 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan351 - BC_STO_ZONE_B_2 | PASS |  |
| 282 | BC-STOLEAF2 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3030 - MLAG_PEER_L3_iBGP: vrf BC_STO_ZONE_B | PASS |  |
| 283 | BC-STOLEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4093 - MLAG_PEER_L3_PEERING | PASS |  |
| 284 | BC-STOLEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS |  |
| 285 | BC-STOLEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan110 - BC_BLUE_ZONE_A_1 | PASS |  |
| 286 | BC-STOLEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3009 - MLAG_PEER_L3_iBGP: vrf BC_BLUE_ZONE_A | PASS |  |
| 287 | BC-STOLEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan310 - BC_STO_ZONE_A_1 | PASS |  |
| 288 | BC-STOLEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan311 - BC_STO_ZONE_A_2 | PASS |  |
| 289 | BC-STOLEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3029 - MLAG_PEER_L3_iBGP: vrf BC_STO_ZONE_A | PASS |  |
| 290 | BC-STOLEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan350 - BC_STO_ZONE_B_1 | PASS |  |
| 291 | BC-STOLEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan351 - BC_STO_ZONE_B_2 | PASS |  |
| 292 | BC-STOLEAF3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3030 - MLAG_PEER_L3_iBGP: vrf BC_STO_ZONE_B | PASS |  |
| 293 | BC-STOLEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4093 - MLAG_PEER_L3_PEERING | PASS |  |
| 294 | BC-STOLEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS |  |
| 295 | BC-STOLEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan110 - BC_BLUE_ZONE_A_1 | PASS |  |
| 296 | BC-STOLEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3009 - MLAG_PEER_L3_iBGP: vrf BC_BLUE_ZONE_A | PASS |  |
| 297 | BC-STOLEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan310 - BC_STO_ZONE_A_1 | PASS |  |
| 298 | BC-STOLEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan311 - BC_STO_ZONE_A_2 | PASS |  |
| 299 | BC-STOLEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3029 - MLAG_PEER_L3_iBGP: vrf BC_STO_ZONE_A | PASS |  |
| 300 | BC-STOLEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan350 - BC_STO_ZONE_B_1 | PASS |  |
| 301 | BC-STOLEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan351 - BC_STO_ZONE_B_2 | PASS |  |
| 302 | BC-STOLEAF4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan3030 - MLAG_PEER_L3_iBGP: vrf BC_STO_ZONE_B | PASS |  |
| 303 | BC-BORDERLEAF1 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS |  |
| 304 | BC-BORDERLEAF2 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS |  |
| 305 | BC-DATALEAF3 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS |  |
| 306 | BC-DATALEAF4 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS |  |
| 307 | BC-DATALEAF5 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS |  |
| 308 | BC-DATALEAF6 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS |  |
| 309 | BC-STOLEAF1 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS |  |
| 310 | BC-STOLEAF2 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS |  |
| 311 | BC-STOLEAF3 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS |  |
| 312 | BC-STOLEAF4 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS |  |
| 313 | BC-BORDERLEAF1 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 314 | BC-BORDERLEAF1 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS |  |
| 315 | BC-BORDERLEAF2 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 316 | BC-BORDERLEAF2 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS |  |
| 317 | BC-DATALEAF3 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 318 | BC-DATALEAF3 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS |  |
| 319 | BC-DATALEAF3 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback100 - BC_BLUE_ZONE_A_VTEP_DIAGNOSTICS | PASS |  |
| 320 | BC-DATALEAF4 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 321 | BC-DATALEAF4 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS |  |
| 322 | BC-DATALEAF4 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback100 - BC_BLUE_ZONE_A_VTEP_DIAGNOSTICS | PASS |  |
| 323 | BC-DATALEAF5 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 324 | BC-DATALEAF5 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS |  |
| 325 | BC-DATALEAF5 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback100 - BC_BLUE_ZONE_A_VTEP_DIAGNOSTICS | PASS |  |
| 326 | BC-DATALEAF6 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 327 | BC-DATALEAF6 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS |  |
| 328 | BC-DATALEAF6 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback100 - BC_BLUE_ZONE_A_VTEP_DIAGNOSTICS | PASS |  |
| 329 | BC-SPINE1 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 330 | BC-SPINE2 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 331 | BC-STOLEAF1 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 332 | BC-STOLEAF1 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS |  |
| 333 | BC-STOLEAF2 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 334 | BC-STOLEAF2 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS |  |
| 335 | BC-STOLEAF3 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 336 | BC-STOLEAF3 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS |  |
| 337 | BC-STOLEAF3 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback100 - BC_BLUE_ZONE_A_VTEP_DIAGNOSTICS | PASS |  |
| 338 | BC-STOLEAF4 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS |  |
| 339 | BC-STOLEAF4 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS |  |
| 340 | BC-STOLEAF4 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback100 - BC_BLUE_ZONE_A_VTEP_DIAGNOSTICS | PASS |  |
| 341 | BC-BORDERLEAF1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet12 - remote: BC-BORDERLEAF2_Ethernet12 | PASS |  |
| 342 | BC-BORDERLEAF1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet13 - remote: BC-BORDERLEAF2_Ethernet13 | PASS |  |
| 343 | BC-BORDERLEAF1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: BC-SPINE1_Ethernet1 | PASS |  |
| 344 | BC-BORDERLEAF1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: BC-SPINE2_Ethernet1 | PASS |  |
| 345 | BC-BORDERLEAF2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet12 - remote: BC-BORDERLEAF1_Ethernet12 | PASS |  |
| 346 | BC-BORDERLEAF2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet13 - remote: BC-BORDERLEAF1_Ethernet13 | PASS |  |
| 347 | BC-BORDERLEAF2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: BC-SPINE1_Ethernet2 | PASS |  |
| 348 | BC-BORDERLEAF2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: BC-SPINE2_Ethernet2 | PASS |  |
| 349 | BC-DATALEAF3 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet12 - remote: BC-DATALEAF4_Ethernet12 | PASS |  |
| 350 | BC-DATALEAF3 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet13 - remote: BC-DATALEAF4_Ethernet13 | PASS |  |
| 351 | BC-DATALEAF3 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: BC-SPINE1_Ethernet3 | PASS |  |
| 352 | BC-DATALEAF3 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: BC-SPINE2_Ethernet3 | PASS |  |
| 353 | BC-DATALEAF4 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet12 - remote: BC-DATALEAF3_Ethernet12 | PASS |  |
| 354 | BC-DATALEAF4 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet13 - remote: BC-DATALEAF3_Ethernet13 | PASS |  |
| 355 | BC-DATALEAF4 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: BC-SPINE1_Ethernet4 | PASS |  |
| 356 | BC-DATALEAF4 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: BC-SPINE2_Ethernet4 | PASS |  |
| 357 | BC-DATALEAF5 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet12 - remote: BC-DATALEAF6_Ethernet12 | PASS |  |
| 358 | BC-DATALEAF5 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet13 - remote: BC-DATALEAF6_Ethernet13 | PASS |  |
| 359 | BC-DATALEAF5 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: BC-SPINE1_Ethernet5 | PASS |  |
| 360 | BC-DATALEAF5 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: BC-SPINE2_Ethernet5 | PASS |  |
| 361 | BC-DATALEAF6 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet12 - remote: BC-DATALEAF5_Ethernet12 | PASS |  |
| 362 | BC-DATALEAF6 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet13 - remote: BC-DATALEAF5_Ethernet13 | PASS |  |
| 363 | BC-DATALEAF6 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: BC-SPINE1_Ethernet6 | PASS |  |
| 364 | BC-DATALEAF6 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: BC-SPINE2_Ethernet6 | PASS |  |
| 365 | BC-OOBM1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet16 - remote: BC-OOBM2_Ethernet16 | PASS |  |
| 366 | BC-OOBM1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet17 - remote: BC-OOBM2_Ethernet17 | PASS |  |
| 367 | BC-OOBM2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet16 - remote: BC-OOBM1_Ethernet16 | PASS |  |
| 368 | BC-OOBM2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet17 - remote: BC-OOBM1_Ethernet17 | PASS |  |
| 369 | BC-SPINE1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: BC-BORDERLEAF1_Ethernet1 | PASS |  |
| 370 | BC-SPINE1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: BC-BORDERLEAF2_Ethernet1 | PASS |  |
| 371 | BC-SPINE1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet3 - remote: BC-DATALEAF3_Ethernet1 | PASS |  |
| 372 | BC-SPINE1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet4 - remote: BC-DATALEAF4_Ethernet1 | PASS |  |
| 373 | BC-SPINE1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet5 - remote: BC-DATALEAF5_Ethernet1 | PASS |  |
| 374 | BC-SPINE1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet6 - remote: BC-DATALEAF6_Ethernet1 | PASS |  |
| 375 | BC-SPINE1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet7 - remote: BC-STOLEAF1_Ethernet1 | PASS |  |
| 376 | BC-SPINE1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet8 - remote: BC-STOLEAF2_Ethernet1 | PASS |  |
| 377 | BC-SPINE1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet9 - remote: BC-STOLEAF3_Ethernet1 | PASS |  |
| 378 | BC-SPINE1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet10 - remote: BC-STOLEAF4_Ethernet1 | PASS |  |
| 379 | BC-SPINE2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: BC-BORDERLEAF1_Ethernet2 | PASS |  |
| 380 | BC-SPINE2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: BC-BORDERLEAF2_Ethernet2 | PASS |  |
| 381 | BC-SPINE2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet3 - remote: BC-DATALEAF3_Ethernet2 | PASS |  |
| 382 | BC-SPINE2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet4 - remote: BC-DATALEAF4_Ethernet2 | PASS |  |
| 383 | BC-SPINE2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet5 - remote: BC-DATALEAF5_Ethernet2 | PASS |  |
| 384 | BC-SPINE2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet6 - remote: BC-DATALEAF6_Ethernet2 | PASS |  |
| 385 | BC-SPINE2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet7 - remote: BC-STOLEAF1_Ethernet2 | PASS |  |
| 386 | BC-SPINE2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet8 - remote: BC-STOLEAF2_Ethernet2 | PASS |  |
| 387 | BC-SPINE2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet9 - remote: BC-STOLEAF3_Ethernet2 | PASS |  |
| 388 | BC-SPINE2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet10 - remote: BC-STOLEAF4_Ethernet2 | PASS |  |
| 389 | BC-STOLEAF1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet12 - remote: BC-STOLEAF2_Ethernet12 | PASS |  |
| 390 | BC-STOLEAF1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet13 - remote: BC-STOLEAF2_Ethernet13 | PASS |  |
| 391 | BC-STOLEAF1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: BC-SPINE1_Ethernet7 | PASS |  |
| 392 | BC-STOLEAF1 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: BC-SPINE2_Ethernet7 | PASS |  |
| 393 | BC-STOLEAF2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet12 - remote: BC-STOLEAF1_Ethernet12 | PASS |  |
| 394 | BC-STOLEAF2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet13 - remote: BC-STOLEAF1_Ethernet13 | PASS |  |
| 395 | BC-STOLEAF2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: BC-SPINE1_Ethernet8 | PASS |  |
| 396 | BC-STOLEAF2 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: BC-SPINE2_Ethernet8 | PASS |  |
| 397 | BC-STOLEAF3 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet12 - remote: BC-STOLEAF4_Ethernet12 | PASS |  |
| 398 | BC-STOLEAF3 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet13 - remote: BC-STOLEAF4_Ethernet13 | PASS |  |
| 399 | BC-STOLEAF3 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: BC-SPINE1_Ethernet9 | PASS |  |
| 400 | BC-STOLEAF3 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: BC-SPINE2_Ethernet9 | PASS |  |
| 401 | BC-STOLEAF4 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet12 - remote: BC-STOLEAF3_Ethernet12 | PASS |  |
| 402 | BC-STOLEAF4 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet13 - remote: BC-STOLEAF3_Ethernet13 | PASS |  |
| 403 | BC-STOLEAF4 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet1 - remote: BC-SPINE1_Ethernet10 | PASS |  |
| 404 | BC-STOLEAF4 | LLDP Topology | lldp topology - validate peer and interface | local: Ethernet2 - remote: BC-SPINE2_Ethernet10 | PASS |  |
| 405 | BC-BORDERLEAF1 | MLAG | MLAG State active & Status connected | MLAG | PASS |  |
| 406 | BC-BORDERLEAF2 | MLAG | MLAG State active & Status connected | MLAG | PASS |  |
| 407 | BC-DATALEAF3 | MLAG | MLAG State active & Status connected | MLAG | PASS |  |
| 408 | BC-DATALEAF4 | MLAG | MLAG State active & Status connected | MLAG | PASS |  |
| 409 | BC-DATALEAF5 | MLAG | MLAG State active & Status connected | MLAG | PASS |  |
| 410 | BC-DATALEAF6 | MLAG | MLAG State active & Status connected | MLAG | PASS |  |
| 411 | BC-OOBM1 | MLAG | MLAG State active & Status connected | MLAG | PASS |  |
| 412 | BC-OOBM2 | MLAG | MLAG State active & Status connected | MLAG | PASS |  |
| 413 | BC-STOLEAF1 | MLAG | MLAG State active & Status connected | MLAG | PASS |  |
| 414 | BC-STOLEAF2 | MLAG | MLAG State active & Status connected | MLAG | PASS |  |
| 415 | BC-STOLEAF3 | MLAG | MLAG State active & Status connected | MLAG | PASS |  |
| 416 | BC-STOLEAF4 | MLAG | MLAG State active & Status connected | MLAG | PASS |  |
| 417 | BC-BORDERLEAF1 | IP Reachability | ip reachability test p2p links | Source: BC-BORDERLEAF1_Ethernet1 - Destination: BC-SPINE1_Ethernet1 | PASS |  |
| 418 | BC-BORDERLEAF1 | IP Reachability | ip reachability test p2p links | Source: BC-BORDERLEAF1_Ethernet2 - Destination: BC-SPINE2_Ethernet1 | PASS |  |
| 419 | BC-BORDERLEAF2 | IP Reachability | ip reachability test p2p links | Source: BC-BORDERLEAF2_Ethernet1 - Destination: BC-SPINE1_Ethernet2 | PASS |  |
| 420 | BC-BORDERLEAF2 | IP Reachability | ip reachability test p2p links | Source: BC-BORDERLEAF2_Ethernet2 - Destination: BC-SPINE2_Ethernet2 | PASS |  |
| 421 | BC-DATALEAF3 | IP Reachability | ip reachability test p2p links | Source: BC-DATALEAF3_Ethernet1 - Destination: BC-SPINE1_Ethernet3 | PASS |  |
| 422 | BC-DATALEAF3 | IP Reachability | ip reachability test p2p links | Source: BC-DATALEAF3_Ethernet2 - Destination: BC-SPINE2_Ethernet3 | PASS |  |
| 423 | BC-DATALEAF4 | IP Reachability | ip reachability test p2p links | Source: BC-DATALEAF4_Ethernet1 - Destination: BC-SPINE1_Ethernet4 | PASS |  |
| 424 | BC-DATALEAF4 | IP Reachability | ip reachability test p2p links | Source: BC-DATALEAF4_Ethernet2 - Destination: BC-SPINE2_Ethernet4 | PASS |  |
| 425 | BC-DATALEAF5 | IP Reachability | ip reachability test p2p links | Source: BC-DATALEAF5_Ethernet1 - Destination: BC-SPINE1_Ethernet5 | PASS |  |
| 426 | BC-DATALEAF5 | IP Reachability | ip reachability test p2p links | Source: BC-DATALEAF5_Ethernet2 - Destination: BC-SPINE2_Ethernet5 | PASS |  |
| 427 | BC-DATALEAF6 | IP Reachability | ip reachability test p2p links | Source: BC-DATALEAF6_Ethernet1 - Destination: BC-SPINE1_Ethernet6 | PASS |  |
| 428 | BC-DATALEAF6 | IP Reachability | ip reachability test p2p links | Source: BC-DATALEAF6_Ethernet2 - Destination: BC-SPINE2_Ethernet6 | PASS |  |
| 429 | BC-SPINE1 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE1_Ethernet1 - Destination: BC-BORDERLEAF1_Ethernet1 | PASS |  |
| 430 | BC-SPINE1 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE1_Ethernet2 - Destination: BC-BORDERLEAF2_Ethernet1 | PASS |  |
| 431 | BC-SPINE1 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE1_Ethernet3 - Destination: BC-DATALEAF3_Ethernet1 | PASS |  |
| 432 | BC-SPINE1 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE1_Ethernet4 - Destination: BC-DATALEAF4_Ethernet1 | PASS |  |
| 433 | BC-SPINE1 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE1_Ethernet5 - Destination: BC-DATALEAF5_Ethernet1 | PASS |  |
| 434 | BC-SPINE1 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE1_Ethernet6 - Destination: BC-DATALEAF6_Ethernet1 | PASS |  |
| 435 | BC-SPINE1 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE1_Ethernet7 - Destination: BC-STOLEAF1_Ethernet1 | PASS |  |
| 436 | BC-SPINE1 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE1_Ethernet8 - Destination: BC-STOLEAF2_Ethernet1 | PASS |  |
| 437 | BC-SPINE1 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE1_Ethernet9 - Destination: BC-STOLEAF3_Ethernet1 | PASS |  |
| 438 | BC-SPINE1 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE1_Ethernet10 - Destination: BC-STOLEAF4_Ethernet1 | PASS |  |
| 439 | BC-SPINE2 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE2_Ethernet1 - Destination: BC-BORDERLEAF1_Ethernet2 | PASS |  |
| 440 | BC-SPINE2 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE2_Ethernet2 - Destination: BC-BORDERLEAF2_Ethernet2 | PASS |  |
| 441 | BC-SPINE2 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE2_Ethernet3 - Destination: BC-DATALEAF3_Ethernet2 | PASS |  |
| 442 | BC-SPINE2 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE2_Ethernet4 - Destination: BC-DATALEAF4_Ethernet2 | PASS |  |
| 443 | BC-SPINE2 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE2_Ethernet5 - Destination: BC-DATALEAF5_Ethernet2 | PASS |  |
| 444 | BC-SPINE2 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE2_Ethernet6 - Destination: BC-DATALEAF6_Ethernet2 | PASS |  |
| 445 | BC-SPINE2 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE2_Ethernet7 - Destination: BC-STOLEAF1_Ethernet2 | PASS |  |
| 446 | BC-SPINE2 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE2_Ethernet8 - Destination: BC-STOLEAF2_Ethernet2 | PASS |  |
| 447 | BC-SPINE2 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE2_Ethernet9 - Destination: BC-STOLEAF3_Ethernet2 | PASS |  |
| 448 | BC-SPINE2 | IP Reachability | ip reachability test p2p links | Source: BC-SPINE2_Ethernet10 - Destination: BC-STOLEAF4_Ethernet2 | PASS |  |
| 449 | BC-STOLEAF1 | IP Reachability | ip reachability test p2p links | Source: BC-STOLEAF1_Ethernet1 - Destination: BC-SPINE1_Ethernet7 | PASS |  |
| 450 | BC-STOLEAF1 | IP Reachability | ip reachability test p2p links | Source: BC-STOLEAF1_Ethernet2 - Destination: BC-SPINE2_Ethernet7 | PASS |  |
| 451 | BC-STOLEAF2 | IP Reachability | ip reachability test p2p links | Source: BC-STOLEAF2_Ethernet1 - Destination: BC-SPINE1_Ethernet8 | PASS |  |
| 452 | BC-STOLEAF2 | IP Reachability | ip reachability test p2p links | Source: BC-STOLEAF2_Ethernet2 - Destination: BC-SPINE2_Ethernet8 | PASS |  |
| 453 | BC-STOLEAF3 | IP Reachability | ip reachability test p2p links | Source: BC-STOLEAF3_Ethernet1 - Destination: BC-SPINE1_Ethernet9 | PASS |  |
| 454 | BC-STOLEAF3 | IP Reachability | ip reachability test p2p links | Source: BC-STOLEAF3_Ethernet2 - Destination: BC-SPINE2_Ethernet9 | PASS |  |
| 455 | BC-STOLEAF4 | IP Reachability | ip reachability test p2p links | Source: BC-STOLEAF4_Ethernet1 - Destination: BC-SPINE1_Ethernet10 | PASS |  |
| 456 | BC-STOLEAF4 | IP Reachability | ip reachability test p2p links | Source: BC-STOLEAF4_Ethernet2 - Destination: BC-SPINE2_Ethernet10 | PASS |  |
| 457 | BC-BORDERLEAF1 | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 458 | BC-BORDERLEAF2 | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 459 | BC-DATALEAF3 | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 460 | BC-DATALEAF4 | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 461 | BC-DATALEAF5 | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 462 | BC-DATALEAF6 | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 463 | BC-SPINE1 | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 464 | BC-SPINE2 | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 465 | BC-STOLEAF1 | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 466 | BC-STOLEAF2 | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 467 | BC-STOLEAF3 | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 468 | BC-STOLEAF4 | BGP | ArBGP is configured and operating | ArBGP | PASS |  |
| 469 | BC-BORDERLEAF1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.255.251.1 | PASS |  |
| 470 | BC-BORDERLEAF1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.0 | PASS |  |
| 471 | BC-BORDERLEAF1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.2 | PASS |  |
| 472 | BC-BORDERLEAF2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.255.251.0 | PASS |  |
| 473 | BC-BORDERLEAF2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.4 | PASS |  |
| 474 | BC-BORDERLEAF2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.6 | PASS |  |
| 475 | BC-DATALEAF3 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.255.251.5 | PASS |  |
| 476 | BC-DATALEAF3 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.8 | PASS |  |
| 477 | BC-DATALEAF3 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.10 | PASS |  |
| 478 | BC-DATALEAF4 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.255.251.4 | PASS |  |
| 479 | BC-DATALEAF4 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.12 | PASS |  |
| 480 | BC-DATALEAF4 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.14 | PASS |  |
| 481 | BC-DATALEAF5 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.255.251.9 | PASS |  |
| 482 | BC-DATALEAF5 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.16 | PASS |  |
| 483 | BC-DATALEAF5 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.18 | PASS |  |
| 484 | BC-DATALEAF6 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.255.251.8 | PASS |  |
| 485 | BC-DATALEAF6 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.20 | PASS |  |
| 486 | BC-DATALEAF6 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.22 | PASS |  |
| 487 | BC-SPINE1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.1 | PASS |  |
| 488 | BC-SPINE1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.5 | PASS |  |
| 489 | BC-SPINE1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.9 | PASS |  |
| 490 | BC-SPINE1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.13 | PASS |  |
| 491 | BC-SPINE1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.17 | PASS |  |
| 492 | BC-SPINE1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.21 | PASS |  |
| 493 | BC-SPINE1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.25 | PASS |  |
| 494 | BC-SPINE1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.29 | PASS |  |
| 495 | BC-SPINE1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.33 | PASS |  |
| 496 | BC-SPINE1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.37 | PASS |  |
| 497 | BC-SPINE2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.3 | PASS |  |
| 498 | BC-SPINE2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.7 | PASS |  |
| 499 | BC-SPINE2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.11 | PASS |  |
| 500 | BC-SPINE2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.15 | PASS |  |
| 501 | BC-SPINE2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.19 | PASS |  |
| 502 | BC-SPINE2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.23 | PASS |  |
| 503 | BC-SPINE2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.27 | PASS |  |
| 504 | BC-SPINE2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.31 | PASS |  |
| 505 | BC-SPINE2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.35 | PASS |  |
| 506 | BC-SPINE2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.39 | PASS |  |
| 507 | BC-STOLEAF1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.255.251.13 | PASS |  |
| 508 | BC-STOLEAF1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.24 | PASS |  |
| 509 | BC-STOLEAF1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.26 | PASS |  |
| 510 | BC-STOLEAF2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.255.251.12 | PASS |  |
| 511 | BC-STOLEAF2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.28 | PASS |  |
| 512 | BC-STOLEAF2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.30 | PASS |  |
| 513 | BC-STOLEAF3 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.255.251.17 | PASS |  |
| 514 | BC-STOLEAF3 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.32 | PASS |  |
| 515 | BC-STOLEAF3 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.34 | PASS |  |
| 516 | BC-STOLEAF4 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 10.255.251.16 | PASS |  |
| 517 | BC-STOLEAF4 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.36 | PASS |  |
| 518 | BC-STOLEAF4 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.38 | PASS |  |
| 519 | BC-BORDERLEAF1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.1 | PASS |  |
| 520 | BC-BORDERLEAF1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.2 | PASS |  |
| 521 | BC-BORDERLEAF2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.1 | PASS |  |
| 522 | BC-BORDERLEAF2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.2 | PASS |  |
| 523 | BC-DATALEAF3 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.1 | PASS |  |
| 524 | BC-DATALEAF3 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.2 | PASS |  |
| 525 | BC-DATALEAF4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.1 | PASS |  |
| 526 | BC-DATALEAF4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.2 | PASS |  |
| 527 | BC-DATALEAF5 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.1 | PASS |  |
| 528 | BC-DATALEAF5 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.2 | PASS |  |
| 529 | BC-DATALEAF6 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.1 | PASS |  |
| 530 | BC-DATALEAF6 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.2 | PASS |  |
| 531 | BC-SPINE1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.1 | PASS |  |
| 532 | BC-SPINE1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.2 | PASS |  |
| 533 | BC-SPINE1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.3 | PASS |  |
| 534 | BC-SPINE1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.4 | PASS |  |
| 535 | BC-SPINE1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.5 | PASS |  |
| 536 | BC-SPINE1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.6 | PASS |  |
| 537 | BC-SPINE1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.7 | PASS |  |
| 538 | BC-SPINE1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.8 | PASS |  |
| 539 | BC-SPINE1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.9 | PASS |  |
| 540 | BC-SPINE1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.10 | PASS |  |
| 541 | BC-SPINE2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.1 | PASS |  |
| 542 | BC-SPINE2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.2 | PASS |  |
| 543 | BC-SPINE2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.3 | PASS |  |
| 544 | BC-SPINE2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.4 | PASS |  |
| 545 | BC-SPINE2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.5 | PASS |  |
| 546 | BC-SPINE2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.6 | PASS |  |
| 547 | BC-SPINE2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.7 | PASS |  |
| 548 | BC-SPINE2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.8 | PASS |  |
| 549 | BC-SPINE2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.9 | PASS |  |
| 550 | BC-SPINE2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.1.10 | PASS |  |
| 551 | BC-STOLEAF1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.1 | PASS |  |
| 552 | BC-STOLEAF1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.2 | PASS |  |
| 553 | BC-STOLEAF2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.1 | PASS |  |
| 554 | BC-STOLEAF2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.2 | PASS |  |
| 555 | BC-STOLEAF3 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.1 | PASS |  |
| 556 | BC-STOLEAF3 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.2 | PASS |  |
| 557 | BC-STOLEAF4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.1 | PASS |  |
| 558 | BC-STOLEAF4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 10.200.0.2 | PASS |  |
| 559 | BC-BORDERLEAF1 | Routing Table | Remote Lo1 address | 192.168.254.1 | PASS |  |
| 560 | BC-BORDERLEAF1 | Routing Table | Remote Lo1 address | 192.168.254.3 | PASS |  |
| 561 | BC-BORDERLEAF1 | Routing Table | Remote Lo1 address | 192.168.254.5 | PASS |  |
| 562 | BC-BORDERLEAF1 | Routing Table | Remote Lo1 address | 192.168.254.7 | PASS |  |
| 563 | BC-BORDERLEAF1 | Routing Table | Remote Lo1 address | 192.168.254.9 | PASS |  |
| 564 | BC-BORDERLEAF2 | Routing Table | Remote Lo1 address | 192.168.254.1 | PASS |  |
| 565 | BC-BORDERLEAF2 | Routing Table | Remote Lo1 address | 192.168.254.3 | PASS |  |
| 566 | BC-BORDERLEAF2 | Routing Table | Remote Lo1 address | 192.168.254.5 | PASS |  |
| 567 | BC-BORDERLEAF2 | Routing Table | Remote Lo1 address | 192.168.254.7 | PASS |  |
| 568 | BC-BORDERLEAF2 | Routing Table | Remote Lo1 address | 192.168.254.9 | PASS |  |
| 569 | BC-DATALEAF3 | Routing Table | Remote Lo1 address | 192.168.254.1 | PASS |  |
| 570 | BC-DATALEAF3 | Routing Table | Remote Lo1 address | 192.168.254.3 | PASS |  |
| 571 | BC-DATALEAF3 | Routing Table | Remote Lo1 address | 192.168.254.5 | PASS |  |
| 572 | BC-DATALEAF3 | Routing Table | Remote Lo1 address | 192.168.254.7 | PASS |  |
| 573 | BC-DATALEAF3 | Routing Table | Remote Lo1 address | 192.168.254.9 | PASS |  |
| 574 | BC-DATALEAF4 | Routing Table | Remote Lo1 address | 192.168.254.1 | PASS |  |
| 575 | BC-DATALEAF4 | Routing Table | Remote Lo1 address | 192.168.254.3 | PASS |  |
| 576 | BC-DATALEAF4 | Routing Table | Remote Lo1 address | 192.168.254.5 | PASS |  |
| 577 | BC-DATALEAF4 | Routing Table | Remote Lo1 address | 192.168.254.7 | PASS |  |
| 578 | BC-DATALEAF4 | Routing Table | Remote Lo1 address | 192.168.254.9 | PASS |  |
| 579 | BC-DATALEAF5 | Routing Table | Remote Lo1 address | 192.168.254.1 | PASS |  |
| 580 | BC-DATALEAF5 | Routing Table | Remote Lo1 address | 192.168.254.3 | PASS |  |
| 581 | BC-DATALEAF5 | Routing Table | Remote Lo1 address | 192.168.254.5 | PASS |  |
| 582 | BC-DATALEAF5 | Routing Table | Remote Lo1 address | 192.168.254.7 | PASS |  |
| 583 | BC-DATALEAF5 | Routing Table | Remote Lo1 address | 192.168.254.9 | PASS |  |
| 584 | BC-DATALEAF6 | Routing Table | Remote Lo1 address | 192.168.254.1 | PASS |  |
| 585 | BC-DATALEAF6 | Routing Table | Remote Lo1 address | 192.168.254.3 | PASS |  |
| 586 | BC-DATALEAF6 | Routing Table | Remote Lo1 address | 192.168.254.5 | PASS |  |
| 587 | BC-DATALEAF6 | Routing Table | Remote Lo1 address | 192.168.254.7 | PASS |  |
| 588 | BC-DATALEAF6 | Routing Table | Remote Lo1 address | 192.168.254.9 | PASS |  |
| 589 | BC-STOLEAF1 | Routing Table | Remote Lo1 address | 192.168.254.1 | PASS |  |
| 590 | BC-STOLEAF1 | Routing Table | Remote Lo1 address | 192.168.254.3 | PASS |  |
| 591 | BC-STOLEAF1 | Routing Table | Remote Lo1 address | 192.168.254.5 | PASS |  |
| 592 | BC-STOLEAF1 | Routing Table | Remote Lo1 address | 192.168.254.7 | PASS |  |
| 593 | BC-STOLEAF1 | Routing Table | Remote Lo1 address | 192.168.254.9 | PASS |  |
| 594 | BC-STOLEAF2 | Routing Table | Remote Lo1 address | 192.168.254.1 | PASS |  |
| 595 | BC-STOLEAF2 | Routing Table | Remote Lo1 address | 192.168.254.3 | PASS |  |
| 596 | BC-STOLEAF2 | Routing Table | Remote Lo1 address | 192.168.254.5 | PASS |  |
| 597 | BC-STOLEAF2 | Routing Table | Remote Lo1 address | 192.168.254.7 | PASS |  |
| 598 | BC-STOLEAF2 | Routing Table | Remote Lo1 address | 192.168.254.9 | PASS |  |
| 599 | BC-STOLEAF3 | Routing Table | Remote Lo1 address | 192.168.254.1 | PASS |  |
| 600 | BC-STOLEAF3 | Routing Table | Remote Lo1 address | 192.168.254.3 | PASS |  |
| 601 | BC-STOLEAF3 | Routing Table | Remote Lo1 address | 192.168.254.5 | PASS |  |
| 602 | BC-STOLEAF3 | Routing Table | Remote Lo1 address | 192.168.254.7 | PASS |  |
| 603 | BC-STOLEAF3 | Routing Table | Remote Lo1 address | 192.168.254.9 | PASS |  |
| 604 | BC-STOLEAF4 | Routing Table | Remote Lo1 address | 192.168.254.1 | PASS |  |
| 605 | BC-STOLEAF4 | Routing Table | Remote Lo1 address | 192.168.254.3 | PASS |  |
| 606 | BC-STOLEAF4 | Routing Table | Remote Lo1 address | 192.168.254.5 | PASS |  |
| 607 | BC-STOLEAF4 | Routing Table | Remote Lo1 address | 192.168.254.7 | PASS |  |
| 608 | BC-STOLEAF4 | Routing Table | Remote Lo1 address | 192.168.254.9 | PASS |  |
| 609 | BC-BORDERLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.1 | PASS |  |
| 610 | BC-BORDERLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.2 | PASS |  |
| 611 | BC-BORDERLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.3 | PASS |  |
| 612 | BC-BORDERLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.4 | PASS |  |
| 613 | BC-BORDERLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.5 | PASS |  |
| 614 | BC-BORDERLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.6 | PASS |  |
| 615 | BC-BORDERLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.7 | PASS |  |
| 616 | BC-BORDERLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.8 | PASS |  |
| 617 | BC-BORDERLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.9 | PASS |  |
| 618 | BC-BORDERLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.10 | PASS |  |
| 619 | BC-BORDERLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.1 | PASS |  |
| 620 | BC-BORDERLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.2 | PASS |  |
| 621 | BC-BORDERLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.3 | PASS |  |
| 622 | BC-BORDERLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.4 | PASS |  |
| 623 | BC-BORDERLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.5 | PASS |  |
| 624 | BC-BORDERLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.6 | PASS |  |
| 625 | BC-BORDERLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.7 | PASS |  |
| 626 | BC-BORDERLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.8 | PASS |  |
| 627 | BC-BORDERLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.9 | PASS |  |
| 628 | BC-BORDERLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.10 | PASS |  |
| 629 | BC-DATALEAF3 | Routing Table | Remote Lo0 address | 10.200.1.1 | PASS |  |
| 630 | BC-DATALEAF3 | Routing Table | Remote Lo0 address | 10.200.1.2 | PASS |  |
| 631 | BC-DATALEAF3 | Routing Table | Remote Lo0 address | 10.200.1.3 | PASS |  |
| 632 | BC-DATALEAF3 | Routing Table | Remote Lo0 address | 10.200.1.4 | PASS |  |
| 633 | BC-DATALEAF3 | Routing Table | Remote Lo0 address | 10.200.1.5 | PASS |  |
| 634 | BC-DATALEAF3 | Routing Table | Remote Lo0 address | 10.200.1.6 | PASS |  |
| 635 | BC-DATALEAF3 | Routing Table | Remote Lo0 address | 10.200.1.7 | PASS |  |
| 636 | BC-DATALEAF3 | Routing Table | Remote Lo0 address | 10.200.1.8 | PASS |  |
| 637 | BC-DATALEAF3 | Routing Table | Remote Lo0 address | 10.200.1.9 | PASS |  |
| 638 | BC-DATALEAF3 | Routing Table | Remote Lo0 address | 10.200.1.10 | PASS |  |
| 639 | BC-DATALEAF4 | Routing Table | Remote Lo0 address | 10.200.1.1 | PASS |  |
| 640 | BC-DATALEAF4 | Routing Table | Remote Lo0 address | 10.200.1.2 | PASS |  |
| 641 | BC-DATALEAF4 | Routing Table | Remote Lo0 address | 10.200.1.3 | PASS |  |
| 642 | BC-DATALEAF4 | Routing Table | Remote Lo0 address | 10.200.1.4 | PASS |  |
| 643 | BC-DATALEAF4 | Routing Table | Remote Lo0 address | 10.200.1.5 | PASS |  |
| 644 | BC-DATALEAF4 | Routing Table | Remote Lo0 address | 10.200.1.6 | PASS |  |
| 645 | BC-DATALEAF4 | Routing Table | Remote Lo0 address | 10.200.1.7 | PASS |  |
| 646 | BC-DATALEAF4 | Routing Table | Remote Lo0 address | 10.200.1.8 | PASS |  |
| 647 | BC-DATALEAF4 | Routing Table | Remote Lo0 address | 10.200.1.9 | PASS |  |
| 648 | BC-DATALEAF4 | Routing Table | Remote Lo0 address | 10.200.1.10 | PASS |  |
| 649 | BC-DATALEAF5 | Routing Table | Remote Lo0 address | 10.200.1.1 | PASS |  |
| 650 | BC-DATALEAF5 | Routing Table | Remote Lo0 address | 10.200.1.2 | PASS |  |
| 651 | BC-DATALEAF5 | Routing Table | Remote Lo0 address | 10.200.1.3 | PASS |  |
| 652 | BC-DATALEAF5 | Routing Table | Remote Lo0 address | 10.200.1.4 | PASS |  |
| 653 | BC-DATALEAF5 | Routing Table | Remote Lo0 address | 10.200.1.5 | PASS |  |
| 654 | BC-DATALEAF5 | Routing Table | Remote Lo0 address | 10.200.1.6 | PASS |  |
| 655 | BC-DATALEAF5 | Routing Table | Remote Lo0 address | 10.200.1.7 | PASS |  |
| 656 | BC-DATALEAF5 | Routing Table | Remote Lo0 address | 10.200.1.8 | PASS |  |
| 657 | BC-DATALEAF5 | Routing Table | Remote Lo0 address | 10.200.1.9 | PASS |  |
| 658 | BC-DATALEAF5 | Routing Table | Remote Lo0 address | 10.200.1.10 | PASS |  |
| 659 | BC-DATALEAF6 | Routing Table | Remote Lo0 address | 10.200.1.1 | PASS |  |
| 660 | BC-DATALEAF6 | Routing Table | Remote Lo0 address | 10.200.1.2 | PASS |  |
| 661 | BC-DATALEAF6 | Routing Table | Remote Lo0 address | 10.200.1.3 | PASS |  |
| 662 | BC-DATALEAF6 | Routing Table | Remote Lo0 address | 10.200.1.4 | PASS |  |
| 663 | BC-DATALEAF6 | Routing Table | Remote Lo0 address | 10.200.1.5 | PASS |  |
| 664 | BC-DATALEAF6 | Routing Table | Remote Lo0 address | 10.200.1.6 | PASS |  |
| 665 | BC-DATALEAF6 | Routing Table | Remote Lo0 address | 10.200.1.7 | PASS |  |
| 666 | BC-DATALEAF6 | Routing Table | Remote Lo0 address | 10.200.1.8 | PASS |  |
| 667 | BC-DATALEAF6 | Routing Table | Remote Lo0 address | 10.200.1.9 | PASS |  |
| 668 | BC-DATALEAF6 | Routing Table | Remote Lo0 address | 10.200.1.10 | PASS |  |
| 669 | BC-SPINE1 | Routing Table | Remote Lo0 address | 10.200.1.1 | PASS |  |
| 670 | BC-SPINE1 | Routing Table | Remote Lo0 address | 10.200.1.2 | PASS |  |
| 671 | BC-SPINE1 | Routing Table | Remote Lo0 address | 10.200.1.3 | PASS |  |
| 672 | BC-SPINE1 | Routing Table | Remote Lo0 address | 10.200.1.4 | PASS |  |
| 673 | BC-SPINE1 | Routing Table | Remote Lo0 address | 10.200.1.5 | PASS |  |
| 674 | BC-SPINE1 | Routing Table | Remote Lo0 address | 10.200.1.6 | PASS |  |
| 675 | BC-SPINE1 | Routing Table | Remote Lo0 address | 10.200.1.7 | PASS |  |
| 676 | BC-SPINE1 | Routing Table | Remote Lo0 address | 10.200.1.8 | PASS |  |
| 677 | BC-SPINE1 | Routing Table | Remote Lo0 address | 10.200.1.9 | PASS |  |
| 678 | BC-SPINE1 | Routing Table | Remote Lo0 address | 10.200.1.10 | PASS |  |
| 679 | BC-SPINE2 | Routing Table | Remote Lo0 address | 10.200.1.1 | PASS |  |
| 680 | BC-SPINE2 | Routing Table | Remote Lo0 address | 10.200.1.2 | PASS |  |
| 681 | BC-SPINE2 | Routing Table | Remote Lo0 address | 10.200.1.3 | PASS |  |
| 682 | BC-SPINE2 | Routing Table | Remote Lo0 address | 10.200.1.4 | PASS |  |
| 683 | BC-SPINE2 | Routing Table | Remote Lo0 address | 10.200.1.5 | PASS |  |
| 684 | BC-SPINE2 | Routing Table | Remote Lo0 address | 10.200.1.6 | PASS |  |
| 685 | BC-SPINE2 | Routing Table | Remote Lo0 address | 10.200.1.7 | PASS |  |
| 686 | BC-SPINE2 | Routing Table | Remote Lo0 address | 10.200.1.8 | PASS |  |
| 687 | BC-SPINE2 | Routing Table | Remote Lo0 address | 10.200.1.9 | PASS |  |
| 688 | BC-SPINE2 | Routing Table | Remote Lo0 address | 10.200.1.10 | PASS |  |
| 689 | BC-STOLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.1 | PASS |  |
| 690 | BC-STOLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.2 | PASS |  |
| 691 | BC-STOLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.3 | PASS |  |
| 692 | BC-STOLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.4 | PASS |  |
| 693 | BC-STOLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.5 | PASS |  |
| 694 | BC-STOLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.6 | PASS |  |
| 695 | BC-STOLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.7 | PASS |  |
| 696 | BC-STOLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.8 | PASS |  |
| 697 | BC-STOLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.9 | PASS |  |
| 698 | BC-STOLEAF1 | Routing Table | Remote Lo0 address | 10.200.1.10 | PASS |  |
| 699 | BC-STOLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.1 | PASS |  |
| 700 | BC-STOLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.2 | PASS |  |
| 701 | BC-STOLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.3 | PASS |  |
| 702 | BC-STOLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.4 | PASS |  |
| 703 | BC-STOLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.5 | PASS |  |
| 704 | BC-STOLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.6 | PASS |  |
| 705 | BC-STOLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.7 | PASS |  |
| 706 | BC-STOLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.8 | PASS |  |
| 707 | BC-STOLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.9 | PASS |  |
| 708 | BC-STOLEAF2 | Routing Table | Remote Lo0 address | 10.200.1.10 | PASS |  |
| 709 | BC-STOLEAF3 | Routing Table | Remote Lo0 address | 10.200.1.1 | PASS |  |
| 710 | BC-STOLEAF3 | Routing Table | Remote Lo0 address | 10.200.1.2 | PASS |  |
| 711 | BC-STOLEAF3 | Routing Table | Remote Lo0 address | 10.200.1.3 | PASS |  |
| 712 | BC-STOLEAF3 | Routing Table | Remote Lo0 address | 10.200.1.4 | PASS |  |
| 713 | BC-STOLEAF3 | Routing Table | Remote Lo0 address | 10.200.1.5 | PASS |  |
| 714 | BC-STOLEAF3 | Routing Table | Remote Lo0 address | 10.200.1.6 | PASS |  |
| 715 | BC-STOLEAF3 | Routing Table | Remote Lo0 address | 10.200.1.7 | PASS |  |
| 716 | BC-STOLEAF3 | Routing Table | Remote Lo0 address | 10.200.1.8 | PASS |  |
| 717 | BC-STOLEAF3 | Routing Table | Remote Lo0 address | 10.200.1.9 | PASS |  |
| 718 | BC-STOLEAF3 | Routing Table | Remote Lo0 address | 10.200.1.10 | PASS |  |
| 719 | BC-STOLEAF4 | Routing Table | Remote Lo0 address | 10.200.1.1 | PASS |  |
| 720 | BC-STOLEAF4 | Routing Table | Remote Lo0 address | 10.200.1.2 | PASS |  |
| 721 | BC-STOLEAF4 | Routing Table | Remote Lo0 address | 10.200.1.3 | PASS |  |
| 722 | BC-STOLEAF4 | Routing Table | Remote Lo0 address | 10.200.1.4 | PASS |  |
| 723 | BC-STOLEAF4 | Routing Table | Remote Lo0 address | 10.200.1.5 | PASS |  |
| 724 | BC-STOLEAF4 | Routing Table | Remote Lo0 address | 10.200.1.6 | PASS |  |
| 725 | BC-STOLEAF4 | Routing Table | Remote Lo0 address | 10.200.1.7 | PASS |  |
| 726 | BC-STOLEAF4 | Routing Table | Remote Lo0 address | 10.200.1.8 | PASS |  |
| 727 | BC-STOLEAF4 | Routing Table | Remote Lo0 address | 10.200.1.9 | PASS |  |
| 728 | BC-STOLEAF4 | Routing Table | Remote Lo0 address | 10.200.1.10 | PASS |  |
| 729 | BC-BORDERLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF1 - 10.200.1.1 Destination: 10.200.1.1 | PASS |  |
| 730 | BC-BORDERLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF1 - 10.200.1.1 Destination: 10.200.1.2 | PASS |  |
| 731 | BC-BORDERLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF1 - 10.200.1.1 Destination: 10.200.1.3 | PASS |  |
| 732 | BC-BORDERLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF1 - 10.200.1.1 Destination: 10.200.1.4 | PASS |  |
| 733 | BC-BORDERLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF1 - 10.200.1.1 Destination: 10.200.1.5 | PASS |  |
| 734 | BC-BORDERLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF1 - 10.200.1.1 Destination: 10.200.1.6 | PASS |  |
| 735 | BC-BORDERLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF1 - 10.200.1.1 Destination: 10.200.1.7 | PASS |  |
| 736 | BC-BORDERLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF1 - 10.200.1.1 Destination: 10.200.1.8 | PASS |  |
| 737 | BC-BORDERLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF1 - 10.200.1.1 Destination: 10.200.1.9 | PASS |  |
| 738 | BC-BORDERLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF1 - 10.200.1.1 Destination: 10.200.1.10 | PASS |  |
| 739 | BC-BORDERLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF2 - 10.200.1.2 Destination: 10.200.1.1 | PASS |  |
| 740 | BC-BORDERLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF2 - 10.200.1.2 Destination: 10.200.1.2 | PASS |  |
| 741 | BC-BORDERLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF2 - 10.200.1.2 Destination: 10.200.1.3 | PASS |  |
| 742 | BC-BORDERLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF2 - 10.200.1.2 Destination: 10.200.1.4 | PASS |  |
| 743 | BC-BORDERLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF2 - 10.200.1.2 Destination: 10.200.1.5 | PASS |  |
| 744 | BC-BORDERLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF2 - 10.200.1.2 Destination: 10.200.1.6 | PASS |  |
| 745 | BC-BORDERLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF2 - 10.200.1.2 Destination: 10.200.1.7 | PASS |  |
| 746 | BC-BORDERLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF2 - 10.200.1.2 Destination: 10.200.1.8 | PASS |  |
| 747 | BC-BORDERLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF2 - 10.200.1.2 Destination: 10.200.1.9 | PASS |  |
| 748 | BC-BORDERLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-BORDERLEAF2 - 10.200.1.2 Destination: 10.200.1.10 | PASS |  |
| 749 | BC-DATALEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF3 - 10.200.1.3 Destination: 10.200.1.1 | PASS |  |
| 750 | BC-DATALEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF3 - 10.200.1.3 Destination: 10.200.1.2 | PASS |  |
| 751 | BC-DATALEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF3 - 10.200.1.3 Destination: 10.200.1.3 | PASS |  |
| 752 | BC-DATALEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF3 - 10.200.1.3 Destination: 10.200.1.4 | PASS |  |
| 753 | BC-DATALEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF3 - 10.200.1.3 Destination: 10.200.1.5 | PASS |  |
| 754 | BC-DATALEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF3 - 10.200.1.3 Destination: 10.200.1.6 | PASS |  |
| 755 | BC-DATALEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF3 - 10.200.1.3 Destination: 10.200.1.7 | PASS |  |
| 756 | BC-DATALEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF3 - 10.200.1.3 Destination: 10.200.1.8 | PASS |  |
| 757 | BC-DATALEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF3 - 10.200.1.3 Destination: 10.200.1.9 | PASS |  |
| 758 | BC-DATALEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF3 - 10.200.1.3 Destination: 10.200.1.10 | PASS |  |
| 759 | BC-DATALEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF4 - 10.200.1.4 Destination: 10.200.1.1 | PASS |  |
| 760 | BC-DATALEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF4 - 10.200.1.4 Destination: 10.200.1.2 | PASS |  |
| 761 | BC-DATALEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF4 - 10.200.1.4 Destination: 10.200.1.3 | PASS |  |
| 762 | BC-DATALEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF4 - 10.200.1.4 Destination: 10.200.1.4 | PASS |  |
| 763 | BC-DATALEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF4 - 10.200.1.4 Destination: 10.200.1.5 | PASS |  |
| 764 | BC-DATALEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF4 - 10.200.1.4 Destination: 10.200.1.6 | PASS |  |
| 765 | BC-DATALEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF4 - 10.200.1.4 Destination: 10.200.1.7 | PASS |  |
| 766 | BC-DATALEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF4 - 10.200.1.4 Destination: 10.200.1.8 | PASS |  |
| 767 | BC-DATALEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF4 - 10.200.1.4 Destination: 10.200.1.9 | PASS |  |
| 768 | BC-DATALEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF4 - 10.200.1.4 Destination: 10.200.1.10 | PASS |  |
| 769 | BC-DATALEAF5 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF5 - 10.200.1.5 Destination: 10.200.1.1 | PASS |  |
| 770 | BC-DATALEAF5 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF5 - 10.200.1.5 Destination: 10.200.1.2 | PASS |  |
| 771 | BC-DATALEAF5 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF5 - 10.200.1.5 Destination: 10.200.1.3 | PASS |  |
| 772 | BC-DATALEAF5 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF5 - 10.200.1.5 Destination: 10.200.1.4 | PASS |  |
| 773 | BC-DATALEAF5 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF5 - 10.200.1.5 Destination: 10.200.1.5 | PASS |  |
| 774 | BC-DATALEAF5 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF5 - 10.200.1.5 Destination: 10.200.1.6 | PASS |  |
| 775 | BC-DATALEAF5 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF5 - 10.200.1.5 Destination: 10.200.1.7 | PASS |  |
| 776 | BC-DATALEAF5 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF5 - 10.200.1.5 Destination: 10.200.1.8 | PASS |  |
| 777 | BC-DATALEAF5 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF5 - 10.200.1.5 Destination: 10.200.1.9 | PASS |  |
| 778 | BC-DATALEAF5 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF5 - 10.200.1.5 Destination: 10.200.1.10 | PASS |  |
| 779 | BC-DATALEAF6 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF6 - 10.200.1.6 Destination: 10.200.1.1 | PASS |  |
| 780 | BC-DATALEAF6 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF6 - 10.200.1.6 Destination: 10.200.1.2 | PASS |  |
| 781 | BC-DATALEAF6 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF6 - 10.200.1.6 Destination: 10.200.1.3 | PASS |  |
| 782 | BC-DATALEAF6 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF6 - 10.200.1.6 Destination: 10.200.1.4 | PASS |  |
| 783 | BC-DATALEAF6 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF6 - 10.200.1.6 Destination: 10.200.1.5 | PASS |  |
| 784 | BC-DATALEAF6 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF6 - 10.200.1.6 Destination: 10.200.1.6 | PASS |  |
| 785 | BC-DATALEAF6 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF6 - 10.200.1.6 Destination: 10.200.1.7 | PASS |  |
| 786 | BC-DATALEAF6 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF6 - 10.200.1.6 Destination: 10.200.1.8 | PASS |  |
| 787 | BC-DATALEAF6 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF6 - 10.200.1.6 Destination: 10.200.1.9 | PASS |  |
| 788 | BC-DATALEAF6 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-DATALEAF6 - 10.200.1.6 Destination: 10.200.1.10 | PASS |  |
| 789 | BC-SPINE1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE1 - 10.200.0.1 Destination: 10.200.1.1 | PASS |  |
| 790 | BC-SPINE1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE1 - 10.200.0.1 Destination: 10.200.1.2 | PASS |  |
| 791 | BC-SPINE1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE1 - 10.200.0.1 Destination: 10.200.1.3 | PASS |  |
| 792 | BC-SPINE1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE1 - 10.200.0.1 Destination: 10.200.1.4 | PASS |  |
| 793 | BC-SPINE1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE1 - 10.200.0.1 Destination: 10.200.1.5 | PASS |  |
| 794 | BC-SPINE1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE1 - 10.200.0.1 Destination: 10.200.1.6 | PASS |  |
| 795 | BC-SPINE1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE1 - 10.200.0.1 Destination: 10.200.1.7 | PASS |  |
| 796 | BC-SPINE1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE1 - 10.200.0.1 Destination: 10.200.1.8 | PASS |  |
| 797 | BC-SPINE1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE1 - 10.200.0.1 Destination: 10.200.1.9 | PASS |  |
| 798 | BC-SPINE1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE1 - 10.200.0.1 Destination: 10.200.1.10 | PASS |  |
| 799 | BC-SPINE2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE2 - 10.200.0.2 Destination: 10.200.1.1 | PASS |  |
| 800 | BC-SPINE2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE2 - 10.200.0.2 Destination: 10.200.1.2 | PASS |  |
| 801 | BC-SPINE2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE2 - 10.200.0.2 Destination: 10.200.1.3 | PASS |  |
| 802 | BC-SPINE2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE2 - 10.200.0.2 Destination: 10.200.1.4 | PASS |  |
| 803 | BC-SPINE2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE2 - 10.200.0.2 Destination: 10.200.1.5 | PASS |  |
| 804 | BC-SPINE2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE2 - 10.200.0.2 Destination: 10.200.1.6 | PASS |  |
| 805 | BC-SPINE2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE2 - 10.200.0.2 Destination: 10.200.1.7 | PASS |  |
| 806 | BC-SPINE2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE2 - 10.200.0.2 Destination: 10.200.1.8 | PASS |  |
| 807 | BC-SPINE2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE2 - 10.200.0.2 Destination: 10.200.1.9 | PASS |  |
| 808 | BC-SPINE2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-SPINE2 - 10.200.0.2 Destination: 10.200.1.10 | PASS |  |
| 809 | BC-STOLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF1 - 10.200.1.7 Destination: 10.200.1.1 | PASS |  |
| 810 | BC-STOLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF1 - 10.200.1.7 Destination: 10.200.1.2 | PASS |  |
| 811 | BC-STOLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF1 - 10.200.1.7 Destination: 10.200.1.3 | PASS |  |
| 812 | BC-STOLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF1 - 10.200.1.7 Destination: 10.200.1.4 | PASS |  |
| 813 | BC-STOLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF1 - 10.200.1.7 Destination: 10.200.1.5 | PASS |  |
| 814 | BC-STOLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF1 - 10.200.1.7 Destination: 10.200.1.6 | PASS |  |
| 815 | BC-STOLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF1 - 10.200.1.7 Destination: 10.200.1.7 | PASS |  |
| 816 | BC-STOLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF1 - 10.200.1.7 Destination: 10.200.1.8 | PASS |  |
| 817 | BC-STOLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF1 - 10.200.1.7 Destination: 10.200.1.9 | PASS |  |
| 818 | BC-STOLEAF1 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF1 - 10.200.1.7 Destination: 10.200.1.10 | PASS |  |
| 819 | BC-STOLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF2 - 10.200.1.8 Destination: 10.200.1.1 | PASS |  |
| 820 | BC-STOLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF2 - 10.200.1.8 Destination: 10.200.1.2 | PASS |  |
| 821 | BC-STOLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF2 - 10.200.1.8 Destination: 10.200.1.3 | PASS |  |
| 822 | BC-STOLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF2 - 10.200.1.8 Destination: 10.200.1.4 | PASS |  |
| 823 | BC-STOLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF2 - 10.200.1.8 Destination: 10.200.1.5 | PASS |  |
| 824 | BC-STOLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF2 - 10.200.1.8 Destination: 10.200.1.6 | PASS |  |
| 825 | BC-STOLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF2 - 10.200.1.8 Destination: 10.200.1.7 | PASS |  |
| 826 | BC-STOLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF2 - 10.200.1.8 Destination: 10.200.1.8 | PASS |  |
| 827 | BC-STOLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF2 - 10.200.1.8 Destination: 10.200.1.9 | PASS |  |
| 828 | BC-STOLEAF2 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF2 - 10.200.1.8 Destination: 10.200.1.10 | PASS |  |
| 829 | BC-STOLEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF3 - 10.200.1.9 Destination: 10.200.1.1 | PASS |  |
| 830 | BC-STOLEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF3 - 10.200.1.9 Destination: 10.200.1.2 | PASS |  |
| 831 | BC-STOLEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF3 - 10.200.1.9 Destination: 10.200.1.3 | PASS |  |
| 832 | BC-STOLEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF3 - 10.200.1.9 Destination: 10.200.1.4 | PASS |  |
| 833 | BC-STOLEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF3 - 10.200.1.9 Destination: 10.200.1.5 | PASS |  |
| 834 | BC-STOLEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF3 - 10.200.1.9 Destination: 10.200.1.6 | PASS |  |
| 835 | BC-STOLEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF3 - 10.200.1.9 Destination: 10.200.1.7 | PASS |  |
| 836 | BC-STOLEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF3 - 10.200.1.9 Destination: 10.200.1.8 | PASS |  |
| 837 | BC-STOLEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF3 - 10.200.1.9 Destination: 10.200.1.9 | PASS |  |
| 838 | BC-STOLEAF3 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF3 - 10.200.1.9 Destination: 10.200.1.10 | PASS |  |
| 839 | BC-STOLEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF4 - 10.200.1.10 Destination: 10.200.1.1 | PASS |  |
| 840 | BC-STOLEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF4 - 10.200.1.10 Destination: 10.200.1.2 | PASS |  |
| 841 | BC-STOLEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF4 - 10.200.1.10 Destination: 10.200.1.3 | PASS |  |
| 842 | BC-STOLEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF4 - 10.200.1.10 Destination: 10.200.1.4 | PASS |  |
| 843 | BC-STOLEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF4 - 10.200.1.10 Destination: 10.200.1.5 | PASS |  |
| 844 | BC-STOLEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF4 - 10.200.1.10 Destination: 10.200.1.6 | PASS |  |
| 845 | BC-STOLEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF4 - 10.200.1.10 Destination: 10.200.1.7 | PASS |  |
| 846 | BC-STOLEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF4 - 10.200.1.10 Destination: 10.200.1.8 | PASS |  |
| 847 | BC-STOLEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF4 - 10.200.1.10 Destination: 10.200.1.9 | PASS |  |
| 848 | BC-STOLEAF4 | Loopback0 Reachability | Loopback0 Reachability | Source: BC-STOLEAF4 - 10.200.1.10 Destination: 10.200.1.10 | PASS |  |
