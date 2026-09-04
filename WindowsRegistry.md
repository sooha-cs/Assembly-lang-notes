# The Windows Registry         
It is a collection of databases that contains the system's configuration data.               
This configuration data can be about the hardware, the software, or the user's information.          
It also includes data about the recently used files, programs used, or devices connected to the system       

**It consists of Keys and Values**         
A Registry Hive is a group of Keys, subkeys, and values stored in a single file on the disk.          

## Structure of the Registry:        

The registry on any Windows system contains the following five root keys:         

1. HKEY_CURRENT_USER          
2. HKEY_USERS         
3. HKEY_LOCAL_MACHINE            
4. HKEY_CLASSES_ROOT           
5. HKEY_CURRENT_CONFIG

Opened in windows using run and searching:
```
regedit.exe
```

## Keys in details:        
1. HKCU: Contains the root of the configuration information for the user who is currently logged on.
   The user's folders, screen colors, and Control Panel settings are stored here. This information is associated with the user's profile.
   This key is sometimes abbreviated as HKCU.
2. HKU: Contains all the actively loaded user profiles on the computer. HKEY_CURRENT_USER is a subkey of HKEY_USERS.
3. HKLM: Contains configuration information particular to the computer (for any user).
4. HKEY_CLASSES_ROOT (HKCR): Is a subkey of HKEY_LOCAL_MACHINE\Software .
   The information that is stored here makes sure that the correct program opens when you open a file by using Windows Explorer.
   The HKEY_CLASSES_ROOT key provides a view of the registry that merges the information from these two sources.
   HKEY_CLASSES_ROOT also provides this merged view for programs that are designed for earlier versions of Windows.       
5. HKCC: Contains information about the hardware profile that is used by the local computer at system startup.       
         
>**The majority of these hives are located in the C:\Windows\System32\Config directory**       

 For Windows 7 and above, a user’s profile directory is located in C:\Users\<username>\ where the hives are:          

1. NTUSER.DAT (mounted on HKEY_CURRENT_USER when a user logs in)         
2. USRCLASS.DAT (mounted on HKEY_CURRENT_USER\Software\CLASSES)
The USRCLASS.DAT hive is located in the directory C:\Users\<username>\AppData\Local\Microsoft\Windows.        
**Reminder that both of these are hidden**      
 
>Registry backups are the opposite of Transaction logs. These are the backups of the registry hives located in the C:\Windows\System32\Config directory. These hives are copied to the C:\Windows\System32\Config\RegBack directory every ten days.
>       
>Apart from these files, there is another very important hive called the **AmCache hive**. This hive is located in C:\Windows\AppCompat\Programs\Amcache.hve. Windows creates this hive to save information on programs that were recently run on the system.        
---------

## Finding system information with registry
1. OS version (register key):
   ```
    SOFTWARE\Microsoft\Windows NT\CurrentVersion
   ```
2. Machine name info:
   ```
   SYSTEM\CurrentControlSet\Control\ComputerName\ComputerName
   ```
3. Machine configuration data: For control sets like ControlSet001,ControlSet002; path will be like: SYSTEM\ControlSet001
   ```
   HKLM\SYSTEM\CurrentControlSet
   ```
   Similarly, the last known good configuration can be found using the following registry value:
   ```
   SYSTEM\Select\LastKnownGood
   ```
 4.  Time zone the computer is located in:
      ```
      SYSTEM\CurrentControlSet\Control\TimeZoneInformation
      ```
5. Network Interfaces:
   ```
   SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\Interfaces
   ```
6. Autostart Programs :
   ```
   NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Run
   NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\RunOnce
   SOFTWARE\Microsoft\Windows\CurrentVersion\RunOnce
   SOFTWARE\Microsoft\Windows\CurrentVersion\policies\Explorer\Run
   SOFTWARE\Microsoft\Windows\CurrentVersion\Run
   ```
7. SAM hive and user information: contains user account information, login information, and group information.
   ```
   SAM\Domains\Account\Users
   ```

## To do: add more about registry keys here 
   
   
