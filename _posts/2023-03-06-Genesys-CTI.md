---
layout: post
title: Genesys CTI
subtitle: genesys cti last report
categories: AICC,Genesys
tags: [AICC, genesys]
---
  
# Genesys CTI Last report
Complete to submit  
## What is Genesys?  
1. Screen popping  
call information screen of Agent  
Inbound case, if recieve the call, automatically user could see the popup screen. Agent could be easy to see the user's information withouth many clicks. It's the famous characteristic.  
2. Automatic Dialing  
execute -> could call automatically  
Outbound case, open list -> call to users: it's really onerous thing. If ther is CTI campaign list, agent could call using campaign list.  
3. Phone Controls  
Enable to call control(call, transfer, release)  
4. Call Routing / Transfering  
Setting to recieve rull of call.  
## Genesys system structure
<img src="https://user-images.githubusercontent.com/46213631/224585610-1a973dcf-43b1-4807-a211-c6a738a7c652.png" />  

### input part
If the call entered by trunk line(국선), entered the SIP server though GateWay(SBC).  
SIP T-Lib: control call  
SIP T-Server: translate  

### management layer
Config Server: Starter when the service starts  
IRD: Rouing Design, make strategy  
URS(Universal Routing): call distribution server. doesn't have status information -> URS ask to STAT server(ex. WHo is longest wait person?)  
STAT: have the real-time information. send this informations to URS  
ORS(Orchestration Server): Centralized task management system(중앙 집중식 관리 시스템), process the automatic task by the interaction between various channels and business.  
  
### Statistics layer
SCI/GAX: GUI of management system  
SCS(Solution Control Server): Combine and mange server, router, media server, and ect. Used to consistent task.  
ICON(Interation Concentrator): Store the information to cut.  
  
### ECT
LCA(Local Control Agent): Real-time system check system  
Message Server: Alarm  
  
## Genesys Package description & structure
### Structure
`READ_ME.html` == `ip_description.xml`  
Description about Product and target platfforms.  
Other files -> Binary files to need to install.  
  
### Description
1. GAX(Genesys Administrator Extension)  
Tool that system manager use  
2. GAXi(Genesys Customer Experience Insights  customer experience analyze and increase solution  
3. InfoMart  
Provide data mart to use history report of Contact Center.  
Provide Database and Manager's GUI, Server architecture.  
4. CCPulse+  
Real-time monitoring and report tool  
5. ICON(Interation Concentrator)  
Use the IDB(Interation Databse)) that the one of analysis provider with Genesys Reporting  
Store Reporting data  
  
## Genesys System vs other CTI system
### Genesys CIM vs CTI Bridge
Genesys CIM: Aim to customer interation management.  
Genesys CTI Bridge: Aim to connect and integrete 3rd system and genesys platform.  
Genesys Bridge doesn't have Rouing process, they only has T-Server.  
  
### Genesys CTI vs Avaya
Genesys CTI: One system that has PBX, T-server, and T-lib. So, It's to convinence to register DNs, they just need to register onetime.  
Avaya: Other system to T-server and AES. So, It's to complex when register DNs. They need to register DNs to AES and T-Server, total 2 times.  
Avaya CTI: T-Server, STAT, URS  
Genesys CTI: PBX, T-Lib, T-Server  
  
Genesys CTI: SW  
Avaya: HW  
## Resolution
1. Sincerity  
2. Collaboration  
3. Technology  