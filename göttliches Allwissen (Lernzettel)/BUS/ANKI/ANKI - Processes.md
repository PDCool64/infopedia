TARGET DECK: BUS::OS Processes

definition: **process** #flashcard
A process is the abstraction that represents an **instance** of a running program.
Set of memory mappings and bundles together threads.
Isolated from each other.
<!--ID: 1783607623839-->


what **states** can a process be in? #flashcard
1. ready
2. running
3. blocked
<!--ID: 1783607623843-->

What three topics are covered in a **Process Control Block (PCB)** #flashcard
1. Runtime
2. Memory
3. Files
<!--ID: 1783608506335-->


What is stored about the "**Runtime**" in a **PCB**? #flashcard
1. process ID (PID)
2. page table pointer (physical address for MMU to find it)
3. signals (pending, masked, handlers)
4. scheduler metadata (used CPU time, next alarm)
5. thread table
<!--ID: 1783608506342-->


What is stored in the **Thread Table** of a **PCB**? #flashcard
For **each** thread, it stores:
- Thread ID
- Registers
	- Instruction Pointer / program counter
	- Stack Pointer
	- General purpose Registers
<!--ID: 1783608506346-->


What is stored about **Memory** in a **PCB**? #flashcard
All information about the virtual Address Space:
- Segments
- Page Table
- Memory mappings
<!--ID: 1783608506350-->


What is stored about **Files** in a **PCB**?
- Current working directory (CWD)
- User ID (UID)
- Group ID (GID)
- file descriptors

What sections is a process' **address space** split up into?
(from 0xFFF... to 0x000...) #flashcard
![[Pasted image 20260709170041.png]]
<!--ID: 1783609457063-->


What does the **Text** section of a Processes Address Space contain? #flashcard
The program code / binary
<!--ID: 1783609457069-->

How does the **Kernel** section of a Processes Address Space work? #flashcard
For all processes, these pages point to a **singular set of page-frames** containing the kernel's memory.
- Supervisor bits in PTEs = 1
pro: system calls don't require changing the page table
<!--ID: 1784040893548-->


What does the **Data** section of a Processes Address Space contain? #flashcard
static **initialized** variables.
<!--ID: 1783609457073-->


What does the **BBS (Block starting symbol)** section of a Processes Address Space contain? #flashcard
static **uninitialized** variables.
<!--ID: 1783609457077-->


What does the **Heap** section of a Processes Address Space contain? #flashcard
dynamically allocated memory.
grows towards larger addresses
<!--ID: 1783609457081-->


What does the **Stack** section of a Processes Address Space contain? #flashcard
- local variables,
- environment variables,
- calling context/stack frame.
grows towards larger addresses
<!--ID: 1783609457085-->


definition: **context switch** #flashcard
The OS changes the currently running process.
<!--ID: 1783609457088-->


Four steps of a **context switch** from process $A\to B$? #flashcard
1. set state of $A$ from running to ready
2. save the CPU registers into $A$'s PCB
3. Copy registers from $B$'s PCB into the CPU registers
	1. load the $B$s page table pointer into the MMU
4. set state of $B$ from ready to running
$\to$ Expensive Overhead
<!--ID: 1783609457092-->


POSIX: `pid_t fork(void)` #flashcard
Create a new process by duplicating the calling process.
New process initially starts with a copy of the PCB and memory.
returns:
- in the parent: PID of the child
- in the child: $0$
<!--ID: 1783609457096-->


POSIX: `int exec(char* path, char* arg, ...)` #flashcard
Replaces the current program with the one passed. Does not return, instead starts the new program in the current process. PID stays the same.
<!--ID: 1783609457099-->


POSIX: `pid_t wait(int *status)` #flashcard
Wait for **any** child process to terminate or change set due to a signal.
Returns the PID of the child.
<!--ID: 1783609457103-->

Processes sit in a parent-child hierarchy.
On UNIX, this creates a {{c1:: full process tree up to init.}}.
<!--ID: 1784040893553-->

On Windows, {{c1:: parents get a handle to child processes, which can be passed around}}
<!--ID: 1784040893560-->


definition: **thread** #flashcard
Entity that executes instructions.
Has its own program counter, registers and stack.
<!--ID: 1783610932265-->


