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

#### Operating Systems Structure:

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

 
