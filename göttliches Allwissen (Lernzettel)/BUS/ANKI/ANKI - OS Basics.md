TARGET DECK: BUS::OS Basics

definition: Operating system #flashcard 
Layer between Hardware and User Applications
tasks:
- **abstraction layer** / easy common interfaces
- **resource management**
<!--ID: 1783353284466-->


An OS is made up of components in both ... and ... #flashcard
1. User Space (libraries, utils, ...)
2. the Kernel / supervisor mode
<!--ID: 1783354481140-->


what are the two **privilege Modes**? #flashcard
**User Mode**
- no privileged instructions
- can't access other process's memory
**Supervisor Mode**
- can use all CPU instructions
- complete hardware/device control
<!--ID: 1783354481147-->


how are **privilege modes / protection domains** realized in hardware? #flashcard
x86: Ring 3 least privileged $\to$ Ring $0$ most privileged
ARM: PL0 least privileged $\to$ PL2 most privileged
<!--ID: 1783354481151-->


What does a **system-call** do? #flashcard
a user thread temporarily switches to supervisor mode and executes **predefined** kernel code.
It also checks if the caller is allowed to perform the request.
<!--ID: 1783354481154-->


List $4$ Operating system architectures #flashcard
1. Monolithic kernel
2. Microkernel
3. Hybrid-kernel
4. unikernel
<!--ID: 1783354481158-->


definition: **monolithic kernel** #flashcard
Most stuff in the kernel: Core stuff plus
- file systems
- drivers
- ...
<!--ID: 1783354481162-->


pro/con: **monolithic kernel** #flashcard
pro:
- performance: few syscalls needed
con:
- limited safety: single component crash kills everything
<!--ID: 1783354481165-->



definition: **Microkernel** #flashcard
Bare minimum in the kernel:
- address-space management
- scheduling
- IPC
user space "**servers**"
<!--ID: 1783354481169-->


pro/con: **Microkernel** #flashcard
pro:
- small memory footprint / embedding
- safety: server crash does not affect anything else
- servers can be replaces without reboot
con:
- limited performance: Way more syscalls required for everything
<!--ID: 1783354481173-->



definition: **hybrid-kernel** #flashcard
just a monolithic kernel with some stuff running as a user space server instead
<!--ID: 1783354481176-->



definition: **Unikernel** #flashcard
**Everything** including user applications runs in supervisor mode.
Entire OS+programs as a single application.
<!--ID: 1783354481180-->



pro/con: **Unikernel** #flashcard
pro:
- Performance: everything just a simple function call
- safety: small $\to$ easy to harden
con:
- hard to build / limited tooling
<!--ID: 1783354481184-->
