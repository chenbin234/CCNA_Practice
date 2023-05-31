# IP Routing in the LAN

## 1. **VLAN Routing with Router 802.1Q Trunks**

Almost all enterprise networks use VLANs. To route IP packets in and out of those VLANs, some devices (either routers or Layer 3 switches) need to have an IP address in each subnet and have a connected route to each of those subnets. Then the IP addresses on those routers or Layer 3 switches can serve as the default gateways in those subnets.

This chapter breaks down the LAN routing options into four categories:

- Use a router, with one router LAN interface and cable connected to the switch for each and every VLAN (typically not used)
- Use a router, with a VLAN trunk connecting to a LAN switch (known as router-on-a- stick, or ROAS)
- Use a Layer 3 switch with switched virtual interfaces (SVI)
- Use a Layer 3 switch with routed interfaces (which may or may not be Layer 3 EtherChannels)

### 1.1 **Configuring ROAS**

This topic discusses how routers route packets to subnets associated with VLANs connected to a router 802.1Q trunk.

ROAS uses router VLAN trunking configuration to give the router a logical router interface connected to each VLAN. Because the router then has an interface connected to each VLAN, the router can also be configured with an IP address in the subnet that exists on each VLAN.

#### The problem is

Routers use subinterfaces as the means to have an interface connected to a VLAN. The router needs to have an IP address/mask associated with each VLAN on the trunk. **However, the router has only one physical interface for the link connected to the trunk.** 

#### How to solve it 

Cisco solves this problem by creating multiple virtual router interfaces, one associated with each VLAN on that trunk (at least for each VLAN that you want the trunk to support). Cisco calls these virtual interfaces subinterfaces. The configuration can then include an **ip address** command for each subinterface.

Because this router needs to route between only two VLANs, **the figure also shows two subinterfaces, named G0/0.10 and G0/0.20, which create a new place in the configuration where the per-VLAN configuration settings can be made.** The router treats frames tagged with VLAN 10 as if they came in or out of G0/0.10 and frames tagged with VLAN 20 as if they came in or out G0/0.20.

<img src="images/image-20230531155423885.png" alt="image-20230531155423885" style="zoom:50%;" />

In addition, note that most Cisco routers do not attempt to negotiate trunking, so both the router and switch need to manually configure trunking. This chapter discusses the router side of that trunking configuration; the matching switch interface would need to be configured with the **switchport mode trunk** command.

![image-20230531155720785](images/image-20230531155720785.png)

<img src="images/image-20230531155732490.png" alt="image-20230531155732490" style="zoom:50%;" />

Each subinterface configuration lists two subcommands. 

1. One command (**encapsulation**) enables trunking and defines the VLAN whose frames are considered to be coming in and out of the subinterface. 
2. The **ip address** command works the same way it does on any other interface. 

<img src="images/image-20230531161256821.png" alt="image-20230531161256821" style="zoom:50%;" />

<img src="images/image-20230531161332839.png" alt="image-20230531161332839" style="zoom:50%;" />

### 1.2 **Verifying ROAS**

Beyond using the **show running-config** command, ROAS configuration on a router can be best verified with two commands: **show ip route** [**connected**] and **show vlans**.

<img src="images/image-20230531161636187.png" alt="image-20230531161636187" style="zoom:50%;" />

<img src="images/image-20230531161837899.png" alt="image-20230531161837899" style="zoom:50%;" />

Additionally, the subinterface state can also be enabled and disabled independently from the physical interface, using the **no shutdown** and **shutdown** commands in subinterface configuration mode.

Another useful ROAS verification command, **show vlans**, spells out which router trunk inter- faces use which VLANs, which VLAN is the native VLAN, plus some packet statistics. 

<img src="images/image-20230531162003498.png" alt="image-20230531162003498" style="zoom:50%;" />

### 1.3 **Troubleshooting ROAS**

troubleshooting ROAS often begins with checking the configuration on both the router and switch because there is no status output on either device that tells you where the problem might be.

<img src="images/image-20230531162145103.png" alt="image-20230531162145103" style="zoom:50%;" />

## 2. **VLAN Routing with Layer 3 Switch SVIs**

**Using a router with ROAS to route packets makes sense in some cases, particularly at small remote sites. In sites with a larger LAN, network designers choose to use Layer 3 switches for most inter-VLAN routing.**

A Layer 3 switch (also called a multilayer switch) is one device, but it executes logic at two layers: Layer 2 LAN switching and Layer 3 IP routing. The Layer 2 switch function forwards frames inside each VLAN, but it will not forward frames between VLANs. The Layer 3 forwarding (routing) logic forwards IP packets between VLANs.



### 2.1 **Configuring Routing Using Switch SVIs**
