---
layout: post
title: SIP message
subtitle: sip invite message
categories: AICC, Genesys
tags: [AICC, genesys, Network]
---
  
# Queue vs Routing Point  
**Queue has a wall, Routing Point has a hole to out.**  

Queue  
enter: EventQueued(CCPulse: CallEntered)  
exit: EventDiverted(CCPulse: CallDistributed)  
failt: EventAbandoned  
  
RoutingPoint  
enter: EventQueued  
exit: EventDiverted  
**Routing Point has a hole to out and enable to load the strategy. So, it's not FIFO always.**  
  
Sometime ANY number is the self phone number in the strategy.  
  
## Difference between Queue and Routing Point
Queue doesn't have the hole to out, So it has fail case and follow the FIFO algorythm.  
Routing Point has a hole to out and enable to CTI strategy.  
  
# SIP message
```
13:39:18.897: SIPTR: Received [0,UDP] 502 bytes from 10.1.33.4:5060 <<<<<
REGISTER sip:10.1.14.175:5060;transport=udp SIP/2.0
From: "Genesys Softphone" <sip:7014@10.1.14.175:5060>;tag=1C711677-9543-43E2-A7CB-F3A814E3DDE2-1
To: <sip:7014@10.1.14.175:5060>
Call-ID: 3E6FB390-0EA6-4CB4-BA6A-92D1C2908E2F-1@10.1.33.4
CSeq: 520 REGISTER
Content-Length: 0
Via: SIP/2.0/UDP 10.1.33.4:5060;branch=z9hG4bK115B9E53-A36B-46AE-9DED-8C89B46E8CD5-523
User-Agent: Genesys-Softphone/8.5.400.10 (Windows 10.0.19045)
Max-Forwards: 70
Contact: <sip:7014@10.1.33.4:5060>
Expires: 60
```  
<<<<< : Entered the SIP message  
7014@10.1.14.175 : URI  
User-Agent: footprint(softphone information)  
Expires 60: Check time -> 60 sec, but usually check the 2/3 times of 60 sec.  

```
13:39:18.897: Sending  [0,UDP] 462 bytes to 10.1.33.4:5060 >>>>>
SIP/2.0 200 OK
From: "Genesys Softphone" <sip:7014@10.1.14.175:5060>;tag=1C711677-9543-43E2-A7CB-F3A814E3DDE2-1
To: <sip:7014@10.1.14.175:5060>;tag=0044E04E-33A9-13E4-8A2B-0100007FAA77-278149
Call-ID: 3E6FB390-0EA6-4CB4-BA6A-92D1C2908E2F-1@10.1.33.4
CSeq: 520 REGISTER
Via: SIP/2.0/UDP 10.1.33.4:5060;branch=z9hG4bK115B9E53-A36B-46AE-9DED-8C89B46E8CD5-523;received=10.1.33.4
Contact: <sip:7014@10.1.33.4:5060>;expires=60
Expires: 60
Content-Length: 0
```  
