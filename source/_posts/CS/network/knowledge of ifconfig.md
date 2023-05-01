---
title: "knowledge of ifconfig"
date: 2023-04-22
categories: [CS,network]
---

***
**i'm a linux learner, i want you teach me something about internet . could you explain me the following content in easy to understand way?**    
***
Sure! What you're looking at is the output of a command that displays information about the network interfaces on a Linux system. This output shows details for four network interfaces: `docker0`, `ens33`, `lo`, and `veth557dd78`.

Let's break down each section in simpler terms:

1. `docker0`: This is a virtual network interface created by Docker, a container platform. The information provided includes:

   ```bash
   docker0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
           inet 172.17.0.1  netmask 255.255.0.0  broadcast 172.17.255.255
           inet6 fe80::42:46ff:fe73:fc6c  prefixlen 64  scopeid 0x20<link>
           ether 02:42:46:73:fc:6c  txqueuelen 0  (以太网)
           RX packets 0  bytes 0 (0.0 B)
           RX errors 0  dropped 0  overruns 0  frame 0
           TX packets 36  bytes 4946 (4.9 KB)
           TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
   ```

2. `ens33`: This is a physical Ethernet interface connected to the system. The information provided includes:

3. `lo`: This is the loopback interface, which is a virtual network interface that allows the system to communicate with itself. 

4. `veth557dd78`: This is another virtual Ethernet interface, likely associated with a Docker container.

In summary, this output provides information about the network interfaces on your system, including IP addresses, subnet masks, broadcast addresses, and details about received and transmitted packets.

***
**physical Ethernet interface    loopback interface,  virtual Ethernet interface, MAC address  i don't know these terms**
***
I understand. Let me explain these terms in a simpler way:

1. **Physical Ethernet interface**: This is a hardware component that connects your computer to a wired network, usually using an Ethernet cable. The Ethernet interface handles sending and receiving data between your computer and the network. An example of a physical Ethernet interface is the `ens33` interface from the output you provided.

2. **Loopback interface**: This is a special virtual network interface that allows your computer to communicate with itself. It is mainly used for testing and troubleshooting purposes. The IP address assigned to the loopback interface is usually `127.0.0.1` for IPv4 and `::1` for IPv6. The `lo` interface from the output you provided is a loopback interface.

3. **Virtual Ethernet interface**: This is a software-created network interface that emulates the behavior of a physical Ethernet interface. Virtual Ethernet interfaces are often used in virtualization and containerization technologies, like Docker, to provide network connectivity for virtual machines or containers. An example of a virtual Ethernet interface is the `docker0` interface from the output you provided.

4. **MAC address**: A Media Access Control (MAC) address is a unique identifier assigned to a network interface. It is used to identify devices on a network at the data link layer (Layer 2) of the OSI model. MAC addresses are 48 bits in length and are usually represented as six groups of two hexadecimal digits, separated by colons or hyphens (e.g., `02:42:46:73:fc:6c`). Every network interface, whether physical or virtual, has a MAC address.

***
**above is my virtual machine's information, following is my real pc's information, tell me their relationship and other details what are helpful to my learning :Windows IP Configuration**
***

```markdown
Windows IP Configuration

Ethernet adapter Ethernet:

   Media State . . . . . . . . . . . : Media disconnected
   Connection-specific DNS Suffix  . :

Wireless LAN adapter Local Area Connection* 1:

   Media State . . . . . . . . . . . : Media disconnected
   Connection-specific DNS Suffix  . :

Wireless LAN adapter Local Area Connection* 2:

   Media State . . . . . . . . . . . : Media disconnected
   Connection-specific DNS Suffix  . :

Ethernet adapter VMware Network Adapter VMnet1:

   Connection-specific DNS Suffix  . :
   Link-local IPv6 Address . . . . . : fe80::9a10:ed69:ef20:bf29%5
   IPv4 Address. . . . . . . . . . . : 192.168.141.1
   Subnet Mask . . . . . . . . . . . : 255.255.255.0
   Default Gateway . . . . . . . . . :

Ethernet adapter VMware Network Adapter VMnet8: 

   Connection-specific DNS Suffix  . :
   Link-local IPv6 Address . . . . . : fe80::b288:751e:149a:1576%7
   IPv4 Address. . . . . . . . . . . : 192.168.255.1
   Subnet Mask . . . . . . . . . . . : 255.255.255.0
   Default Gateway . . . . . . . . . :

Wireless LAN adapter Wi-Fi:

   Connection-specific DNS Suffix  . :
   Link-local IPv6 Address . . . . . : fe80::d68c:caed:21ae:5496%11
   IPv4 Address. . . . . . . . . . . : 192.168.31.56
   Subnet Mask . . . . . . . . . . . : 255.255.255.0
   Default Gateway . . . . . . . . . : 192.168.31.1

Ethernet adapter Bluetooth Network Connection:

   Media State . . . . . . . . . . . : Media disconnected
   Connection-specific DNS Suffix  . :
```
***
The information you provided shows the network interfaces on your real PC, which is running Windows. There are several network interfaces listed, including Ethernet, Wireless LAN (Wi-Fi), and virtual network interfaces created by VMware. Let's look at the relationship between your real PC and the virtual machine (VM) you mentioned earlier, as well as other useful details for your learning.

1. **Ethernet adapter Ethernet**: This is the physical Ethernet interface on your real PC. It is currently disconnected (Media State: Media disconnected).

2. **Wireless LAN adapters (Local Area Connection* 1, Local Area Connection* 2, Wi-Fi)**: These are the Wi-Fi interfaces on your real PC. Only the Wi-Fi adapter is connected and has an IP address (IPv4 Address: 192.168.31.56) and a default gateway (192.168.31.1).

3. **Ethernet adapter VMware Network Adapter VMnet1 & VMnet8**: These are virtual network interfaces created by VMware, a virtualization software. They provide network connectivity between your real PC and the virtual machines running on VMware. The IP addresses assigned to these interfaces are 192.168.141.1 and 192.168.255.1, respectively.

4. **Ethernet adapter Bluetooth Network Connection**: This is a network interface related to Bluetooth connectivity. It is currently disconnected (Media State: Media disconnected).

Now let's discuss the relationship between your real PC and the virtual machine:

- Your real PC is running VMware, which hosts your Linux virtual machine. 
- The virtual machine is connected to your real PC through virtual network interfaces (VMware Network Adapter VMnet1 and VMnet8).
- The `ens33` interface on your virtual machine is connected to the VMware Network Adapter VMnet8 on your real PC. We can tell this by the matching IP address subnet (192.168.255.x).

In summary, your real PC has several network interfaces, including physical Ethernet, Wi-Fi, and virtual network interfaces created by VMware. The virtual machine hosted on VMware is connected to your real PC through one of these virtual network interfaces. By understanding the relationship between the network interfaces on your real PC and the virtual machine, you can gain a better understanding of how network connectivity is established between them.