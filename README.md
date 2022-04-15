## checkmk-opcua   
  
# looking for sponsors!      
contact: info@andreas-heine.net    
  
### Monitoring of OPC UA Servers with checkmk  

Keep track of all your OPC UA Serveres by monitoring valuable information.  
   
## Projectstatus  

:heavy_check_mark: Writing technical requirments, checking documentations and gather information!  
:full_moon: Working on a Proof of Concept (Testing)!  
  
feel free to use the discussions feature for asking questions or contact me directly  
  
### Important to know :warning:  
"Genuine Checkmk plug-in" will be avalible for CheckMK 2.0.0 or newer  
Python Version: 3.7 or newer  
OPC UA Stack: [opcua-asyncio](https://github.com/FreeOpcUa/opcua-asyncio) (needs Python 3.7=<)  
Licence: OpenSource (GPL or MIT)  
Maintainer: Andreas Heine  
Contribution: via PR is possible and is welcome, if it does not break anything existing!  
  
I will not write customer specific opc ua plugins which have to many similarities to this project and which have restricting source code clauses and would influence this project in a negative way!  
Currently having multiple contacts from interested companys but there is no agreement at this point, but all share at least **90%** the same idea on how a CheckMK OPC UA Plugin should look like! If enought company's team up and share the developement cost it would speed up the whole process!  
  
## RoadMap  
BasePlugin: 2021/Q2 (sponsored by Andreas Heine)  
Limited functionality:
OPC UA Client connects to a Endpoint-URL (e.g. „opc.tcp://127.0.0.1:4840“) using the "OPC UA Binary Protokoll" and reads ServerState (e.g. "0:Running") and ServiceLevel (e.g. "255") and returns a CheckResult (e.g. "CRIT")  
  
Further development requires Sponsors!  
  
### Implemented Features
  
:white_check_mark: Configurable Endpoint-URL  
:white_check_mark: OPC UA Binary Protocol  
:white_check_mark: SecurityMode None  
:white_check_mark: Check OPC UA Servers ServerState and ServiceLevel  
  
### Planed Features
  
Status | Sponsor | Feature  
|---|---|---|  
:new_moon: | :x: | User Authorization: Username/Password support  
:new_moon: | :x: | User Authorization: Certificate support  
:new_moon: | :x: | SecurityMode SIGN / SIGN&ENCRYPT (Policy: Basic256Sha256) support  
:new_moon: | :x: | Support for OPC UA Tags with a Numeric DataType  
:new_moon: | :x: | Support for OPC UA Tags with String DataType  
:new_moon: | :x: | tbc...  
  
## Usability and Concerns  
Its not ment to be used as a SCADA replacement! Cyclic check with a cycletime less then the OPC UA Servers SessionTimeout is not recommended, if the Server does not support persistent Sessions (Reuse of Sessions), this could lead to a **"Denail of Service"** due to Session exhaustion (OPC UA Servers can only handle a finite number of Sessions e.g. PLC's mostly less then 50 but it depends on the used ServerProfile: https://profiles.opcfoundation.org/v104/reporting/)!  
It is also not recommended to have one check for each Variable it can also lead to Session exhaustion, all checks which are for the same OPC UA Server must be in the same check!  
If OPC UA Events need to be monitored, a middleware is required which Subscribes the Variables/Properties and buffer the results independend till the next check executes!  
  
## Interessting to Monitor  
### ServerStatus + ServiceLevel    
Check if the OPC UA Server is up and healthy  
![serverstate](https://user-images.githubusercontent.com/56362817/124394445-c5e7b500-dcff-11eb-8ccd-a7ffc87801f1.PNG)  
[OPC UA Server States](https://reference.opcfoundation.org/v104/Core/DataTypes/ServerState/)  
[OPC UA ServiceLevel](https://reference.opcfoundation.org/v104/Core/docs/Part4/6.6.2/#Table109)  
  
### ServerDiagnostics  
Check the OPC UA Diagnostics for Problems  
![serverdiagnostic](https://user-images.githubusercontent.com/56362817/124394493-fb8c9e00-dcff-11eb-9657-59adbff8cce9.PNG)  
[ServerDiagnostics](https://reference.opcfoundation.org/v104/Core/docs/Part5/6.3.3/)  
  
### Clientinformation  
Check the OPC UA Clients which are connected to gather Session Information  
![clientdiagnostic](https://user-images.githubusercontent.com/56362817/124394467-e152c000-dcff-11eb-9aec-3108bdf25529.PNG)  
[SessionDiagnostic](https://reference.opcfoundation.org/v104/Core/docs/Part5/6.3.4/)  
  
