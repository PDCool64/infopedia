
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

What strategies exist to choose which chunk of memory to **allocate**?
- First Fit (superior)
- Next Fit
- Best Fit
- Worst Fit

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


pro: Paging and virtual address spaces #flashcard
- provides relocation and protection
- efficient in hardware with MMU + TLB
- fixed sized pages: not fragmentation
- swap at page granularity: fast
<!--ID: 1784363193499-->


virtual adress spaces are giant: how to store page table efficiently? #flashcard
- process never uses entire address space simultaneously
- use multilevel page table
- only load the tables from each level into memory which are being used currently
<!--ID: 1784363193506-->



Why do we need **large/huge pages**? #flashcard
TLB is **small** and can only store translations for a couple MiB of memory.
-> Can't effectively cache when multiple GiB are used quickly
<!--ID: 1784363193510-->


How are **large/huges pages** implemented? #flashcard
Use Multilevel paging: stop at an earlier level in the page walk.
Use address found there as physical address to large/huge page directly, rest of the address becomes offset.
- Large page: stop at the PD
- Huge page: stop at the PDP
(PD and PDP also store PTE-esque metadata and a bit to signal: continue deeper or stop here for large/huge page)
<!--ID: 1784363193515-->


---
# Segmentation

What is **Segmentation**? #flashcard
Alternative virtual memory implementation without paging.
Process can split its address space into multiple **segments**,
which are each mapped to contiguous physical memory.
- segments can have any size
- segments can grow
<!--ID: 1784363193519-->


How is **Segmentation** implemented? #flashcard
segment table and two-part adresses:
- segment number: lookup base+limit in segment table
- **add (_not append_)**  base to offset
- check if below limit
<!--ID: 1784363193523-->


fragmentation when using **segmentation** #flashcard
- varying segment sizes cause fragmentation
- smaller granularity compared to dynamic relocation makes it less severe
<!--ID: 1784363193528-->


Two types of **memory fragmentation** #flashcard
External: Wasted space between segments/address spaces
Internal: Wasted free space inside the page/segment
<!--ID: 1784363193532-->


Why is segmentation not **transparent**? #flashcard
Compiler/assembly code/program has to be aware that segmentation is used: cant just assume flat address space.
Has to specify segment+address explicitly:
`mov eax, [DS:x]` asks for the Data Segment 
(usually the compiler handles this, not the programmer)
<!--ID: 1784363193536-->


comparison: dynamic relocation, segmentation, paging : swapping/fragmentation/transparency #flashcard
![[Pasted image 20260718094458.png]]
<!--ID: 1784363193540-->


How does **Segmentation with Paging** work? #flashcard
Split segments into pages to partially swap them.
Virtual address:
- segment number
- page number
- offset
Segment table contains a pointer to a page table.
"two level paging where the first level is variable size"
<!--ID: 1784363193545-->


---
# Page Faults and Eviction

What would be the optimal eviction strategy and how is it approximated? #flashcard
Optimal: Evict page whose next use is the furthest away
Approximation: Least recently used
<!--ID: 1784363193549-->


Design decision: whose page gets evicted? #flashcard
- a page of the process requesting a new one gets evicted:
  limits number of page frames a single process can use
- a page of another process gets evicted:
  processes can unload each others pages
<!--ID: 1784363193553-->


Name three eviction algorithms #flashcard
- FIFO
- Clock
- LRU with aging
<!--ID: 1784363193558-->


How does FIFO eviction work? #flashcard
- sort list by when they were swapped in
- evict oldest page
<!--ID: 1784363193562-->


Problem with FIFO eviction? #flashcard
Only tracks initial swap in, not later accesses: 
Not an accurate measurement of usage
<!--ID: 1784363193566-->


How does **Clock** eviction work? #flashcard
FIFO with second chance to recently accessed pages.
Uses MMU/TLB referenced bit.
- move around FIFO list 
- skip pages that have referenced bit set to 1
	- reset their referenced bit to 0
- evict first page with referenced = 0
<!--ID: 1784363193571-->


pro: **Clock eviction** #flashcard
avoids swapping out frequently used pages
<!--ID: 1784363193575-->


How does **LRU Approximation with Aging** work? #flashcard
- store a small counter for each page
- at every clock tick
	  - shift counter to the right
	  - add referenced bit as new left bit
- evict page with smallest counter
<!--ID: 1784363193580-->


pro/con: **LRU Approximation with Aging**
- little time/space overhead
- good approximation of LRU
- does not scale for very large address spaces: many counters

---
# Memory allocators

What three levels of Memory allocators do we need? #flashcard
- **page frame allocator**: allocate page frames to pages when an unmaped page is accessed. Part of the kernel.
- **kernel high-level allocator**: Allocates arbitrary size objects for use in the kernel. These object are allocated inside pages given by the page frame allocator.
- **user high-level allocator**: arbitrary size object for user programs.
  Asks the kernel for memory through syscalls and allocates within that.
<!--ID: 1784363193585-->



What **Page Frame allocator** does Linux use? #flashcard
**Buddy allocator**: Merge physical page frames into chunks for $2^{n}$ page frames
<!--ID: 1784363193589-->


How does page frame allocation with the **Buddy Allocator** work? #flashcard
- requested allocation size rounded up to the next $2^{n}$
- if a chunk of that size is available, return it
- Split a chunk in half until reaching that size
	- the resulting halves are called "buddies"
<!--ID: 1784363193594-->


How does freeing page frames with the **Budy Allocator** work?
- tag free chunk as free
- if two buddies are free, merge back into larger chunk
(two neighbors of same size are not always budies)

How do **User Space allocators** work?
- pre-allocate **large chunks of memory at once**
	- request multiple pages from OS
- manages user objects within the large chunk itself
	- free lists
	- metadata
- if user requested allocation fits within the large chunks already pre-allocated, no OS interaction is needed

