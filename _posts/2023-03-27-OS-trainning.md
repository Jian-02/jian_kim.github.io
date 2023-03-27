---
layout: post
title: OS basic trainning for server maintance
subtitle: Windows and Linux command
categories: AICC, OS 
tags: [AICC, os]
---

# Windows
## Firewall setting
  
Windows Defender Firewall -> Advanced settings -> Inbound Rules  
User could add the inbound rules using `programs and services` tab, but should use `Protocols and Ports` tab.  
  
## Internet Information Services(IIS)
  
User can able to use Windows features of Control pannel.  
`wcm`(ga) -> port (on right)  
  
## WIndows features
  
Control pannel -> Programs -> Windows features turn on/off  
could add .Net or telnet features.  
Telent is for test, if there is real server, should be turn off.  
  
## Manage Disk
  
Process related with Genesys, store on D disk.  
  
## SysternalSuite
  
[download link](https://www.learn.microsoft.com/en-us/sysinternals/downloads/sysinternals-suite)  
Process Explorer: tools about port  
TCP Viewer, TCP Monitor  
  
* command: `forfiles` user could delete various log files.  
  
# Linux
## command
1. systemctl  
* start / stop / status / restart / reload  
2. tar/unzip  
* tar -cvzf *.tar.gz: make archieve file  
* tar -xvzf *.tar.gz: decompress archieve file  
3. vi  
* i: insert back  
* a: insert front  
* x: delete back  
* o: insert below line  
* O: insert above line  
* ctrl+f: previous page  
* ctrl+b: next page  
* /: search word from first line  
* ?: search word from last line  
* :set nu: show line  
* u: undo  
* dd: delete one line  
4. chkconfig  
* utility to set program on boot  
* --list / on / off  
5. ulimit  
* command to set process resource limits.  
6. bash_profile  
* ~/.bashprofile file edit  
7. netcat  
* nc: command tto read and write data on network.  
* nc [ip] [port]  
8. httpd  
* user could edit `/etc/httpd/conf/httpd.conf`  
9. crontab  
* minuates hours days month week file  
* crontab -e  
10. telnet  
* default port: 23  
* `firewall-cmd --permanet --add-port=23/tcp`: could add the port  
11. wget  
* wget link  
* unreliable wweb site: `--no-check-certificate` oprtion  
12. rpm updage & status  
* `rpm -ivh package.rpm`: install  
* `rpm -Uvh package.rpm`: upgrade  
* `rpm -e package.rpm`: delete  
* `rpm -q package`: verify pcackage is it installed  
13. gcc  
* compiler  
* `gcc -o *.o o`  
14. make  
* make  
* make clean  
15. nslookup  
* command to search domain information  
* `nslookup domain`  
16. ftp  
* `ftp ip adress`  
