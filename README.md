## checkmk-opcua   
  
# looking for sponsors!      
contact: info@andreas-heine.net    
  
### Monitoring of OPC UA Servers with checkmk  

Keep track of all your OPC UA Serveres by monitoring valuable information.  
   
### Projectstatus  

Writing technical requirments, checking documentations and gather information!  
Planing for a proof of concept as an ["Special Agent / API-Integration"](https://docs.checkmk.com/latest/en/devel_check_plugins.html)-Plugin  
The OPC UA Client part is already written with [opcua-asyncio](https://github.com/FreeOpcUa/opcua-asyncio) for the information/variables below!  
  
feel free to use the discussions feature for asking questions or contact me directly  
   
### ServerStatus + ServiceLevel    
![serverstate](https://user-images.githubusercontent.com/56362817/124394445-c5e7b500-dcff-11eb-8ccd-a7ffc87801f1.PNG)  
[OPC UA Server States](https://reference.opcfoundation.org/v104/Core/DataTypes/ServerState/)  
[OPC UA ServiceLevel](https://reference.opcfoundation.org/v104/Core/docs/Part4/6.6.2/#Table109)  

### ServerDiagnostics  
![serverdiagnostic](https://user-images.githubusercontent.com/56362817/124394493-fb8c9e00-dcff-11eb-9657-59adbff8cce9.PNG)  
[ServerDiagnostics](https://reference.opcfoundation.org/v104/Core/docs/Part5/6.3.3/)  

### Clientinformation  
![clientdiagnostic](https://user-images.githubusercontent.com/56362817/124394467-e152c000-dcff-11eb-9aec-3108bdf25529.PNG)  
[SessionDiagnostic](https://reference.opcfoundation.org/v104/Core/docs/Part5/6.3.4/)  

...  
maybe later GDS and LDS support which would work like connecting to a DiscoveryServer and explore the known Servers dynamically  
