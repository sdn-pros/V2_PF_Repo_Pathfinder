# PF_NETWORK

## Table of Contents

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

## Fabric Switches and Management IP

| POD | Type | Node | Management IP | Platform | Provisioned in CloudVision | Serial Number |
| --- | ---- | ---- | ------------- | -------- | -------------------------- | ------------- |
| PF_NETWORK | wan_router | Edge10 | - | - | Provisioned | - |
| PF_NETWORK | wan_router | Edge12 | - | - | Provisioned | - |
| PF_NETWORK | wan_router | Edge13 | - | - | Provisioned | - |
| PF_NETWORK | wan_router | Edge14 | - | - | Provisioned | - |
| PF_NETWORK | wan_router | Edge20 | - | - | Provisioned | - |
| PF_NETWORK | wan_router | Edge22 | - | - | Provisioned | - |
| PF_NETWORK | wan_router | Edge23 | - | - | Provisioned | - |
| PF_NETWORK | wan_router | Edge24 | - | - | Provisioned | - |
| PF_NETWORK | wan_router | P10 | - | - | Provisioned | - |
| PF_NETWORK | wan_router | P11 | - | - | Provisioned | - |
| PF_NETWORK | wan_router | P20 | - | - | Provisioned | - |
| PF_NETWORK | wan_router | P21 | - | - | Provisioned | - |
| PF_NETWORK | wan_rr | RR1 | - | - | Provisioned | - |
| PF_NETWORK | wan_rr | RR2 | - | - | Provisioned | - |
| PF_NETWORK | wan_rr | RR3 | - | - | Provisioned | - |
| PF_NETWORK | wan_rr | RR4 | - | - | Provisioned | - |

> Provision status is based on Ansible inventory declaration and do not represent real status from CloudVision.

### Fabric Switches with inband Management IP

| POD | Type | Node | Management IP | Inband Interface |
| --- | ---- | ---- | ------------- | ---------------- |

## Fabric Topology

| Type | Node | Node Interface | Peer Type | Peer Node | Peer Interface |
| ---- | ---- | -------------- | --------- | ----------| -------------- |

## Fabric IP Allocation

### Fabric Point-To-Point Links

| Uplink IPv4 Pool | Available Addresses | Assigned addresses | Assigned Address % |
| ---------------- | ------------------- | ------------------ | ------------------ |

### Point-To-Point Links Node Allocation

| Node | Node Interface | Node IP Address | Peer Node | Peer Interface | Peer IP Address |
| ---- | -------------- | --------------- | --------- | -------------- | --------------- |

### Loopback Interfaces (BGP EVPN Peering)

| Loopback Pool | Available Addresses | Assigned addresses | Assigned Address % |
| ------------- | ------------------- | ------------------ | ------------------ |
| 10.99.101.0/24 | 256 | 10 | 3.91 % |
| 10.99.201.0/24 | 256 | 6 | 2.35 % |

### Loopback0 Interfaces Node Allocation

| POD | Node | Loopback0 |
| --- | ---- | --------- |
| PF_NETWORK | Edge10 | 10.99.101.11/32 |
| PF_NETWORK | Edge12 | 10.99.101.12/32 |
| PF_NETWORK | Edge13 | 10.99.101.13/32 |
| PF_NETWORK | Edge14 | 10.99.101.14/32 |
| PF_NETWORK | Edge20 | 10.99.201.21/32 |
| PF_NETWORK | Edge22 | 10.99.201.22/32 |
| PF_NETWORK | Edge23 | 10.99.201.23/32 |
| PF_NETWORK | Edge24 | 10.99.201.24/32 |
| PF_NETWORK | P10 | 10.99.101.61/32 |
| PF_NETWORK | P11 | 10.99.101.62/32 |
| PF_NETWORK | P20 | 10.99.201.71/32 |
| PF_NETWORK | P21 | 10.99.201.72/32 |
| PF_NETWORK | RR1 | 10.99.101.1/32 |
| PF_NETWORK | RR2 | 10.99.101.2/32 |
| PF_NETWORK | RR3 | 10.99.101.3/32 |
| PF_NETWORK | RR4 | 10.99.101.4/32 |

### VTEP Loopback VXLAN Tunnel Source Interfaces (VTEPs Only)

| VTEP Loopback Pool | Available Addresses | Assigned addresses | Assigned Address % |
| --------------------- | ------------------- | ------------------ | ------------------ |
| 10.99.102.0/24 | 256 | 0 | 0.0 % |
| 10.99.202.0/24 | 256 | 0 | 0.0 % |

### VTEP Loopback Node allocation

| POD | Node | Loopback1 |
| --- | ---- | --------- |
