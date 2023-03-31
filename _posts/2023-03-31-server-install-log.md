---
layout: post
title: 0330 & 0331 log
subtitle: icon, infomart install
categories: AICC, daily, network
tags: [AICC, daily, network]
---

# Icon install
1. make Application on CM.  
2. Install ICon on the server.  
3. Copy `ccon_adata_spec_GIM.xml` file and edit options.  
4. Run the `CoreSchemaPart_ora.sql` in the `/gcti/icon/scripts/oracle` directory.  
5. Run the Icon Server.  
  
  
# Info Mart install
1. Install Oracle using `rpm`.  
    * `rpm -ivh /gcti/setup/oracle_client/*`  
    * Make `tnsames.ora` file on `/etc/oracle`  
```
    confserv=
(DESCRIPTION=
    (ADDRESS=
        (PROTOCOL=TCP)
        (HOST=10.1.14.174)
        (PORT=1521)
    )
    (CONNECT_DATA=
        (SID=CONFSERV)
    )
)

log=
(DESCRIPTION=
    (ADDRESS=
        (PROTOCOL=TCP)
        (HOST=10.1.14.174)
        (PORT=1521)
    )
    (CONNECT_DATA=
        (SID=LOG)
    )
)

gax=
(DESCRIPTION=
    (ADDRESS=
        (PROTOCOL=TCP)
        (HOST=10.1.14.174)
        (PORT=1521)
    )
    (CONNECT_DATA=
        (SID=GAX)
    )
)

logdb=
(DESCRIPTION=
    (ADDRESS=
        (PROTOCOL=TCP)
        (HOST=10.1.14.174)
        (PORT=1521)
    )
    (CONNECT_DATA=
        (SID=LOGDB)
    )
)
```  
2. Edit `.bash_profile` file  
```
PATH=$PATH:$HOME/.local/bin:$HOME/bin:$LD_LIBRARY_PATH

JAVA_HOME=/gcti/openjdk
PATH=$PATH:$JAVA_HOME/bin
CLASSPATH=/usr/lib/oracle/21/client64/lib/ojdbc8.jar:$JAVA_HOME/jre/lib:$JAVA_HOME/lib/tools.jar
export NLS_LANG=KOREAN_KOREA.AL32UTF8
export ORACLE_HOME=/usr/lib/oracle/21/client64
export PATH=${PATH}:$HOME/bin:$ORACLE_HOME/bin
export LD_LIBRARY_PATH=${LD_LIBRARY_PATH}:$ORACLE_HOME/lib
export CFLAGS=-l/usr/lib/oracle/21/client64
export TNS_ADMIN=/etc/oracle
```
  
3. DAP InfoMart option  
    * DBS-> None / ServerInfo -> Where DBS is installed / port=1521  
    * gim-etl section -> jdbc-url
    ```jdbc:oracle:thin:@(DESCRIPTION = (ADDRESS = (PROTOCOL = TCP)(HOST = 10.1.14.174)(PORT = 1521))(CONNECT_DATA = (SERVER = DEDICATED)(SID = LOG)))```  
  
4. Run `make_gim.sql` on sql_scripts/oracle directory.  
5. Run InfoMart Server  
  
## Error list
`20005 Error JDBC driver 'oracle.jdbc.OracleDriver' is not installed or properly configured`  
--> add the file name in `CLASSPATH` on .bash_profile  
  
`table or view does not exist.`  
--> DAP InfoMart option -> None (Own DB Server)  
--> Option Schema value -> (blank)  