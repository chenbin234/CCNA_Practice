# **OSPF Network Types and Neighbors**

## 1. **OSPF Network Types**

<img src="images/image-20230602155746139.png" alt="image-20230602155746139" style="zoom:50%;" />

### 1.1 **The OSPF Broadcast Network Type**

OSPF defaults to use a broadcast network type on all types of Ethernet interfaces. Note that all the Ethernet interfaces in examples in Chapter 20 relied on that default setting.

<img src="images/image-20230602160042332.png" alt="image-20230602160042332" style="zoom:50%;" />

<img src="images/image-20230602160123821.png" alt="image-20230602160123821" style="zoom:50%;" />

**Verifying Operations with Network Type Broadcast**

<img src="images/image-20230602160524241.png" alt="image-20230602160524241" style="zoom:50%;" />

<img src="images/image-20230602160545386.png" alt="image-20230602160545386" style="zoom:50%;" />

<img src="images/image-20230602160652647.png" alt="image-20230602160652647" style="zoom:50%;" />

<img src="images/image-20230602160705389.png" alt="image-20230602160705389" style="zoom:50%;" />

**Configuring to Influence the DR/BDR Election**

In some cases, you may want to influence the DR/BDR election with two configurable settings, listed here in order of precedence:

![image-20230602160801783](images/image-20230602160801783.png)

<img src="images/image-20230602160820537.png" alt="image-20230602160820537" style="zoom:50%;" />

<img src="images/image-20230602160836010.png" alt="image-20230602160836010" style="zoom:50%;" />



### 1.2 **The OSPF Point-to-Point Network Type**

<img src="images/image-20230602160903126.png" alt="image-20230602160903126" style="zoom:50%;" />

<img src="images/image-20230602160924250.png" alt="image-20230602160924250" style="zoom:50%;" />

<img src="images/image-20230602160935890.png" alt="image-20230602160935890" style="zoom:50%;" />

<img src="images/image-20230602161138983.png" alt="image-20230602161138983" style="zoom:50%;" />

## 2. **OSPF Neighbor Relationships**

A router’s OSPF configuration enables OSPF on a set of interfaces. IOS then attempts to dis- cover other neighbors on those interfaces by sending and listening for OSPF Hello messages. However, once discovered, two routers may not become neighbors. 

### 2.1 **OSPF Neighbor Requirements**

<img src="images/image-20230602161323451.png" alt="image-20230602161323451" style="zoom:50%;" />

![image-20230602161411234](images/image-20230602161411234.png)

### 2.2 **Issues That Prevent Neighbor Adjacencies**

this section uses the same topology shown earlier in Figure 21-1 but now with some incorrect configuration introduced. In other words, the configuration matches Example 21-1 that began this chapter, but with the following errors introduced:

<img src="images/image-20230602161647894.png" alt="image-20230602161647894" style="zoom:50%;" />

**Finding Area Mismatches**

**Finding Duplicate OSPF Router IDs**

**Finding OSPF Hello and Dead Timer Mismatches**

**Shutting Down the OSPF Process**

### 2.3 **Issues That Allow Adjacencies but Prevent IP Routes**

The last two issues to discuss in this section have a symptom in which the **show ip ospf neighbor** command does list a neighbor, but some other problem exists that prevents the eventual addition of OSPF routes to the routing table. The two issues: 

- **Mismatched MTU Settings**

- **Mismatched OSPF Network Types**

<img src="images/image-20230602161914166.png" alt="image-20230602161914166" style="zoom:50%;" />

## **Command References**

<img src="images/image-20230602161949127.png" alt="image-20230602161949127" style="zoom:50%;" />

<img src="images/image-20230602162006017.png" alt="image-20230602162006017" style="zoom:50%;" />



