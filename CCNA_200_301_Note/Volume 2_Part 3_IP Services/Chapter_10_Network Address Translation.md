# Network Address Translation

## 1. **Perspectives on IPv4 Address Scalability**

**Private Addressing**

![image-20230605142737854](images/image-20230605142737854.png)

<img src="images/image-20230605142822039.png" alt="image-20230605142822039" style="zoom:50%;" />



## 2. **Network Address Translation Concepts**

![image-20230605143504060](images/image-20230605143504060.png)

### 2.1 **Static NAT**

Static NAT works just like the example shown in Figure 10-2, but with the IP addresses statically mapped to each other. 

![image-20230605143928593](images/image-20230605143928593.png)

![image-20230605144215641](images/image-20230605144215641.png)



### 2.2 **Dynamic NAT**

![image-20230605144315511](images/image-20230605144315511.png)



### 2.3 **Overloading NAT with Port Address Translation**

The NAT Overload feature, also called **Port Address Translation (PAT)**, solves this problem. Overloading allows NAT to scale to support many clients with only a few public IP addresses.

<img src="images/image-20230605145031213.png" alt="image-20230605145031213" style="zoom:50%;" />



## 3. **NAT Configuration and Troubleshooting**

### 3.1 **Static NAT Configuration**

![image-20230605145419536](images/image-20230605145419536.png)

<img src="images/image-20230605145504969.png" alt="image-20230605145504969" style="zoom:50%;" />

When planning a NAT configuration, you must find some IP addresses to use as inside global IP addresses. Because these addresses must be part of some registered IP address range, it is common to use the extra addresses in the subnet connecting the enterprise to the Internet

<img src="images/image-20230605145627383.png" alt="image-20230605145627383" style="zoom:50%;" />

<img src="images/image-20230605145647476.png" alt="image-20230605145647476" style="zoom:50%;" />



### 3.2 **Dynamic NAT Configuration**

![image-20230605150116397](images/image-20230605150116397.png)

![image-20230605150129559](images/image-20230605150129559.png)

The next example shows a sample dynamic NAT configuration using the same network topology as the previous example 

<img src="images/image-20230605150336855.png" alt="image-20230605150336855" style="zoom:50%;" />

**Dynamic NAT Verification**

<img src="images/image-20230605150442209.png" alt="image-20230605150442209" style="zoom:50%;" />

<img src="images/image-20230605150513965.png" alt="image-20230605150513965" style="zoom:50%;" />

<img src="images/image-20230605150543881.png" alt="image-20230605150543881" style="zoom:50%;" />



### 3.3 **NAT Overload (PAT) Configuration**

<img src="images/image-20230605150634219.png" alt="image-20230605150634219" style="zoom:50%;" />

<img src="images/image-20230605151009565.png" alt="image-20230605151009565" style="zoom:50%;" />

![image-20230605151034008](images/image-20230605151034008.png)





### 3.4 **NAT Troubleshooting**



