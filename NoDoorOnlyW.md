## Event Logs Collection
The event logs are organized in EVTX files, often called log channels or just logs: Security.evtx, System.evtx, and hundreds more.     
>located in the ***C:\Windows\System32\winevt\Logs\*** folder.
    
The average size of the folder is 50-400 MB, but it can reach a few gigabytes on some configurations.      

*On DefenseBox, you can read the logs with the default Event Viewer,   
or export them to CSV with EvtxECmd and read them in another viewer or ingest the file into a SIEM.*     

Example usage:
```
# 1. Export the EVTX logs to the "Export" folder
# 2. Run EvtxECmd and receive a single merged CSV file
C:\Users\Administrator\Export> EvtxECmd.exe -d EventLogs --csv ./ --csvf evtx_merged.csv
```

### Tips by this amazing person on Tryhackme (gracias!)     

Always include event logs in your DFIR collection pack, regardless of the host.      
Most forensic tools acquire the entire EVTX folder by default, but if you're constrained by collection size for any reason, 
you can pull just the highest-value channels instead. The exact list will vary with the case, but here is a starting point:

**Logged by Default**      

Security.evtx: Your #1 channel, at least because it reveals logon events (Event ID 4624 and 4625)    
System.evtx: Tracks services (Event ID 7040 and 7045), shutdowns, USB and driver events, and more    
Windows PowerShell.evtx: Can reveal PowerShell launch and its launch command line     
Microsoft-Windows-Windows Defender%4Operational.evtx: Defender detections and AV events    
Microsoft-Windows-TerminalServices-RDPClient%4Operational.evtx: RDP logins from the machine   
Microsoft-Windows-TerminalServices-LocalSessionManager%4Operational.evtx: RDP logins to the machine    

**Disabled by Default**    

Microsoft-Windows-PowerShell%4Operational.evtx: Reveals full, decoded PowerShell commands    
Microsoft-Windows-Sysmon%4Operational.evtx: If installed, Sysmon can solve the incident on its own   
