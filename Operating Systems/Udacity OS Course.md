
#### Introduction of Operating Systems by Udacity :


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
-
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







