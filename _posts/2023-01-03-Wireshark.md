---
layout: post
title: Wireshark
subtitle: network & wireshark
categories: freshman training
tags: [network,wireshark]
---

2023/01/03 Freshman Training of Hansol Inticube.  
Instructor is **전홍렬**.  

## Network  

Network means net+works. It has graph structure, so one user is also network.  

## Wireshark  

Wireshart is using when there are some matters in network.  
  
### Wireshart install  

[download link](https://www.wireshark.org/#download)  
  
### Wireshart using
  
<img src="/assets/images/posts/wireshark_capture.PNG"/>  
Then user can see packet status, and make filter using like code.  

### Difference between Hub and Switch
  
Hub: Broadcasting(all port).  
Switch: Only destination port.  
  
### Subnet Mask
  
8bit * 4
Subnetmask -> before come 0, forward elementries are 1.  
It means 1 doesn't change other number.  
  
* example.  
IPv4: 1.1.1.1  
Subnetmask: 255.255.255.0  
Change the ip to bit number.  
IPv4: 00000001.00000001.00000001.00000001.  
Subnetmask: 11111111.11111111.11111111.00000000 == 1.1.1.0/24 (24 means numbers of 1)  
So, that could be Ipv4 are 1.1.1.1 ~ 1.1.1.254.  
1.1.1.0 couldn't be exist and 1.1.1.255 means doing broadcasting. It means send signal to all ports.  
  
**MAC address Broadcast: ff:ff:ff:ff:ff:ff**
  
### Fragmentation
  
We could know the packet is fragmentation, or not using flags of header.  
<img src="/assets/posts/fragmentation.PNG"/>  
If the second 0 is 1, it means that is not fragmentation.  
And the above value, Identification prove the second packet and first packet are one packet.  
  
### Router
  
Routing is to find the other network way.  
  
Static Routing: Admin register destination and start point.  
Dynamic Routing: Make Routing Table. (Start point <-> Destination)  
  
### GateWay
  
Each Pc, set gateway to broadcast of the same network.  
  
## ARP Protocol
  
ARP is used to when user doesn't know other user's MAC address.  
So, client send the request to all users of LAN, the right user reply to the user the MAC address.  
Once the ARP request occurs, our computer store it. So, when connects to other user more than twice times, PC could find MAC address easily.  
  
**Wireshart could see images of the packet and listen sounds of the packet.**