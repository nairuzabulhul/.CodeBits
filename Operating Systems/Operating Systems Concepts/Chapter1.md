### Source :


###Chapter 1: 


### Cluster Systems:

-  Clustered systems gather together multiple CPUs to accomplish computational work

-  Clustered systems differ from multiprocessor systems.

-  clustered computers share storage and are closely linked via LAN (Local Area Network)

-  Beowulf clusters are designed for solving high-performance computing tasks

-  Beowulf clusters a set of open-source software libraries that allow 

   the con1puting nodes in the cluster to communicate with one another

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


#### SANS: 
Storage Area Network, which allow many systems to attach to a pool of storage


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


#### CPU Scheduling:
	
- CPU makes a decision on which program to execute first out of the job pool


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
 
