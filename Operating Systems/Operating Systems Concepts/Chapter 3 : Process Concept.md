### Chapter 3: Process Concept
----------------------------------------------------------------
- __Text Secton: program code__

- __Program counter: counts the current acctivity__

- __Stack containts temporary data__

- __Heap, which is memory thatis dynamically allocated during process run time__

- A program becomes a process when an executable file is loaded into memory.

- Although two processes may be associated with the same program, 
  they are nevertheless considered two separate execution sequences. 
  For instance, several users may be running different copies of the mail program,
 or the same user may invoke many copies of the Web browser program. Each of these is a separate process;

### Process State

- __New__ The process is being created. 
- __Running__. Instructions are being executed. 
- __Waiting__. The process is waiting for some event to occur (such as an I/0 completion or reception of a signal). 
- __Ready__. The process is waiting to be assigned to a processor. 
- __Terminated__. The process has finished execution. 

###  Process Control Block 

- __Process Control Block:__  It contains many pieces of information associated with a specific process

- __Process state__. The state may be new, ready runnil•g, waiting, halted, and so on. 

- __Program counter__. The counter indicates the address of the next instruction to be executed for this process.

- __CPU registers.__ The registers vary in number and type, depending on the computer architecture 

- __CPU-scheduling information.__ This information includes a process priority

- __Memory-management information.__ This information may include such information as the value of the base and limit registers, 
  the page tables, or the segment tables, dependmg on the memory system 

- __Accounting information__ This mformation includes the amount of CPU and real time used, 
  time limits, account numbers, job or process numbers

- __I/O status__ information. This information includes the list of I/O devices allocated to the process, 

### Threads:
 __Definition : is a peciece of code executed independetly from the main program__

### Process Scheduling

- __Scheduling Queue__: The processes that are residing in main memory and are ready 
   and waiting to execute are kept on a list called the ready queue 

- Within the Linux kernel, all active processes are represented using a doubly linked list

- This queue is generally stored as a linked list


### Scheduler:

-  The operating system must select, for scheduling purposes, processes from these queues in some fashion. 
   The selection process is carried out by the appropriate scheduler. 

- __The long-term scheduler__, or job scheduler, selects processes from this pool 
  and loads them into memory for execution

- __The short-term scheduler__, or CPU scheduler, selects from among the processes 
  that are ready to execute and allocates the CPU to one of them

 __Types of processes:__

- __I/O-bound process__ is one that spends more of its time doing I/O than it spends doing computations

- __A CPU-bound process__, in contrast, generates I/0 requests infrequently, using more of its time doing computations

-  __Interrupts__ cause the operating system to change a CPU from its current task and to run a kernel routine

- __Context Switch__: Switching the CPU to another process requires performing a state save of the current process 
	           and a state restore of a different process. 	This task is known as a When a context switch occurs, 
		   the kernel saves the context

### Operation Porcesses:

#### Porcess Creation:

- Parent process create children processes, which, in turn create other processes, forming a tree of processes 

- The parent may have to partition its resources among its children, or it may be able to share some resources 

- __When a process creates a new process, two possibilities exist in terms of execution:__ 

	- The parent continues to execute concurrently with its children. 

	- The parent waits until some or all of its children have terminated. 

- __There are also two possibilities in terms of the address space of the new process:__ 

	- The child process is a duplicate of the parent process (it has the same program and data as the parent). 

	- The child process has a new program loaded into it. 

### Process Termination :

- __Process Termination:__ Process executes last statement and asks the operating system to 
                       delete it (by making exit() system call)

- A parent may terminate the execution of one of its children for a variety of reasons, such as these:
 
	- The child has exceeded its usage of some of the resources that it has been allocated.  

	- The task assigned to the child is no longer required. 

	- The parent is exiting, and the operating system does not allow a child to continue if its parent terminates.  

- __Cascading termination:__ if a process terminates (either normally or abnormally), then all its children must also be terminated

### Interprocess Communication:
- Processes executing concurrently in the operating system may be either independent processes or cooperating processes.  
- __A process is independent if it cannot affect or be affected by the other processes executing in the system__
-  A process is cooperating if it can affect or be affected by the other processes executing in the system
- Any process that shares data with other processes is a cooperating process.  

- __There are several reasons for providing an environment that allows process cooperation:__ 

	- __Information sharing:__
	- __Computation speedup.__ If we want a particular task to run faster, we must break it into subtasks, each of which will be executing in parallel with the others.
	- __Modularity.__ We may want to construct the system in a modular fashion, dividing the system functions into separate processes or threads

	- __Convenience.__ Even an individual user may work on many tasks at the same time. 

- __Interprocess communication (IPC)__ mechanism that will allow them to exchange data and information. 

- __There are two fundamental models of interprocess communication__: 

	- __Shared memory:__  a region of memory that is shared by cooperating processes is established. Processes can then exchange 
			  information by reading and writing data to the shared region 

	- __Message passing__ : communication takes place by means of messages exchanged 

### Shared Memory Systems:

-  Normally, the operating system tries to prevent one process from accessing another process's memory. 

- Shared memory requires that two or more processes agree to remove this restriction. They can then excbange information by reading and writing data in the shared areas

- A producer process produces information that is consumed by a consumer process. 

- __There are two tyeps of buffers:__

	- __Unbounded Buffer:__  no practical limit on the size of the buffer

	- __Bounded Buffer:__ a fixed buffer size

### Mesaage Passing:

- __Two basic operations:__
	- __send__(destination, message)  
	- __receive__(source, message) 
-  If processes wish to communicate, they need to establish a communication link between them  

- __There are many variants of how send() and receive() behave :__

- __Direct communication :__ Processes must name each other explicitly

- __Indirect Communciation:__ Messages are sent and received to/from mailboxes 

- __Synchronous communication :__

	Also called synchronous message passing :
	- sender waits until the receiver receives the message 
	-  receiver waits until the sender sends the message 
 
	- __Advantages:__ 
		- inherently synchronizes the sender with the receiver 
		- single copying sufficient
	- __Disadvantages:__ 

		- possible deadlock problem 

- __Asynchronous Communication:__

	- __Non-blocking send:__  the sender continues before the delivery of the message 

	- __Non-blocking receive:__ check whether there is a message available, return immediately  

- __Automatic or explicit buffering:__ 

 	- With blocking direct communication, no buffering is needed – the message stays in the sender’s buffer 
	  until it is copied into the receiver’s buffer 

	- With non-blocking communication, the sender might reuse the buffer 

### Comunication in CLient-Sever Systems:

#### Socket: is defined as an endpoint for communication. A pair of processes communicating over 
	    a network employ a pair of sockets-one for each process. 
	    A socket is identified by an IP address concatenated with a port number


### What is Pipe:

 A unidirectional channel 
	- One write end
	-  One read end 
	
__Why Piping is used?__ 

The UNIX/Linux pipes allows linking of processes to obtain complex functions from simple commands 

	-  who | sort 


### Remote Procedure Calls 
 -  The computers might have different data format 
 -  Support for locating the server/procedure needed 
 -  Stubs – client and server – side proxies implementing the needed communication 
 -  The client-side stub locates the server and marshalls the parameters. 
 - The server-side stub receives this message, unpacks the marshalled parameters, and performs the procedure on the server.



