### Source :


###Chapter 1: 


### Cluster Systems:

-  Clustered systems gather together multiple CPUs to accomplish computational work

-  Clustered systems differ from multiprocessor systems.

-  clustered computers share storage and are closely linked via LAN (Local Area Network)

-  Beowulf clusters are designed for solving high-performance computing tasks

-  Beowulf clusters a set of open-source software libraries that allow 

   the con1puting nodes in the cluster to communicate with one another

#### Clusterin.g can be structured or symmetrically

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

- 
