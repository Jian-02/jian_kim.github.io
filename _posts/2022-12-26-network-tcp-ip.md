---
layout: post
title: Network TCP/IP course
subtitle: TCP/IP & UDP, Socket Programming
categories: freshman training
tags: [Network, TCP/IP, UDP, Socket]
---

2022/12/16 Freshman Training of Hansol Inticube.  
Instructor is **정갑식** and **위장민**.  
  
## TCP/IP
  
Connection - 3 Way HandShacking  

@startuml firstDiagram

Client->Server: SYN
Server->Client: SYN, ACK
Client->Server: DATA
Server->Client: ACK
@enduml
  
Close - 4 Way HandShaking  

@startuml SecondDiagram
Client->Server: FIN
Note left of Client: Activate close
Note right of Server: Recieve Close Signal
Server->Client: ACK
Server->Client: FIN
Client->Server: ACK
Note left of Client: Closed
Note right of Server: Closed
@enduml
  
## UDP
  
They doesn't connection between server and client.  
Client/Server just send data like to throw into the hole.  
Thus, Some data may be lost. It used to sending and recieving media data. Because they don't have any problem, loosing some data.  



  