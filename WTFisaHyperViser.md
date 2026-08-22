## First things first   
Virtualisation = concept of creating multiple virtual environments from shared physical hardware.    
This is done by : **abstracting computing resources and allocating portions to each VM environment**     
Mainly used in: cloud computing.

## What's the need for these VMs?           
1. Virtualization reduces cost: multiple machines on a single hardware; so less cost in multiple devices & services            
2. Easier management and navigation:  everything you need is available and manageable on a single device           
3. Improved CPU utilization: more services mean CPU can utilize most of its' time, reducing idle time                           

Now, to hide away the messy and complex details from the dumbos like us..the concept of ***abstraction*** is used on virtualization. 
***That is called a Hypervisor.***   

----------------
## Types of HyperVisor    
Hypervisor are divided based on their position (abstraction) in relation to the hardware of the physical device.        
1. Bare metal - our abstraction is done at hardware level.             
   Pros: Sophisticated & scalable. Workloads can be distributed amongst each other.            
   Example: Hyper-V and VMware ESXi              
2. Hosted - these run on top of an existing operating system (software)           
   Pros: easy-to-use & widely compatible            
   Example: VirtualBox and VMware Workstation/Player.            
