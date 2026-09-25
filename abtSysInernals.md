## Sysinternals     

The Sysinternals tools are a compilation of over 70+ Windows-based tools. Each of the tools falls into one of the following categories:     

1. File and Disk Utilities     
2. Networking Utilities    
3. Process Utilities    
4. Security Utilities     
5. System Information    
6. Miscellaneous

Some popular tools:    
### TCPView - Networking Utility tool.    
TCPView is a Windows program that will show you detailed listings of all TCP and UDP endpoints on your system, including the local and remote addresses and state of TCP connections.     
It provides a more informative and conveniently presented subset of the Netstat program that ships with Windows.       
The TCPView download includes Tcpvcon, a command-line version with the same functionality.      

### Process Explorer      

The Process Explorer display consists of two sub-windows.        
The top window always shows a list of the currently active processes, including the names of their owning accounts,      
whereas the information displayed in the bottom window depends on the mode that Process Explorer is in.     
if it is in handle mode, you'll see the handles that the process selected in the top window has opened;    
if Process Explorer is in DLL mode you'll see the DLLs and memory-mapped files that the process has loaded.      

## Windows Event Logs     

The Windows Event Logs are not text files that can be viewed using a text editor.       
However, the raw data can be translated into XML using the Windows API.      
The events in these log files are stored in a proprietary binary format with a .evt or .evtx extension.     
The log files with the .evtx file extension typically reside in      
```
C:\Windows\System32\winevt\Logs
```

There are three main ways of accessing these event logs within a Windows system:    
Event Viewer (GUI-based application)    
Wevtutil.exe (command-line tool)     
Get-WinEvent (PowerShell cmdlet)   

## Sysmon    
 
Sysmon, a tool used to monitor and log events on Windows, is commonly used by enterprises as part of their monitoring and logging solutions.         
As part of the Windows Sysinternals package, Sysmon is similar to Windows Event Logs with further detail and granular control.     


Sysmon gathers detailed and high-quality logs as well as event tracing that assists in identifying anomalies in your environment.      
It is commonly used with a security information and event management (SIEM) system or other log parsing solutions that aggregate, filter, and visualize events.     

**It includes 27 types of Event IDs, all of which can be used within the required configuration file to specify how the events should be handled and analyzed.**    

### OSQuery     
Osquery is an open-source tool created by Facebook. With Osquery, Security Analysts, Incident Responders, and Threat Hunters can query an endpoint (or multiple endpoints) using SQL syntax.      
Osquery can be installed on various platforms: Windows, Linux, macOS, and FreeBSD.     

To interact with the Osquery interactive console/shell, open CMD (or PowerShell) and run osqueryi.    

### Wazuh     

﻿Wazuh is an open-source, freely available, and extensive EDR solution, which Security Engineers can deploy in all scales of environments.    

Wazuh operates on a management and agent model where a dedicated manager device is responsible for managing agents installed on the devices you'd like to monitor.    
