---
layout: post
title: Genesys & Network
subtitle: relationship of genesys and network
categories: AICC,Genesys
tags: [AICC, genesys, Network]
---
  
2023/02/23 ~ 2023/02/27 Genesys & Network course.  
The instructor is 추한승.  
  
-----
# Virtual IP
VIP(Virtual IP): It could be boss of many IP address of one host.  
<img src="https://t1.daumcdn.net/cfile/tistory/998DF73E5C23877321">  
  
## L4=Load Balance  
Set one VIP, that represent all server provide same service.  
  
# In Genesys, VIP
There are two server, one is Genesys SIP server and backup server.  
When user use microSIP, if the Genesys SIP server is dead, config value must be changed the IP address to backup server IP adress.  
  
But Genesys has VIP.  
So, if SIP server is dead, it's ok not to change the ip config value.  
Load Balance turn on the primary server.  
* OS: virtual lan interface ok.  
  
# Genesys
<img src="https://user-images.githubusercontent.com/46213631/220823257-cd0c1fda-ab78-48bb-8ce0-8147964dfb22.PNG">
  
Genesys SoftPhone: Tlib(3300/TCP) connect  
SIP S is (5060/UDP) connect.  
Micro SIP: SIP S(5060/UDP) connect(inner number 7017)  
  
If user call using genesys softphone, then user can see the log about who and when, etc...  
  
CTI: controller  
command CTI to call, then SIP Server call to them.  
  
## AD
AD: Active Directory  
  
## LDAP
LDAP(Lightweight Directory Access Protocol)  
  
# Genesys configuration manager
Environment -> Applications -> SIP server -> Server Info : There is port information, the port is 3300.  
  
Environmnet -> Persons : There is the person database information.  
It same to remote(10.1.14.179, database).  
And putty `sqlplus genesys/oracle@confserv`  
  
## CTI Link
The connection betwenn CTI and PBX.  
  
# Genesys CTI Tollbar
GWS Architecture(Genesys Web Server) has octopus structure. (Cassandra DB, Elastic Search Cluster, Genesys Environment(Config Server, T-Server, Interaction Server, Chat Server), Universal Contact Server)  
  
## GWS node
Cassandra - elasticsearch : much than 3.  
Use CometD connection.  
->   
Change WebSocket server.  
Use websocket connction.  
  
## Genesys IVR Server
Use PSDK way.  
<img src="https://user-images.githubusercontent.com/46213631/220859415-ca3b11fd-69f7-44b1-a9e2-223e30671fb6.png">
  
## Media GateWay
Media Gateway change TDM data of PSTN to Packet of IP.  
  
## SBC
SBC(Session Board Controller)  
SBC is like Media Gateway, send the result of PSTN to SBC of client.  
They do  
1. Firewall  
2. NAT  
3. Security  
4. Change Codec  
5. Translate SIP message(I think it is necessary, because if codec information is changed, the package message must be changed).  
  
# Genesys Support phone log
Need to be familiar.  
AttributeCallType 3 means it's outbound.  
AttributeCallType 1 means it's internal call.  
AttributeCallType 2 means It's inbound.  
  
ANI: 02-1544-...  
DNIS: 010-9.....  
-> It means it's outbound.  
  
# Genesys Stat Server
Stat Server: Real Time Matrix Engine.  
Stat Server store datas in memory, so they need to much memory.  
  
## Genesys CTI Login
Genesys CTI Login(agent id / agent-logins) = Agent(person information) and Call DNS mapping.  
When use Genesys Config Manager,  
add agent to person DB and add the agent-id.  
Then in support phone, enter the agent id value.  
  
# VoIP
VoIP(Voice over Internet Protocol) : transmission of voice traffic over IP networks.  
VoIP Protocols: Signaling protocols, Media protocols  
  
## SIP
SIP(Session Initiation Protocol)  
based on UCP and IETF.  
* Genesys SIP: Signaling protocol 

## H.323
 Protocol. based on TDP and ITU-T.  
  
## RTP/RTCP
RTP(Real-time Transport Protocol)  
RTCP(Real-time COntrol Protocol)  
Could be different the transfer way between SIP and RTP.  
* SIP transfer way could be long = Transfering data is more faster = The start message(ex. Hi, hello) could be cut.  
  
# Genesys SIP
Genesys SIP can act as Proxy, Register, B2BUA.  
  
# Genesys Stream manager
Genesys stream manager == genesy MCP(Media Control Platform)  
Main function: Playing announcements, simple prompting,ect...  
  
## IP voice quality
1. delay  
2. packet loss  
3. echo compression  
  
# SIP packet massage
  
<img src="https://user-images.githubusercontent.com/46213631/221750388-485707f3-3b11-4d9e-9abf-6ef559ea91cd.PNG"/>
  
INVITE -> start a call.  
Max-Forwards -> hops of the middle  
Via -> waypoint(경유지)
Contact -> real destination address  
  
## Response number
1. 100 -> Trying
2. 180 -> Ringing
3. 200 OK
4. ACK
5. BYE
  
# Genesys support phone log
```
2/27/2023@09:11:44.94
  Event:EventDNOutOfService
   Server:65200
   ThisDN:3011
   Seconds:1677456704
   USeconds:97089
   Server Time:2/27/2023@09:11:44.97

2/27/2023@09:11:51.893
  Event:EventDNBackInService
   Server:65200
   ThisDN:3011
   Seconds:1677456711
   USeconds:890700
   Server Time:2/27/2023@09:11:51.890

```
  
In this log, Out of Service -> usually said OOS.  
OOS check time and reconnect time are managed the oos check option and oos force option.  
  
# Practice make genesys stat server and sip server
/gcti/sipserver/run.sh -> excute arguments: host and port.  
* host, port : configuration server  
  
gax -> `Application` -> `sipserver/statserver` -> auto restart option (if check, kill the process but auto restart)  
  
need to add config value as text value in `confserver.conf` -> because, confserver is the process that runs at the first time.  
  
# Genesys CTI
## Media Gateway
Media Gateway translate TDM to IP.  
  
# Difference of microSIP and Genesys Support phone
microSIP: config manager -> `Annex` -> `Tserver` -> `sip-cti-control` -> token value to `talk, homd, dtmf`: need to click the receive button.  
genesys support phone: doesn't need to click the receive button.  
--> because the token value means that I hook my phone.  
  
# Virtual Queue
*Need to maaping Virtual Queue and Routing Point*  
-> When increase the routing points, don't need to modify the code. just mapping virtual queue and routing point.  
  
Virtual Queue : focous on statistics. Genesys designed to pass the virtual queue.  
  
User can make the virtual queue, and can connect to the virtual queue with routing point using Routing Design.  
Exampel)  
`Routing Design` -> `IVR_IN` click -> some target click -> `use virtual queue` click -> select the switch(ex. seoulSIP) -> Then could see the virtual queues of the switch.  
The virtual queues placed in `Switches` -> `seouldSIP` -> `DNs` of Config Manager.  
  
# Make the new application
There exist sample templates. 
name -> small leteral  
server info -> the place where user install the server.  
ex>   
```
host: glab-framework1
port: 2020
id: default
passwd: password
```
If install *statserver*, one option value is `no`.  
  
# Genesys UR Server
Genesys URS(Genesys Unvisersal Routing)  
Genesys UR is the server that distribute the port, doesn't have the status information.  
  
ex> 
```
URS ask to StatServer: Who is the longest wait person?  
T-Server: **translate** the longest wait, and find the person.  
```
So, URS need to high CPU and doesn't need to memory.  
Stat Server need to high memory.  
  
IRD has loader builder == loading and monitoring.  
In Routing Designer program, `view` tab -> `check intigrety` means check the intigrety(무결성), the red value means the *inconsistency* (불일치)  

  
# OutBound
## Important things of Outbound
* Calling List(DB Table)  
* DNC(Do Not Call)  
-> Who decline the call  
  
Like these things, OCS search the customer information.  
  
Example)  
One customer deny the call center, but it couldn't reflect the Stat Server because it's too fast morning.  
If the OCS search the customer DB, it's reflected but if not it couldn't be reflected.  
  
## Maximum Call number
* Power: the number of the agent * 2  
* Predictive: Predictive  
* Progressive: 1:1 mapping  
* Preview: see and decine the call by agent directly  
* Optimized watched: How to busy the agent, lower than predictive.  
  
## Outbound Contact Server(OCS)
OCS controls the data transfer rate.  
It means OSC know the status of data transfter, and also manage the status.  
  
### How to bring the status?
OCS could bring the status using the mapping data with campaign, calling lists and agent group(Routing Point).  
  
## Stat Server
Stat Server looks at the `place 7011` and the `place 7011` looks at the extension number `7011`.  
  
## CPD Server
CPD Server(Call Progress Detection) Server  
CPD Server is to call actually. It deals with media, so it's same to Media Server(MCP).  
