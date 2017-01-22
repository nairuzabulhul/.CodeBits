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

