---
layout: post
title: Kubernetes
subtitle: Kubernetes & Docker
categories: Inflearn
tags: [linux,kubernetes,docker,container,orchastration]
---
  
2023/02/06 Kubernetes course.  
  
# Kubernetes
How to manage server?  
1. Make documentation(PPT, Word, Hangul etc...).  
2. Server Management Tool(CHEF, ANSIBLE, PUPPET).  
3. Manage version(Virtual Box).  
  
--> Let's use Docker!  
Docker: All environment is container.  
  
## What is Container?
Contatiner  
* Easier, more efficient.  
* Easy to deployment and callback.  
* No dependency about specific cloud bander.  
  
## Flow
Implement(Write code) -> Build(Make a container) -> Ship(Save the container) -> Run  
--> It's standardized.  
  
# After docker
server1: `docker stop app & run`  
server2: `docker stop app & run`  
server3: `docker stop app & run`  
--> It's waste.  
  
Previous  
  * Proxy --manage--> web  

If the web is more than 2 because of the much datas.  
  * Proxy --LoadBalancer--> web  
                        --> web
                          
## Service Exposure(GateWay)
|Nginx(Proxy)|Nginx(Proxy)|Nginx(Proxy)|Nginx(Proxy)|
|----|----|----|----|
|App1|App2|App3|App4|

  
Manage error -> Contatiner Orchestration  
  
# Kubernetes
Kubernetes: Deployment and management the applications containered.  
  
### Architecture: Desired state  
Check status -> Find difference -> solve -> check... --> Loop architecture.  
  
### Ingres
Wrap as the kubernetes nginx services.  
  
### Yaml
Array: use `-`  
Annotation: use `#`
True/False: `ture/false, TRUE/FALSE, yes/no`  