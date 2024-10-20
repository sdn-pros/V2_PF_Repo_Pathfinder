# ISP-1

## Table of Contents

- [Spanning Tree](#spanning-tree)
  - [Spanning Tree Summary](#spanning-tree-summary)
  - [Spanning Tree Device Configuration](#spanning-tree-device-configuration)
- [Interfaces](#interfaces)
  - [Ethernet Interfaces](#ethernet-interfaces)
  - [Loopback Interfaces](#loopback-interfaces)
- [Routing](#routing)
  - [IP Routing](#ip-routing)
  - [Static Routes](#static-routes)
  - [Router BGP](#router-bgp)
- [Filters](#filters)
  - [Prefix-lists](#prefix-lists)
  - [Route-maps](#route-maps)

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
| Ethernet1 | - | routed | - | 192.16.51.1/24 | default | 1500 | False | - | - |
| Ethernet2 | - | routed | - | 192.16.52.1/24 | default | 1500 | False | - | - |
| Ethernet3 | - | routed | - | 192.16.71.1/24 | default | 1500 | False | - | - |
| Ethernet4 | - | routed | - | 192.16.72.1/24 | default | 1500 | False | - | - |
| Ethernet5 | - | routed | - | 192.10.16.2/24 | default | 1500 | False | - | - |
| Ethernet6 | - | routed | - | 192.11.16.2/24 | default | 1500 | False | - | - |
| Ethernet7 | - | routed | - | 192.12.16.2/24 | default | 1500 | False | - | - |
| Ethernet8 | - | routed | - | 192.13.16.2/24 | default | 1500 | False | - | - |
| Ethernet9 | - | routed | - | 192.14.16.2/24 | default | 1500 | False | - | - |
| Ethernet10 | - | routed | - | 192.16.75.1/24 | default | 1500 | False | - | - |

#### Ethernet Interfaces Device Configuration

```eos
!
interface Ethernet1
   no shutdown
   mtu 1500
   no switchport
   ip address 192.16.51.1/24
!
interface Ethernet2
   no shutdown
   mtu 1500
   no switchport
   ip address 192.16.52.1/24
!
interface Ethernet3
   no shutdown
   mtu 1500
   no switchport
   ip address 192.16.71.1/24
!
interface Ethernet4
   no shutdown
   mtu 1500
   no switchport
   ip address 192.16.72.1/24
!
interface Ethernet5
   no shutdown
   mtu 1500
   no switchport
   ip address 192.10.16.2/24
!
interface Ethernet6
   no shutdown
   mtu 1500
   no switchport
   ip address 192.11.16.2/24
!
interface Ethernet7
   no shutdown
   mtu 1500
   no switchport
   ip address 192.12.16.2/24
!
interface Ethernet8
   no shutdown
   mtu 1500
   no switchport
   ip address 192.13.16.2/24
!
interface Ethernet9
   no shutdown
   mtu 1500
   no switchport
   ip address 192.14.16.2/24
!
interface Ethernet10
   no shutdown
   mtu 1500
   no switchport
   ip address 192.16.75.1/24
```

### Loopback Interfaces

#### Loopback Interfaces Summary

##### IPv4

| Interface | Description | VRF | IP Address |
| --------- | ----------- | --- | ---------- |
| Loopback10 | ISP_lo10 | default | 192.168.0.16/32 |

##### IPv6

| Interface | Description | VRF | IPv6 Address |
| --------- | ----------- | --- | ------------ |
| Loopback10 | ISP_lo10 | default | - |

#### Loopback Interfaces Device Configuration

```eos
!
interface Loopback10
   description ISP_lo10
   no shutdown
   ip address 192.168.0.16/32
```

## Routing

### IP Routing

#### IP Routing Summary

| VRF | Routing Enabled |
| --- | --------------- |
| default | True |

#### IP Routing Device Configuration

```eos
!
ip routing
```

### Static Routes

#### Static Routes Summary

| VRF | Destination Prefix | Next Hop IP | Exit interface | Administrative Distance | Tag | Route Name | Metric |
| --- | ------------------ | ----------- | -------------- | ----------------------- | --- | ---------- | ------ |
| default | 0.0.0.0/0 | - | Null0 | 1 | - | - | - |

#### Static Routes Device Configuration

```eos
!
ip route 0.0.0.0/0 Null0
```

### Router BGP

ASN Notation: asplain

#### Router BGP Summary

| BGP AS | Router ID |
| ------ | --------- |
| 65103 | 192.168.0.16 |

#### BGP Neighbors

| Neighbor | Remote AS | VRF | Shutdown | Send-community | Maximum-routes | Allowas-in | BFD | RIB Pre-Policy Retain | Route-Reflector Client | Passive | TTL Max Hops |
| -------- | --------- | --- | -------- | -------------- | -------------- | ---------- | --- | --------------------- | ---------------------- | ------- | ------------ |
| 192.10.16.1 | 65000 | default | - | - | - | Allowed, allowed 6 times | - | - | - | - | - |
| 192.11.16.1 | 65000 | default | - | - | - | Allowed, allowed 6 times | - | - | - | - | - |
| 192.12.16.1 | 65000 | default | - | - | - | Allowed, allowed 6 times | - | - | - | - | - |
| 192.13.16.1 | 65000 | default | - | - | - | Allowed, allowed 6 times | - | - | - | - | - |
| 192.14.16.1 | 65000 | default | - | - | - | Allowed, allowed 6 times | - | - | - | - | - |
| 192.16.51.2 | 65000 | default | - | - | - | Allowed, allowed 6 times | - | - | - | - | - |
| 192.16.52.2 | 65000 | default | - | - | - | Allowed, allowed 6 times | - | - | - | - | - |
| 192.16.71.2 | 65000 | default | - | - | - | Allowed, allowed 6 times | - | - | - | - | - |
| 192.16.72.2 | 65000 | default | - | - | - | Allowed, allowed 6 times | - | - | - | - | - |
| 192.16.75.2 | 65002 | default | - | - | - | Allowed, allowed 3 (default) times | - | - | - | - | - |

#### Router BGP Device Configuration

```eos
!
router bgp 65103
   router-id 192.168.0.16
   neighbor 192.10.16.1 remote-as 65000
   neighbor 192.10.16.1 allowas-in 6
   neighbor 192.11.16.1 remote-as 65000
   neighbor 192.11.16.1 allowas-in 6
   neighbor 192.12.16.1 remote-as 65000
   neighbor 192.12.16.1 allowas-in 6
   neighbor 192.13.16.1 remote-as 65000
   neighbor 192.13.16.1 allowas-in 6
   neighbor 192.14.16.1 remote-as 65000
   neighbor 192.14.16.1 allowas-in 6
   neighbor 192.16.51.2 remote-as 65000
   neighbor 192.16.51.2 allowas-in 6
   neighbor 192.16.52.2 remote-as 65000
   neighbor 192.16.52.2 allowas-in 6
   neighbor 192.16.71.2 remote-as 65000
   neighbor 192.16.71.2 allowas-in 6
   neighbor 192.16.72.2 remote-as 65000
   neighbor 192.16.72.2 allowas-in 6
   neighbor 192.16.75.2 remote-as 65002
   neighbor 192.16.75.2 allowas-in
   !
   address-family ipv4
      neighbor 192.10.16.1 activate
      neighbor 192.11.16.1 activate
      neighbor 192.12.16.1 activate
      neighbor 192.13.16.1 activate
      neighbor 192.14.16.1 activate
      neighbor 192.16.51.2 activate
      neighbor 192.16.52.2 activate
      neighbor 192.16.71.2 activate
      neighbor 192.16.72.2 activate
      neighbor 192.16.75.2 activate
      network 0.0.0.0/0
      network 192.16.71.0/24
      network 192.16.72.0/24
      network 192.168.0.16/32
      redistribute connected
```

## Filters

### Prefix-lists

#### Prefix-lists Summary

##### DEFAULTONLY

| Sequence | Action |
| -------- | ------ |
| 10 | permit 0.0.0.0/0 |

##### ISP1CONNECTED

| Sequence | Action |
| -------- | ------ |
| 10 | permit 192.16.71.0/24 |
| 20 | permit 192.16.72.0/24 |
| 30 | permit 192.10.16.0/24 |
| 40 | permit 192.11.16.0/24 |
| 50 | permit 192.12.16.0/24 |
| 60 | permit 192.13.16.0/24 |
| 70 | permit 192.14.16.0/24 |

#### Prefix-lists Device Configuration

```eos
!
ip prefix-list DEFAULTONLY
   seq 10 permit 0.0.0.0/0
!
ip prefix-list ISP1CONNECTED
   seq 10 permit 192.16.71.0/24
   seq 20 permit 192.16.72.0/24
   seq 30 permit 192.10.16.0/24
   seq 40 permit 192.11.16.0/24
   seq 50 permit 192.12.16.0/24
   seq 60 permit 192.13.16.0/24
   seq 70 permit 192.14.16.0/24
```

### Route-maps

#### Route-maps Summary

##### DEFAULTONLY

| Sequence | Type | Match | Set | Sub-Route-Map | Continue |
| -------- | ---- | ----- | --- | ------------- | -------- |
| 10 | permit | ip address prefix-list DEFAULTONLY | - | - | - |

##### ISP1CONNECTED

| Sequence | Type | Match | Set | Sub-Route-Map | Continue |
| -------- | ---- | ----- | --- | ------------- | -------- |
| 10 | permit | ip address prefix-list ISP1CONNECTED | - | - | - |

#### Route-maps Device Configuration

```eos
!
route-map DEFAULTONLY permit 10
   match ip address prefix-list DEFAULTONLY
!
route-map ISP1CONNECTED permit 10
   match ip address prefix-list ISP1CONNECTED
```
