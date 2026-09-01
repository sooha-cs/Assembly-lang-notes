### MOV:
The MOV instruction copies data from source to destination (original source is unchanged):
  ```
  mov destination, source
  ```
MOV immediate copies a value directly into a register:
  ```
  mov register, value
  ```
 
Example tasks: Write one line of assembly code for each task:       

Put the number 5 into the rax register.      
Put the number 7 into the rbx register.     
Put the number 3 into the rcx register.    
```
; TODO: Put the number 5 into the rax register.
mov rax,5
; TODO: Put the number 7 into the rbx register.
mov rbx,7
; TODO: Put the number 3 into the rcx register.
mov rcx,3
```

MOV Register to Register: Copy a value between registers using mov (source remains unchanged).     
```
mov rax, 5      ; rax = 5
mov rbx, rax    ; rbx = 5 (rax still = 5)
```

Example tasks: Write the assembly code for these tasks:

Put the number 4 into rax
Copy the value from rax into rbx
Copy the value from rbx into rcx
```
; TODO: Put the number 4 into rax
mov rax,4
; TODO: Copy the value from rax into rbx
mov rbx,rax
; TODO: Copy the value from rbx into rcx
mov rcx,rbx
```

MOV Memory to Register: Use brackets [ ] to load a value from memory into a register:        
```
mov al, [number]    ; loads the VALUE stored at address "number" into al   
```
Without brackets, you load the address itself, not the value:    
```
mov al, number      ; Wrong: loads the ADDRESS, not the value
```
Size must match: use al (byte) for byte-sized memory, not rax.     
