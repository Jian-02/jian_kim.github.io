---
layout: post
title: Server install
subtitle: server install
categories: AICC, Genesys
tags: [AICC, genesys]
---
  
There is the proxy about configuration server.  
If there are many people in the server -> make the configuration proxy server process.  
--> User: access the configuration proxy server, then get the data to need.  
  
## GVP
RM(Resource Manager): sip proxy(notiong to do just manage)  
mcp: main process  
was: be embedded was in the mcp.(because the process enable to run to bring the interpreter the scenario)  
  
-> OCS: be embedded mcp, rm  
  
SIP server usage port: 3300 TCP/ 5060 UDP  
RM, MCP port: support only UDP  
  
In general, RM consists of Primary and BackUp server. But sometiones RM consists of Primary and Primary server.  
RM, MCP doesn't need to make connection. They only need to the server information to go look for.  
SIP server: only need to know where RM and MCP are placed.  
--> Config server needs to have the information that where MS is.  
  
## MS vs MCP
MS: Play only hold music  
MCP: media control  
  
(CM)Switches -> ms_mcp: used to throw from SIP to MCP.  
  
## Type
Extension: Agent internal call number  
VTP: Internal call number used to IVR  
RP: waypoint  
VoIP service: used to throw to MCP  
Trunk: Connect between each PBX  
-> if set up the prefix value, call to the ip value registered  
  
### Practice
EventnetworkReached: Means to pass the trunk  
  
Set up SIP annex because of different connID -> Doens't work.  
  
## How to play the hold music using the option of RM/MCP
sip-enable-moh -> true
msml_support -> true
resource_management_by_rm -> true 
  

## IRD
Extension vs Voice Treatment Port   
-> Different to apply in the IRD.  