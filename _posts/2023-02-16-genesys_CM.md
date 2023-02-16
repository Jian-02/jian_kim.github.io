---
layout: post
title: Genesys Conversation Manager 
subtitle: Genesys CM
categories: Genesys
tags: [genesys, AICC]
---
  
2023/02/16 Genesys CM course of 공재석, AICC2 책임.  

-----
## Context data 
Call, Message, Video -> Omni channels == Context data.  
Context data has a bisuiness rule, it's same to routing rule.  
  
## Context Service  
Context service has context database. The DB is Kasandra.(Genesys couldn't care other DB.)  
Context service use **REST API**.  
  
## Context Structure
Context Service  
```bash
├── Context Service
│   ├── Context State
│       ├── Context Task
│       ├── Context Task
│   ├── Context State
│       ├── Context Task
│       ├── Context Task
├── Context Service
│   ├── Context State
``` 

Task: detail.  
Context Service is like a funtion.  

----

## Business Rule
business rule: rule + action  
Ex) Platinum customer: The customer who has higher platinum level, connect the vip agent.  
  
* CTI has the stratgy about customer level, but CTI couldn't process in real time.  
  
* CM could process in real time. But CM needs call data about all customer. Then, engine and URI process the stratgy.  
  
* ORS: Orchestration Routing Service  
  
## Genesys journey
Genesys has the default web UI that provides journey history.  
But the statistics web UI needs to develop.  
  
* CTI & IVR made by virtual machine using 뉴타닉스. And they could save data about customers.  
** CTI & IVR update customer information after recive uuid, message and homepage update the data. -> It means that genesys is the main.  
  
* The result is that customer wants journey.  
  
**It develops using gcxi(genesys statistics package)**
  
* Genesys lisense price = (The number of consultant) * (1 per price)  