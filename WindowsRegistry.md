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
       
