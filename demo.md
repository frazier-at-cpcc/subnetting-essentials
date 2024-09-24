# Subnetting Fundamentals
Welcome!
----
Welcome to your journey in mastering one of the most critical concepts in networking: subnetting. This self-paced course is designed to provide a comprehensive foundation, empowering you with the knowledge and skills to design and manage efficient networks.

Throughout this lesson, you’ll explore key topics starting with an introduction to IPv4 address classes and specialty address ranges. You’ll learn about private address spaces, default subnet masks, and the basics of networking math, including binary and decimal conversions. The course will help you identify network and host addresses, and understand how subnet masks work—both default and custom.

As you progress, you’ll develop the ability to determine subnet sizes, practice ANDing operations, and delve into practical subnetting exercises, applying your knowledge to real-world scenarios.

By the end of this course, you will have a solid understanding of subnetting and feel confident in applying these concepts to create efficient, scalable networks. Take your time, absorb the material, and enjoy the learning process!

## Introduction to Subnetting

Welcome to the first lesson of **Subnetting Fundamentals**. In this section, we will lay the foundation by discussing what subnetting is, why it’s important, and how it fits into the broader field of networking.

What is Subnetting?
----

Subnetting is the process of dividing a larger network into smaller, more efficient sub-networks (subnets). It helps optimize IP address usage and improves network performance and security.

- A **subnet** allows network administrators to split a network into logical groups.
- This improves traffic management, reduces congestion, and helps in organizing a network's structure.

![](``` ascii
  +-------------------------------+
  |   Network A (192.168.1.0/24)   |
  |                               |
  |  Subnet 1      Subnet 2        |
  |  (192.168.1.0/26)  (192.168.1.64/26) |
  +-------------------------------+
```)

Why is Subnetting Important?
----

Subnetting offers several key advantages:

* **Efficient use of IP addresses**: Helps prevent wasting IP addresses by assigning only the necessary range.
* **Network security**: Smaller subnets allow for more specific firewall rules.
* **Improved performance**: Localizes network traffic to reduce congestion.


Use Case
====
Imagine a company that has three departments: HR, Sales, and IT. Each department requires its own sub-network. Subnetting allows you to divide a single network into multiple subnets, each one isolated but part of the same overall network.

__Questions to Consider:__

* Why might a network need to be divided into smaller subnets?
* What are the challenges of managing a large network without subnetting?

In the next lesson, we'll dive into **IP Addresses**, where you will learn how networks are categorized and how addresses are assigned.

### IP Addresses

An **IP address** is a unique identifier assigned to each device connected to a network. It stands for "Internet Protocol" address and serves two primary purposes:

1. Identifying the host or network interface.
2. Providing the location of the host in the network.

IP addresses are essential for devices to communicate over the internet or within a local network.

```ascii
+---------------------------+
| Device A   IP: 192.168.1.2 |
+---------------------------+
        ↕
+---------------------------+
| Router     IP: 192.168.1.1 |
+---------------------------+
        ↕
+---------------------------+
| Device B   IP: 192.168.1.3 |
+---------------------------+
```

Types of IP Addresses
----
There are two types of IP addresses currently in use:

| Type | Description |
| -------- | :------: |
| **IPv4** | Uses a 32-bit address, usually written in decimal format (e.g., 192.168.1.1) |
| **IPv6** | Uses a 128-bit address, written in hexadecimal (e.g., 2001:0db8:85a3:0000:0000:8a2e:0370:7334) |

IPv4 is the most common and will be the focus of this lesson.

Structure of an IPv4 Address
----
An IPv4 address consists of four octets, each ranging from 0 to 255, separated by periods:

```
192.168.1.1
```

Each octet is a group of 8 bits, meaning an IPv4 address is __32__ bits in total.

Address Components
----
An IPv4 address has two key components:
- **Network portion**: Identifies the specific network.
- **Host portion**: Identifies a specific device (or host) within the network.

### IPv4 Address Classes

IP addresses are divided into different classes to define how the network and host portions are allocated. This classification system helps organize networks of various sizes.

The Five IPv4 Address Classes
----

There are five main classes of IPv4 addresses: **A, B, C, D, and E**. Each class has a different range of addresses and specific uses.

| Class | Start Address | End Address   | Default Subnet Mask | Usage                     |
|-------|---------------|---------------|---------------------|---------------------------|
| A     | 0.0.0.0       | 127.255.255.255 | 255.0.0.0           | Large networks            |
| B     | 128.0.0.0     | 191.255.255.255 | 255.255.0.0         | Medium-sized networks      |
| C     | 192.0.0.0     | 223.255.255.255 | 255.255.255.0       | Small networks            |
| D     | 224.0.0.0     | 239.255.255.255 | N/A                 | Multicast (special use)    |
| E     | 240.0.0.0     | 255.255.255.255 | N/A                 | Experimental (reserved)    |

Class A
====
- **Address range**: 0.0.0.0 to 127.255.255.255
- **Default subnet mask**: 255.0.0.0
- Class A is used for very large networks, often in major organizations or ISPs. The first octet is used for the network portion, while the remaining three octets are used for the host portion.

```ascii
  Network: | 0xxxxxxx | . Host: | xxxxxxxx.xxxxxxxx.xxxxxxxx |
```

Class B
====
- **Address range**: 128.0.0.0 to 191.255.255.255
- **Default subnet mask**: 255.255.0.0
- Class B is designed for medium-sized networks. The first two octets are used for the network portion, and the last two octets are used for the host portion.

```ascii
  Network: | 10xxxxxx.xxxxxxxx | . Host: | xxxxxxxx.xxxxxxxx |
```

Class C
====
- **Address range**: 192.0.0.0 to 223.255.255.255
- **Default subnet mask**: 255.255.255.0
- Class C is the most common for small networks. The first three octets are used for the network portion, and the last octet is used for the host portion.

```ascii
  Network: | 110xxxxx.xxxxxxxx.xxxxxxxx | . Host: | xxxxxxxx |
```
Class D (Multicast)
====
- **Address range**: 224.0.0.0 to 239.255.255.255
- Class D addresses are reserved for multicast groups, which are used to send data to multiple destinations at once.

Class E (Experimental)
====
- **Address range**: 240.0.0.0 to 255.255.255.255
- Class E addresses are reserved for experimental use and are not used in public networks.

#### Check Your Understanding
**Instructions:** Choose the best answer for each multiple-choice question.

1. Which IP address class is used for multicast groups?
- [( )] Class A
- [( )] Class B
- [( )] Class C
- [(X)] Class D
- [( )] Class E

2. What is the default subnet mask for a Class B network?
- [( )] 255.0.0.0
- [(X)] 255.255.0.0
- [( )] 255.255.255.0
- [( )] 255.255.255.255

3. Which class of IP addresses is typically used for small networks?
- [( )] Class A
- [( )] Class B
- [(X)] Class C
- [( )] Class D
- [( )] Class E


### Specialty Address Ranges

In our exploration of IP addressing, we've learned about how networks assign unique identifiers to devices.  While most addresses are used for connecting devices to the internet or within local networks, there are special address ranges reserved for specific purposes.  

These "specialty" addresses have unique functions and aren't intended for general internet communication. 

| Address Range | Purpose | Notes |
|---|---|---|
| 127.0.0.0 - 127.255.255.255 | Loopback | Used for testing network applications on the local machine. 127.0.0.1 is the most common loopback address. |
| 169.254.0.0 - 169.254.255.255 | Link-Local |  Allows devices on the same physical network segment to communicate even without a functioning internet connection or configured router. |
| 192.0.2.0 - 192.0.2.255 | TEST-NET | Reserved for testing and learning purposes. |
| 240.0.0.0 - 255.255.255.254 | Experimental | Reserved for future use. |

Loopback Addresses
----

Imagine you want to test a device's network configuration without actually sending data over the network. That's where loopback addresses come in.

The single address **127.0.0.1** is universally recognized as the loopback address. It acts as a virtual connection, directing any data sent to it back to the same device. This means you can use it to test network applications or services running on your own computer without needing external connectivity.

Interestingly, the entire range from **127.0.0.0 to 127.255.255.255** is reserved for loopback addresses.  While 127.0.0.1 is the most common, you can technically use any address within this block for local testing.

Link-Local Addresses
----

Link-local addresses are designed for devices on the same physical network segment, like a home or office LAN. They allow devices to communicate with each other even without a functioning internet connection or a configured router.

The address range for link-local addresses is **169.254.0.0 to 169.254.255.255 (169.254.0.0/16)**. When a device joins a network and can't obtain an IP address automatically (e.g., DHCP failure), it will often assign itself a link-local address, enabling basic communication within the local segment.

TEST-NET Addresses
----
The address block **192.0.2.0 to 192.0.2.255 (192.0.2.0/24)** is specifically reserved for testing and learning purposes. It's a handy range for educational environments, labs, or personal projects where you need a dedicated network space for experimentation without interfering with real-world traffic.

Experimental Addresses
----

The range **240.0.0.0 to 255.255.255.254** is designated as "reserved for future use" according to RFC 3330. While these addresses aren't currently assigned to specific purposes, they might be used for experimental technologies or future internet protocols.


Understanding these specialty address ranges helps you grasp the nuances of IP addressing and how networks are designed to function efficiently and securely.

### Private Address Space

As we've learned, IP addresses are essential for devices to communicate on a network. 

While public IP addresses are assigned by internet service providers (ISPs) and route traffic globally, there's a special category of IP addresses designed for use *within* private networks. These are known as **private addresses**.  

Private addresses are not routable on the public internet. This means they don't appear on the global routing tables and can't be directly accessed from outside a private network. 

This segregation provides several benefits:

* **Security:** It prevents unauthorized access to internal networks from the outside world.
* **Address Conservation:** Organizations can use private addresses within their own networks without needing a large block of public IPs from an ISP.
* **Flexibility:**  Private networks can be easily configured and reconfigured without impacting the public internet.

Private Address Classes
====

| Class | Address Range | Notes |
|---|---|---|
| Class A | 10.0.0.0 - 10.255.255.255 |  Large range, suitable for large private networks |
| Class B | 172.16.0.0 - 172.31.255.255 |  Balanced range for medium to large private networks |
| Class C | 192.168.0.0 - 192.168.255.255 | Most common for smaller private networks (home, small office) |

There are three defined classes of private addresses:

Class A: 10.0.0.0 - 10.255.255.255
----
This class allocates a large portion of the IP address space for private use. It allows for a significant number of hosts within a single private network.

Class B: 172.16.0.0 - 172.31.255.255
----
This class provides another substantial range for private networks, offering a balance between address space and manageability.

Class C: 192.168.0.0 - 192.168.255.255
----
This class is the most common for smaller private networks, such as home and small office networks.

**Important Note:** While these are the designated private address ranges, it's possible to configure devices to use them even outside these blocks.  However, doing so may lead to conflicts or unexpected behavior.  It's best to stick to the standard private address ranges for optimal network stability and security.

#### Check Your Understanding

**Instructions:** Choose the best answer for each multiple-choice question.

1.  Which private address class is typically used for smaller networks, such as home or small office setups?
- [( )] Class A
- [( )] Class B
- [(X)] Class C
- [( )] Class D
- [( )] Class E

2.  What is the primary purpose of using private IP addresses?
- [(X)]  To enhance network security and conserve public IP addresses.
- [( )] To enable direct communication between devices on different continents.
- [( )] To route traffic through the public internet more efficiently.
- [( )] To identify specific devices on a global scale.
- [( )] To allocate unique addresses for public web servers.


3.  Which private address range falls within the 10.0.0.0 - 10.255.255.255 block?
- [( )] 172.16.0.0 - 172.31.255.255
- [(X)] 10.10.10.0 - 10.255.255.255
- [( )] 192.168.1.0 - 192.168.255.255
- [( )] None of the above

### Default Subnet Masks

Introduction to Subnet Masks
====

Subnet masks are the method that nodes on a network use to determine the network portion and host portion of an IP address. A subnet mask is a 32-bit number that is used in conjunction with an IP address to identify the network and host portions of the address. The subnet mask is essential for proper network communication and is used to determine whether a destination IP address is on the same network as the source IP address or if it belongs to a different network.

Classful Networking
====

Before diving too deep into subnet masks, it is essential to understand the concept of classful networking. In the early days of the internet, IP addresses were divided into five classes: Class A, Class B, Class C, Class D, and Class E. Each class had a specific range of IP addresses and a default subnet mask associated with it. For this lesson moving forward, we are going to be focusing on Class A, Class B, and Class C.

| Class | Default Subnet Mask | Network Portion | Host Portion |
|-------|---------------------|-----------------|--------------|
| A     | 255.0.0.0           | 8 bits          | 24 bits      |
| B     | 255.255.0.0         | 16 bits         | 16 bits      |
| C     | 255.255.255.0       | 24 bits         | 8 bits       |

Class A Networks
====

Class A networks are designed for large organizations with a vast number of hosts. The IP address range for Class A networks is from 1.0.0.0 to 127.255.255.255. The default subnet mask for Class A networks is 255.0.0.0, which means that the first octet represents the network portion, and the remaining three octets represent the host portion.

Subnet Mask: 255.0.0.0
Network Portion: 8 bits
Host Portion: 24 bits

Class B Networks
====

Class B networks are designed for medium-sized organizations with a moderate number of hosts. The IP address range for Class B networks is from 128.0.0.0 to 191.255.255.255. The default subnet mask for Class B networks is 255.255.0.0, which means that the first two octets represent the network portion, and the remaining two octets represent the host portion.

Subnet Mask: 255.255.0.0
Network Portion: 16 bits
Host Portion: 16 bits

Class C Networks
====

Class C networks are designed for small organizations with a limited number of hosts. The IP address range for Class C networks is from 192.0.0.0 to 223.255.255.255. The default subnet mask for Class C networks is 255.255.255.0, which means that the first three octets represent the network portion, and the remaining octet represents the host portion.

Subnet Mask: 255.255.255.0
Network Portion: 24 bits
Host Portion: 8 bits

Conclusion
====

Understanding default subnet masks for Class A, B, and C networks is essential for network administrators and IT professionals. It helps in designing and troubleshooting network infrastructure effectively. While classful networking has been largely replaced by Classless Inter-Domain Routing (CIDR) in modern networks, the concepts of default subnet masks still apply and are widely used in network configuration and management. In this lesson, you will learn about both "Class" and "Classless" subnetting. 

## Networking Math
In the realm of computer networking, understanding the mathematical foundations behind IP addressing and subnetting is crucial for network administrators and IT professionals. This section of the lesson focuses on the essential concepts of binary-to-decimal and decimal-to-binary conversions, as well as network versus host identification. Mastery of these fundamental skills will enable you to effectively design, configure, and troubleshoot network infrastructures.

Binary and decimal number systems form the backbone of IP addressing. While humans are accustomed to working with the decimal system (base 10), computers operate using the binary system (base 2). Understanding how to convert between these two number systems is essential for working with IP addresses and subnet masks.

Furthermore, distinguishing between the network and host portions of an IP address is a critical skill in network management. The network portion identifies the specific network to which a device belongs, while the host portion uniquely identifies the device within that network. Comprehending how to separate these two components using subnet masks is vital for proper network communication and segmentation.

In the following sections, we will delve into the details of binary-to-decimal and decimal-to-binary conversions, as well as explore the concepts of network and host identification. By the end of this lesson, you will have a solid foundation in the mathematical principles that underpin IP addressing and subnetting, empowering you to confidently navigate the world of computer networking.

### Binary to Decimal Conversions
**What is Binary?**
====

Binary is a number system that uses only two digits: 0 and 1. It's the language of computers and is used to represent information in computer systems. In networking, binary is used to represent IP addresses, subnet masks, and other network configuration settings.

**Why Convert Binary to Decimal?**
======
In networking, it's often necessary to work with IP addresses and subnet masks, which are typically represented in binary form. However, most people find it easier to work with decimal numbers. Converting binary to decimal allows you to easily perform calculations and comparisons on these network settings.

**How to Convert Binary to Decimal**
====

Converting binary to decimal is a simple process that involves adding up the values of each binary digit (or bit) in the binary number.

Here's the step-by-step process:

Step 1: Write down the binary number
-----
Write down the binary number you want to convert to decimal. For example, let's use the binary number `10101010`.

Step 2: Break down the binary number into individual bits
-----
Break down the binary number into individual bits, starting from the right. Each bit has a place value, just like in decimal numbers.

```
  2^7  2^6  2^5  2^4  2^3  2^2  2^1  2^0
  1    0    1    0    1    0    1    0
```

Step 3: Calculate the decimal value of each bit
----
Calculate the decimal value of each bit by multiplying the bit value (0 or 1) by its place value.

```
  2^7  = 128 (1 x 128 = 128)
  2^6  = 64  (0 x 64 = 0)
  2^5  = 32  (1 x 32 = 32)
  2^4  = 16  (0 x 16 = 0)
  2^3  = 8   (1 x 8 = 8)
  2^2  = 4   (0 x 4 = 0)
  2^1  = 2   (1 x 2 = 2)
  2^0  = 1   (0 x 1 = 0)
```

Step 4: Add up the decimal values
----
Add up the decimal values of each bit to get the final decimal value.

```
  128 + 32 + 8 + 2 = 170
```

The decimal equivalent of the binary number `10101010` is `170`.

**Real-World Application in Networking**
-----------------------------------------

In networking, you may need to convert binary IP addresses and subnet masks to decimal for easier calculations. For example, an IP address in binary form might be `11000000.10101000.00001111.00001010`. Converting each octet (or group of 8 bits) to decimal gives you the IP address in dotted decimal notation: `192.168.15.10`.

Converting binary to decimal is an essential skill in networking math. By following the simple steps outlined above, you can easily convert binary numbers to decimal for easier calculations and comparisons. Remember, practice makes perfect, so be sure to try converting more binary numbers to decimal to solidify your understanding!

**Practice Exercises**
--------------------
<iframe src="https://frazier-at-cpcc.github.io/subnetting-essentials/binary-decimal.html" style="border:0px #ffffff none;" name="myiFrame" scrolling="no" frameborder="0" marginheight="0px" marginwidth="0px" height="100%" width="100%" allowfullscreen></iframe>


### Decimal to Binary Conversions
**Converting Decimal to Binary for Networking Math**
======================================================

**What is Decimal?**
------------------

The decimal system, also known as base-10, is the standard system for denoting integer and non-integer numbers. It uses ten digits: 0 through 9.

**Why Convert Decimal to Binary?**
---------------------------------

In networking, many settings such as IP addresses and subnet masks are represented in binary to facilitate efficient data processing and transmission. Converting decimal to binary allows you to understand how these values are stored and manipulated at the hardware level.

**How to Convert Decimal to Binary**
------------------------------------

Converting a decimal number to binary involves dividing the number by 2 repeatedly and keeping track of the remainders. Here are the steps:

1.  Write down the decimal number

Write down the decimal number you want to convert to binary. For example, let's use the decimal number `170`.

2. Divide the number by 2

Divide the number by 2 and keep track of both the quotient and the remainder.

```
170 ÷ 2 = 85 with a remainder of 0
```

3. Repeat the division process

Take the quotient from the previous division and divide it by 2, again keeping track of the quotient and the remainder.

```
85 ÷ 2 = 42 with a remainder of 1
42 ÷ 2 = 21 with a remainder of 0
21 ÷ 2 = 10 with a remainder of 1
10 ÷ 2 = 5  with a remainder of 0
5  ÷ 2 = 2  with a remainder of 1
2  ÷ 2 = 1  with a remainder of 0
1  ÷ 2 = 0  with a remainder of 1
```

4. Write down the remainders

Write down the remainders in reverse order (from last to first). This is your binary number.

```
170 in decimal = 10101010 in binary
```

**Real-World Application in Networking**
-----------------------------------------

In networking, you often need to convert decimal IP addresses to binary to understand subnetting and other network configurations. For example, an IP address `192.168.15.10` in decimal format can be converted to binary as follows:

```
192  = 11000000
168  = 10101000
15   = 00001111
10   = 00001010
```

So, `192.168.15.10` in binary format is `11000000.10101000.00001111.00001010`.

**Practice Exercise**
--------------------

Convert the following decimal number to binary: `237`

(Hint: follow the steps above and write down the binary number)

**Answer**
--------

```
237 ÷ 2 = 118 with a remainder of 1
118 ÷ 2 = 59  with a remainder of 0
59  ÷ 2 = 29  with a remainder of 1
29  ÷ 2 = 14  with a remainder of 1
14  ÷ 2 = 7   with a remainder of 0
7   ÷ 2 = 3   with a remainder of 1
3   ÷ 2 = 1   with a remainder of 1
1   ÷ 2 = 0   with a remainder of 1
```

Reversing the remainders, we get:

```
237 in decimal = 11101101 in binary
```

**Conclusion**
--------------

Converting decimal to binary is a crucial skill in networking math. By following the straightforward steps of dividing by 2 and recording the remainders, you can easily convert decimal numbers to binary. Practice converting more decimal numbers to binary to enhance your proficiency. Happy networking!


### Identifying Address Classes
**Identifying the Class of an IP Address**
===========================================

**Introduction to IP Classes**
------------------------------

In classful IP addressing, IP addresses are divided into five distinct classes: A, B, C, D, and E. Each class has a unique range and serves different purposes in the network. Understanding how to identify the class of an IP address is essential for network configuration, subnetting, and efficient IP address management.

**Why Identify IP Classes?**
----------------------------

Identifying the class of an IP address helps in determining the network and host portions of the address. It also provides insights into the scale of the network and the number of hosts it can support. Properly classifying IP addresses is critical for tasks such as routing, IP address allocation, and network design.

**Class Ranges and Characteristics**
------------------------------------

Here are the characteristics and ranges for each class:

- **Class A:** 
  - Range: **1.0.0.0 to 126.0.0.0**
  - First Octet Range: **1-126**
  - Default Subnet Mask: **255.0.0.0**
  - Network/Host Split: **8 bits for network, 24 bits for hosts**
  - Suitable for: Large networks with many hosts.
  
- **Class B:**
  - Range: **128.0.0.0 to 191.255.0.0**
  - First Octet Range: **128-191**
  - Default Subnet Mask: **255.255.0.0**
  - Network/Host Split: **16 bits for network, 16 bits for hosts**
  - Suitable for: Medium-sized networks.
  
- **Class C:**
  - Range: **192.0.0.0 to 223.255.255.0**
  - First Octet Range: **192-223**
  - Default Subnet Mask: **255.255.255.0**
  - Network/Host Split: **24 bits for network, 8 bits for hosts**
  - Suitable for: Small networks.
  
- **Class D:**
  - Range: **224.0.0.0 to 239.255.255.255**
  - First Octet Range: **224-239**
  - Usage: Reserved for multicast groups.
  
- **Class E:**
  - Range: **240.0.0.0 to 255.255.255.255**
  - First Octet Range: **240-255**
  - Usage: Reserved for experimental purposes.

**Step-by-Step Guide to Identify IP Class**
-------------------------------------------

1. Examine the First Octet

Look at the first octet (the first 8 bits) of the IP address. This octet will help you determine the class of the IP address.

2. Compare Against Class Ranges

Match the first octet to the predefined ranges for each class:

- **Class A:** First octet is between 1 and 126.
- **Class B:** First octet is between 128 and 191.
- **Class C:** First octet is between 192 and 223.
- **Class D:** First octet is between 224 and 239.
- **Class E:** First octet is between 240 and 255.

### Examples

1. `10.0.0.1`

- **First Octet:** 10
- **Range:** 1-126
- **Class:** A

2. `172.16.5.4`

- **First Octet:** 172
- **Range:** 128-191
- **Class:** B

3. `192.168.1.100`

- **First Octet:** 192
- **Range:** 192-223
- **Class:** C

4. `224.0.0.1`

- **First Octet:** 224
- **Range:** 224-239
- **Class:** D (Multicasting)

5. `250.1.1.1`

- **First Octet:** 250
- **Range:** 240-255
- **Class:** E (Experimental)

**Practice Exercise**
----------------------

Identify the class of the following IP addresses:

1. `130.25.5.10`
2. `15.0.0.1`
3. `200.100.50.25`
4. `233.9.1.5`
5. `245.10.0.2`

**Answers:**

1. Class B
2. Class A
3. Class C
4. Class D
5. Class E

**Conclusion**
--------------

Identifying the class of an IP address is a foundational skill in networking. By analyzing the first octet of the IP address and comparing it against the predefined class ranges, you can easily determine the class. This knowledge is crucial for network design, IP allocation, and understanding the scale and scope of different networks. Practice identifying IP classes to become proficient in this essential networking concept!
### Identifying Network Addresses

### Identifying Host Addresses
**Identifying the Host Portion of an IP Address Using Classful Addressing**
=============================================================

**Introduction to Classful Addressing**
--------------------------------------

Classful addressing is an IP addressing architecture used in the early days of the Internet. It divides IP addresses into five classes: A, B, C, D, and E. Each class has a predefined range of addresses and a fixed structure, which determines how the network and host portions of the IP address are delineated.

Below is a summary of the different classes:

- **Class A:** Supports a large number of hosts on few networks.
- **Class B:** Supports a moderate number of hosts on more networks.
- **Class C:** Supports a small number of hosts on many networks.
- **Class D:** Reserved for multicast groups.
- **Class E:** Reserved for experimental purposes.

**Why Understand the Host Portion?**
------------------------------------

The host portion of an IP address uniquely identifies a device within a specific network. Understanding the host portion helps in tasks like network configuration, troubleshooting, and subnetting.

**Steps to Identify the Host Portion by Class**
-----------------------------------------------

Let's go through the process of identifying the host portion for Classes A, B, and C, which are commonly used in networking.

1. Determine the IP Class

Identify the class of an IP address by examining its first octet.

- **Class A:** First octet range is 1-126
  - Format: `0xxxxxxx` (7 bits for network, 24 bits for host)
- **Class B:** First octet range is 128-191
  - Format: `10xxxxxx` (14 bits for network, 16 bits for host)
- **Class C:** First octet range is 192-223
  - Format: `110xxxxx` (21 bits for network, 8 bits for host)

2. Apply the Default Subnet Mask

Use the default subnet mask to separate the network and host portions.

- **Class A:** Default subnet mask is `255.0.0.0`
- **Class B:** Default subnet mask is `255.255.0.0`
- **Class C:** Default subnet mask is `255.255.255.0`

3. Identify the Host Portion

Determine which part of the IP address represents the host by using the subnet mask.

**Example 1: Class A IP Address**
---------------------------------

Let's use the IP address `10.0.1.5`:

- The first octet `10` falls within the Class A range (1-126).
- Default subnet mask for Class A is `255.0.0.0`.

```
IP address:       10.0.1.5
Subnet mask:      255.0.0.0
Binary form:      00001010.00000000.00000001.00000101
Network portion:  00001010
Host portion:               .00000000.00000001.00000101
```

The host portion of the IP address `10.0.1.5` is `0.1.5`.

**Example 2: Class B IP Address**
---------------------------------

Let's use the IP address `172.16.5.12`:

- The first octet `172` falls within the Class B range (128-191).
- Default subnet mask for Class B is `255.255.0.0`.

```
IP address:       172.16.5.12
Subnet mask:      255.255.0.0
Binary form:      10101100.00010000.00000101.00001100
Network portion:  10101100.00010000
Host portion:                        .00000101.00001100
```

The host portion of the IP address `172.16.5.12` is `5.12`.

**Example 3: Class C IP Address**
----------------------------------

Let's use the IP address `192.168.1.100`:

- The first octet `192` falls within the Class C range (192-223).
- Default subnet mask for Class C is `255.255.255.0`.

```
IP address:       192.168.1.100
Subnet mask:      255.255.255.0
Binary form:      11000000.10101000.00000001.01100100
Network portion:  11000000.10101000.00000001
Host portion:                                  .01100100
```

The host portion of the IP address `192.168.1.100` is `100`.

**Conclusion**
--------------

Identifying the host portion of an IP address using classful addressing is a critical skill in networking. By understanding the class of an IP address and applying the default subnet mask, you can easily separate the network and host portions. This foundational knowledge will aid in various networking tasks, including IP address planning, subnetting, and troubleshooting. Practice identifying the host portion of different IP addresses to solidify your understanding!

## Subnet Masks

**Identifying the Network Portion of an IP Address**
====================================================

**Introduction to IP Address Structure**
----------------------------------------

An IP address is composed of two main parts: the network portion and the host portion. The network portion identifies the specific network in which a device resides, while the host portion identifies the specific device within that network. Identifying the network portion of an IP address is crucial for tasks such as routing, subnetting, and network management.

**Classful vs. Classless Addressing**
-------------------------------------

In classful addressing, IP addresses are divided into classes (A, B, C, D, and E), and each class has a default subnet mask that separates the network and host portions. In classless addressing, a custom subnet mask (CIDR notation) is used, offering more flexibility in defining network and host portions.

**Understanding Subnet Masks**
------------------------------

A subnet mask is a 32-bit number that masks an IP address and divides it into the network and host portions. It is written in the same format as an IP address, typically in dotted-decimal notation.

### Default Subnet Masks for Classful Addressing:

- **Class A:** `255.0.0.0`
- **Class B:** `255.255.0.0`
- **Class C:** `255.255.255.0`

### CIDR Notation for Classless Inter-Domain Routing:

CIDR notation uses a slash (/) followed by the number of bits in the network portion, e.g., `192.168.1.0/24`.

**Steps to Identify the Network Portion**
------------------------------------------

1. Identify the Subnet Mask

For classful addressing, use the default subnet mask based on the IP class. For CIDR notation, derive the subnet mask from the CIDR prefix length.

2. Convert IP Address and Subnet Mask to Binary

Convert both the IP address and subnet mask to their binary forms. This helps visualize which bits belong to the network portion and which belong to the host portion.

3. Perform a Bitwise AND Operation

To find the network portion, perform a bitwise AND operation between the binary IP address and subnet mask. The result will give you the network address.

### Examples

1. Classful Addressing (Class B IP Address)

IP Address: `172.16.5.4`
Default Subnet Mask for Class B: `255.255.0.0`

**Convert to Binary:**

```
IP address:       172.16.5.4
                  10101100.00010000.00000101.00000100

Subnet mask:      255.255.0.0
                  11111111.11111111.00000000.00000000
```

**Perform Bitwise AND Operation:**

```
Network Address:  172.16.0.0
                  10101100.00010000.00000000.00000000
```

The network portion of the IP address `172.16.5.4` is `172.16.0.0`.

2. Classless Addressing (CIDR Notation)

IP Address: `192.168.1.130/25`
CIDR Notation: `/25` (This means the first 25 bits are the network portion)

**Convert to Binary:**

```
IP address:       192.168.1.130
                  11000000.10101000.00000001.10000010

Subnet mask /25:  255.255.255.128
                  11111111.11111111.11111111.10000000
```

**Perform Bitwise AND Operation:**

```
Network Address:  192.168.1.128
                  11000000.10101000.00000001.10000000
```

The network portion of the IP address `192.168.1.130/25` is `192.168.1.128`.

**Practice Exercise**
----------------------

Identify the network portion of the following IP addresses:

1. `10.1.2.3` (Class A, default subnet mask)
2. `173.45.67.89` (Class B, default subnet mask)
3. `203.0.113.20` (Class C, default subnet mask)
4. `192.168.10.15/28` (CIDR notation)
5. `172.16.32.45/20` (CIDR notation)

**Solutions:**

1. **Class A:**
   - IP Address: `10.1.2.3`
   - Default Subnet Mask: `255.0.0.0`
   - Network Portion: `10.0.0.0`

2. **Class B:**
   - IP Address: `173.45.67.89`
   - Default Subnet Mask: `255.255.0.0`
   - Network Portion: `173.45.0.0`

3. **Class C:**
   - IP Address: `203.0.113.20`
   - Default Subnet Mask: `255.255.255.0`
   - Network Portion: `203.0.113.0`

4. **CIDR Notation:**
   - IP Address: `192.168.10.15/28`
   - Subnet Mask: `255.255.255.240`
   - Network Portion: `192.168.10.0`

5. **CIDR Notation:**
   - IP Address: `172.16.32.45/20`
   - Subnet Mask: `255.255.240.0`
   - Network Portion: `172.16.32.0`

**Conclusion**
--------------

Identifying the network portion of an IP address is a fundamental skill in networking. By employing subnet masks and CIDR notation, you can accurately determine the network address, which is essential for network design, IP allocation, and troubleshooting. Understanding and practicing these concepts will enhance your ability to manage and configure networks efficiently.

### ANDing with Default Subnet Masks

**Subnetting Through ANDing for Default Subnet Masks**
======================================================

**Introduction to Subnetting**
------------------------------

Subnetting is the process of dividing a larger network into smaller, more manageable sub-networks, known as subnets. This practice helps optimize network performance and enhances security and organization. Understanding subnetting is crucial for network administration, especially when dealing with IP address allocation and routing.

**Understanding ANDing in IP Networking**
------------------------------------------

ANDing is a bitwise operation used to determine the network address from a given IP address and subnet mask. In this lesson, we'll focus on using ANDing with the default subnet masks for classful IP addressing (Classes A, B, and C).

**What is ANDing?**
-------------------

The AND operation compares two binary digits (bits) and outputs 1 if both bits are 1; otherwise, it outputs 0. The operation applies to each pair of corresponding bits in two binary numbers.

**Step-by-Step Guide to ANDing**
--------------------------------

1. Convert IP Address and Subnet Mask to Binary

Convert both the IP address and the subnet mask to their binary forms. This helps visualize the ANDing process.

2. Perform the Bitwise AND Operation

Compare each bit of the IP address with the corresponding bit of the subnet mask. Use the AND operation to determine the resulting network address.

3. Convert the Resulting Network Address Back to Decimal

Convert the binary result of the AND operation back to its decimal form to get the network address.

### Examples

1. Class A IP Address
======================

Let's use the IP address `10.20.30.40` and the default Class A subnet mask `255.0.0.0`.

1. Convert to Binary

```
IP Address:             10.20.30.40
Binary IP Address:      00001010.00010100.00011110.00101000

Subnet Mask:            255.0.0.0
Binary Subnet Mask:     11111111.00000000.00000000.00000000
```

2. Perform AND Operation

```
Binary Network Address: (00001010.00010100.00011110.00101000)
AND                                     (11111111.00000000.00000000.00000000)
Result:                                 (00001010.00000000.00000000.00000000)
```

3. Convert Back to Decimal

```
Resulting Network Address: 10.0.0.0
```

2. Class B IP Address
=====================

Let's use the IP address `172.16.5.128` with the default Class B subnet mask `255.255.0.0`.

1. Convert to Binary

```
IP Address:             172.16.5.128
Binary IP Address:      10101100.00010000.00000101.10000000

Subnet Mask:            255.255.0.0
Binary Subnet Mask:     11111111.11111111.00000000.00000000
```

2. Perform AND Operation

```
Binary Network Address: (10101100.00010000.00000101.10000000)
AND                                     (11111111.11111111.00000000.00000000)
Result:                                 (10101100.00010000.00000000.00000000)
```

3. Convert Back to Decimal

```
Resulting Network Address: 172.16.0.0
```

3. Class C IP Address
=================================

Let's use the IP address `192.168.1.1` with the default Class C subnet mask `255.255.255.0`.

1. Convert to Binary

```
IP Address:             192.168.1.1
Binary IP Address:      11000000.10101000.00000001.00000001

Subnet Mask:            255.255.255.0
Binary Subnet Mask:     11111111.11111111.11111111.00000000
```

2. Perform AND Operation

```
Binary Network Address: (11000000.10101000.00000001.00000001)
AND                                     (11111111.11111111.11111111.00000000)
Result:                                 (11000000.10101000.00000001.00000000)
```

3. Convert Back to Decimal

```
Resulting Network Address: 192.168.1.0
```

**Practice Exercises**
-----------------------

Identify the network address for the following IP addresses using their default subnet masks:

1. `11.22.33.44` (Class A)
2. `150.200.100.50` (Class B)
3. `203.0.113.25` (Class C)

Solutions
----------
1. **Class A:**
   - IP Address: `11.22.33.44`
   - Subnet Mask: `255.0.0.0`
   - Network Address: `11.0.0.0`

2. **Class B:**
   - IP Address: `150.200.100.50`
   - Subnet Mask: `255.255.0.0`
   - Network Address: `150.200.0.0`

3. **Class C:**
   - IP Address: `203.0.113.25`
   - Subnet Mask: `255.255.255.0`
   - Network Address: `203.0.113.0`

**Conclusion**
--------------

Subnetting through ANDing is an essential skill in networking for understanding how IP addresses and subnet masks interact to define network boundaries. By converting IP addresses and subnet masks to binary, performing the AND operation, and converting the result back to decimal, you can accurately determine the network address. This foundational knowledge aids in network design, routing, and efficient IP address management. Practice these steps to become proficient in subnetting with default subnet masks!

### ANDing with Custom Subnet Masks
**Subnetting Through ANDing for Custom CIDR Subnet Masks**
==========================================================

**Introduction to CIDR and Custom Subnet Masks**
------------------------------------------------

Classless Inter-Domain Routing (CIDR) is a method for allocating IP addresses and routing that allows for more granular and flexible subnetting compared to classful addressing. CIDR notation specifies a network prefix length, which determines how many bits are used for the network portion of an IP address. This helps in efficiently using IP address space and simplifying routing.

**Understanding CIDR Notation**
-------------------------------

CIDR notation uses the format `A.B.C.D/n`, where:
- `A.B.C.D` is the IP address.
- `/n` indicates the number of bits used for the network portion.

For example, `192.168.1.10/24` means the first 24 bits of the IP address represent the network portion.

**Steps to Subnetting Through ANDing with Custom CIDR Subnet Masks**
--------------------------------------------------------------------

This process involves determining the network address using a custom subnet mask derived from the CIDR prefix length.

### Step 1: Convert IP Address and Subnet Mask to Binary

Convert both the IP address and the subnet mask to their binary forms. For a custom subnet mask, the CIDR prefix length will help you create the subnet mask in binary.

### Step 2: Perform the Bitwise AND Operation

Compare each bit of the IP address with the corresponding bit of the subnet mask. Use the AND operation to determine the resulting network address.

### Step 3: Convert the Resulting Network Address Back to Decimal

Convert the binary result of the AND operation back to its decimal form to get the network address.

### Examples

#### Example 1: CIDR Notation `/26`

IP Address: `192.168.1.130/26`
CIDR Notation: `/26` (26 bits for the network portion)

**Step 1: Convert to Binary**

```
IP Address:             192.168.1.130
Binary IP Address:      11000000.10101000.00000001.10000010

Subnet Mask /26:        255.255.255.192
Binary Subnet Mask:     11111111.11111111.11111111.11000000
```

**Step 2: Perform AND Operation**

```
Binary Network Address: (11000000.10101000.00000001.10000010)
AND                     (11111111.11111111.11111111.11000000)
Result:                 (11000000.10101000.00000001.10000000)
```

**Step 3: Convert Back to Decimal**

```
Resulting Network Address: 192.168.1.128
```

#### Example 2: CIDR Notation `/20`

IP Address: `172.16.50.200/20`
CIDR Notation: `/20` (20 bits for the network portion)

**Step 1: Convert to Binary**

```
IP Address:             172.16.50.200
Binary IP Address:      10101100.00010000.00110010.11001000

Subnet Mask /20:        255.255.240.0
Binary Subnet Mask:     11111111.11111111.11110000.00000000
```

**Step 2: Perform AND Operation**

```
Binary Network Address: (10101100.00010000.00110010.11001000)
AND                     (11111111.11111111.11110000.00000000)
Result:                 (10101100.00010000.00110000.00000000)
```

**Step 3: Convert Back to Decimal**

```
Resulting Network Address: 172.16.48.0
```

#### Example 3: CIDR Notation `/19`

IP Address: `203.0.113.25/19`
CIDR Notation: `/19` (19 bits for the network portion)

**Step 1: Convert to Binary**

```
IP Address:             203.0.113.25
Binary IP Address:      11001011.00000000.01110001.00011001

Subnet Mask /19:        255.255.224.0
Binary Subnet Mask:     11111111.11111111.11100000.00000000
```

**Step 2: Perform AND Operation**

```
Binary Network Address: (11001011.00000000.01110001.00011001)
AND                     (11111111.11111111.11100000.00000000)
Result:                 (11001011.00000000.01100000.00000000)
```

**Step 3: Convert Back to Decimal**

```
Resulting Network Address: 203.0.96.0
```

**Practice Exercises**
-----------------------

Identify the network address for the following IP addresses using their CIDR subnet masks:

1. `10.1.2.3/8`
2. `192.168.100.50/23`
3. `172.16.5.10/21`
4. `198.51.100.6/30`
5. `203.0.113.75/28`

### Solutions:

1. **CIDR `/8`:**
   - IP Address: `10.1.2.3`
   - Subnet Mask: `255.0.0.0`
   - Network Address: `10.0.0.0`

2. **CIDR `/23`:**
   - IP Address: `192.168.100.50`
   - Subnet Mask: `255.255.254.0`
   - Network Address: `192.168.100.0`

3. **CIDR `/21`:**
   - IP Address: `172.16.5.10`
   - Subnet Mask: `255.255.248.0`
   - Network Address: `172.16.0.0`

4. **CIDR `/30`:**
   - IP Address: `198.51.100.6`
   - Subnet Mask: `255.255.255.252`
   - Network Address: `198.51.100.4`

5. **CIDR `/28`:**
   - IP Address: `203.0.113.75`
   - Subnet Mask: `255.255.255.240`
   - Network Address: `203.0.113.64`

**Conclusion**
--------------

Subnetting through ANDing with custom CIDR subnet masks provides a flexible and efficient way to manage IP address space. By converting IP addresses and subnet masks to binary, performing a bitwise AND operation, and converting the result back to decimal, you can accurately determine the network address. This knowledge is fundamental for tasks such as IP address planning, network design, and efficient routing. Practice these steps to become proficient in subnetting with CIDR!
### Determining Subnet Sizes
Sure, here's a more textbook-like version of the lesson, with an explanation of why we subtract two hosts for the broadcast and network addresses:

---

# Determining the Size of a Subnet in VLSM Subnetting

## Objective
By the end of this lesson, you will be able to determine the size of a subnet when performing Variable Length Subnet Mask (VLSM) subnetting.

## Introduction

In network design, Variable Length Subnet Masking (VLSM) is an advanced technique that allows for more efficient use of IP address space. Unlike Fixed Length Subnet Masking (FLSM), where each subnet is of equal size, VLSM enables the creation of subnets with varying sizes. This flexibility is particularly useful in real-world scenarios where different segments of a network require different numbers of hosts.

### Understanding Subnet Masks
A subnet mask divides an IP address into two parts: the network part and the host part. For instance, the subnet mask `255.255.255.224` in binary is:

```
11111111.11111111.11111111.11100000
```

This informs us that the first 27 bits are used for the network part, while the remaining bits are for host addresses. But how do we use this information to calculate the number of hosts per subnet? Let's break it down step-by-step.

## Step-by-Step Guide

### Step 1: Determine the Subnet Mask

First, convert the subnet mask to its binary form. For `255.255.255.224`:

```
11111111.11111111.11111111.11100000
```

Count the number of consecutive 1's from the left. In this case, it's 27.

### Step 2: Calculate the Number of Subnets

The number of subnets that can be created depends on the number of bits borrowed for the subnetting. This is determined by:

```
2^(number of bits borrowed)
```

Here, 27 bits are used for the network part, leaving 5 bits for subnetting:

```
2^5 = 32 subnets
```

But it's more common to refer to the network bits directly as the new CIDR notation would now be /27 for each subnet.

### Step 3: Calculate the Number of Hosts per Subnet

To calculate the number of hosts per subnet, we focus on the remaining host bits. For an IPv4 address, there are a total of 32 bits. If 27 are used for the network part, then:

```
32 - 27 = 5 bits left for the host part
```

The formula to calculate the number of hosts is:

```
2^(number of host bits) - 2
```

The subtraction of 2 accounts for two special addresses: the network address and the broadcast address. The network address is the first address in the subnet, used to identify the network itself. The broadcast address is the last address in the subnet, used to communicate with all hosts on the subnet simultaneously. Because these addresses are reserved, they cannot be assigned to individual hosts.

Applying the formula here:

```
2^5 - 2 = 32 - 2 = 30 hosts
```

Thus, each subnet can accommodate 30 hosts.

### Example

Let's consider a practical scenario. Suppose we have a network `192.168.1.0/24` and aim to create subnets with a subnet mask of `255.255.255.224`.

1. **Determine the Subnet Mask**: `255.255.255.224`
2. **Calculate the Number of Network Bits**: `27`
3. **Calculate the Number of Subnets**: `2^(27-24) = 2^3 = 8`
4. **Calculate the Number of Hosts per Subnet**: `2^(32-27) - 2 = 2^5 - 2 = 32 - 2 = 30`

So, in the network `192.168.1.0/24`, with a subnet mask of `255.255.255.224`, each subnet can accommodate 30 hosts.

## Conclusion

In this lesson, you learned to determine the size of a subnet when performing VLSM subnetting. This involves identifying the subnet mask in binary, calculating the number of subnets and hosts per subnet, and understanding why we subtract two addresses to account for the network and broadcast addresses. These are essential concepts in efficient IP address management and network design.

## Practice Exercises

1. Given a subnet mask of `255.255.254.0`, how many hosts can each subnet accommodate? Explain your steps.
2. You have the network `10.0.0.0/16`. Create subnets with a subnet mask of `255.255.255.128`. How many hosts can each subnet accommodate? Show your calculations and explain any subtractions made.

**Hint: Carefully count the network and host bits, and always remember to subtract the two reserved addresses for network and broadcast.**

---

This comprehensive guide should provide clarity on VLSM subnetting and help in understanding how to calculate the size of subnets effectively.
### Custom Subnet Masks
Sure, here's a textbook-style lesson on how to calculate custom subnet masks using Liascript markdown:

---

# Calculating Custom Subnet Masks

## Objective
By the end of this lesson, you will be able to calculate custom subnet masks for specific network requirements.

## Introduction

Custom subnet masks are used to divide a network into subnets of varying sizes according to the specific needs of each subnet. This enhances the efficient use of IP address space. To calculate a custom subnet mask, you need to determine the subnet requirements based on the number of hosts or subnets needed.

## Step-by-Step Guide

### Step 1: Determine the Requirement

First, identify whether your requirement is based on the number of hosts per subnet or the number of subnets.

- **Number of Hosts per Subnet**: If you need a specific number of hosts per subnet, you need to calculate the number of host bits required.
- **Number of Subnets**: If you need a specific number of subnets, you need to calculate the number of bits to be borrowed from the host part.

### Step 2: Calculate Host Bits Needed

**Formula**: 
\[ \text{Number of Host Bits} = \text{ceil}(\log_2(\text{Number of Required Hosts} + 2)) \]

The `+ 2` accounts for the network and broadcast addresses which cannot be assigned to hosts.

### Step 3: Calculate the Subnet Mask

Subtract the number of host bits from 32 to get the number of network bits (for IPv4 addresses). Then, convert the number of network bits into a dotted-decimal format to get the subnet mask.

**Formula**: 
\[ \text{Number of Network Bits} = 32 - \text{Number of Host Bits} \]

### Step 4: Convert to Dotted-Decimal Notation

Convert the binary subnet mask to its dotted-decimal notation.

### Example: Custom Subnet Mask for a Given Number of Hosts

#### Scenario
Suppose you need to create subnets that can each hold up to 50 hosts from a network `192.168.1.0`.

1. **Calculate Host Bits Needed**:
   \[ \log_2(50 + 2) = \log_2(52) \approx 5.7 \]
   Rounding up:
   \[ \text{Number of Host Bits} = 6 \]

2. **Calculate the Subnet Mask**:
   \[ \text{Number of Network Bits} = 32 - 6 = 26 \]

3. **Construct the Subnet Mask in Binary**:
   \[ \text{11111111.11111111.11111111.11000000} \]

4. **Convert to Dotted-Decimal Notation**:
   The binary `11111111.11111111.11111111.11000000` converts to:
   \[ 255.255.255.192 \]

So, the custom subnet mask for subnets that can each hold up to 50 hosts is `255.255.255.192`.

### Example: Custom Subnet Mask for a Given Number of Subnets

#### Scenario
Suppose we need 10 subnets within a network `192.168.1.0/24`.

1. **Calculate Bits Needed for Subnets**:
   \[ \log_2(10) \approx 3.3 \]
   Rounding up:
   \[ \text{Number of Subnet Bits} = 4 \]

2. **Calculate the Subnet Mask**:
   Starting from a /24 network (`255.255.255.0`):
   \[ \text{New CIDR Notation} = 24 + 4 = 28 \]

3. **Construct the Subnet Mask in Binary**:
   \[ \text{11111111.11111111.11111111.11110000} \]

4. **Convert to Dotted-Decimal Notation**:
   Binary `11111111.11111111.11111111.11110000` converts to:
   \[ 255.255.255.240 \]

So, the custom subnet mask for 10 subnets within a `192.168.1.0/24` network is `255.255.255.240`.

## Conclusion

In this lesson, we explored how to calculate custom subnet masks based on specific network requirements. By understanding the need for hosts per subnet or the number of subnets, we can appropriately allocate the number of bits and convert these to a subnet mask in dotted-decimal notation. Mastering this skill is crucial for effective network design and IP address management.

## Practice Exercises

1. **Calculate the Subnet Mask**: Determine the custom subnet mask for a network that needs to support up to 200 hosts per subnet.
2. **Custom Subnets**: Calculate the subnet mask needed to create 15 subnets from a `172.16.0.0/16` network.

---

This structured guide helps in understanding the process of calculating custom subnet masks and is useful for students and professionals in network design.

## Subnetting
Insert introduction copy here for practicing defining subnets. 
## Practical Subnetting
Now, take the practicing of subnets and make it real-life. 
