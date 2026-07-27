# Multi-AS Routing Lab in GNS3

A networking project demonstrating communication between multiple
Autonomous Systems using **eBGP** while each AS runs a different
Interior Gateway Protocol (IGP). The project also showcases **route
redistribution**, allowing internal routers to learn external routes and
achieve complete end-to-end connectivity.

## Network Overview

This topology consists of **four Autonomous Systems**, each configured
with a different routing approach:

  Autonomous System   Routing Protocol
  ------------------- ------------------
  AS6                 EIGRP
  AS7                 RIP v2
  AS66                Static Routing
  AS77                OSPF

The ASes communicate using **External Border Gateway Protocol (eBGP)**,
while redistribution injects BGP routes into the respective interior
routing protocols.

------------------------------------------------------------------------

## Features

-   Multi-Autonomous System topology
-   EIGRP configuration
-   RIP v2 configuration
-   OSPF configuration
-   Static routing
-   eBGP neighbor configuration
-   Route advertisement using BGP
-   Route redistribution between BGP and IGPs
-   End-to-end connectivity verification
-   Realistic enterprise network simulation

------------------------------------------------------------------------

## Topology

-   10 Cisco Routers
-   10 Ethernet Switches
-   10 VPCS Hosts
-   Multiple LAN segments
-   Multiple point-to-point WAN links

> Add your topology image here:
>
> `![Topology](screenshots/topology.png)`

------------------------------------------------------------------------

## Implementation

### 1. IP Addressing

-   Assigned unique IPv4 subnets for every LAN and WAN link.
-   Used mostly classful addressing for simplicity.

### 2. Interior Routing Protocols

Configured:

-   **EIGRP** in AS6
-   **RIP v2** in AS7
-   **OSPF (Process ID 1)** in AS77
-   **Static Routing** in AS66

### 3. Exterior Routing

Configured **eBGP** between border routers to exchange routes across
Autonomous Systems.

### 4. Route Redistribution

Redistributed BGP routes into the respective IGPs:

-   BGP → EIGRP
-   BGP → RIP
-   BGP → OSPF

This enabled routers that were not running BGP to learn routes from
other Autonomous Systems.

------------------------------------------------------------------------

## Verification

The network was verified through:

-   Successful ping tests between hosts in different ASes
-   Routing table inspection
-   BGP route verification
-   Packet capture using Wireshark
-   Connectivity validation across the entire topology

------------------------------------------------------------------------

## Technologies Used

-   GNS3
-   Cisco IOS c7200
-   VPCS
-   EIGRP
-   RIP v2
-   OSPF
-   Static Routing
-   eBGP
-   IPv4
-   Wireshark

------------------------------------------------------------------------

## Learning Outcomes

Through this project, I gained practical experience with:

-   Enterprise network design
-   Autonomous System architecture
-   Dynamic routing protocols
-   eBGP configuration
-   Route redistribution
-   Inter-domain routing
-   Network troubleshooting
-   Packet analysis using Wireshark

------------------------------------------------------------------------

## Results

The final topology achieved complete connectivity across all Autonomous
Systems. Every host was able to communicate with every other host,
demonstrating successful BGP route exchange and redistribution into the
interior routing protocols.

------------------------------------------------------------------------

## Repository Structure

``` text
├── configs/
├── screenshots/
├── topology/
├── report/
│   └── routing-report.pdf
├── README.md
└── LICENSE
```

------------------------------------------------------------------------

## License

This project is released under the MIT License.
