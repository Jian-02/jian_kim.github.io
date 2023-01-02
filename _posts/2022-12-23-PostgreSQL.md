---
layout: post
title: PostgreSQL
subtitle: PostgreSQL base
categories: freshman training
tags: [Server, Database]
---

2022/12/23 Freshman Training of Hansol Inticube.  
Instructor is **김배일**.  
  
## PostgreSQL
PostgreSQL is famous as one of free source DataBase.  
MySQL and MariaDB are also free Database, but the two has some matters, we usually use PostgreSQL.  
  
----
### Install PostgreSQL on Ubuntu
Use Ubuntu with WSL2.  
* WSL install on Windows PowerShell
```wsl --install```
  
```sudo apt-get update && upgrade```  
```sudo apt-get install postgresql postgresql-contrib```
  
----
### PostgreSQL cluster structure
<img src="./images/postgreSQL cluster structure.png" />
  
We need to make cluster.  
It can be made the below command.  

```initdb -D [directory location]```
  
If you see `initdb:command not found`, then `sudo find / -name "initdb"`.  
And change the directory to the result of the second command.  
`./initdb -D [directory location]`
  
Move the work directory, you can see the cluster.  
Edit the postgresql.conf file.  
```
#------------------------------------------------------------------------------
# CONNECTIONS AND AUTHENTICATION
#------------------------------------------------------------------------------

# - Connection Settings -

#listen_addresses = 'localhost'         # what IP address(es) to listen on;
                                        # comma-separated list of addresses;
                                        # defaults to 'localhost'; use '*' for all
                                        # (change requires restart)
port = 6000                             # (change requires restart)
```  

Chane port number to you want.  
And have to edit bg_hba.conf file. But couldn't remeber that.  

Anyway start PostgreSQL server. ...  
TODO: ADD them.