
## Chapter 2 Notes :

__KeyWords (REVIEW):__


- __Direct Communication__

- __Indirect communication__

- __Sycnchronouns (Block)vs Asynchrnous (Non-blocking)___

- __Automatic or explicit Buffering__

- __Pipe__ __Unix__ __Piper__ (how concept ) +  (C code (Unix Pipes))

- __Unidirectional Pipe__ __Bidirectional Pipe__

- __Pipes - attaching to 0  and1__ : using dup2() command (what is the use of the command)

- if the pipe is not close it will be in a waiting mode

- __Unix Named Pipes__

- __Unix Signals__ (communication concepts) (what are they?)

- __Socket__ : definition IP and port number

- Remote procedure Calls -- __stubs__ , __masrshalls__



## Chapter 3:

- __Process Charateristics__

- __Resource Ownership__

- __Execution__

- __Threads vs Process__

-__Thread = Lightweight processes__

- __Motivation for threads__

- __Kernel Threads vs User Threads__

- __Multithreading Models__

- __Many to one model__ : 

- __One_to_One model__ : 

- __Many to Many model__

- Multithreading

- Switching between processors vs threads, it is cheaper and faster to switch between threads than between processors.

- Difference between user threads and kernel threads



Feb 23, 2017 Threads

__What is preemptive scheduling of the CPU ?__

- CPU short term scheduler 
- Preemptive scheduling
- Dispatcher is the short term scheduler
- Scheduling Criteria :
    - Resource Utilization
    - Response time on time-shared system
    - Throughput : how many jobs are going to be exectuted        in one CPU cycle
    - On batch systems
    - On heavily loaded system
    - Scheduling Critieria Example (charts for the average)
    - Throupuht 4/24
    - Turnaround time : the time when the job is submitted()
   
    - __Calculation is important__
    - Algorithms for scheduling CPU
    - First comes first serves (Convey Effect)
    - Shortest Job First 
    - If the arrival time is the same as the burst time, pick the       first one 
    - If two Burst times are equal, look at the arrival time and        pick the one that has the shortest time  
    - Starvation is a job with long CPU burst 
    - Priority Scheduling: Advatages and Disadvantaging 
    - Round Robin Algorithm divide the job into slices, and serve them based on priotity 
    - Priority Scheduler
   
 Feb 27, 2017
 
 - Bust time: the time is required by the CPU
 - 
