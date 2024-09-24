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

**Practice Activities**
-----------------------
<iframe src="https://frazier-at-cpcc.github.io/subnetting-essentials/decimal-binary.html" style="border:0px #ffffff none;" name="myiFrame" scrolling="no" frameborder="0" marginheight="0px" marginwidth="0px" height="100%" width="100%" allowfullscreen></iframe>


