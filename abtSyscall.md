## Syscall()
A syscall is a request from your program to the OS for tasks the CPU cannot do alone (print, read input, exit, open files).      
    
How to make a syscall:    

1. Put the syscall number in rax    
2. Put arguments in rdi, rsi, rdx, etc.    
3. Execute the syscall instruction    
    
Common syscall numbers: 

| Syscall| 	Number	| What it does |
|--------|------------|-------------|
|write	| 1 |	Prints text to screen |
|exit	|60	| Ends the program |   
    
**Every program must end with an exit syscall**
Exp:    
``` 
mov rax, 60    ; syscall number for exit    
mov rdi, 0     ; exit code (0 = success)     
syscall        ; ask the OS to exit    
```
Common conventions:    

1: General error      
2: Missing input file     
3: Permission denied     
4: Network error      

> Always set rdi before the exit syscall: forgetting leaves a garbage value in the register, causing a random exit code.     

