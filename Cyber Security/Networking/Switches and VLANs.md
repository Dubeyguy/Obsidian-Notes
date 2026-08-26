# Switches and VLANs

## Basics of a Switch

A **switch** is a device which connects multiple devices locally. It maintains a table called **MAC Address Table** which contains a list of all the MAC addresses associated with the ports of the switch

![[Pasted image 20260825142816.png|277]]

When the switch gets a request from a device who's MAC address is not in the list, it adds that in the list and forwards the packet to the destination MAC address

If the destination MAC address is not in the list either, it broadcasts it to all the devices connected instead. This process is called flooding

![[Pasted image 20260825143018.png|556]]

## VLANs

A **VLAN** or **Virtual LAN** is used to divide the ports in a switch virtually to form separate networks that do not interfere with each other. This is useful for segmenting devices without using multiple separate switches

![[Pasted image 20260825143510.png|519]]

But just using VLANs can also cause issues.
Creating multiple networks using **VLAN** and connecting them can lead to poor management and cost issues when you need to scale the network.

![[Pasted image 20260825143736.png|526]]

To solve this issue, IEEE created a protocol for VLANs called **802.1Q**, also known as VLAN tagging/trunking

### IEEE 802.1Q

**IEEE 802.1Q** (often called **dot1q**) is the industry-standard networking protocol for implementing Virtual Local Area Networks (VLANs) on Ethernet networks. It allows a single physical switch port or network cable to carry traffic for multiple isolated logical networks simultaneously—a process known as **VLAN trunking**.

![[Pasted image 20260825144356.png|496]]

When an Ethernet frame travels over a trunk link between switches or firewalls, 802.1Q inserts a **4-byte header (tag)** directly into the original Ethernet frame format:

- **TPID (Tag Protocol Identifier):** A 2-byte field set to `0x8100` that identifies the frame as an 802.1Q-tagged frame.
- **PCP (Priority Code Point):** A 3-bit field used for Quality of Service (QoS) prioritization (CoS / Class of Service), allowing voice or real-time traffic to take precedence.
- **DEI (Drop Eligible Indicator):** A 1-bit flag indicating if the packet can be dropped during high network congestion.
- **VLAN ID (VID):** A 12-bit field specifying the VLAN the frame belongs to. With 12 bits, it supports up to **4,094 distinct VLAN IDs** (VLAN 1 to 4094; 0 and 4095 are reserved).

When a switch sends a packet to another switch using the trunk port, it also attaches a VLAN tag to it stating the destination VLAN of the packet. The receiving switch then reads the tag, removes it and forwards the packet to the intended VLAN

> For VLAN trunking to work, both the source and destination ports needs to be **Trunk ports**


If we truncate the switches in such a way that they all form a loop, it is called a **Switching Loop**

![[Pasted image 20260825144810.png]]

In this case, if a switch receives a multicast or broadcast frame, those frames keep getting casted by all the other switches too, resulting in an endless cycle. This situation is called a **Broadcast Storm**

To solve this issue, the concept of a **Spanning Tree** was introduced

### Spanning Tree

Inside a spanning tree, a single switch is designated as the **Root Bridge**. All the ports of the Root bridge are in forwarding state ( *i.e. They can both receive and forward network packets* ) . 

Then a single port is selected on all the other switches which provide the best path to the Root Bridge. These ports are also set to forwarding state

All the other redundant ports on the other switches are put in a blocked state ( *i.e. These ports can not forward or receive network packets*) preventing the Broadcast Storm situation.

![[Pasted image 20260825145457.png|496]]

Another advantage of a Spanning Tree is that whenver a link to the root bridge is down, it recalculates and selects another link to connect that diconnected switch to the Root Bridge

![[Pasted image 20260825150209.png|494]]

They way switches communicate in a Spanning Tree is through BPDUs (**Bridge Protocol Data Units**)
The root bridge sends out configuration BPDUs every 2 seconds by default 

![[Pasted image 20260826131759.png|575]]

Every BPDU frame contains

- **Root ID** : Identifies the current root bridge
- **Root Path Cost** : Total cost to reach the root from the sending switch's perspective
- **Bridge ID** : Shows who sent the BPDU
- **Port ID** : Which port the BPDU was sent from
Also, all the spanning tree timers get set inside the BPDU ( *Message Age, Max Age, Hello Time, FWD Delay*)

When a non root switch receives a BPDU from a root bridge, it updates the path cost, bridge ID and port ID and sends out that BPDU to the next switch from the **Designated Port**.


## Layer 3 Switch

A layer 3 switch has the ability to route between networks just like a router

![[Pasted image 20260825224803.png|475]]


## Router

Routers are devices that connect two or more networks. not only do they route data between networks, they also act as a gateway to other networks. 

![[Pasted image 20260826123309.png|530]]

They primarily operate on layer 3 of the **OSI** model

Routers do not know the entire network pathway. They only know the next **hop**. This is made possible by the use of a **Route Table**

![[Pasted image 20260826123517.png]]

### Static Routing

Routers that have static routing have a manually configured, non - changing route table

Static routing becomes messy and redundant very quickly as you try to scale the network.

![[Pasted image 20260826124008.png|499]]

In order to overcome this issue, **dyamic routing** was introduced.

### Dynamic Routing

Dynamic routing uses **routing protocols** in order to handle the routing based on metrics

Some common routing protocols are :

- **OSPF (Open Shortest Path First):**
    
    - **Type:** IGP (Link-State).
    - **Algorithm:** Dijkstra’s Shortest Path First (SPF).
    - **How It Works:** Every router builds a complete map (topology database) of the entire network by exchanging Link-State Advertisements (LSAs). Networks are split into hierarchical "Areas" to conserve memory and CPU.
    - **Best For:** Open-standard, multi-vendor enterprise LANs and internal networks.
    
- **EIGRP (Enhanced Interior Gateway Routing Protocol):**
    
    - **Type:** IGP (Advanced Distance-Vector / Hybrid).
    - **Algorithm:** DUAL (Diffusing Update Algorithm).
    - **How It Works:** Routers do not keep a map of the whole network; instead, they exchange routes with direct neighbors and calculate the fastest path using a combination of bandwidth and delay metrics. Features rapid convergence and low overhead.
    - **Best For:** Cisco-heavy enterprise networks needing fast convergence and simple administration.
    
- **BGP (Border Gateway Protocol):**
    
    - **Type:** EGP (Path-Vector).
    - **How It Works:** Connects independent Autonomous Systems (ASes) using unique AS numbers. Instead of focusing solely on speed or link cost, BGP routes based on granular network policies, hop-by-hop AS paths, and peering agreements.
    - **Best For:** The global Internet backbones, multi-homed ISP connections, and interconnecting large data centers/clouds.

> IGP: Interior Gateway Protocol
> EGP: Exterior  Gateway Protocol

You tell the protocols 

- What interfaces or networks to use
- Which networks to advertise
- Setting metrics or tuning (optional)

In dynamic routing, routers advertise about the devices they know about to the other routers

![[Pasted image 20260826124431.png|488]]

Some advantages of dynamic routing are :

- Easier to manage (auto update routes)
- Choosing the best path (generally)
- Failover (switches to another path if one breaks)

### Router on a stick

**Router-on-a-Stick (RoaS)** is a networking setup used to route traffic between multiple VLANs (Virtual Local Area Networks) using a **single physical network interface** connected to a switch.

Instead of plugging dedicated physical router ports into every separate VLAN, all traffic flows in and out over one multiplexed physical trunk link.

![[Pasted image 20260826125109.png|630]]

**How It Works**

- **802.1Q Trunk Link:** The connection between the switch and the router interface is configured as an 802.1Q trunk cable, carrying tagged Ethernet frames for every VLAN.
- **Subinterfaces:** The router breaks down its single physical interface (e.g., `GigabitEthernet0/0`) into multiple logical subinterfaces (e.g., `Gig0/0.10`, `Gig0/0.20`).
- **VLAN Tagging & Gateways:** Each subinterface is assigned an IP address to act as the default gateway for a specific VLAN and is configured to tag/untag frames matching that VLAN ID.
- **Traffic Flow:** When a host on VLAN 10 talks to VLAN 20, traffic goes **up the trunk cable to the router**, gets processed and switched to the corresponding subinterface, and travels **back down the same trunk cable** to the switch.

### Redundancy

For situations where if a router breaks down in your network and you can't afford your network to be down, some redundancy protocols are made. Some of them are

- **HSRP (Hot Standby Router Protocol)** 
- **VRRP (Virtual Router Redundancy Protocol)**

**HSRP** (Hot Standby Router Protocol) and **VRRP** (Virtual Router Redundancy Protocol) are **First Hop Redundancy Protocols (FHRPs)**.

They provide a continuous default gateway for devices on a network. Instead of configuring end-user devices with a physical router's IP address, devices point to a shared **Virtual IP (VIP)** address. HSRP or VRRP allows multiple routers to back up that VIP—if the primary active router dies, a standby router immediately takes over without breaking network connectivity or requiring configuration changes on host devices.

![[Pasted image 20260826130026.png|502]]
### How They Work

1. **Virtual Identity:** Two or more routers form a redundancy group. They share a Virtual IP address and a corresponding Virtual MAC address.
2. **Election Process:** Routers negotiate roles based on a **priority value** (typically 1 to 254; default is 100). The router with the highest priority wins the election:
    
    - In **HSRP**, it becomes the **Active** router.
    - In **VRRP**, it becomes the **Master** router.
    
3. **Heartbeats:** The primary router regularly transmits hello messages/advertisements to a multicast address.
4. **Failover:** If the secondary (Standby/Backup) router stops receiving heartbeats from the primary within a set timer window (hold time), it assumes the primary has failed. It immediately assumes the Virtual IP and Virtual MAC, continuing to route host traffic seamlessly.

### Security Best Practices for Routers

![[Pasted image 20260826131330.png]]