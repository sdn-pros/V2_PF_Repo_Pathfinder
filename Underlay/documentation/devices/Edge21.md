# Edge21

## Table of Contents

- [Spanning Tree](#spanning-tree)
  - [Spanning Tree Summary](#spanning-tree-summary)
  - [Spanning Tree Device Configuration](#spanning-tree-device-configuration)
- [Interfaces](#interfaces)
  - [Ethernet Interfaces](#ethernet-interfaces)
  - [Loopback Interfaces](#loopback-interfaces)
- [Routing](#routing)
  - [IP Routing](#ip-routing)
  - [IPv6 Routing](#ipv6-routing)
  - [Router BGP](#router-bgp)
- [VRF Instances](#vrf-instances)
  - [VRF Instances Summary](#vrf-instances-summary)
  - [VRF Instances Device Configuration](#vrf-instances-device-configuration)

## Spanning Tree

### Spanning Tree Summary

STP mode: **none**

### Spanning Tree Device Configuration

```eos
!
spanning-tree mode none
```

## Interfaces

### Ethernet Interfaces

#### Ethernet Interfaces Summary

##### L2

| Interface | Description | Mode | VLANs | Native VLAN | Trunk Group | Channel-Group |
| --------- | ----------- | ---- | ----- | ----------- | ----------- | ------------- |

*Inherited from Port-Channel Interface

##### IPv4

| Interface | Description | Type | Channel Group | IP Address | VRF |  MTU | Shutdown | ACL In | ACL Out |
| --------- | ----------- | -----| ------------- | ---------- | ----| ---- | -------- | ------ | ------- |
| Ethernet3 | - | routed | - | 192.21.33.1/24 | VRF_A | 1500 | False | - | - |
| Ethernet4 | - | routed | - | 192.21.25.1/24 | default | 1500 | False | - | - |
| Ethernet5 | - | routed | - | 192.21.26.1/24 | default | 1500 | False | - | - |
| Ethernet6 | - | routed | - | 192.21.34.1/24 | default | 1500 | False | - | - |

#### Ethernet Interfaces Device Configuration

```eos
!
interface Ethernet1
   shutdown
   mtu 1500
   no switchport
!
interface Ethernet2
   shutdown
   mtu 1500
   no switchport
!
interface Ethernet3
   no shutdown
   mtu 1500
   no switchport
   vrf VRF_A
   ip address 192.21.33.1/24
   ip ospf network point-to-point
   ip ospf area 0
!
interface Ethernet4
   no shutdown
   mtu 1500
   no switchport
   ip address 192.21.25.1/24
!
interface Ethernet5
   no shutdown
   mtu 1500
   no switchport
   ip address 192.21.26.1/24
!
interface Ethernet6
   no shutdown
   mtu 1500
   no switchport
   ip address 192.21.34.1/24
```

### Loopback Interfaces

#### Loopback Interfaces Summary

##### IPv4

| Interface | Description | VRF | IP Address |
| --------- | ----------- | --- | ---------- |
| Loopback10 | Edge-21_lo10 | default | 192.168.0.21/32 |

##### IPv6

| Interface | Description | VRF | IPv6 Address |
| --------- | ----------- | --- | ------------ |
| Loopback10 | Edge-21_lo10 | default | - |

#### Loopback Interfaces Device Configuration

```eos
!
interface Loopback10
   description Edge-21_lo10
   no shutdown
   ip address 192.168.0.21/32
```

## Routing

### IP Routing

#### IP Routing Summary

| VRF | Routing Enabled |
| --- | --------------- |
| default | True |
| VRF_A | True |

#### IP Routing Device Configuration

```eos
!
ip routing
ip routing vrf VRF_A
```

### IPv6 Routing

#### IPv6 Routing Summary

| VRF | Routing Enabled |
| --- | --------------- |
| default | False |
| VRF_A | false |

### Router BGP

ASN Notation: asplain

#### Router BGP Summary

| BGP AS | Router ID |
| ------ | --------- |
| 65000 | 192.168.0.21 |

#### BGP Neighbors

| Neighbor | Remote AS | VRF | Shutdown | Send-community | Maximum-routes | Allowas-in | BFD | RIB Pre-Policy Retain | Route-Reflector Client | Passive | TTL Max Hops |
| -------- | --------- | --- | -------- | -------------- | -------------- | ---------- | --- | --------------------- | ---------------------- | ------- | ------------ |
| 192.21.25.2 | 65202 | default | - | - | - | Allowed, allowed 6 times | - | - | - | - | - |
| 192.21.26.2 | 65203 | default | - | - | - | Allowed, allowed 6 times | - | - | - | - | - |

#### Router BGP VRFs

| VRF | Route-Distinguisher | Redistribute |
| --- | ------------------- | ------------ |
| VRF_A | - | connected<br>ospf |

#### Router BGP Device Configuration

```eos
!
router bgp 65000
   router-id 192.168.0.21
   neighbor 192.21.25.2 remote-as 65202
   neighbor 192.21.25.2 allowas-in 6
   neighbor 192.21.26.2 remote-as 65203
   neighbor 192.21.26.2 allowas-in 6
   redistribute connected
   !
   address-family ipv4
      neighbor 192.21.25.2 activate
      neighbor 192.21.26.2 activate
      network 192.168.0.21/32
   !
   vrf VRF_A
      redistribute connected
      redistribute ospf
```

## VRF Instances

### VRF Instances Summary

| VRF Name | IP Routing |
| -------- | ---------- |
| VRF_A | enabled |

### VRF Instances Device Configuration

```eos
!
vrf instance VRF_A
```
