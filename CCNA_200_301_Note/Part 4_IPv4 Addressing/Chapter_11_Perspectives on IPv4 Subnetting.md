# **Perspectives on IPv4 Subnetting**

### 1. **Rules About Which Hosts Are in Which Subnet**

<img src="images/image-20230530213338433.png" alt="image-20230530213338433" style="zoom: 67%;" />

<img src="images/image-20230530213430108.png" alt="image-20230530213430108" style="zoom: 67%;" />

### 2. **Determining the Number of Subnets**

![image-20230530213700984](images/image-20230530213700984.png)

### 3. **Determining the Number of Hosts per Subnet**

However, the subnet’s size is not 2H. It’s 2H – 2 because two numbers in each subnet are reserved for other purposes. Each subnet reserves the numerically lowest value for the **subnet number** and the numerically highest value as the **subnet broadcast address**. As a result, the number of usable IP addresses per subnet is 2H – 2.

<img src="images/image-20230530214941093.png" alt="image-20230530214941093" style="zoom:67%;" />

### 4. **Choose a Classful Network**

**Growth Exhausts the Public IP Address Space**

![image-20230530215621823](images/image-20230530215621823.png)

![image-20230530215827006](images/image-20230530215827006.png)

![image-20230530215927642](images/image-20230530215927642.png)

### 5. **Choose the Mask**

![image-20230530220314225](images/image-20230530220314225.png)

<img src="images/image-20230530220353285.png" alt="image-20230530220353285" style="zoom:67%;" />

#### 5.1 Borrowing Host Bits to Create Subnet Bits

<img src="images/image-20230530220429629.png" alt="image-20230530220429629" style="zoom:67%;" />

#### 5.2 Choosing Enough Subnet and Host Bits

![image-20230530220538020](images/image-20230530220538020.png)

![image-20230530220801237](images/image-20230530220801237.png)