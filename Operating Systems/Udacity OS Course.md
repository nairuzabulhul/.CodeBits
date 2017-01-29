###### Source : Udacity Operating Systems

<img src="https://in.udacity.com/assets/images/partners/logo_color_udacity.png?v=c37f67d7" width="500px">

### P1L2: Introduction

##### Visual Metaphor
 Come back to this later 
 
#### What is an Operating System ?
__What is an operating systems and what its role in computer systems?__

- Computer systems consists of a number of hardware components. This includes one or more processing units __CPU__
- Today's CPUs are multicores, means that they have more than one processing elements
- Other components aside of CPU is memory, internet connection like __Ethernet port__, or __Wifi card__
- Also not to forget GPU __Graphics Processing Cards__
- Storage devices like hard disks, SSDs and flash drives 
- Except for embedded systems. all the above component will be used by multiple applications in the computer system like your word processor or browser application
- __Operating system is the layer of systems software that sits between the complex hardware and all the software applications__

##### OS roles and functionalities:

- __Operating systems hide the complexity of the hardware from the applications as well as the application developers__

- Operating systems manage a higher level of abstraction. For example, when you are writing to a flle, you do not want to worry about the low level of computation, as the operating system takes care of it. ALso, when surfing the internet. the user do not want to be bothered by the packets needed to be sent in order to access the webpage. All this should be handled by the Operating system

- In networks the operating system abstract the low level  layer of networks into a form of sockets, which provides some services as of sending and receiving packets

- __Resource Management__ The operating systems decides how much resources to allocate to every application in the system

- One of the things that operating systems takes care of is the allocation of memory in a form of CPU scheduling (CPU can execute them )

- __Provides isolation and protection__ when multiple application are co-running on the same hardware,the operating system must ensure that each of the application can make an adequate progress and they do not hurt each other

- Also the operating system make sure that no application access another application memory, This is very important both from the a protection perspective so they do not read each other data, and also from isolation perspective, so they do not end up overwriting each other's memory 

- __Embedded platforms__ like mobile phone where hardware is typically running one application

##### Operating System Definition:

What is the following are likely to be a component of an operating system ?

- File System
- CPU Scheduler 
- Device Drivers making decision on how things on the system would work

__Note: Cache memory does not directly manage the OS performance so we can consider it an OS compenent__ 

__What is the difference between abstraction and arbitration ?__

- __Abstraction__: where the operating system simplifies something about the underlying hardware

- __Arbitration:__ where the operating system manages the underlying hardware

##### Operating System Examples:

There are many different operating systems used on different targets:

    - Desktop
    - Embedded 
    - Ultra high end like Main frame
    
##### Desktop OS:

- Microsoft Windows
- Unix-based OS like Mac OS X and BSD
- Linux 

##### Embedded OS:
- Android
- iOS
- Windows
- Symbian

##### OS Elements:

To achieve its goal, an operating system supports a number of higher-level abstraction and a number of key mechanism that operate on top of these instructions.

- __Abstartction__: includes processors, and threads correspond to the applications that the operating system executes

- __Mechanisms__ includes creating, launching or scheduling things that run on the CPU

- __Policies__: Operating systems integrate specific policies that determine can be used to manage the underlying hardware, like OS can manage the amount of packets can run through a socket

- Policies also control which data will be removed from physical memory

##### OS Elements Example:

- __Swapping__: the pages are no longer in physical memory, it is in disk

- __LRU__ : is a common policy used by the operating systems to decide that the pages that have been least recently used over a period of time are the ones who are no longer be in the physical memory and instead will be copied and stored on the disk.

##### OS Design Principles:

- __Spearation between mechanisms and policy__: means that an operating system should have a number of flexible mechanisms that can support a range of policies. For memory management, some policies would include __least recently used,least frequently used, or completely random.

- __Optimize for the common case__ which means is that we need to understand a number of questions on how the operating system will be used, and what it will need to provide to understand what common case is
- Other questions will be on what machine will be run on, and how many processing elements does it have,how many CPUs, how much memory, what kinds of devices. Also, what type of application will be executed by the operating system

##### OS Protection Boundary:
To achieve its role of controlling and managing hardware resources on behalf of applications, the operating system must have special privileges, to have a direct access to hardware

- Computer platforms distinguish between two mode:
    - User mode --unprivileged
    - Kernel mode -- privileged
- Since the operating system must have a direct access to the CPU and memory, it must operate in a privileged kernel mode

- Applications on the other hand operate in unprivileged user mode

- Crossing from Kernel mode to user mode or vice versa is supported by the hardware on most modern platforms

- For example, when in kernel mode, a special bit is set in the CPU, and if this bit is set,any instruction that directly manipulates hardware is permitted to execute. 

- In the user mode this bit is not set, and such instructions that attempt to perform privileges operations will be forbidden. such attempts in the user mode will cause a __trap__, the application will be interrupted and the hardware will switch the control to the operating system at specific location

- At that point the operating system will have a chance to check what caused that trap, and verify if it should grant an access or terminate the process if it was trying to perform something illegal

-__System Interface__ interaction between the applications and operating system. The set of operations that the applications can explicitly invoke if they want the operating system to perform certain service and to perform certain privilege access on their behalf. Example on that open file, send packet through sockets and memory allocation

##### System Call Flowchart: 

- To make system call, an application must write arguments,
- Save all relevant data at well-defined location
- Make the actual system call using this specific system call number
- The well-defined location is necessary so that the operating system kernel base on the system call number can determine which, how many arguments it should retrieve and where are they at this well-defined location
- The arguments can either be passed directly between user program and the operating system, or they can be passed indirectly by specifying their address.

__In synchronous mode__ the process will wait until the system call completes 

##### Crossing the OS Boundary:

- In summary, user/kernel transitions are necessary step during application execution.

- Applications may need to perform access to certains types of hardware, or may need to request change in the allocation of hardware resources that have been made to them 

- Only the kernel mode are allowed to perform those types of operations.

- The hardware provides support for performing user/kernel transitions. however this transition effect the hardware cache usage.The application performance is very dependent on the ability on the ability to use hardware cache.

- In general, accessing cache takes few cycles, but accessing memory takes hundred of cycles

##### OS Services
An operating system provides applications with access to underlying hardware. it does so by exporting a number of services:

- These services are directly linked to some of the components of hardware for example __scheduling__ component which is controlling the access to the CPU, or may thery are even multiple CPUs.

- __The memory manager__ is responsible for allocating the underlying physical memory to one or more co-running applications and also has to make sure that multiple applications do not overwrite each other
access memory 

- __Block driver__: is responsible for access to a block device like disk

- __Higher level services__: such file system is a useful abstraction that's supported by operating systems.In principle. operating systems integrate file systems as a service

- Services include:
    - Process Management
    - file management
    - device management
    - storage management
    - security

##### Monolithic OS


##### Modular OS:

Operating system operates on the idea of modules, everything can be added as a module.With this approach you can easily customize which particular file system, or scheduler the operating system uses.

![Log] (https://s27.postimg.org/tn80efcvn/os1.png)

- This is possible because the operating system specifies certain interfaces that any module must implement in order to be part of the operating system, and then dynamically, on the workload, we can install a module that implements the interface in a way that make sense for the workload

- Also, one of the things that are great about operating system modularity is that the ability to install new modules

__The benefits of modularity in OSs:__

- It is easier to maintain an upgrade __(maintainability)__
- Less resource intensive since it has a smaller code base
- Memory management, since the modules use less resources, they will leave more resources of memory for the applications

__The downside of modularity__ 

- Indirection can impact performance. because modules need to move between module interface and module workload, the opportunity for optimizations is effected through slower performance

- Maintainability can be an issue because code bases are disparate and can be a source of bugs

##### Microkernel:
![Log] (https://s28.postimg.org/3viberzz1/os2.png)

Microkernels only require the most basic primitives at the operating system level.
On the operating system level, the microkernel can support some basic services such as: 
    - represent an executing application, its address space, and           its context, so a thread

__Microkernel-based organization__ of operating systems requires lots of inter process interactions. So typically, the microkernel itself will support inter-process communications as one of its core abstractions and mechanisms along with address space and threads.

__The benefits of microkernel :__

- __size__ is very small, which can lead to lower overheads and better performance
- __verfiability__ since the size of the microkernel is small, it is very easy to verify and test the code behaviour as it should be 

- Examples on microkernel is embedded computer systems.

__The down-side of microkernels__

- Although, microkernel is small, its __protability__is sort of questionable because it is typically very specialized,very customized to the underlying hardware.

- __Software Complexity__:  the fact that there may be more one-off versions of microkernel specialized for different platforms makes it mat be harder to find common components of software, and that leads to software complexity 

- __Cost__: interaction between different processes means there is a need  for frequent user/kernel transitions, which can get very costly

##### Linux and Mac Architecture:
__Starting with Linux Architecture,__ 
<img scr="https://s28.postimg.org/mg7k5z7kd/os3.png" width="400px">

- Starting at the bottom, we have hardware, and linux kernel abstracts and manages that hardware by supporting a number of abstractions and the associated mechanisms.

- Then comes a number of standard libraries such as those that implement __System Call Interface__ 

- Followed by a number of utility programs that make it easier for users and developers to interact with the operating system

- Finally at the very top, you have the user developed applications

- The kernel itself, consists of several logical components like __I/O management, memory management, process management__ that can be separately modifies to replaced

__Mac Operating System Architecture :__
<img src="https://s27.postimg.org/fclckcigj/os4.png">

- Mac has a different organization, at the core is that Mac micro kernel, which implements key primitives like memory management, thread scheduling and interprocess communication mechanism including for what we call __RPC__

- __BSD__ component provides Unix interoperability vias BSD command line interface, POSIX API __(Portable Operating System Interface [for Unix])__ support as well as network I/O

- All application environment sits on the top the above layer.

- At the bottom, there are two modules, they are the environments for development of drivers and also for kernel modules that can by dynamically loaded into .





















