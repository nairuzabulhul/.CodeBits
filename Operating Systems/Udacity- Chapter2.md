
### Chapter 2 : Proces Management 

- __Application__ is a program is on disk, flash memory and even in the cloud. It is not executing, it is on static entity

- __Process__: once the application is launched, the program is loaded into the memeory, and starts executing 

- If the application is launched more than one time, muliple processes will be created. These processes will be running the same the applications, but each process has its own status

- Process represents the execution state of an active applicaiton

#### Process Address Space:

<img src="https://s29.postimg.org/42axzim6f/image.png" width="300px") >

- A process encapsulates all of the above information

- Every single elment of the process state has to be uniquely identified by 

#### Types of state:
- __Text__ : is the code 
- __Date__ is available when the process is first initialized
- __Text__ and Data represents a Static state when process first loads
- __Heap__ is dynamically created during execution. It allocates memory, stores them per resilts, read data from files
- __Stack__: it is a dynamic part of the address space state that growns and shrinks using LIFO -- First In First out

__How stacks work__ :
- Consider for instance we are exectuing a particular portion of the process, and now we nee to call some procedure to jump to a differnt part of the address space.
- We want to make sure that the state that we were in at this point of the execution, before we called this other procedure is saved, and that it will be restored once we come back from the execution.
- We can place the state on the stack and jump to execute this porton of the code, the state x will be popped from the stack and we can continue the execution of the state that we were in before the call of the new one .

#### What are the different types of state in a process?
-  Running 
- Terminate
- Process
- New
- 
- 

#### Address Space 
__Address space__ in memory representation of the process

__Virtual memory__ is memory mapping, the memory addresses do not have to correspond to the physical address.

- virtual memory is a management memory technique that is implemented using both hardware and software. it is a section of hard disk that's set up to emulate they computer's RAM

- Virtual memory uses page tables to map memory address
physical with virtual

#### Address Space and Memory and Space
- __Example on Virtual memory__:  
- For instance, if we have virtual addresses that are 32 bit long, and out address space can have only up to 4GB.If we have several process running at the same time,
we will run with physical memory 

- To deal with this, the operating system dynamically decides which portion of address space will be present where in the physical memeory

- Portion of the address space will be on RAM and the rest on the disk. the part on the disk will be brought whenver it is needed.

- One thing to keep in mind that the extra address spaces will be on the disk to give more room to new process to use the memory

- The mapping of virtual memory will keep track of the virtual address their correspnding physical addresses

- The mapping also checks the validity if a process and if is allowed to access the memory 

#### Process Execution State

__How does the OS know what a process is doing ?__

- Let's start with CPU and see how it executes applications. Applications before they can execute, their source code mush be compiled and binary is produced.

- __Binary__ is a sequence of instruction that are not necessarily executes sequentially.They may have jumps, loops, and interrupts that will interrupt the execurtion fo the binary

- At any given point of time, the CPU needs to know where in the instruction sequence the process is currently is, known as __Program Counter__

- __Program Counter__ is actually maintained on the CPU, while the process is executing in a register.

- The registers are located on the CPU and hold values during the execution.

- The registers may have addresses data or status information

- Another piece of state that defines what process is doing is the process stack .

- On the top of the stack is defined by the stack pointer,the stack pointer maintance information about what process are saved in the memory and which on is resumed.

- To main all of this information about every single process,the operating system maintans what we call a __process control bloxk or PCB__

#### Process Control Block
- __PCB__ is a data structure that the operating system that maintains for every one of the processes that it manages.

- __The Process Control Block__ must contain process state like the program counter the stack pointer, all of the CPU registers, the below picture shows what every process contain in terms of information

<img src="https://s28.postimg.org/cfsktiw8d/image.png" width="300px">

- The PCB is created when the process is created.For instance, the program counter will be set to point to the vert first instruction in that process.
 
- Certain fields of the process are updated whenever the process state changes.For instance, when the process requests more memory, the operating system will allocate more memory and will establish new valid virtual to physical memory mappings for this process

- Other field in PCB can change frequently. For instance, during the execution of the program, the program counter changes on every single instruction

- Note: update the program counter is a job done by the register in the CPU

- The operating system's hob to collect to save all the inforamtion that CPU maintains for a process, and to store it in the Process Control Block structure whenever that particular process is no longer running on the CPU.

#### What is a PCB Used?

<img src="https://s29.postimg.org/oirp7ix7b/image.png" width="300px">

- Let's assume the operating system manages two processes, __P1 and P2__.It has already created them and their Process Control Blocks, and these Process Control Blocks are stored somewhere in memory.

- Let's say P1 is currently running on the CPU, and P2 is idle. What this means, that P1 is running, is that the CPU registers currently hold a value that correspond to the state of P1.

- Then at some point, the operating system decides to interrupt P1, so P1 will become idle.Now, what the operating system has to do,

- It has to save all the state information regarding P1,
including the CPU registers, into the Process Control Block for P1.Next, the operating system must restore the state about process 2 so that process 2 can execute.

- What that means is that it has to update the CPU registers with values that correspond to those of the Program Control Block for process 2.

- If at some point during its execution, P2 needs more physical memory,it will make a request via the malloc call, for instance, and the operating system will allocate that memory and establish new virtual to physical address mappings for, and update as appropriate the control block data structure for process P2.

- When P2 is done executing, or when the operating system decides to interrupt P2,it will save all the information regarding P2 state in the Process Control Block for P2, and then it will restore the Process Control Block for P1.
P1 will now be running, and the CPU registers will reflect the state of P1.

- Given that the value of the Process Control Block for P1 corresponds exactly to the values it had when we interrupted P1 earlier, that means that P1 will resume its execution at the exact same point where it was interrupted earlier by the operating system.

- Each time the swapping between processes is performed,
the operating system performs what we call context switch.

#### Context Switch :

- Now we can more formally state that a context switch is the mechanism used by the operating system to switch the execution from the context of one process to the context of another process.

- This is happening both when the operating system switches from the execution of P1 to the execution of P2.And then again a second time when the OS switches from the execution of P2 back to the execution of P1.

- This operation can be expensive, and that's for two reasons.

- First, there are __direct costs__, and this is basically the number of cycles that have to be executed to simply load and store all the values of the process control blocks to and from memory.

- __There are also indirect costs.__ When process 1 is running on the CPU,a lot of its data is going to be stored into the processor cache.As long as P1 is executing, a lot of its data is likely going to be present somewhere in the processor cache hierarchy.

- Modern CPUs, have a hierarchy of caches from L1 to L2, down to the last level cache.Each one is larger, but potentially slower than the previous one.

- More importantly, however, accessing this cache is much,
much faster than accessing the memory.For instance, the accesses along the processor cache hierarchy will be on
the order of cycles, whereas the accesses to memory will be on the order of hundreds of cycles, 

- For instance,When the data we need is present in the cache, in this case,that's P1's data, we call this that the cache is hot.But when we context switch to P2, some, or even all, of the data belonging to P1 in the cache will be replaced to make room for the data needed by P2.

- So, the next time P1 is scheduled to execute, its data will not be in the cache.It will have to spend much more time to read data from memory,so it will incur cache misses.We call this the cold cache.Running with a cold cache is clearly bad because every single data access requires much longer latency to memory and it slows down the execution of the process.

#### Process Life Cycle: States:

__What other states can a process be in?__

- Initially, when a process is created, it enters the new state. This is when the OS will perform admission control, and if it's determined that it's okay, the operating system will allocate and initiate a __process control block__ and some initial resources for this process.

- The it starts executing, but it isn't actually executing on the CPU.It will have to wait in this ready state until the __scheduler__ is ready to move it into a running state when it schedules it on the CPU.

- Once the __scheduler__ gives the CPU to a ready process, that ready process is in the running state.

__Note:__ the process can be interrupted while running, so that a __context switch__ can be performed.This would move the running process back into the ready state.

- If the process initiates some longer operation, like reading data from disk or to wait on some event like a timer or input from a keyboard.At that point, the process enters a __waiting state.__ When the event occurs or
the I/O operation completes, the process will become ready again.

- Finally, when a running process finishes all operations in the program or when it encounters some kind of error, it will exit. It will return the appropriate exit code, either success or error, and at that point, the process is __terminated__

__Note__ __The CPU is able to execute  a process when a process in the state of running and ready__

#### Process Life Cycle :

<img src="https://s27.postimg.org/p6ipl38g3/image.png" width="300px">

__How a process is created ?__

- In operating systems, a process can create child processes.In this diagram here, you see that all processes will come from a single root, and they will have some relationship to one another .

- the creator of the process is the parent and the created process is the child of that parent.Some of these will be privileged processes.They will be root processes.

- In most operating systems, once the initial boot process is done and the operating system is loaded on the machine will create some number of initial processes.

- 1When a user logs into a system, a user shell process is created. And then when the user types in commands, like list or emacs, then new processes get spawned from that shell parent process.

- The final relationship looks like this tree.

- Most operating systems support two basic mechanisms for
process creation, __fork and exec.__

- A process can create a child via either one of these mechanisms.

__With the fork mechanism,__

- the operating system will create a new Process Control Block for the child. And then it will copy the exact same values from the parent Process Control into the child Process Control Block. At that point, both the parent and the child will continue their execution at the instruction that's immediately after the fork.

- And this is because both the parent and the child have the exact same values in their Process Control Block, and this includes the value of the program counter.So, after the operating system completes the fork,both of these processes will start their execution at the exact same point.

__Exec behaves differently.__

- It will take a Process Control Block structure created via fork, but it will not leave its values to match the parent's values like with fork.
Instead, the operating system place the child's image. It will load a new program. And the child's PCB will now point to values or describe values that describe this new program.

- In particular, the program counter for the child will now point to the first instruction of the new program.Now, the behavior of actually creating a new program.

- More examples, when you call a fork, the fork creates the initial process, And then you call an exec, which replaces the child's image,the image that was created in the fork, with the image of this new program.



__QUIZ:__

<img src="https://s24.postimg.org/hlppweq2d/ps5.png" width="300px">

#### Role of the CPU Scheduler:

- For the CPU to start executing a process, the process must be ready first. however, there will be multiple ready processes waiting in the ready queue.

- __How do we pick what is the right process that should be given the CPU next,__ that should be __scheduled on the CPU?__

- The __CPU scheduler__  is an operating system component that manages how processes use the CPU resources.It decides which one of the currently ready processes will be dispatched to the CPU so that it can start running, start using the CPU.And it also determines how long this process should be allowed to run for.

- Over time this means that in order to manage the CPU,
the operating system must be able to __preempt to interrupt the executing process and save its current context.This operation is called preemption.__

- Then the operating system must run the __scheduling algorithm,in order to choose one of the ready processes that should be run next.__

- And finally, once the process is chosen, the OS must __dispatch this process on to the CPU and switch into its context so that process can finally start executing.__

#### What about I/O?

<img src="https://s29.postimg.org/va8plt047/ps6.png" width="450px">

- In this diagram, imagine a process had made an I/O request. The operating system delivered that request.For instance, it was a read request to disk.and then plays the process on the I/O queue that's associated with that
particular disk device.

- So the process is now waiting in the I/O queue.The process will remain waiting in the queue until the device completes the operations, so the I/O event is complete, and responds to that particular request.

- So once the I/O request is met, the process is ready to run again, and depending on the current load in the system, it may be placed in the ready queue, or it may be actually scheduled on the CPU if there's nothing else waiting in the ready queue before it.

#### Inter Process Communication 

- Here's an example of a web application consisting of
two processes on the same machine. The first one is the web server,the front-end, that accepts the customer request. And the second one is the backend,the database that stores customer profiles and other information.

__How may these processes interact?__

- The of mechanisms for interacting between processes are called __inter-process communication__ or we refer to them as IPC.

- __The IPC mechanisms__ help __transfer data and information from one address space to another, while continuing to maintain the protection and isolation that operating systems are trying to enforce.__

- IPC mechanisms need to provide flexibility as well as clearly performance.

<img src="https://s27.postimg.org/495bku1ir/ps7.png" width="300px">

- One mechanism that operating systems support is __message passing IPC.__ The operating system establishes a communication channel, is like a shared buffer for instance, and the processes interact with it by writing or sending a message into that buffer, Or, reading or receiving a message from that shared communication channel.

- So, it's message passing because every process has to put the information that it wants to send to the other process, explicitly in a message and then to send it to this dedicated communication channel.

- __The benefits of this approach__ is that it's really the operating system who will manage this channel, and it's the operating system that provides the exact same APIs, the exact same system calls for writing or sending data, and the reading or receiving data from this communication channel.

- __The downside is the overhead.__ Every single piece of information that we want to pass between these two processes we have to copy from the user space of the first process into this channel that's sitting in the OS, in the kernel memory.And then back into the address space of the second process.

<img src="https://s29.postimg.org/53lpem4sn/ps8.png" width="300px">
- __The other type of IPC mechanism is what we call shared memory IPC.__ The way this works is the operating system establishes the shared memory channel, and then it maps it into the address space of both processes.

- The processes are then allowed to directly read and write from this memory, as if they would to any memory location that's part of their virtual address space.So the operating system is completely out of the way in this case.

- __the main advantage of this type of IPC.__ That the operating system is not in the fast path of the communication.So the processes, while they're communicating are not going to incur any kind of overheads from the operating system.

- __The disadvantage of this approach__ is because the operating system is out of the way it no longer supports fixed and well defined APIs how this particular shared memory region is used. For that reason, its usage sometimes becomes more error prone, or developers simply have to re-implement code to use this shared memory region in a correct way.


#### KeyWords (REVIEW):
__Direct Communication__
__Indirect communication__
__Sycnchronouns (Block)vs Asynchrnous (Non-blocking)___
__Automatic or explicit Buffering__
__Pipe__ __Unix__ __Piper__
__Unidirectional Pipe__ __Bidirectional Pipe__
