#  Understanding Ansible, Puppet, and Chef

## 1. **Device Configuration Challenges and Solutions**

### 1.1 **Configuration Drift**

![image-20230607092341425](images/image-20230607092341425.png)

### 1.2 **Centralized Configuration Files and Version Control**

![image-20230607093140153](images/image-20230607093140153.png)



### 1.3 **Configuration Monitoring and Enforcement**

![image-20230607093342807](images/image-20230607093342807.png)

Using the model shown in Figure 19-4 still has dangers. Former correct con- figuration changes might be overwritten, and made incorrect, by future changes. In other words, eventually, some configuration drift can occur.

![image-20230607093525792](images/image-20230607093525792.png)



### 1.4 **Configuration Provisioning**

Configuration provisioning refers to how to provision or deploy changes to the configura- tion once made by changing files in the configuration management system. As one of the primary functions of a configuration management tool, you would likely see features like these:

![image-20230607094018659](images/image-20230607094018659.png)

![image-20230607094030442](images/image-20230607094030442.png)

**Configuration Templates and Variables**

<img src="images/image-20230607094413034.png" alt="image-20230607094413034" style="zoom:50%;" />

![image-20230607094431110](images/image-20230607094431110.png)

![image-20230607094442552](images/image-20230607094442552.png)

![image-20230607094519239](images/image-20230607094519239.png)

**Files That Control Configuration Automation**

<img src="images/image-20230607094740329.png" alt="image-20230607094740329" style="zoom:50%;" />



## 2. **Ansible, Puppet, and Chef Basics**

Ansible, Puppet, and Chef are software packages. You can purchase each tool, with varia- tions on which package. However, they all also have different free options that allow you to download and learn about the tools, although you might need to run a Linux guest because some of the tools do not run in a Windows OS.

### 2.1 **Ansible**

<img src="images/image-20230607095053401.png" alt="image-20230607095053401" style="zoom:50%;" />

As far as how Ansible works for managing network devices, it uses an agentless archi- tecture. That means Ansible does not rely on any code (agent) running on the network device. Instead, Ansible relies on features typical in network devices, namely SSH and/or NETCONF, to make changes and extract information. When using SSH, the Ansible control node actually makes changes to the device like any other SSH user would do, but doing the work with Ansible code, rather than with a human.

![image-20230607095202729](images/image-20230607095202729.png)



### 2.2 **Puppet**

<img src="images/image-20230607095310170.png" alt="image-20230607095310170" style="zoom:50%;" />

<img src="images/image-20230607095512497.png" alt="image-20230607095512497" style="zoom:50%;" />

<img src="images/image-20230607095620461.png" alt="image-20230607095620461" style="zoom:50%;" />



### 2.3 **Chef**

<img src="images/image-20230607095703420.png" alt="image-20230607095703420" style="zoom:50%;" />



### 2.4 **Summary of Configuration Management Tools**

![image-20230607095811157](images/image-20230607095811157.png)
