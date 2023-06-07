# Understanding REST and JSON

The CCNA blueprint mentions one type of API—**REpresentational State Transfer (REST)**—because of its popularity as a type of API in networking automation applications.

## 1. **REST-Based APIs**

### 1.1 **REST-Based (RESTful) APIs**

Those six attributes are

<img src="images/image-20230607082309661.png" alt="image-20230607082309661" style="zoom:50%;" />

The first three of these attributes get at the heart of how a REST API works. You can more easily see those first three features at work with networking REST APIs, so the next few paragraphs give a little more explanation about those first three points.

1. **Client/Server Architecture**

<img src="images/image-20230607082559936.png" alt="image-20230607082559936" style="zoom:50%;" />

2. **Stateless Operation**

each API request and reply does not use any other past history considered when processing the request.

3. **Cacheable (or Not)**

REST APIs require that any resource requested via an API call have a clear method by which to mark the resource as cacheable or not. The goals remain the same: improve performance by retrieving resources less often (cacheable). Note that cacheable resources are marked with a timeframe so that the client knows when to ask for a new copy of the resource again.

### 1.2 **Background: Data and Variables**

### 1.3 **REST APIs and HTTP**

Many APIs need to be available to pro- grams that run on other computers, so the API must define the type of networking proto- cols supported by the API—and many REST-based APIs use the HTTP protocol.

**Software CRUD Actions and HTTP Verbs**

<img src="images/image-20230607083304631.png" alt="image-20230607083304631" style="zoom:50%;" />

<img src="images/image-20230607083627655.png" alt="image-20230607083627655" style="zoom:50%;" />

![image-20230607083701658](images/image-20230607083701658.png)

**Using URIs with HTTP to Specify the Resource**

<img src="images/image-20230607083947112.png" alt="image-20230607083947112" style="zoom:50%;" />

<img src="images/image-20230607084054054.png" alt="image-20230607084054054" style="zoom:50%;" />



## 2. **Data Serialization and JSON**

### 2.1 **The Need for a Data Model with APIs**

<img src="images/image-20230607084856823.png" alt="image-20230607084856823" style="zoom:50%;" />



### 2.2 **Data Serialization Languages**

**JSON**

**XML**

**YAML**

<img src="images/image-20230607085318466.png" alt="image-20230607085318466" style="zoom:50%;" />

**Summary of Data Serialization**

![image-20230607085343853](images/image-20230607085343853.png)



### 2.3 **Interpreting JSON**

#### 2.3.1 Interpreting JSON Key:Value Pairs

![image-20230607085958272](images/image-20230607085958272.png)

![image-20230607090010364](images/image-20230607090010364.png)

![image-20230607090037710](images/image-20230607090037710.png)



#### 2.3.2 Interpreting JSON Objects and Arrays

**NOTE** Python, the most common language to use for network automation, **converts JSON objects to Python dictionaries, and JSON arrays to Python lists.** For general conversation, many people refer to the JSON structures as dictionaries and lists rather than as objects and arrays.

![image-20230607090232417](images/image-20230607090232417.png)

![image-20230607090246862](images/image-20230607090246862.png)

![image-20230607090320758](images/image-20230607090320758.png)

![image-20230607090443626](images/image-20230607090443626.png)![image-20230607090509800](images/image-20230607090509800.png)

![image-20230607090601823](images/image-20230607090601823.png)

#### 2.3.3 Minified and Beautified JSON









