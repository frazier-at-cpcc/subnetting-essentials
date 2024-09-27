# Subnetting Essentials
Welcome to the Subnetting Essentials course! This course is designed to give you a strong foundational understanding of subnetting, a critical skill for network professionals. Whether you are new to the concept or looking to strengthen your subnetting skills, this course will guide you through the essentials and beyond.

**Learning Objectives**
=======================
- Understand the basic principles of IP addressing and subnetting
- Perform binary and decimal conversions as they apply to subnetting
- Learn to identify network and broadcast addresses
- Calculate subnet sizes and custom subnet masks
- Apply practical subnetting techniques for real-world network scenarios

**Course Outline**
==================
1. **Introduction to IP Addressing**
- IP Address Classes
- Private Address Spaces
- Special Address Ranges
- Default Subnet Masks
- Activities and Assessments

2. **Binary and Decimal Conversions**
- Binary to Decimal Conversion
- Decimal to Binary Conversion
- ANDing with Default and Custom Subnet Masks
- Activities and Assessments

3. **Subnetting Calculations**
- Subnetting Techniques and Calculations
- Custom Subnet Masks
- Network and Broadcast Address Identification
- Activities and Assessments

4. **Practical Subnetting**
- Variable Length Subnet Masks (VLSM)
- Seven Second Subnetting Method
- Addressing Scheme Design
- Network Growth Planning

5. **Summative Assessment**
- Comprehensive subnetting assessment

Throughout this lesson, you'll engage in hands-on activities, interactive quizzes, and practical exercises to solidify your knowledge. By the end, you’ll be prepared to design and implement subnetting solutions for complex networking environments.

---

**Let's dive into Subnetting Essentials!**

## Introduction to IP Addressing
In this section, we will explore the fundamental concepts of IP addressing, which is the backbone of modern network communication. Understanding how IP addresses are structured, classified, and used is essential for effective network design and management. By the end of this section, you'll be familiar with various IP address classes, private and special-use addresses, and default subnet masks.

**Learning Objectives**
=======================
- Understand the structure of IP addresses
- Learn about different IP address classes (A, B, C, D, E)
- Distinguish between private and public IP addresses
- Identify special address ranges and their uses
- Recognize default subnet masks and their significance in networking

**Topics Covered**
===================
1. **IP Address Classes**
   - Characteristics and ranges of each class
   - Typical use cases for each class
2. **Private Address Spaces**
   - 10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16
   - Their significance and applications
3. **Special Address Ranges**
   - Loopback, link-local, and multicast addresses
   - Their specific use cases and purposes in networking
4. **Default Subnet Masks**
   - Definition and importance of default subnet masks
   - How default subnet masks apply to different IP address classes

---

Let’s begin by diving into IP address classes, starting with Class A addresses.

### IP Address Classes

| Class | Range                          | Default Subnet Mask | Hosts per Network | Use Case |
|-------|---------------------------------|---------------------|-------------------|----------|
| A     | 0.0.0.0 to 127.255.255.255      | 255.0.0.0           | 16,777,214        | Large ISPs or enterprises |
| B     | 128.0.0.0 to 191.255.255.255    | 255.255.0.0         | 65,534            | Universities, organizations |
| C     | 192.0.0.0 to 223.255.255.255    | 255.255.255.0       | 254               | Small businesses, local networks |
| D     | 224.0.0.0 to 239.255.255.255    | N/A                 | N/A               | Multicasting (e.g., streaming) |
| E     | 240.0.0.0 to 255.255.255.255    | N/A                 | N/A               | Research, experimental use |


IP addresses are categorized into five classes (A, B, C, D, E) based on their range and intended use. Understanding these classes is fundamental for network addressing and design, as each class has its own characteristics regarding the number of networks and hosts.

**Class A**
===========
- **Range:** 0.0.0.0 to 127.255.255.255
- **Default Subnet Mask:** 255.0.0.0
- **Networks Available:** 128
- **Hosts per Network:** 16,777,214
- **Use Case:** Suitable for very large networks such as those used by ISPs or large enterprises.
  
**Class B**
================
- **Range:** 128.0.0.0 to 191.255.255.255
- **Default Subnet Mask:** 255.255.0.0
- **Networks Available:** 16,384
- **Hosts per Network:** 65,534
- **Use Case:** Used for medium to large networks such as universities or large organizations.

**Class C**
===========
- **Range:** 192.0.0.0 to 223.255.255.255
- **Default Subnet Mask:** 255.255.255.0
- **Networks Available:** 2,097,152
- **Hosts per Network:** 254
- **Use Case:** Commonly used for small to medium-sized networks such as small businesses or local networks.

**Class D**
===========
- **Range:** 224.0.0.0 to 239.255.255.255
- **Purpose:** Reserved for multicast communication, where data is sent to multiple recipients at once.
- **Use Case:** Typically used for services such as streaming video, teleconferencing, and other multicast applications.

**Class E**
===========
- **Range:** 240.0.0.0 to 255.255.255.255
- **Purpose:** Reserved for experimental and future use.
- **Use Case:** Not typically assigned for public use and is reserved for research and development purposes.

Now that you have an understanding of the IP address classes, let’s move on to the concept of **Private Address Spaces**.

### Private Address Spaces
Private IP address spaces are reserved for use within private networks and are not routable on the global internet. These addresses allow organizations to create internal networks without consuming public IP address space. Devices on these private networks communicate using local addressing but require Network Address Translation (NAT) to communicate with external networks.

**Private Address Ranges**
==========================

| Class | Private Range               | Hosts per Network   | Use Case                 |
|-------|-----------------------------|---------------------|--------------------------|
| A     | 10.0.0.0 to 10.255.255.255   | 16,777,216          | Large private networks   |
| B     | 172.16.0.0 to 172.31.255.255 | 1,048,576           | Medium-sized networks    |
| C     | 192.168.0.0 to 192.168.255.255 | 65,536            | Small office/home networks|

The private IP address spaces are divided into three major ranges based on IP class:

**Class A Private Range:** `10.0.0.0/8`
-------
- **Range:** 10.0.0.0 to 10.255.255.255
- **Hosts per Network:** 16,777,216
- **Use Case:** Suitable for very large private networks, such as those used by large organizations or data centers.

**Class B Private Range:** `172.16.0.0/12`
-------
- **Range:** 172.16.0.0 to 172.31.255.255
- **Hosts per Network:** 1,048,576
- **Use Case:** Used for medium to large-sized private networks, often found in organizations with multiple departments or locations.

**Class C Private Range:** `192.168.0.0/16`
--------
- **Range:** 192.168.0.0 to 192.168.255.255
- **Hosts per Network:** 65,536
- **Use Case:** Commonly used for small office or home networks (SOHO).

**Purpose of Private IP Addresses**
-----------------------------------
Private address spaces are used to:
- Conserve globally unique IPv4 addresses by allowing reuse within private networks.
- Enable internal communication within an organization without exposing internal devices to the public internet.
- Allow multiple devices in private networks to share a single public IP address through Network Address Translation (NAT).

**Private vs Public IP Addressing**
-----------------------------------
- **Private IP Addresses:** 
  - Are not routable on the public internet.
  - Must be unique within the local network but can be reused across different private networks.

- **Public IP Addresses:** 
  - Are globally unique and routable on the public internet.
  - Assigned by an internet service provider (ISP) or a regional internet registry (RIR).

>**Example Scenarios**
>---------------------
>1. **Corporate Network:**
>   A large enterprise uses the `10.0.0.0/8` private range for its internal departments, with each department allocated a different subnet (e.g., 10.1.0.0/16 for HR, 10.2.0.0/16 for IT).
>
>2. **Home Network:**
>    A home network uses the `192.168.0.0/24` range to assign private addresses to devices such as computers, smartphones, and smart home devices.
> 
> Private IP addresses are essential for managing internal communication in networks and reducing the demand for public IP addresses. These addresses are widely used in corporate networks, homes, and small businesses, providing flexibility and security by keeping internal traffic within the local network.
>
> ---
> 
> Next, we will explore **Special Address Ranges** that are reserved for specific purposes in networking.

### Special Address Ranges

| Special Address Range      | Purpose                     | Example Use Case                       |
|----------------------------|-----------------------------|----------------------------------------|
| 127.0.0.0/8 (__Loopback__)      | Internal testing and diagnostics | Testing software on local machine      |
| 169.254.0.0/16 (__Link-local__) | Communication without DHCP   | Devices communicating in absence of DHCP |
| 224.0.0.0/4 (__Multicast__)     | Sending data to multiple devices | Streaming video to multiple devices    |
| 233.0.0.0/8 (__Anycast__)       | Routing to nearest receiver  | CDN directing traffic to nearest server |
| Network-specific Broadcast  | Sending data to all devices  | ARP requests or network discovery      |


In addition to private IP address spaces, there are several special address ranges that serve specific purposes in networking. These ranges are reserved for use in testing, multicasting, and device communication within a local network. Understanding these ranges is crucial for network administrators to ensure proper network configurations and operations.

**Loopback Address Range**
--------------------------
- **Range:** `127.0.0.0/8` (typically `127.0.0.1` is used)
- **Purpose:** The loopback address is used for testing and diagnostics within a local machine. It allows a device to send network traffic to itself, which is useful for testing network software.
- **Example Use Case:** Testing a web server running on the same machine using `127.0.0.1`.

**Link-Local Address Range**
----------------------------
- **Range:** `169.254.0.0/16`
- **Purpose:** Link-local addresses are automatically assigned when a device cannot obtain an IP address from a DHCP server. These addresses are used for communication within the local network but are not routable on the wider internet.
- **Example Use Case:** When a device connects to a network without a DHCP server, it assigns itself a link-local address, allowing it to communicate with other devices on the same network.

**Multicast Address Range**
---------------------------
- **Range:** `224.0.0.0/4`
- **Purpose:** Multicast addresses are used for the simultaneous transmission of data to multiple recipients. This is useful for services such as streaming media or video conferencing.
- **Example Use Case:** Sending a video stream to multiple devices on a network using a multicast address like `224.0.1.1`.

**Anycast Address Range**
-------------------------
- **Range:** Reserved IPs within `233.0.0.0/8`
- **Purpose:** Anycast is used to route data to the nearest or best destination in a group of potential receivers that share the same address. It helps improve performance and reliability by routing traffic to the closest server.
- **Example Use Case:** Content Delivery Networks (CDNs) use anycast to direct users to the nearest server for faster loading times.

**Broadcast Address**
---------------------
- **Range:** Varies depending on the subnet (e.g., `192.168.1.255` for a `/24` subnet)
- **Purpose:** Broadcast addresses allow data to be sent to all devices on a specific network. Broadcast traffic is used for network discovery and communication.
- **Example Use Case:** ARP (Address Resolution Protocol) requests are sent to the broadcast address to find the MAC address associated with an IP address.

Special address ranges play a critical role in various networking functions, from device diagnostics and testing to efficient data distribution through multicast and anycast routing. Understanding these addresses ensures that networks are configured properly for both internal and external communication.

---

Next, we will explore **Default Subnet Masks** and how they are used to segment networks.

### Default Subnet Masks
| IP Class | Address Range               | Default Subnet Mask | Network Bits | Host Bits   | Maximum Hosts per Network |
|----------|-----------------------------|---------------------|--------------|-------------|---------------------------|
| A        | 0.0.0.0 – 127.255.255.255    | 255.0.0.0           | 8            | 24          | 16,777,214                 |
| B        | 128.0.0.0 – 191.255.255.255  | 255.255.0.0         | 16           | 16          | 65,534                     |
| C        | 192.0.0.0 – 223.255.255.255  | 255.255.255.0       | 24           | 8           | 254                        |

A subnet mask is a 32-bit number that segments an IP address into the network and host portions. The subnet mask helps determine which part of the IP address identifies the network and which part identifies the host (a device or interface). Each class of IP address (A, B, C) has a default subnet mask that defines how much of the address is used for the network and how much for the hosts.

**Class A Subnet Mask (255.0.0.0)**
-----------------------------------
- **Network Portion:** The first 8 bits (1st octet) identify the network.
- **Host Portion:** The remaining 24 bits (3 octets) identify hosts.
- **Use Case:** Class A networks are suitable for very large networks with millions of hosts, such as ISPs and large corporations.

**Class B Subnet Mask (255.255.0.0)**
--------------------------------------
- **Network Portion:** The first 16 bits (2 octets) identify the network.
- **Host Portion:** The remaining 16 bits (2 octets) identify hosts.
- **Use Case:** Class B networks are used for medium-sized networks like large organizations or universities.

**Class C Subnet Mask (255.255.255.0)**
-----------------------------------
- **Network Portion:** The first 24 bits (3 octets) identify the network.
- **Host Portion:** The remaining 8 bits (1 octet) identify hosts.
- **Use Case:** Class C networks are ideal for small networks, like small businesses or home networks.

**Why Are Subnet Masks Important?**
-----------------------------------
- **Network Segmentation:** Subnet masks are used to divide a network into smaller, more manageable subnetworks.
- **Routing:** Routers use subnet masks to determine whether traffic is for a local network or if it needs to be routed to another network.
- **Network Efficiency:** By limiting the number of hosts in a network, subnet masks help minimize network traffic and reduce the chances of network collisions.

**CIDR Notation**
=================
Subnet masks can also be expressed using **CIDR (Classless Inter-Domain Routing)** notation. In CIDR, the subnet mask is represented by a slash (/) followed by the number of network bits.

- **Examples:**
  - Class A: `/8` (255.0.0.0)
  - Class B: `/16` (255.255.0.0)
  - Class C: `/24` (255.255.255.0)

> **Example: Using Subnet Masks in Practice**
>
>Suppose you have an IP address `192.168.1.10` with a default Class C subnet mask of `255.255.255.0`. To determine which part of the address represents the network and which part represents the host:
> 
> - **Network Portion:** The first three octets (`192.168.1`) represent the network.
> - **Host Portion:** The last octet (`.10`) represents the host.
> 
> Thus, the network address for `192.168.1.10` would be `192.168.1.0`, and the broadcast address would be `192.168.1.255`.
> 
> Default subnet masks play a crucial role in determining the size and structure of networks. Understanding how subnet masks divide IP addresses into network and host portions helps in the design and implementation of efficient and scalable networks.

---

In the next section, we will engage in an **Activity** to practice what we've learned about subnet masks and IP address classes.

### Activity
<iframe src="https://frazier-at-cpcc.github.io/subnetting-essentials/classid.html" style="border:0px #ffffff none;" name="myiFrame" scrolling="no" frameborder="1" marginheight="0px" marginwidth="0px" height="600px" width="600px" allowfullscreen></iframe>

### Check Your Knowledge
This quiz will help reinforce your understanding of IP address classes (A, B, C, D, and E). You'll need to identify the class of various IP addresses based on their range. Let's test your knowledge!

**Instructions**
----------------
For each of the following IP addresses, identify which class (A, B, C, D, or E) they belong to. Select the correct option for each question.

**Quiz**
========

Question 1: What class does the IP address `240.1.1.1` belong to?
-----------------------------------------------------------------

[( )] Class A
[( )] Class B
[( )] Class C
[( )] Class D
[(X)] Class E


Question 2: What class does the IP address `10.1.1.1` belong to?
----------------------------------------------------------------

[(X)] Class A
[( )] Class B
[( )] Class C
[( )] Class D
[( )] Class E


Question 3: What class does the IP address `224.0.0.1` belong to?
-----------------------------------------------------------------

[( )] Class A
[( )] Class B
[( )] Class C
[(X)] Class D
[( )] Class E


Question 4: What class does the IP address `192.168.1.100` belong to?
---------------------------------------------------------------------

[( )] Class A
[( )] Class B
[(X)] Class C
[( )] Class D
[( )] Class E


Question 5: What class does the IP address `172.16.0.5` belong to?
------------------------------------------------------------------

[( )] Class A
[(X)] Class B
[( )] Class C
[( )] Class D
[( )] Class E
*****************************************************************************************************************************************************************
> **Review Your Answers**
> 
> Once you've answered all the questions, review your answers to see which IP address classes you've identified correctly. If you need more practice, review the material on IP address classes (A, B, C, D, E) and take the quiz again.
> 
> **Summary of IP Address Classes**
> 
> - **Class A**: `0.0.0.0` to `127.255.255.255`
> - **Class B**: `128.0.0.0` to `191.255.255.255`
> - **Class C**: `192.0.0.0` to `223.255.255.255`
> - **Class D**: `224.0.0.0` to `239.255.255.255` (Multicast)
> - **Class E**: `240.0.0.0` to `255.255.255.255` (Experimental)

---

Congratulations on completing this quiz! Continue practicing and solidifying your understanding of IP address classes.
*****************************************************************************************************************************************************************

## Binary and Decimal Conversions
In networking, understanding how to convert between binary and decimal numbers is essential, as IP addresses and subnet masks are represented in both formats. This module will guide you through the process of converting decimal numbers to binary and vice versa, which is crucial for IP address manipulation, subnetting, and network calculations.

**Learning Objectives**
=======================

By the end of this module, you will be able to:

- Understand the relationship between binary and decimal numbering systems.
- Convert decimal IP addresses to binary format.
- Convert binary IP addresses to decimal format.
- Perform bitwise operations like ANDing with subnet masks for network identification.

IP addresses are represented in binary by computers, but they are often displayed in decimal format for easier readability by humans. Understanding how to convert between these two systems allows network professionals to perform critical tasks such as subnetting, IP address calculation, and overall network troubleshooting. 

---
Now, let’s begin by diving into the basics of **Binary to Decimal Conversion**, where you'll learn to convert binary IP addresses into their decimal equivalents.

### Binary to Decimal Conversion

IP addresses are represented as a series of 32 binary digits (1s and 0s), but humans often use decimal notation for readability. Converting binary to decimal is an essential skill for understanding how devices communicate on a network. This section will guide you through the process of converting binary IP addresses into decimal format.

**Steps for Binary to Decimal Conversion**

To convert a binary number to its decimal equivalent, you can follow these steps:

1. **Write down the binary number**: Start with the binary IP address, which is usually divided into four octets.
   
2. **Assign powers of 2 to each bit**: Starting from the rightmost bit (least significant), assign the value of 2 raised to the power of its position in the binary sequence (from right to left, starting with 0).

3. **Multiply each bit by its corresponding power of 2**: Only the bits that are set to 1 contribute to the final decimal value.

4. **Add the results**: Sum the values from each octet to get the final decimal number for each.

> **Example: Converting Binary to Decimal**
> Let’s convert the binary IP address `11000000.10101000.00000001.00000001` to decimal.
> 
>1. **Binary IP Address**: `11000000.10101000.00000001.00000001`
>   
>2. **Break it down into octets**:
>   - First octet: `11000000`
>   - Second octet: `10101000`
>   - Third octet: `00000001`
>   - Fourth octet: `00000001`
>
>3. **Convert each octet from binary to decimal**:
>
>   - **First octet**: `11000000`
>     - (1 × 2^7) + (1 × 2^6) + (0 × 2^5) + (0 × 2^4) + (0 × 2^3) + (0 × 2^2) + (0 × 2^1) + (0 × 2^0)
>     - = 128 + 64 = **192**
>
>   - **Second octet**: `10101000`
>     - (1 × 2^7) + (0 × 2^6) + (1 × 2^5) + (0 × 2^4) + (1 × 2^3) + (0 × 2^2) + (0 × 2^1) + (0 × 2^0)
>     - = 128 + 32 + 8 = **168**
>
>   - **Third octet**: `00000001`
>     - (0 × 2^7) + (0 × 2^6) + (0 × 2^5) + (0 × 2^4) + (0 × 2^3) + (0 × 2^2) + (0 × 2^1) + (1 × 2^0)
>     - = 1
>
>   - **Fourth octet**: `00000001`
>     - (0 × 2^7) + (0 × 2^6) + (0 × 2^5) + (0 × 2^4) + (0 × 2^3) + (0 × 2^2) + (0 × 2^1) + (1 × 2^0)
>     - = 1
>
> 4. **Final Decimal Address**: Combine the decimal values from each octet:
>    - `192.168.1.1`

**Practice Problem**

Let'ss try converting the following binary IP address to decimal:
- **Binary IP Address**: `11000000.10101000.00000010.00000011`

What is the decimal equivalent?

      [[192.168.2.3]]
**************************************************************************************************
> **Solution to Practice Problem**
> 
> - First octet: `11000000` = **192**
> - Second octet: `10101000` = **168**
> - Third octet: `00000010` = **2**
> - Fourth octet: `00000011` = **3**
> 
> - **Final Decimal IP Address**: `192.168.2.3`
***************************************************************************************************


Binary to decimal conversion is crucial for interpreting IP addresses and understanding how devices communicate over a network. This skill will help you perform essential tasks such as subnetting and network design.

---

Next, let’s move on to **Decimal to Binary Conversion** to learn how to reverse the process and convert decimal IP addresses back to binary.

### Decimal to Binary Conversion


Just as binary can be converted to decimal, it’s also important to know how to convert decimal numbers back into binary. This is especially useful in networking when determining network and host portions of an IP address. In this section, we will walk through the steps to convert a decimal IP address into binary format.

**Steps for Decimal to Binary Conversion**

To convert a decimal number to its binary equivalent, follow these steps:

1. **Write down the decimal number**: Start with the decimal IP address, which consists of four octets (numbers between 0 and 255).

2. **Divide the decimal number by 2**: For each octet, continuously divide the number by 2, noting the remainder each time.

3. **Record the remainders**: The remainder from each division step forms a binary digit (1 or 0).

4. **Reverse the order of the remainders**: The remainders form the binary equivalent, starting from the least significant bit (rightmost) to the most significant bit (leftmost).

> **Example: Converting Decimal to Binary**
> 
> Let’s convert the decimal IP address `192.168.1.1` to binary.
> 
> 1. **Decimal IP Address**: `192.168.1.1`
> 
> 2. **Convert each octet to binary**:
> 
>    - **First octet**: `192`
>      - 192 ÷ 2 = 96, remainder = 0
>      - 96 ÷ 2 = 48, remainder = 0
>      - 48 ÷ 2 = 24, remainder = 0
>      - 24 ÷ 2 = 12, remainder = 0
>      - 12 ÷ 2 = 6, remainder = 0
>      - 6 ÷ 2 = 3, remainder = 0
>      - 3 ÷ 2 = 1, remainder = 1
>      - 1 ÷ 2 = 0, remainder = 1
>      - **Binary for 192** = `11000000`
> 
>    - **Second octet**: `168`
>      - 168 ÷ 2 = 84, remainder = 0
>      - 84 ÷ 2 = 42, remainder = 0
>      - 42 ÷ 2 = 21, remainder = 0
>      - 21 ÷ 2 = 10, remainder = 1
>      - 10 ÷ 2 = 5, remainder = 0
>      - 5 ÷ 2 = 2, remainder = 1
>      - 2 ÷ 2 = 1, remainder = 0
>      - 1 ÷ 2 = 0, remainder = 1
>      - **Binary for 168** = `10101000`
> 
>    - **Third octet**: `1`
>      - 1 ÷ 2 = 0, remainder = 1
>      - **Binary for 1** = `00000001`
> 
>    - **Fourth octet**: `1`
>      - 1 ÷ 2 = 0, remainder = 1
>      - **Binary for 1** = `00000001`
> 
> 3. **Final Binary Address**: Combine the binary values from each octet:
>    - `11000000.10101000.00000001.00000001`

**Practice Problem**

Let’s try converting the following decimal IP address to binary:
- **Decimal IP Address**: `10.0.15.255`

What is the binary equivalent?

      [[00001010.00000000.00001111.11111111]]
******************************************************************************************************************
> **Solution to Practice Problem**
> 
> - **First octet**: `10`
>   - 10 ÷ 2 = 5, remainder = 0
>   - 5 ÷ 2 = 2, remainder = 1
>   - 2 ÷ 2 = 1, remainder = 0
>   - 1 ÷ 2 = 0, remainder = 1
>   - **Binary for 10** = `00001010`
> 
> - **Second octet**: `0`
>   - **Binary for 0** = `00000000`
> 
> - **Third octet**: `15`
>   - 15 ÷ 2 = 7, remainder = 1
>   - 7 ÷ 2 = 3, remainder = 1
>   - 3 ÷ 2 = 1, remainder = 1
>   - 1 ÷ 2 = 0, remainder = 1
>   - **Binary for 15** = `00001111`
> 
> - **Fourth octet**: `255`
>   - 255 ÷ 2 = 127, remainder = 1
>   - 127 ÷ 2 = 63, remainder = 1
>   - 63 ÷ 2 = 31, remainder = 1
>   - 31 ÷ 2 = 15, remainder = 1
>   - 15 ÷ 2 = 7, remainder = 1
>   - 7 ÷ 2 = 3, remainder = 1
>   - 3 ÷ 2 = 1, remainder = 1
>   - 1 ÷ 2 = 0, remainder = 1
>   - **Binary for 255** = `11111111`
> 
> - **Final Binary IP Address**: `00001010.00000000.00001111.11111111`

Converting decimal to binary is an essential skill when working with IP addresses in networking. Understanding how to perform this conversion allows you to manipulate and analyze IP addresses for tasks like subnetting and IP planning.

---

In the next section, we will explore **ANDing with Subnet Masks** and learn how to identify the network portion of an IP address.
******************************************************************************************************************

### ANDing with Default Subnet Masks


ANDing is a bitwise operation used in networking to identify the network portion of an IP address. This operation involves comparing an IP address with its corresponding subnet mask to determine which part of the address belongs to the network and which part is reserved for hosts. Understanding how to AND with default subnet masks is crucial for tasks like subnetting and routing.

**What is ANDing?**

ANDing is a binary operation where two bits are compared:
- 1 AND 1 = 1
- 1 AND 0 = 0
- 0 AND 0 = 0

When we AND an IP address with a subnet mask, we compare each bit in the IP address with the corresponding bit in the subnet mask. This operation identifies the network portion (the part of the IP address that corresponds to the 1s in the subnet mask).

**Steps for ANDing with Default Subnet Masks**

1. **Convert the IP address and subnet mask to binary**: Write down the binary equivalent of both the IP address and the default subnet mask.

2. **Perform the AND operation**: Compare each bit of the IP address with the corresponding bit in the subnet mask. Apply the AND rule to determine the result.

3. **Result**: The result of the AND operation gives you the network portion of the IP address.

> **Example: ANDing with a Default Subnet Mask**
> 
> Let’s say you have the following IP address and a default Class C subnet mask:
> 
> - **IP Address**: `192.168.1.10`
> - **Default Subnet Mask**: `255.255.255.0`
> 
> 1. **Convert to Binary**:
> 
>    - **IP Address**: `192.168.1.10`
>      - `11000000.10101000.00000001.00001010`
> 
>    - **Subnet Mask**: `255.255.255.0`
>      - `11111111.11111111.11111111.00000000`
> 
> 2. **AND the IP Address and Subnet Mask**:
> 
>    - IP: `11000000.10101000.00000001.00001010`
>    - Mask: `11111111.11111111.11111111.00000000`
>    - Result: `11000000.10101000.00000001.00000000`
> 
> 3. **Convert the Result to Decimal**:
>    - **Network Address**: `192.168.1.0`
> 
> This shows that the network portion of the IP address `192.168.1.10` is `192.168.1.0`.

**Practice Problem**

Try ANDing the following IP address with the default Class B subnet mask:

- **IP Address**: `172.16.45.78`
- **Subnet Mask**: `255.255.0.0`

**Your Turn**: What is the network address?

      [[172.16.0.0]]
***********************************************************************
> **Solution to Practice Problem**
> 
> 1. **Convert to Binary**:
>   - **IP Address**: `172.16.45.78`
>     - `10101100.00010000.00101101.01001110`
>   - **Subnet Mask**: `255.255.0.0`
>     - `11111111.11111111.00000000.00000000`
> 
> 2. **AND the IP Address and Subnet Mask**:
>   - IP: `10101100.00010000.00101101.01001110`
>   - Mask: `11111111.11111111.00000000.00000000`
>   - Result: `10101100.00010000.00000000.00000000`
>
> 3. **Convert the Result to Decimal**:
>   - **Network Address**: `172.16.0.0`
***********************************************************************

Understanding ANDing with default subnet masks is fundamental for working with IP networks. It helps network administrators quickly determine the network segment an IP address belongs to, making tasks like subnetting, routing, and IP planning easier.

---

In the next section, we will explore **ANDing with Custom Subnet Masks**, where we apply the same principle to custom subnet sizes.


### ANDing with Custom Subnet Masks


While ANDing with default subnet masks helps identify the network portion for standard networks (Class A, B, or C), many networks use custom subnet masks to divide the network into smaller subnets. Custom subnet masks are used when networks require more flexibility in the number of hosts or subnets. This section will guide you through how to perform the AND operation using custom subnet masks.

**What is a Custom Subnet Mask?**

A custom subnet mask extends the number of network bits beyond the default mask, allowing you to create subnets of different sizes. For example, instead of using the default Class C mask `/24` (255.255.255.0), you could use `/26` (255.255.255.192) to create more subnets with fewer hosts in each.

**Steps for ANDing with Custom Subnet Masks**

1. **Convert the IP address and custom subnet mask to binary**: Write down the binary equivalents of both the IP address and the custom subnet mask.

2. **Perform the AND operation**: Compare each bit of the IP address with the corresponding bit in the subnet mask, using the AND rule (1 AND 1 = 1, otherwise 0).

3. **Result**: The result of the AND operation gives you the network address for that particular subnet.

> **Example: ANDing with a Custom Subnet Mask**
> 
> Let’s take an IP address and a custom subnet mask:
> 
> - **IP Address**: `192.168.1.130`
> - **Custom Subnet Mask**: `255.255.255.192` (This is a `/26` subnet mask, which allows for 64 IP addresses per subnet)
> 
> 1. **Convert to Binary**:
> 
>    - **IP Address**: `192.168.1.130`
>     - `11000000.10101000.00000001.10000010`
>   
>   - **Custom Subnet Mask**: `255.255.255.192`
>     - `11111111.11111111.11111111.11000000`
>
> 2. **AND the IP Address and Subnet Mask**:
> 
>    - IP: `11000000.10101000.00000001.10000010`
>   - Mask: `11111111.11111111.11111111.11000000`
>   - Result: `11000000.10101000.00000001.10000000`
> 
> 3. **Convert the Result to Decimal**:
>    - **Network Address**: `192.168.1.128`
> 
> This shows that the IP address `192.168.1.130` belongs to the subnet `192.168.1.128/26`.

**Practice Problem**

Let’s practice ANDing with a custom subnet mask. Perform the AND operation for the following IP address and custom subnet mask:

- **IP Address**: `10.10.5.200`
- **Custom Subnet Mask**: `255.255.255.224` (This is a `/27` subnet mask)

- What is the network address?

**Your Turn**: Please enter the network address for the IP address above.

      [[10.10.5.192]]
**********************************************************************************************************************************
> **Solution to Practice Problem**
>
> 1. **Convert to Binary**:
>    - **IP Address**: `10.10.5.200`
>    - `00001010.00001010.00000101.11001000`
>   
>   - **Custom Subnet Mask**: `255.255.255.224`
>     - `11111111.11111111.11111111.11100000`
>
> 2. **AND the IP Address and Subnet Mask**:
>    - IP: `00001010.00001010.00000101.11001000`
>    - Mask: `11111111.11111111.11111111.11100000`
>    - Result: `00001010.00001010.00000101.11000000`
> 
> 3. **Convert the Result to Decimal**:
>    - **Network Address**: `10.10.5.192`

**Why Use Custom Subnet Masks?**

Custom subnet masks offer more flexibility in network design by allowing you to:
- Create multiple subnets of different sizes from a larger network block.
- Optimize the use of IP address space by reducing wasted addresses.
- Segment traffic for better security and management.



ANDing with custom subnet masks is essential for modern network design, where creating subnets of varying sizes is often required. By mastering this skill, you can design efficient networks that make better use of available IP address space.

### Activity
<iframe src="https://frazier-at-cpcc.github.io/subnetting-essentials/binary-decimal.html" style="border:0px #ffffff none;" name="myiFrame" scrolling="no" frameborder="1" marginheight="0px" marginwidth="0px" height="600px" width="600px" allowfullscreen></iframe>
<iframe src="https://frazier-at-cpcc.github.io/subnetting-essentials/decimal-binary.html" style="border:0px #ffffff none;" name="myiFrame" scrolling="no" frameborder="1" marginheight="0px" marginwidth="0px" height="600px" width="600px" allowfullscreen></iframe>

## Subnetting Calculations
Subnetting involves dividing a larger network into smaller, more manageable subnets. Each subnet operates as an independent network, allowing you to efficiently use IP address space, improve security, and optimize network performance. In this section, we will focus on the calculations needed to determine the appropriate subnet mask, calculate the number of subnets and hosts, and identify key network elements such as network and broadcast addresses.

**Steps for Subnetting Calculations**

To perform subnetting calculations, follow these steps:

1. **Determine the Subnet Mask**:
   - Start by deciding how many subnets or hosts you need. The subnet mask will define how many bits are used for the network versus the hosts.

2. **Calculate the Number of Subnets**:
   - Use the formula:  
     \[
     \text{Number of Subnets} = 2^n
     \]
     where \( n \) is the number of bits borrowed from the host portion of the address.

3. **Calculate the Number of Hosts per Subnet**:
   - Use the formula:  
     \[
     \text{Number of Hosts} = 2^h - 2
     \]
     where \( h \) is the number of host bits, and the subtraction of 2 accounts for the network and broadcast addresses.

4. **Identify the Network and Broadcast Addresses**:
   - The network address is the first address in each subnet, and the broadcast address is the last. The range between these addresses represents usable host addresses.

> **Example: Subnetting a Class C Network**
> 
> Let’s take the network `192.168.10.0/24` and subnet it into 4 subnets.
> 
> 1. **Determine the Subnet Mask**:
>    - To create 4 subnets, we need to borrow 2 bits from the host portion (because \( 2^2 = 4 \)).
>    - The default Class C subnet mask is `255.255.255.0` (`/24`). Borrowing 2 bits gives us a new subnet mask of `255.255.255.192` (`/26`).
> 
> 2. **Calculate the Number of Hosts per Subnet**:
>    - With 6 bits remaining for hosts (8 bits in the original Class C - 2 bits borrowed for subnetting), we can calculate the number of hosts per subnet:
>     \[
>     2^6 - 2 = 62 \text{ hosts per subnet}
>     \]
> 
> 3. **Identify the Network and Broadcast Addresses**:
> 
>    - **Subnet 1**:  
>      - Network Address: `192.168.10.0`
>      - Broadcast Address: `192.168.10.63`
>      - Usable IP Range: `192.168.10.1` – `192.168.10.62`
>      
>    - **Subnet 2**:  
>      - Network Address: `192.168.10.64`
>      - Broadcast Address: `192.168.10.127`
>      - Usable IP Range: `192.168.10.65` – `192.168.10.126`
>      
>    - **Subnet 3**:  
>      - Network Address: `192.168.10.128`
>      - Broadcast Address: `192.168.10.191`
>      - Usable IP Range: `192.168.10.129` – `192.168.10.190`
>      
>    - **Subnet 4**:  
>      - Network Address: `192.168.10.192`
>      - Broadcast Address: `192.168.10.255`
>      - Usable IP Range: `192.168.10.193` – `192.168.10.254`

**Practice Problem**

You are given the network `172.16.0.0/16` and need to create 8 subnets. Calculate the subnet mask, the number of hosts per subnet, and the network and broadcast addresses for the first two subnets.

What is the subnet mask?
      [[255.255.224.0]]
**************************************************************************************************************************************
>   - Borrow 3 bits from the host portion of the Class B address (`2^3 = 8 subnets`).
>   - The new subnet mask is `255.255.224.0` (`/19`).
**************************************************************************************************************************************

How many hosts per subnet? 
      [[8190]]
**************************************************************************************************************************************
> With 13 host bits remaining, the number of hosts per subnet is: 8190

**Once you have identified the subnet mask and the number of hosts, you'll identify the network and broadcast addresses for the first two subnets.**:
   - **Subnet 1**:  
     - Network Address: `172.16.0.0`
     - Broadcast Address: `172.16.31.255`
     - Usable IP Range: `172.16.0.1` – `172.16.31.254`
   
   - **Subnet 2**:  
     - Network Address: `172.16.32.0`
     - Broadcast Address: `172.16.63.255`
     - Usable IP Range: `172.16.32.1` – `172.16.63.254`


Subnetting calculations are essential for creating subnets that meet the needs of a network, whether it’s for a small office or a large enterprise. By mastering subnetting calculations, you can design networks that optimize IP address usage, improve performance, and scale with future growth.

---

Next, let’s explore **Calculating Custom Subnet Masks**, where you'll learn to create subnet masks tailored to specific network requirements.

**************************************************************************************************************************************

### Calculating Custom Subnet Masks

Custom subnet masks allow you to create subnetworks with specific numbers of hosts and subnets, tailored to your network's needs. Calculating a custom subnet mask involves determining how many bits should be borrowed from the host portion to create the desired number of subnets. This flexibility allows network administrators to efficiently use IP address space and control network segmentation.

**Steps for Calculating a Custom Subnet Mask**

1. **Determine the Required Subnets or Hosts**:
   - Decide whether the goal is to create a specific number of subnets or to support a particular number of hosts within each subnet.

2. **Calculate the Number of Bits to Borrow**:
   - Use the formula:
     \[
     2^n \geq \text{Required Subnets}
     \]
     where \( n \) is the number of bits borrowed from the host portion.

3. **Calculate the New Subnet Mask**:
   - Add the borrowed bits to the default subnet mask for your IP class to determine the custom subnet mask.

4. **Verify the Number of Hosts per Subnet**:
   - Use the formula:
     \[
     2^h - 2 \geq \text{Required Hosts}
     \]
     where \( h \) is the remaining number of host bits.

> **Example: Creating a Custom Subnet Mask**
> 
> Let’s say you have the network `192.168.1.0/24` and you need to create 8 subnets. Here’s how you can calculate the custom subnet mask:
> 
> 1. **Determine the Number of Bits to Borrow**:
>    - You need at least 8 subnets. To calculate the number of bits required, use the formula:
>      \[
>      2^n \geq 8 \quad \text{so} \quad n = 3
>      \]
>      - Borrow 3 bits from the host portion.
> 
> 2. **Calculate the New Subnet Mask**:
>    - The default subnet mask for a Class C network is `255.255.255.0` (`/24`).
>    - Adding 3 borrowed bits changes the subnet mask to `255.255.255.224` (`/27`).
> 
> 3. **Verify the Number of Hosts per Subnet**:
>    - With 5 remaining host bits (`32 total bits - 27 network bits = 5 host bits`):
>      \[
>      2^5 - 2 = 30 \text{ hosts per subnet}
>      \]
>    - This gives you 30 usable hosts per subnet.
> 
> **Example Result**:
> You’ve created 8 subnets, each with a subnet mask of `255.255.255.224` and 30 usable hosts.

> **Practice Problem**
> 
> You are given the network `10.0.0.0/8` and need to create 16 subnets. What is the custom subnet mask, and how many hosts can each subnet support?
> 
> 1. **Determine the Number of Bits to Borrow**:
>    - You need at least 16 subnets. 
>     - Borrow 4 bits from the host portion.
> 
> 2. **Calculate the New Subnet Mask**:
>    - The default subnet mask for a Class A network is `255.0.0.0` (`/8`).
>    - Adding 4 borrowed bits changes the subnet mask to `255.240.0.0` (`/12`).
> 
> 3. **Verify the Number of Hosts per Subnet**:
>    - With 20 remaining host bits (`32 total bits - 12 network bits = 20 host bits`):
>      2^{20} - 2 = 1,048,574 hosts per subnet

Calculating custom subnet masks allows you to optimize network performance and scalability while effectively managing IP address space. This essential skill is key to designing networks that meet the unique needs of any organization.


## Practical Subnetting
### Variable Length Subnet Masks

Variable Length Subnet Masks (VLSM) is a subnetting technique that allows for more efficient use of IP address space by enabling subnets of different sizes within the same network. With VLSM, you can allocate smaller or larger subnets depending on the specific needs of different segments of your network. This flexibility is crucial for networks that must accommodate a wide variety of devices or services, each with unique IP addressing requirements.

**Why Use VLSM?**

Using VLSM provides several advantages:

- **Optimized IP Address Space**: Avoid wasting IP addresses by tailoring subnet sizes to the exact number of required hosts.
- **Efficient Network Design**: Create subnetworks that fit the needs of specific departments or services without over-provisioning.
- **Scalability**: Easily scale your network by adjusting subnet sizes as the network grows.

**Steps for Implementing VLSM**

1. **Identify Requirements**:
   - Determine how many hosts are needed for each subnet. Different subnets may require different sizes (e.g., one subnet for 50 devices, another for 200).

2. **Allocate the Largest Subnet First**:
   - Start by allocating the subnet with the largest number of hosts to ensure you have enough address space for it.

3. **Work Down to Smaller Subnets**:
   - After allocating the largest subnet, continue by assigning the remaining address space to smaller subnets, adjusting the subnet mask as needed.

4. **Apply VLSM in Hierarchical Design**:
   - Use hierarchical addressing with VLSM to group related subnets and ensure efficient routing.

**Example: Using VLSM to Design Subnets**

Suppose you are working with the network `192.168.10.0/24` and need to create subnets for three different departments with varying host requirements:
- Department 1: 100 hosts
- Department 2: 50 hosts
- Department 3: 10 hosts

**Step 1: Start with the Largest Subnet**

- **Department 1 (100 hosts)**:
  - Use a `/25` subnet mask (`255.255.255.128`), which provides 126 usable IP addresses.
  - **Subnet Range**: `192.168.10.0` to `192.168.10.127`

**Step 2: Allocate the Next Subnet**

- **Department 2 (50 hosts)**:
  - Use a `/26` subnet mask (`255.255.255.192`), which provides 62 usable IP addresses.
  - **Subnet Range**: `192.168.10.128` to `192.168.10.191`

**Step 3: Allocate the Smallest Subnet**

- **Department 3 (10 hosts)**:
  - Use a `/28` subnet mask (`255.255.255.240`), which provides 14 usable IP addresses.
  - **Subnet Range**: `192.168.10.192` to `192.168.10.207`

After allocating the subnets, the remaining address space (`192.168.10.208` to `192.168.10.255`) can be reserved for future growth or additional subnets.

> **Practice Problem**
> 
> You are given the network `10.0.0.0/16` and need to create subnets for the following:
> - Subnet 1: 500 hosts
> - Subnet 2: 200 hosts
> - Subnet 3: 50 hosts
> 
> How would you allocate the subnets using VLSM?
> 
> 
> **Solution to Practice Problem**
> 
> 1. **Subnet 1 (500 hosts)**:
>    - Use a `/23` subnet mask (`255.255.254.0`), which provides 510 usable IP addresses.
>    - **Subnet Range**: `10.0.0.0` to `10.0.1.255`
> 
> 2. **Subnet 2 (200 hosts)**:
>    - Use a `/24` subnet mask (`255.255.255.0`), which provides 254 usable IP addresses.
>    - **Subnet Range**: `10.0.2.0` to `10.0.2.255`
> 
> 3. **Subnet 3 (50 hosts)**:
>    - Use a `/26` subnet mask (`255.255.255.192`), which provides 62 usable IP addresses.
>    - **Subnet Range**: `10.0.3.0` to `10.0.3.63`

VLSM is a powerful tool that allows for more granular control over IP address allocation, helping you design efficient, scalable networks. By understanding how to use VLSM, you can optimize your IP space and create subnets that match your specific needs.

---

Next, we will explore the **Seven Second Subnetting** method, a quick technique for calculating subnets in time-sensitive situations.

### Seven Second Subnetting
Welcome to this lesson on the 7-second subnetting shortcut! This method, explained by Professor Messer, is a quick and efficient way to calculate subnet information without using complex binary-to-decimal conversions. It's particularly useful for networking exams and real-world scenarios where rapid subnet calculations are necessary.

!?[](https://www.youtube.com/watch?v=I3LBYMXBhus)


The 7-second subnetting shortcut is a method that allows you to quickly calculate subnet information without performing complex binary-to-decimal conversions. Here are the key points:

- It's similar to the magic number method but requires no calculations
- All necessary information is contained in a predefined chart
- The only math involved is adding or subtracting one for first and last IP addresses
- It works well for both online exams with whiteboards and physical testing centers

The core of the 7-second subnetting process is creating a comprehensive chart. This chart will be your reference for all subnet calculations.

Your chart should include:
1. Subnet masks
2. Networks
3. Addresses
4. Decimal subnet mask columns

Additionally, you may want to create a separate chart for subnet boundaries for quick reference.

> **Exercise**: Create your own subnetting chart. Include columns for CIDR notation (/24, /25, etc.), decimal subnet mask (255.255.255.0, 255.255.255.128, etc.), number of networks, and number of hosts per subnet.

The 7-second subnetting process consists of four main steps:

1. Convert IP addresses and subnet masks to decimal
2. Determine the subnet address
3. Find the broadcast address for the subnet
4. Calculate the first and last usable IP addresses

Let's go through each step in detail:
-------------------------------------
1. Use your chart to quickly convert CIDR notation to decimal subnet masks.
2. Reference your chart to find the network address based on the given IP and subnet mask.
3. Use your chart to determine the broadcast address for the subnet.
4. Calculate First and Last Usable IP Addresses



Practice
--------------------------------

Now that you understand the process, let's practice with various IP addresses and subnet masks.

IP: 172.16.45.178, Subnet Mask: 255.255.255.240 (/28)
-----------------------------------------------------

**Network Address**

      [[172.16.45.176]]
************************************************************************************************
> Convert the subnet mask to binary: 255.255.255.240 = 11111111.11111111.11111111.11110000
> IP in binary: 172.16.45.178 = 10101100.00010000.00101101.10110010
> Perform an AND operation between the IP address and the subnet mask:
> Network address in binary: 10101100.00010000.00101101.10110000
> Convert back to decimal: 172.16.45.176
************************************************************************************************

**Broadcast Address** 

      [[172.16.45.191]]
************************************************************************************************
> The broadcast address is the last IP in the subnet.
> Flip the host bits in the network address to all 1s:
> Broadcast address in binary: 10101100.00010000.00101101.10111111
> Convert back to decimal: 172.16.45.191
************************************************************************************************

**First Usable IP Address**

      [[172.16.45.177]]
************************************************************************************************
> First usable IP = Network address + 1: 172.16.45.177
************************************************************************************************

**Last Usable IP Address**

      [[172.16.45.190]]
************************************************************************************************
> Last usable IP = Broadcast address - 1: 172.16.45.190
************************************************************************************************

The 7-second subnetting shortcut is a powerful tool for quickly calculating subnet information. Remember these key points:

- Practice regularly to improve your speed and accuracy
- Create a clear, readable chart for exam success
- Adapt the method to work well in both online and physical exam environments
- Understanding subnet boundaries is crucial for accurate calculations

With consistent practice, you'll be able to perform subnet calculations rapidly and accurately, a valuable skill for IT professionals and certification exams.

Additional Resources
--------------------

- Professor Messer's networking courses and videos
- Online subnet calculators for checking your work
- Networking certification exam practice tests

Keep practicing, and soon you'll be subnetting like a pro in just 7 seconds!
Now that you are confident in how to subnet, let's look at a scenario where a network was designed for a specific environment.

### Addressing Scheme Design

The Challenge
-------------
Sarah, the lead network engineer at NetworkCo, a growing tech company, faced a daunting task. The company was expanding rapidly, opening new offices across the country, and their current IP addressing scheme was becoming a tangled mess. With each new office, the ad-hoc approach to assigning IP addresses was causing conflicts, making network management a nightmare, and hindering further growth.

As Sarah stared at the network diagram plastered across her office wall, she knew it was time for a change. "We need a comprehensive IP addressing scheme that can accommodate our current needs and future growth," she muttered to herself. "But where do I start?"

The Journey Begins
------------------
Sarah decided to approach this challenge methodically. She gathered her team and began to outline the key considerations they needed to address:

1. **Current Network Size**: They had to account for all existing devices across their five offices.
2. **Future Growth**: The company planned to open 10 new offices in the next two years.
3. **Departmental Structure**: Each office had distinct departments: Sales, Engineering, HR, and IT.
4. **Special Requirements**: The Engineering department needed larger subnets for their development environments.

Choosing the Address Range
--------------------------
After assessing their needs, Sarah decided to use private IP addresses from the Class A range: 10.0.0.0/8. "This will give us plenty of room to grow," she explained to her team.

Designing the Structure
-----------------------
Sarah sketched out a hierarchical structure on the whiteboard:

- The first octet (10) would remain constant.
- The second octet would represent the office location (0-254).
- The third octet would represent the department:
  - 1: Sales
  - 2: Engineering
  - 3: HR
  - 4: IT
- The fourth octet would be for individual hosts.

"This way," Sarah explained, "we can have up to 255 offices, each with up to 255 subnets, and each subnet can have up to 254 devices."

Implementing VLSM
-----------------
To address the Engineering department's need for larger subnets, Sarah implemented Variable Length Subnet Masking (VLSM):

- Sales, HR, IT: 10.office.dept.0/24 (254 hosts each)
- Engineering: 10.office.2.0/23 (510 hosts)

"By using VLSM," Sarah said, "we can allocate more IP addresses to Engineering without wasting addresses in smaller departments."

Naming Convention
-----------------
To improve clarity, Sarah established a naming convention: 
Location-Department-DeviceType-Number

For example: NYC-ENG-PRINTER-01 would be a printer in the New York City office's Engineering department.

Documentation and Growth Planning
---------------------------------
Sarah meticulously documented the new scheme, creating a spreadsheet that outlined:

- IP ranges for each office and department
- Subnet masks
- Reserved IP addresses for network devices
- Procedures for adding new subnets

"We'll reserve the IP ranges 10.250-254.0.0/16 for future expansion," Sarah told her team. "This gives us room to grow beyond our current plans if needed."

Implementation and Results
--------------------------
Over the next few months, Sarah and her team gradually implemented the new IP addressing scheme. They set up DHCP servers to automatically assign addresses within the defined ranges and updated firewall rules to reflect the new structure.

The results were transformative:

1. Network troubleshooting became much easier, as the IP address immediately indicated the device's location and department.
2. Adding new offices to the network became a straightforward process.
3. The clear structure eliminated IP conflicts, improving network stability.
4. The company was well-prepared for future growth, with a scheme that could easily accommodate new offices and departments.

Final Findings
-----------
As Sarah looked at the updated network diagram in her office, she felt a sense of accomplishment. The new IP addressing scheme had brought order to chaos, making NetworkCo's network more manageable, scalable, and robust.

"Remember," Sarah told her team during their final review meeting, "this isn't set in stone. As our company grows and technology evolves, we'll need to review and possibly revise our scheme. But for now, we have a solid foundation to build upon."

Through careful planning, consideration of current and future needs, and methodical implementation, Sarah had successfully designed an IP addressing scheme that would serve NetworkCo for years to come.

### Network Growth Planning

As networks grow, careful planning is necessary to ensure scalability, efficient use of IP address space, and ease of network management. Network growth planning involves forecasting future needs, determining the right subnet structure, and designing a network that can accommodate new devices and subnets without major reconfiguration. This section covers the strategies and considerations for planning a scalable network using subnetting and IP address allocation.

**Key Considerations for Network Growth**

1. **Predicting Future Network Needs**:
   - Estimate how many additional hosts or subnets your network will require in the coming months or years. Plan for growth, not just immediate needs.
   
2. **Choosing the Right Subnet Structure**:
   - Subnet your network in a way that leaves room for expansion. Overly tight subnetting can limit flexibility, while too large subnets may waste IP addresses.

3. **Reserving IP Address Space for Growth**:
   - Allocate more IP addresses than you currently need to accommodate future devices and subnets without requiring a complete redesign.

4. **Planning for Hierarchical Addressing**:
   - Use hierarchical addressing to structure your network in a way that supports routing efficiency and simplifies management. Group related subnets into logical blocks.

5. **Maintaining Network Performance**:
   - As the network grows, ensure performance is maintained by segmenting traffic into subnets that reduce congestion and broadcast domains.

6. **Documentation and IP Address Management**:
   - Keep detailed documentation of your IP address allocation and subnet structure to make future network expansions easier to manage.

**Steps for Network Growth Planning**

1. **Assess Current Network Utilization**:
   - Review your current IP address allocation and subnet utilization. Identify which subnets are nearing capacity and which have room for growth.

2. **Estimate Future Requirements**:
   - Determine how many devices, users, and subnets you expect to add in the next 1–3 years. Factor in technology trends such as IoT (Internet of Things) devices, which may add significantly more devices to your network.

3. **Design for Scalability**:
   - Choose a subnet structure that allows for easy expansion. For example, if you currently use a `/24` subnet mask but expect your network to grow, consider using a `/22` or `/21` subnet mask to leave room for additional hosts and subnets.

4. **Implement IP Address Management (IPAM)**:
   - Use IPAM tools to monitor and manage IP address allocation. These tools help you keep track of IP addresses and prevent conflicts as your network expands.

5. **Consider Hierarchical Subnetting**:
   - Structure your network into larger blocks of IP addresses that can be broken down into smaller subnets as needed. For example, reserve a larger block of addresses (`10.0.0.0/16`) and divide it into smaller subnets (`10.0.1.0/24`, `10.0.2.0/24`) as the network grows.

6. **Prepare for Future Protocols (IPv6)**:
   - As networks expand, consider adopting IPv6 to future-proof your network, especially if you anticipate a significant increase in connected devices.

**Example Scenario: Planning for Growth**

Suppose your company currently has the network `192.168.10.0/24` and is anticipating doubling the number of devices within the next year. You could plan for growth by:

1. **Choosing a Larger Subnet Mask**:  
   - Use a subnet mask of `/23` (`255.255.254.0`), which will allow for twice as many hosts (510 instead of 254). The new network range will be `192.168.10.0` to `192.168.11.255`, providing sufficient room for the projected growth.

2. **Reserving Additional Address Space**:  
   - If additional growth is expected, reserve the block `192.168.12.0/22`, which gives you flexibility to expand into this range without needing to renumber your entire network.

> **Practice Problem**
> 
> Your organization currently uses the network `172.16.0.0/16` and anticipates adding 500 new devices across multiple subnets in the next year. How would you plan for growth? What subnet mask would you use, and how would you allocate subnets?
> 
> 1. **Assess Current Network**:
>    - The network `172.16.0.0/16` provides 65,534 hosts per subnet, which may be too large for your future needs. Dividing this network will help improve manageability and performance.
> 
> 2. **Choose a Subnet Mask**:
>    - To create smaller subnets while allowing for growth, you could use a `/22` subnet mask (`255.255.252.0`), providing 1,022 hosts per subnet.
> 
> 3. **Allocate Subnets**:
>   - Break down `172.16.0.0/16` into multiple `/22` subnets:
>     - Subnet 1: `172.16.0.0/22`
>     - Subnet 2: `172.16.4.0/22`
>     - Subnet 3: `172.16.8.0/22`
>     - These subnets will support the addition of new devices while leaving room for future expansion.

Planning for network growth is essential to ensure your network can handle future demands without disruption. By designing a scalable IP addressing scheme, maintaining performance, and reserving IP address space, you can ensure your network is ready for expansion.

## Summative Assessment
### Assessment
It's time to apply everything that you have learned! 

Based on the information in the graphic shown, design a classfull network addressing scheme that will supply the minimum number of hosts per subnet, and allow enough extra subnets and hosts for 25% growth in all areas.

<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1" width="969px" viewBox="-0.5 -0.5 969 371" style="max-width:100%;max-height:371px;"><defs/><g><g data-cell-id="0"><g data-cell-id="1"><g data-cell-id="r2ITRVLeoLMtrR3wu55q-1"><g><rect x="349" y="121" width="78" height="53" fill="none" stroke="none" pointer-events="all"/><path d="M 427 136.38 C 427 144.85 409.61 151.74 387.99 151.74 C 366.39 151.74 349 144.85 349 136.38 C 349 158.64 349 158.64 349 158.64 C 349 167.11 366.39 174 387.99 174 C 409.61 174 427 167.11 427 158.64 Z M 387.99 151.74 C 409.61 151.74 427 144.85 427 136.38 C 427 127.89 409.61 121 387.99 121 C 366.39 121 349 127.89 349 136.38 C 349 144.85 366.39 151.74 387.99 151.74 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 379.04 130.54 L 382.2 135.31 L 370.08 137.97 L 372.72 135.84 L 354.27 132.66 L 359.01 128.95 L 376.92 132.13 Z M 396.44 142.2 L 393.8 137.43 L 404.86 134.79 L 403.28 136.9 L 421.2 140.08 L 416.99 143.26 L 398.54 140.08 Z M 390.11 127.89 L 402.22 124.71 L 402.76 129.48 L 399.6 128.95 L 393.8 134.25 L 387.99 133.2 L 393.8 128.43 Z M 384.83 146.97 L 373.24 149.1 L 372.72 143.26 L 376.4 144.33 L 382.73 138.49 L 388.53 139.56 L 381.67 145.92 Z" fill="#ffffff" stroke="none" pointer-events="all"/></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-2"><g><rect x="599" y="121" width="78" height="53" fill="none" stroke="none" pointer-events="all"/><path d="M 677 136.38 C 677 144.85 659.61 151.74 637.99 151.74 C 616.39 151.74 599 144.85 599 136.38 C 599 158.64 599 158.64 599 158.64 C 599 167.11 616.39 174 637.99 174 C 659.61 174 677 167.11 677 158.64 Z M 637.99 151.74 C 659.61 151.74 677 144.85 677 136.38 C 677 127.89 659.61 121 637.99 121 C 616.39 121 599 127.89 599 136.38 C 599 144.85 616.39 151.74 637.99 151.74 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 629.04 130.54 L 632.2 135.31 L 620.08 137.97 L 622.72 135.84 L 604.27 132.66 L 609.01 128.95 L 626.92 132.13 Z M 646.44 142.2 L 643.8 137.43 L 654.86 134.79 L 653.28 136.9 L 671.2 140.08 L 666.99 143.26 L 648.54 140.08 Z M 640.11 127.89 L 652.22 124.71 L 652.76 129.48 L 649.6 128.95 L 643.8 134.25 L 637.99 133.2 L 643.8 128.43 Z M 634.83 146.97 L 623.24 149.1 L 622.72 143.26 L 626.4 144.33 L 632.73 138.49 L 638.53 139.56 L 631.67 145.92 Z" fill="#ffffff" stroke="none" pointer-events="all"/></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-3"><g><rect x="149" y="241" width="101" height="50" fill="none" stroke="none" pointer-events="all"/><path d="M 225.14 291 L 225.14 265.73 L 149 265.73 L 149 291 Z M 149 265.73 L 179.66 241 L 250 241 L 224.62 265.73 Z M 225.14 291 L 250 263.63 L 250 241 L 225.14 265.73 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><rect x="149" y="241" width="0" height="0" fill="none" stroke="#ffffff" stroke-width="2" pointer-events="all"/><path d="M 193.42 259.41 L 191.83 260.47 L 173.32 260.47 L 171.21 262.57 L 165.93 260.47 L 176.49 257.31 L 174.38 259.41 Z M 208.22 249.94 L 206.63 251.52 L 188.13 251.52 L 186.01 253.1 L 180.73 251 L 191.31 248.36 L 189.18 249.94 Z M 196.59 256.26 L 198.18 255.21 L 217.21 255.21 L 218.8 253.1 L 224.08 255.21 L 214.04 258.37 L 215.62 256.26 Z M 206.63 246.78 L 208.22 245.74 L 226.73 245.74 L 228.84 243.62 L 234.14 246.26 L 223.56 248.9 L 225.67 246.78 Z" fill="#ffffff" stroke="none" pointer-events="all"/></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-4"><g><rect x="149" y="1" width="101" height="50" fill="none" stroke="none" pointer-events="all"/><path d="M 225.14 51 L 225.14 25.73 L 149 25.73 L 149 51 Z M 149 25.73 L 179.66 1 L 250 1 L 224.62 25.73 Z M 225.14 51 L 250 23.63 L 250 1 L 225.14 25.73 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><rect x="149" y="1" width="0" height="0" fill="none" stroke="#ffffff" stroke-width="2" pointer-events="all"/><path d="M 193.42 19.41 L 191.83 20.47 L 173.32 20.47 L 171.21 22.57 L 165.93 20.47 L 176.49 17.31 L 174.38 19.41 Z M 208.22 9.94 L 206.63 11.52 L 188.13 11.52 L 186.01 13.1 L 180.73 11 L 191.31 8.36 L 189.18 9.94 Z M 196.59 16.26 L 198.18 15.21 L 217.21 15.21 L 218.8 13.1 L 224.08 15.21 L 214.04 18.37 L 215.62 16.26 Z M 206.63 6.78 L 208.22 5.74 L 226.73 5.74 L 228.84 3.62 L 234.14 6.26 L 223.56 8.9 L 225.67 6.78 Z" fill="#ffffff" stroke="none" pointer-events="all"/></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-5"><g><rect x="799" y="31" width="101" height="50" fill="none" stroke="none" pointer-events="all"/><path d="M 875.14 81 L 875.14 55.73 L 799 55.73 L 799 81 Z M 799 55.73 L 829.66 31 L 900 31 L 874.62 55.73 Z M 875.14 81 L 900 53.63 L 900 31 L 875.14 55.73 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><rect x="799" y="31" width="0" height="0" fill="none" stroke="#ffffff" stroke-width="2" pointer-events="all"/><path d="M 843.42 49.41 L 841.83 50.47 L 823.32 50.47 L 821.21 52.57 L 815.93 50.47 L 826.49 47.31 L 824.38 49.41 Z M 858.22 39.94 L 856.63 41.52 L 838.13 41.52 L 836.01 43.1 L 830.73 41 L 841.31 38.36 L 839.18 39.94 Z M 846.59 46.26 L 848.18 45.21 L 867.21 45.21 L 868.8 43.1 L 874.08 45.21 L 864.04 48.37 L 865.62 46.26 Z M 856.63 36.78 L 858.22 35.74 L 876.73 35.74 L 878.84 33.62 L 884.14 36.26 L 873.56 38.9 L 875.67 36.78 Z" fill="#ffffff" stroke="none" pointer-events="all"/></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-6"><g><rect x="9" y="41" width="55.71" height="50" fill="none" stroke="none" pointer-events="all"/><rect x="9" y="41" width="0" height="0" fill="none" stroke="#ffffff" stroke-width="2" pointer-events="all"/><path d="M 56.75 83.81 L 56.75 74.72 L 9 74.72 L 9 83.81 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 41.97 79.64 L 54.09 79.64" fill="none" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 64.71 67.14 L 16.96 67.14 L 9 74.72 L 56.75 74.72 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 64.71 75.09 L 64.71 67.14 L 56.75 74.72 L 56.75 83.81 Z M 48.41 91 L 48.41 89.1 L 52.58 83.05 L 52.58 86.83 Z M 48.41 89.1 L 48.41 91 L 10.14 91 L 10.14 89.1 Z M 48.41 89.1 L 10.14 89.1 L 14.3 83.05 L 52.58 83.05 Z M 50.3 70.17 L 50.3 46.31 L 17.71 46.31 L 17.71 70.17 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 20.37 51.6 C 20.37 48.95 22.64 48.58 22.64 48.58 C 22.64 48.58 42.35 48.58 44.62 48.58 C 47.66 48.58 47.66 51.6 47.66 51.6 C 47.66 51.6 47.66 63.35 47.66 65.24 C 47.66 66.76 45 67.51 45 67.51 C 45 67.51 25.29 67.51 23.02 67.51 C 21.12 67.51 20.37 65.24 20.37 65.24 Z" fill="none" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 55.99 41 L 23.02 41 L 17.71 46.31 L 50.3 46.31 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 55.99 65.24 L 55.99 41 L 50.3 46.31 L 50.3 70.17 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/></g><g><g transform="translate(-0.5 -0.5)"><switch><foreignObject pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility" style="overflow: visible; text-align: left;"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe flex-start; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 98px; margin-left: 37px;"><div data-drawio-colors="color: rgb(0, 0, 0); " style="box-sizing: border-box; font-size: 0px; text-align: center;"><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: rgb(0, 0, 0); line-height: 1.2; pointer-events: all; white-space: nowrap;">Administrative</div></div></div></foreignObject><text x="37" y="110" fill="rgb(0, 0, 0)" font-family="&quot;Helvetica&quot;" font-size="12px" text-anchor="middle">Administr...</text></switch></g></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-9"><g><path d="M 64.71 59.15 L 149 38.42" fill="none" stroke="rgb(0, 0, 0)" stroke-width="3" stroke-miterlimit="10" pointer-events="stroke"/></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-10"><g><path d="M 250 241 L 358.36 168.7" fill="none" stroke="rgb(0, 0, 0)" stroke-width="3" stroke-miterlimit="10" pointer-events="stroke"/></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-11"><g><path d="M 236.87 38 L 358.36 126.3" fill="none" stroke="rgb(0, 0, 0)" stroke-width="3" stroke-miterlimit="10" pointer-events="stroke"/></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-17"><g><path d="M 427 147.5 L 470 122.67 L 513 147.5 L 556 172.33 L 599 147.5" fill="none" stroke="#ff3333" stroke-width="4" stroke-miterlimit="10" pointer-events="stroke"/></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-18"><g><rect x="9" y="271" width="55.71" height="50" fill="none" stroke="none" pointer-events="all"/><rect x="9" y="271" width="0" height="0" fill="none" stroke="#ffffff" stroke-width="2" pointer-events="all"/><path d="M 56.75 313.81 L 56.75 304.72 L 9 304.72 L 9 313.81 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 41.97 309.64 L 54.09 309.64" fill="none" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 64.71 297.14 L 16.96 297.14 L 9 304.72 L 56.75 304.72 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 64.71 305.09 L 64.71 297.14 L 56.75 304.72 L 56.75 313.81 Z M 48.41 321 L 48.41 319.1 L 52.58 313.05 L 52.58 316.83 Z M 48.41 319.1 L 48.41 321 L 10.14 321 L 10.14 319.1 Z M 48.41 319.1 L 10.14 319.1 L 14.3 313.05 L 52.58 313.05 Z M 50.3 300.17 L 50.3 276.31 L 17.71 276.31 L 17.71 300.17 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 20.37 281.6 C 20.37 278.95 22.64 278.58 22.64 278.58 C 22.64 278.58 42.35 278.58 44.62 278.58 C 47.66 278.58 47.66 281.6 47.66 281.6 C 47.66 281.6 47.66 293.35 47.66 295.24 C 47.66 296.76 45 297.51 45 297.51 C 45 297.51 25.29 297.51 23.02 297.51 C 21.12 297.51 20.37 295.24 20.37 295.24 Z" fill="none" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 55.99 271 L 23.02 271 L 17.71 276.31 L 50.3 276.31 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 55.99 295.24 L 55.99 271 L 50.3 276.31 L 50.3 300.17 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/></g><g><g transform="translate(-0.5 -0.5)"><switch><foreignObject pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility" style="overflow: visible; text-align: left;"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe flex-start; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 328px; margin-left: 37px;"><div data-drawio-colors="color: rgb(0, 0, 0); " style="box-sizing: border-box; font-size: 0px; text-align: center;"><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: rgb(0, 0, 0); line-height: 1.2; pointer-events: all; white-space: nowrap;">Marketing</div></div></div></foreignObject><text x="37" y="340" fill="rgb(0, 0, 0)" font-family="&quot;Helvetica&quot;" font-size="12px" text-anchor="middle">Marketing</text></switch></g></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-19"><g><path d="M 677 147.5 L 799 80" fill="none" stroke="rgb(0, 0, 0)" stroke-width="3" stroke-miterlimit="10" pointer-events="stroke"/></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-21"><g><rect x="900" y="174" width="55.71" height="50" fill="none" stroke="none" pointer-events="all"/><rect x="900" y="174" width="0" height="0" fill="none" stroke="#ffffff" stroke-width="2" pointer-events="all"/><path d="M 947.75 216.81 L 947.75 207.72 L 900 207.72 L 900 216.81 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 932.97 212.64 L 945.09 212.64" fill="none" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 955.71 200.14 L 907.96 200.14 L 900 207.72 L 947.75 207.72 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 955.71 208.09 L 955.71 200.14 L 947.75 207.72 L 947.75 216.81 Z M 939.41 224 L 939.41 222.1 L 943.58 216.05 L 943.58 219.83 Z M 939.41 222.1 L 939.41 224 L 901.14 224 L 901.14 222.1 Z M 939.41 222.1 L 901.14 222.1 L 905.3 216.05 L 943.58 216.05 Z M 941.3 203.17 L 941.3 179.31 L 908.71 179.31 L 908.71 203.17 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 911.37 184.6 C 911.37 181.95 913.64 181.58 913.64 181.58 C 913.64 181.58 933.35 181.58 935.62 181.58 C 938.66 181.58 938.66 184.6 938.66 184.6 C 938.66 184.6 938.66 196.35 938.66 198.24 C 938.66 199.76 936 200.51 936 200.51 C 936 200.51 916.29 200.51 914.02 200.51 C 912.12 200.51 911.37 198.24 911.37 198.24 Z" fill="none" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 946.99 174 L 914.02 174 L 908.71 179.31 L 941.3 179.31 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/><path d="M 946.99 198.24 L 946.99 174 L 941.3 179.31 L 941.3 203.17 Z" fill="#036897" stroke="#ffffff" stroke-width="2" stroke-linejoin="round" stroke-miterlimit="10" pointer-events="all"/></g><g><g transform="translate(-0.5 -0.5)"><switch><foreignObject pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility" style="overflow: visible; text-align: left;"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe flex-start; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 231px; margin-left: 928px;"><div data-drawio-colors="color: rgb(0, 0, 0); " style="box-sizing: border-box; font-size: 0px; text-align: center;"><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: rgb(0, 0, 0); line-height: 1.2; pointer-events: all; white-space: nowrap;">Sales</div></div></div></foreignObject><text x="928" y="243" fill="rgb(0, 0, 0)" font-family="&quot;Helvetica&quot;" font-size="12px" text-anchor="middle">Sales</text></switch></g></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-23"><g><path d="M 64.04 302.7 L 149 285" fill="none" stroke="rgb(0, 0, 0)" stroke-width="3" stroke-miterlimit="10" pointer-events="stroke"/></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-24"><g><path d="M 860.02 81 L 910.5 201" fill="none" stroke="rgb(0, 0, 0)" stroke-width="3" stroke-miterlimit="10" pointer-events="stroke"/></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-25"><g><rect x="1.85" y="109" width="70" height="30" fill="none" stroke="none" pointer-events="all"/></g><g><g transform="translate(-0.5 -0.5)"><switch><foreignObject pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility" style="overflow: visible; text-align: left;"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 124px; margin-left: 37px;"><div data-drawio-colors="color: rgb(0, 0, 0); " style="box-sizing: border-box; font-size: 0px; text-align: center;"><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: rgb(0, 0, 0); line-height: 1.2; pointer-events: all; white-space: nowrap;">30 hosts</div></div></div></foreignObject><text x="37" y="128" fill="rgb(0, 0, 0)" font-family="&quot;Helvetica&quot;" font-size="12px" text-anchor="middle">30 hosts</text></switch></g></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-26"><g><rect x="1.85" y="341" width="70" height="30" fill="none" stroke="none" pointer-events="all"/></g><g><g transform="translate(-0.5 -0.5)"><switch><foreignObject pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility" style="overflow: visible; text-align: left;"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 356px; margin-left: 37px;"><div data-drawio-colors="color: rgb(0, 0, 0); " style="box-sizing: border-box; font-size: 0px; text-align: center;"><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: rgb(0, 0, 0); line-height: 1.2; pointer-events: all; white-space: nowrap;">50 hosts</div></div></div></foreignObject><text x="37" y="360" fill="rgb(0, 0, 0)" font-family="&quot;Helvetica&quot;" font-size="12px" text-anchor="middle">50 hosts</text></switch></g></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-27"><g><rect x="887.86" y="241" width="80" height="30" fill="none" stroke="none" pointer-events="all"/></g><g><g transform="translate(-0.5 -0.5)"><switch><foreignObject pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility" style="overflow: visible; text-align: left;"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 256px; margin-left: 928px;"><div data-drawio-colors="color: rgb(0, 0, 0); " style="box-sizing: border-box; font-size: 0px; text-align: center;"><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: rgb(0, 0, 0); line-height: 1.2; pointer-events: all; white-space: nowrap;">185 hosts</div></div></div></foreignObject><text x="928" y="260" fill="rgb(0, 0, 0)" font-family="&quot;Helvetica&quot;" font-size="12px" text-anchor="middle">185 hosts</text></switch></g></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-28"><g><rect x="349" y="169" width="50" height="30" fill="none" stroke="none" pointer-events="all"/></g><g><g transform="translate(-0.5 -0.5)"><switch><foreignObject pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility" style="overflow: visible; text-align: left;"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 184px; margin-left: 374px;"><div data-drawio-colors="color: rgb(0, 0, 0); " style="box-sizing: border-box; font-size: 0px; text-align: center;"><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: rgb(0, 0, 0); line-height: 1.2; pointer-events: all; white-space: nowrap;">F0/1</div></div></div></foreignObject><text x="374" y="188" fill="rgb(0, 0, 0)" font-family="&quot;Helvetica&quot;" font-size="12px" text-anchor="middle">F0/1</text></switch></g></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-29"><g><rect x="349" y="91" width="50" height="30" fill="none" stroke="none" pointer-events="all"/></g><g><g transform="translate(-0.5 -0.5)"><switch><foreignObject pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility" style="overflow: visible; text-align: left;"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 106px; margin-left: 374px;"><div data-drawio-colors="color: rgb(0, 0, 0); " style="box-sizing: border-box; font-size: 0px; text-align: center;"><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: rgb(0, 0, 0); line-height: 1.2; pointer-events: all; white-space: nowrap;">F0/0</div></div></div></foreignObject><text x="374" y="110" fill="rgb(0, 0, 0)" font-family="&quot;Helvetica&quot;" font-size="12px" text-anchor="middle">F0/0</text></switch></g></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-30"><g><rect x="419" y="144" width="60" height="30" fill="none" stroke="none" pointer-events="all"/></g><g><g transform="translate(-0.5 -0.5)"><switch><foreignObject pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility" style="overflow: visible; text-align: left;"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 159px; margin-left: 449px;"><div data-drawio-colors="color: rgb(0, 0, 0); " style="box-sizing: border-box; font-size: 0px; text-align: center;"><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: rgb(0, 0, 0); line-height: 1.2; pointer-events: all; white-space: nowrap;">S0/0/1</div></div></div></foreignObject><text x="449" y="163" fill="rgb(0, 0, 0)" font-family="&quot;Helvetica&quot;" font-size="12px" text-anchor="middle">S0/0/1</text></switch></g></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-31"><g><rect x="539" y="121" width="60" height="30" fill="none" stroke="none" pointer-events="all"/></g><g><g transform="translate(-0.5 -0.5)"><switch><foreignObject pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility" style="overflow: visible; text-align: left;"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 136px; margin-left: 569px;"><div data-drawio-colors="color: rgb(0, 0, 0); " style="box-sizing: border-box; font-size: 0px; text-align: center;"><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: rgb(0, 0, 0); line-height: 1.2; pointer-events: all; white-space: nowrap;">S0/0/0</div></div></div></foreignObject><text x="569" y="140" fill="rgb(0, 0, 0)" font-family="&quot;Helvetica&quot;" font-size="12px" text-anchor="middle">S0/0/0</text></switch></g></g></g><g data-cell-id="r2ITRVLeoLMtrR3wu55q-32"><g><rect x="669" y="144" width="50" height="30" fill="none" stroke="none" pointer-events="all"/></g><g><g transform="translate(-0.5 -0.5)"><switch><foreignObject pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility" style="overflow: visible; text-align: left;"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 159px; margin-left: 694px;"><div data-drawio-colors="color: rgb(0, 0, 0); " style="box-sizing: border-box; font-size: 0px; text-align: center;"><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: rgb(0, 0, 0); line-height: 1.2; pointer-events: all; white-space: nowrap;">F0/0</div></div></div></foreignObject><text x="694" y="163" fill="rgb(0, 0, 0)" font-family="&quot;Helvetica&quot;" font-size="12px" text-anchor="middle">F0/0</text></switch></g></g></g></g></g></g><switch><g requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"/><a transform="translate(0,-5)" xlink:href="https://www.drawio.com/doc/faq/svg-export-text-problems" target="_blank"><text text-anchor="middle" font-size="10px" x="50%" y="100%">Text is not SVG - cannot display</text></a></switch></svg>


Assessment Questions
====================

**What is the address class of this network?**

- [( )] A 
- [(X)] B
- [( )] C
- [( )] D
*********************************************************
> The IP address 172.16.0.0 belongs to a Class B network.
*********************************************************


You need to calculate the appropriate subnet mask to accommodate the largest number of hosts, allowing for 25% growth.

__How many hosts do you need to plan for?__ _Round up to the closest whole number of hosts._

      [[232]]
**************************************************************
> The largest group is Sales, which requires __185__ hosts. With __25% growth__, this increases to approximately __232__ hosts. This requires a minimum of 256 addresses, meaning you would need a subnet mask of /24 (__255.255.255.0__).
**************************************************************

__What is the ~~minimum~~ number of subnets needed for this design?__

- [( )] 2
- [( )] 3
- [(x)] 4
- [( )] 5
********************************************************************************
> You have __4__ subnets to plan: Sales, Marketing, Administrative, and the serial link between Router A and Router B.
> The serial link typically only needs 2 IP addresses (point-to-point link), which is the smallest subnet size, requiring a subnet mask of /30.
> 
> Extra Subnets for 25% Growth:
> Planning for future growth requires an additional 25% more subnets. Since you have 4 subnets now, add 1 more for growth.

>> Total Subnets = 4 + 1 =__ 5 subnets__.
********************************************************************************

For each of the examples below, determine what size subnet will be needed.
==========================================================================

__What subnet mask should be used for Sales?__

- [( )] /23
- [(x)] /24
- [( )] /25
- [( )] /26
**************************************************************************
> Use 172.16.0.0/24 (256 addresses).
**************************************************************************

__What subnet mask should be used for Marketing?__

- [( )] /23
- [( )] /24
- [(x)] /25
- [( )] /26
**************************************************************************
> Marketing needs 50 hosts, and with 25% growth, that becomes around 63 hosts. This would need at least a /25 subnet.
> Use 172.16.1.0/25.
**************************************************************************


__What subnet mask should be used for Administrative?__

- [( )] /25
- [(x)] /26
- [( )] /29
- [( )] /30
*********************************************************************************
Administrative needs 30 hosts, and with 25% growth, that becomes around 38 hosts, requiring at least a /26 subnet.
Use 172.16.1.128/26.
*********************************************************************************

__What subnet mask should be used for router-to-router connection?__

- [( )] /25
- [( )] /26
- [( )] /29
- [(x)] /30
***************************************************************************************
> This point-to-point link needs only 2 addresses. A /30 subnet would suffice.
> Use 172.16.1.192/30.
***************************************************************************************