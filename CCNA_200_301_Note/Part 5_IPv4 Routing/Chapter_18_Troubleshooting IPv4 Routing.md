# **Troubleshooting IPv4 Routing**

## 1  **Problem Isolation Using the ping Command**

<img src="images/image-20230531215507350.png" alt="image-20230531215507350" style="zoom:50%;" />

![image-20230531215718584](images/image-20230531215718584.png)

The extended **ping** command does allow the user to type all the parameters on a potentially long command, but it also allows users to simply issue the **ping** command, press **Enter**, with IOS then asking the user to answer questions to complete the command, as shown in Example 18-3. The example shows the **ping** command on R1 that matches the logic in Figure 18-6. This same command could have been issued from the command line as **ping 172.16.2.101 source 172.16.1.1.**

<img src="images/image-20230531215837165.png" alt="image-20230531215837165" style="zoom:50%;" />

**Testing LAN Neighbors with Standard Ping**

<img src="images/image-20230531220022780.png" alt="image-20230531220022780" style="zoom:67%;" />

![image-20230531220058770](images/image-20230531220058770.png)

**Testing LAN Neighbors with Extended Ping**

![image-20230531220147286](images/image-20230531220147286.png)

## 2. **Problem Isolation Using the traceroute Command**

<img src="images/image-20230531220349781.png" alt="image-20230531220349781" style="zoom: 67%;" />

**How the traceroute Command Works**

<img src="images/image-20230531220451483.png" alt="image-20230531220451483" style="zoom:67%;" />

  <img src="images/image-20230531220506882.png" alt="image-20230531220506882" style="zoom:67%;" />

**Standard and Extended traceroute**

![image-20230531220542524](images/image-20230531220542524.png)

## 3. **Telnet and SSH**

<img src="images/image-20230531220954033.png" alt="image-20230531220954033" style="zoom:67%;" />

<img src="images/image-20230531221020628.png" alt="image-20230531221020628" style="zoom:67%;" />

<img src="images/image-20230531221033387.png" alt="image-20230531221033387" style="zoom:67%;" />