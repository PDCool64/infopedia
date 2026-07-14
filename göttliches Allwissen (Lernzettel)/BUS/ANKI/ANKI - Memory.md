
TARGET DECK: BUS::OS Memory
# Direct Physical mapping

definition: **direct physical** memory mapping #flashcard
Physical memory addresses hardcoded into programs.
Memory managed by programs not the OS.
<!--ID: 1784040893463-->


consequences: **direct physical** memory mapping #flashcard
Programs can touch kernel memory (guidelines only).
Only one program can be loaded at a time.
<!--ID: 1784040893468-->


Memory Layouts for **direct physical** mapping (3): #flashcard
- OS+Programs in RAM
- OS in ROM
- OS in RAM; Drivers in ROM
<!--ID: 1784040893473-->


definition: direct physical memory mapping: **static relocation**  #flashcard
when a program is loaded into memory, all addresses/pointers have the **base address** of the program added to them by **editing the binary**.
<!--ID: 1784040893477-->


consequences: direct physical memory mapping: **static relocation**  #flashcard
- needs **metadata** to differentiate pointers and regular values
- slow **parsing of binary**
<!--ID: 1784040893481-->


def: direct physical memory mapping: **dynamic relocation** #flashcard
A process holds to values: **base and limit**.
When a process accesses memory, the **CPU hardware**:
- adds the value of the base 
- checks if the result is smaller than the limit
<!--ID: 1784040893485-->


consequences: direct physical memory mapping: **dynamic relocation** #flashcard
- Each memory access requires addition/comparison instructions by the CPU: slow
- varying "limit" values can cause fragmentation
<!--ID: 1784040893490-->


Two techniques to work around **limited physical memory**: #flashcard
- Swapping
- Virtual Memory
<!--ID: 1784040893494-->


---
# Address-Spaces

definition: Address Space #flashcard
Abstract view of memory **as seen by a process**.
Independent per process and may be mapped to any physical address.
<!--ID: 1784040893498-->


Which two properties does Memory Management need to fulfill: #flashcard
- protection (programs can't access each others or the kernels memory)
- relocation (programs can be loaded into any memory location)
<!--ID: 1784040893502-->


Two ways to achieve **protection and relocation** for Memory mapping? #flashcard
- Swapping with Dynamic Relocation
- Virtual Memory
<!--ID: 1784040893507-->


Problems with Dynamic Relocation + Swapping (4) #flashcard
- Address spaces still contiguous memory: difficult to grow
- Fragmentation
- Swapping to storage is costly
- Address spaces cannot be larger than physical memory
<!--ID: 1784040893511-->


Variables-Size Address Spaces: list two layouts #flashcard
- UNIX:
	- Stack and Head grow towards each other
	- copy Stack upwards when they touch
- Fixed-Stack
	- Stack grows towards BBS, fixed size
	- Heap grows upwards towards (current) limit
	- move limit up 
<!--ID: 1784040893515-->


# Free Memory Management

Name two mechanisms for free memory management: #flashcard
- Free Lists
	- split memory into chunks
	- list element per chunks stores
		- state: Used/Free
		- start address
		- size
- Bitmap
	- each bit represents the state of a chunk
<!--ID: 1784040893519-->


# Virtual Memory

With virtual Memory, what component not sits **between the CPU and Memory**? #flashcard
The **MMU** (Memory Management Unit):
- translates virtual addresses to physical ones
- needs a pointer to the physical address of **page table** of the currently running process
<!--ID: 1784040893525-->


definition: **page** and **page frame** #flashcard
- **page**: fixed-size unit of **virtual** memory.
- **page frame**: fixed-size unit of **physical** memory
both are contiguous ranges.
<!--ID: 1784040893530-->


3 key properties of **Virtual Memory** #flashcard
- address space size independent from physical memory size
	- can be partially mapped
- address space split into **pages** which can be mapped anywhere
- translation of **virtual$\to$physical address**  required 
<!--ID: 1784040893535-->


what happens when a page is accessed, which **isn't currently mapped** to a page frame #flashcard
**page fault**: 
- choose another page to swap out
- swap in the needed page
<!--ID: 1784040893540-->


What 7 things are stored in a **Page Table Entry** #flashcard
- **Page Frame Number**
  (the actual translation)
- **Protection**: rwx
- **Modified**/**dirty**: has been written to since being swapped in
  (does the swap in storage have to be updated?)
- **Referenced**: has been read from / written to 
  (metadata for reclamation)
- **Supervisor**: only accessible to kernel?
- **Present**: is the page mapped to a pageframe?
  (accessing a page with this set to 0 triggers a page fault)
- **Uncached**: Page should never be cached in CPU
  (hardware interaction: value can change)
<!--ID: 1784040893544-->


pro: Paging and virtual address spaces
- provides relocation and protection
- efficient in hardware with MMU + TLB