**There are three main functionalities that RE tools provide:**    
### debugging, disassembling, and decompiling      

        
**Disassemblers** will translate the program from its bytes on disk or in memory into its assembly code equivalent.     
**Decompilers** are similar to disassemblers except instead of giving us the assembly, it attempts to recreate the code in C/C++.     
*The downside to decompilers is that they can be inaccurate, or lack information.*       
      
**Debuggers** will allow us to place breakpoints within the program while it's running and analyze registers, memory, statuses, and more.      
They also allow for changing data in memory while the program is running.      

-------
## Imports, Exports, Modules in DLLs     
Tools like IDA recognizes the function and names it accordingly by FLIRT (Fast Library Identification and Recognition Technology) signatures.    
FLIRT signatures are used to identify standard library functions.       
> The general idea of how they work is they search memory for a chunk of bytes that match a known chunk of bytes in a standard library function.
> Once a match is found, the function can be named accordingly.

Function name can be preserved because it's imported from or exported by a DLL too!     
The DLL can expose its function names through the DLL/PE header, library file, or header file (.h or .hpp).      
Imports are the functions the executable is using/importing from a DLL, and exports are the functions a DLL provides/exports.       
DLL's are known as **dynamic-link libraries** since they are loaded into memory once and can be loaded into any number of processes at any time without making any more copies. 
The Windows OS is built on DLLs.    
Modules are essentially anything related to a process that import or export functions.     

A program that called rundll32.exe loads your DLL making DllMain() execute; which is done within the context of the process which loads the DLL.   

