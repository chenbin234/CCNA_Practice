# **Implementing OSPF**

## 1. **Implementing Single-Area OSPFv2**

<img src="images/image-20230601113203202.png" alt="image-20230601113203202" style="zoom:50%;" />

<img src="images/image-20230601113229723.png" alt="image-20230601113229723" style="zoom:50%;" />

<img src="images/image-20230601113942191.png" alt="image-20230601113942191" style="zoom:50%;" />

### 1.1 **OSPF Single-Area Configuration**

**Figure 20-2 shows a sample network that will be used for most examples throughout this chapter.** 

1. All links reside in area 0, making the area design a single-area design, with four routers. 
2. You can think of Router R1 as a router at a central site, with WAN links to each remote site, and using router-on-a-stick (ROAS) to connect to two LAN subnets on the left. 
3. Routers R2 and R3 might be at one large remote site that needs two WAN links and two routers for WAN redundancy, with both routers connected to the LAN at that remote site. 
4. Router R4 might be a typical smaller remote site with a single router needed for that site.

<img src="images/image-20230602144505385.png" alt="image-20230602144505385" style="zoom:50%;" />

<img src="images/image-20230602144816282.png" alt="image-20230602144816282" style="zoom:50%;" />

**How to config?**

1. The OSPF configuration begins with the **router ospf** process-id global command, which puts the user in OSPF configuration mode, and sets the OSPF process-id value.

2. The process-id number just needs to be unique on the local router, allowing the router to support multiple OSPF processes in a single router by using different process IDs. (The **router** command uses the process-id to distinguish between the processes.) **The process-id does not have to match on each router, and it can be any integer between 1 and 65,535.**
3. Second, the configuration needs one or more **network** commands in OSPF mode. These commands tell the router to find its local interfaces that match the first two parameters on the **network** command. Then, for each matched interface, the router enables OSPF on those interfaces, discovers neighbors, creates neighbor relationships, and assigns the interface to the area listed in the **network** command. 

<img src="images/image-20230602145236433.png" alt="image-20230602145236433" style="zoom:50%;" />

**Wildcard Matching with the network Command**

The key to understanding the traditional OSPFv2 configuration shown in this first example is to understand the OSPF **network** command. The OSPF **network** command compares the first parameter in the command to each interface IP address on the local router, trying to find a match. However, rather than comparing the entire number in the **network** command to the entire IPv4 address on the interface, the router can compare a subset of the octets, based on the wildcard mask, as follows:

<img src="images/image-20230602145435846.png" alt="image-20230602145435846" style="zoom:50%;" />

<img src="images/image-20230602145620309.png" alt="image-20230602145620309" style="zoom:50%;" />

<img src="images/image-20230602145635043.png" alt="image-20230602145635043" style="zoom:50%;" />

<img src="images/image-20230602145650646.png" alt="image-20230602145650646" style="zoom:50%;" />

<img src="images/image-20230602145707095.png" alt="image-20230602145707095" style="zoom:50%;" />

**Verifying OSPF Operation**

<img src="images/image-20230602150035021.png" alt="image-20230602150035021" style="zoom:50%;" />

<img src="images/image-20230602150056638.png" alt="image-20230602150056638" style="zoom:50%;" />

<img src="images/image-20230602150211903.png" alt="image-20230602150211903" style="zoom:50%;" />

<img src="images/image-20230602150237938.png" alt="image-20230602150237938" style="zoom:50%;" />

<img src="images/image-20230602150405840.png" alt="image-20230602150405840" style="zoom:50%;" />

<img src="images/image-20230602150428001.png" alt="image-20230602150428001" style="zoom:50%;" />

**Verifying OSPF Configuration**

Once you can configure OSPF with confidence, you will likely verify OSPF focusing on OSPF neighbors and the IP routing table as just discussed. However, if OSPF does not work immediately, you may need to circle back and check the configuration. To do so, you can use these steps:

<img src="images/image-20230602151339746.png" alt="image-20230602151339746" style="zoom:50%;" />

**Configuring the OSPF Router ID**

While OSPF has many other optional features, most enterprise networks that use OSPF choose to configure each router’s OSPF router ID. OSPF-speaking routers must have a router ID (RID) for proper operation. By default, routers will choose an interface IP address to use as the RID. However, many network engineers prefer to choose each router’s router ID, so com- mand output from commands like **show ip ospf neighbor** lists more recognizable router IDs.

<img src="images/image-20230602151518671.png" alt="image-20230602151518671" style="zoom:50%;" />

<img src="images/image-20230602151541259.png" alt="image-20230602151541259" style="zoom:50%;" />

<img src="images/image-20230602151610716.png" alt="image-20230602151610716" style="zoom:50%;" />

### 1.2 **Implementing Multiarea OSPF**

<img src="images/image-20230602151650573.png" alt="image-20230602151650573" style="zoom:50%;" />

<img src="images/image-20230602151713352.png" alt="image-20230602151713352" style="zoom:50%;" />



## 2. **Using OSPFv2 Interface Subcommands**

From the earliest days of OSPFv2 support in Cisco routers, the configuration used the OSPF **network** command as discussed in this chapter. However, **that configuration style can be confusing**, and it does require some interpretation of the **network** commands and interface IP addresses to decide on which interfaces IOS will enable OSPF. **As a result, Cisco added another option for OSPFv2 configuration called OSPF interface configuration.**

The newer interface-style OSPF configuration still enables OSPF on interfaces, but it does so directly with the **ip ospf** interface subcommand instead of using the **network** command in router configuration mode. Basically, instead of matching interfaces with indirect logic using **network** commands, you directly enable OSPFv2 on interfaces by configuring an interface subcommand on each interface.

**OSPF Interface Configuration Example**

<img src="images/image-20230602152027040.png" alt="image-20230602152027040" style="zoom:50%;" />

<img src="images/image-20230602152114239.png" alt="image-20230602152114239" style="zoom:50%;" />

<img src="images/image-20230602152137798.png" alt="image-20230602152137798" style="zoom:50%;" />

<img src="images/image-20230602152150996.png" alt="image-20230602152150996" style="zoom:50%;" />

**Verifying OSPF Interface Configuration**

OSPF operates the same way whether you use the new style or old style of configuration. The OSPF area design works the same, neighbor relationships form the same way, routers negotiate to become the DR and BDR the same way, and so on. However, you can see a few small differences in show command output when using the newer OSPFv2 configuration if you look closely.

<img src="images/image-20230602152304798.png" alt="image-20230602152304798" style="zoom:50%;" />

<img src="images/image-20230602152319003.png" alt="image-20230602152319003" style="zoom:50%;" />

![image-20230602152344532](images/image-20230602152344532.png)

## 3. **Additional OSPFv2 Features**

This final major section of the chapter discusses some very popular but optional OSPFv2 configuration features, as listed here in their order of appearance:

- Passive interfaces
- Default routes 
- Metrics 
- Load balancing

### 3.1 **OSPF Passive Interfaces**

Sometimes, a router does not need to form neighbor relationships with neighbors on an interface. Often, no other routers exist on a particular link, so the router has no need to keep sending those repetitive OSPF Hello messages. In such cases, an engineer can make the inter- face passive, which means

<img src="images/image-20230602153007329.png" alt="image-20230602153007329" style="zoom:50%;" />

<img src="images/image-20230602153333813.png" alt="image-20230602153333813" style="zoom:50%;" />

<img src="images/image-20230602153357766.png" alt="image-20230602153357766" style="zoom:50%;" />

### 3.2 **OSPF Default Routes**

<img src="images/image-20230602153637380.png" alt="image-20230602153637380" style="zoom:50%;" />

<img src="images/image-20230602153655255.png" alt="image-20230602153655255" style="zoom:50%;" />

<img src="images/image-20230602153720950.png" alt="image-20230602153720950" style="zoom:50%;" />



### 3.3 **OSPF Metrics (Cost)**

<img src="images/image-20230602153748992.png" alt="image-20230602153748992" style="zoom:50%;" />

<img src="images/image-20230602153800651.png" alt="image-20230602153800651" style="zoom:50%;" />

<img src="images/image-20230602153827012.png" alt="image-20230602153827012" style="zoom:50%;" />

<img src="images/image-20230602153848294.png" alt="image-20230602153848294" style="zoom:50%;" />

### 3.4 **OSPF Load Balancing**

When a router uses SPF to calculate the metric for each of several routes to reach one sub- net, one route may have the lowest metric, so OSPF puts that route in the routing table. However, when the metrics tie for multiple routes to the same subnet, the router can put multiple equal-cost routes in the routing table (the default is four different routes) based on the setting of the **maximum-paths** number router subcommand. 

For example, if an internet- work has six possible paths between some parts of the network, and the engineer wants all routes to be used, the routers can be configured with the **maximum-paths 6** subcommand under **router ospf**.



## **Command References**

<img src="images/image-20230602154046267.png" alt="image-20230602154046267" style="zoom:50%;" />

<img src="images/image-20230602154100107.png" alt="image-20230602154100107" style="zoom:50%;" />

<img src="images/image-20230602154113921.png" alt="image-20230602154113921" style="zoom:50%;" />

<img src="images/image-20230602154125608.png" alt="image-20230602154125608" style="zoom:50%;" />
