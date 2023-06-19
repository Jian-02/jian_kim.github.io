---
layout: post
title: Genesys Dual Register Error 
subtitle: genesys
categories: AICC, Genesys
tags: [AICC, Genesys]
---

# Make new switchies  
   
In CME, 
Make new sip server: sipserver_kim,  
Listening Port: 7010,  
sip port: 5060,  
Directory: /gcti/sipserver_kim,  
Log Directory: /logs/sipserver_kim  
  
Switch Office: JianOffice,  
DN, Agent Logins: Same to Switch_jian  
  
# Install sip server  
Lisense Host&Port: 7260@glab-winsvr  
  
# Dual Register error  
Using Genesys SoftPhone,  
Register 7201 of 5060 port and 6070 port.  
  
MicroSIP: 7202 of 5060  
  
When 7202 calls to 7201, not try to call.  
* Unregister Genesys Softphone(diable status) -> not works.  
* Using configuration file, unregister Genesys Softphone -> works.  
  
# When occurs dual register in site  
** Unregister on the phone, Restart **
