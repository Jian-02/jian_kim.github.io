---
layout: post
title: AICC2 course
subtitle: important of OS, DB
categories: AICC
tags: [AICC]
---
  
2023/02/20, 21 first course of team, AICC2.  
The instructor is 추한승.  
  
-----
# OS
We use RedHat OS or CentOS.  
  
# DB
We use oracle DB, using sqlplus.  
  
# Server file
Recieved the file about server id and passwd to development.  
  
----
# Linux(CentOS 7.0) SetUp
## Network setup
When turn on the linux, you can see the wifi is down.  
1. Verify the nework status using `ifconfig` command.  
2. If the network(ens**) is down, ifup the network. The command is `ifup <ens**>`  
3. Then, you can see the network connects well.  
  
### Network Automatic Setting
1. Verify the network config file in `/etc/sysconfig/network-scripts/ifcfg-ens**` if that is it.  
```
ls /etc/sysconfig/network-scripts/ifcfg-ens**
```
2. Backup the config file.  
3. Edit the config file `ONBOOT=no` to `ONBOOT=yes`.  
  
