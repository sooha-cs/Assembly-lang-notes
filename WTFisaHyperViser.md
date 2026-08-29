## First things first   
Virtualisation = concept of creating multiple virtual environments from shared physical hardware.    
This is done by : **abstracting computing resources and allocating portions to each VM environment**     
Mainly used in: cloud computing.

### What's the need for these VMs?           
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

## Network Virtualisation

Much like CPU, RAM, and storage, Hypervisors abstract the physical networking devices of the host machine to the guest lab machines.   
This abstraction is achieved by using Virtual Network Interfaces (vNICs).       
These vNICs work just like a network adapter and handle data, obtain an IP address and are assigned a MAC address.       

Guest lab machines can have multiple vNICs attached (for example, operating on different subnets simultaneously) while one physical network adapter on the host is used. Additionally, vNICs allow for multiple lab machines to communicate with one another on the same network.      

## Paravirtualisation

Unlike full virtualisation, guest lab machines using paravirtualisation are aware that they are operating on virtualised hardware.     
For example, the guest knows that the CPU, RAM, storage and network are virtualised. This allows the guest lab machine to make direct calls to the Hypervisor.       
Pros: better performance, less overhead        
Cons: the guest's operating system needs to support paravirtualisation           
Exp: KVM uses paravirtualisation for I/O (disk read/writes and network activity) for its performance increase whilst using full virtualisation for components such as CPU & RAM for compatibility.             

## Nested Virtualisation

Nested virtualisation allows for lab machines within lab machines.      
For example, running VirtualBox within a guest.       
This is achieved by using hardware-supported virtualisation such as Intel VT-x or AMD-V.     

The use of Intel VT-x and AMD-V improves performance because the instructions are handled on the hardware directly rather than through software.         
Additionally, technologies such as these provide better security by isolating lab machines.          
Cons: more complex, significant performance overhead       
