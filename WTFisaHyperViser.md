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


## CPU & Memory Virtualisation

Hypervisors use virtual CPUs (vCPUs) to virtualise the CPU, which are mapped to the cores available on the physical CPU.          
In modern Hypervisors, a vCPU is not permanently assigned to a core on the physical  CPU.    
Instead, the Hypervisor will take the instructions coming from the VM and spread these across the physical cores as needed.     

## Storage Virtualisation
A Hypervisor uses virtual disks to create the illusion of a lab machine having its own physical storage drive.     
When, in fact, it is sharing the host's physical storage device (such as a hard drive).     
For example, VMware uses "VMDK",  whereas VirtualBox uses "VDI"                
