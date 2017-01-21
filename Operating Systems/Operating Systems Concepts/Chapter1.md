##### Source: [Operating System Concepts 8th Edition by Abraham Silberschatz] (https://www.amazon.com/Operating-System-Concepts-Abraham-Silberschatz/dp/0470128720)

![Log] (https://images-na.ssl-images-amazon.com/images/I/51spVw9pGKL._SY344_BO1,204,203,200_.jpg)


###Chapter 1: Introduction


#### Cluster Systems:

-  Clustered systems gather together multiple CPUs to accomplish computational work

-  Clustered systems differ from multiprocessor systems.

-  clustered computers share storage and are closely linked via LAN (Local Area Network)

-  Beowulf clusters are designed for solving high-performance computing tasks

-  Beowulf clusters a set of open-source software libraries that allow 

   the computing nodes in the cluster to communicate with one another

#### Clusterin.g can be structured or symmetrically or asymmetrically 

- In asymmetric clustering, one machine is in hot-standby mode while the other is running the applications

   If that server fails, the hot-standby host becomes the active server.
 

- In asymmetric mode, two or more hosts are rmming applications and are monitoring each other. 

  This mode is obviously more efficient, as it uses all of the available hardware. 

- Other types of clustering :

	-  Parallel clusters allow multiple hosts to access the same data on the shared storage over WAN Ex:  Oracle's database

#### Distributed Lock Manager:

  To provide this shared access to data, the system must also supply access control and locking to 
 
  ensure that no conflicting operations occur. 	This function, commonly known as Distributed Lock Manager,
  
  is included in some cluster technology. 


#### SANS: Storage Area Network, which allow many systems to attach to a pool of storage


#### How clustered systems work? 

-  High availability is generally obtained by adding a level of redundancy in the system. A layer 

  of cluster software runs on the cluster nodes. Each node can monitor one or more of the others (over the LAN)

- If the monitored machine fails, the monitoring machine can take ownership of its storage 

   and restart the applications that were running on the failed machine. 

=========================================================
### 1.4  Operating Systems Structures:
=========================================================

- An operating system provides the envirorunent within which programs are executed.

- One of the most important aspects of operating systems is the ability to multiprogram. 

#### Multiprogramming :

- increases CPU utilization by organizing jobs, so that the CPU always has one to execute.

- The operating system keeps several jobs in memory simultaneously

-  Since, in general, main memory is too small to accommodate all jobs, the jobs are kept initially 

 on the disk in the "job pool".

- This pool consists of all processes residing on disk awaiting allocation of main memory. 

- In a non-multiprogrammed system, the CPU would sit idle. In a multiprogrammed system, 

  the operatilcg system simply switches to, and executes, another job


#### Multitasking:

- is alogical extension of multiprogramming

-  In a time-sharing systems,the CPU executes multiple jobs by switching among them, but the switches occur so frequently
 that the users can interact with each program while it is running

- A time-shared operating system allows many users to share the computer simultaneously.

- A time-shared operating system 11ses CPU scheduling and multiprogramming

- Since each action or command in a time-shared system tends to be short, only a little CPU time is needed for each user.

-  As the system switches rapidly from one user to the next, each user is given the impression that the entire computer system is dedicated to his use

#### Process:

- A program loaded into memory and executing .

- When a process executes, it typically executes for only a short tirne it either finishes or needs to perform I/0. 

- I/0 may be interactive; that is, output goes to a display for the user, 

  and input comes from a user keyboard, mouse, or other device

- interactive I/0 may take a long time to complete.


#### Time sharing and multiprogramming

- Time sharing and multiprogramming require that several jobs be kept simultaneously in memory. 

If several jobs are ready to be brought into memory, and if there is not enough room for all of them,

 then the system must choose among them.


#### CPU Scheduling: CPU makes a decision on which program to execute first out of the job pool


#### Swapping:

- In a time-sharing system, the operating system must ensure reasonable response time, 

  which is sometimes accomplished through "swapping", where processes are swapped in and out

  of main memory to the disk

#### Virtual Memory :

- a techniqu that allows the execution of aprocessthat is not completely in memory

- The main advai1tage of the virtual-memory scheme is that it enables users to run programs 
	
  that are larger than actual physical memory

- it abstracts main memory into a large, uniform array of storage, 

  separating logical memory as viewed by the user from physical memory 

=========================================================
### 1.5 Operating Systems Operations:
=========================================================
 
#### 1.5.1  Dual Mode Operation:

- There are two separate mode of operation:
	
	- User Mode
	- Kernel Mode

- Bit Mode : is added to the hardware of the computer to indicate the current mode: kernel (0) or user (1)

- With Bit mode we are able to distinguish between a task that is executed on behalf of the operating system and
	  the one that is executed on behalf of the user


#### How Operating Systems boot?

- At system boot time, the hardware starts in kernel mode. 
The operating system is then loaded and starts user applications in user mode.

- When an interrupt occurs the hardware switches from user mode to kernel mode



#### Privileged Instruction : the hardware allows privileged instruction to be executed on kernel mode only

	- Ex: Some other examples include I/0 control timer management and interrupt management


Note: control is switched back to the operating system via an interrupt, a trap, or a system call.

#### System Call:

System calls provide the means for a user program to ask the operating 
system to perform tasks reserved for the operating system on the user program's behalf

=======================================
### 1.5.2 Timer
=======================================

- A timer can be set to interrupt the computer after a specified period of time.

- if the timer interrupts, control transfers automatically to the operating system, which may 
   treat the interrupt as a fatal error or may give the program more time

=================================================
### 1.6 Process Management 
=================================================

#### What is a process? 

- a process is a program in execution 

- A process needs certain resources -including CPU time, memory, files, and I/O devices - to accomplish its task

- These resources are either given to the process when it is created or allocated to it while it is running

- When the process terminates, the operating system will reclaim any reusable resources. 


#### Single-threaded Process:

 - has one program counter to specify the next instruction to execute

 - The execution of such a process must be sequential. The CPU executes one
   instruction of the process after another, until the process completes

#### Multiple-threaded Process:

- A multithreaded process has multiple program counters, each pointing to the next 
  instruction to execute for a given thread. 


#### Q1- What is multiplexing on Single CPU ?




#### Operating System responsibilities in connection with process management:
 
- Scheduling processes and threads on the CPUs 
- Creating and deleting both user and system processes 
- Suspending and resuming processes 
- Providing mechanisms for process synchronization 
- Providing mechanisms for process communication


=======================================================
### 1.7 Memory Management
======================================================

#### What is the main memory:

 - Main memory is a repository of quickly accessible data shared by the CPU and I/0 devices

 - the main memory is generally the only large storage device that the CPU is able to address and access directly

 - For example, for the CPU to process data from disk, those data mu.st first be transferred to main n"lemory by CPU-generated I/0 calls.

 - For a program to be executed, it must be mapped to absolute addresses and loaded into memory. 
 
 - As the program executes, it accesses program instructions and data from memory by generating these absolute addresses.

 - To improve both the utilization of the CPU and the speed of the computer's response to its users, 
   general-purpose computers must keep several programs in memory, creating a need for memory management

#### Operating Systems responsibilities in connection with memory management:

- Keeping track of which parts of memory are currently being used and by whom 
- Deciding which processes (or parts thereof) and data to move into and out of memory 
- Allocating and deallocating memory space as needed 


==================================================
###  1.8 Storage Management
==================================================

 - File management is one of the most visible components of an operating system. Computers can store information 
   on several different types of physical media. 
		- Magnetic disk, 
		- optical disk
		- magnetic tape are the most common

#### File : A file is a collection of related information defined by its creator


#### Operating Systems responsibilities in connection with file management:

- Creating and deleting files 
- Creating and deleting directories to organize files 
- Supporting primitives for manipulating files and directories 
- Mapping files onto secondary storage 
- Backing up files on stable (nonvolatile) storage media


##### Operating Systems responsibilities in connection with disk management:

- Free-space management 
- Storage allocation 
- Disk scheduling


#### What is Caching ?

- Caching: is the process of storing data in a cache. A cache is a temporary storage area.

- For example, the files you automatically request by looking at a Web page are stored on your 
  hard disk in a cache subdirectory under the directory for your browser.
	
- In operating systems,  information are used directly from the cache; if it is not there, the system uses 
  the information from the source, and puts a copy in the cache under the assumption that it will be used it again soon


#### What is registers ?

 -  is one of a small set of data holding places that are part of the computer processor. 
    A register may hold an instruction, a storage address, or any kind of data


#### Information Storage:

- The movement of information between levels of a storage hierarchy may be either explicit or implicit
 
- For instance,data transfer from cache to CPU and registers is usually a hardware function, with no operating system
  intervention

- In contrast, transfer data from disk to memory is usually controlled by operating system


===========================================
#### 1.8    I/O Systems
===========================================

- One of the purposes of all operating system is to hide the peculiarities of specific hardware 
  devices from the user

- The I/O subsystem consists of several components: 

- A memory-management component that includes buffering, caching, and spooling 
- A general device-driver interface 
- Drivers for specific hardware devices

==================================================
### 1.9 Protection and Security
==================================================

#### Protection: Protection, is any mechanism for controlling the access of processes or users-to the resources defined by a computer system

#### Security :the job of security to defend a system from external and internal attacks

==================================================
### 1.10 Distributed Systems
==================================================

#### What is a distributed System ?

A distributed system is a collection of physically separate, possibly heterogeneous, 

computer systems that are networked to provide the users with access to the various 

resources that the system maintains


- Distributed systems depend on networking for their functionality. Networks vary by the protocols used, 
  the distances between nodes, and the transport media

- TCP /IP is the most common network protocol

- LAN: connects computers within a room, a floor, or a building

- WAN: buildings, cities, or countries


#### Network Operating System:

is an operating system that provides features such as file sharing across the network and that includes a communication scheme that 

allows different processes on different computers to exchange messages. 








