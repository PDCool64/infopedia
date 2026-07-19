TARGET DECK: BUS::OS Files

definition: **volatile memory** #flashcard
requires power to maintain stored information.
If power is lost, the data is also lost.
<!--ID: 1784461952191-->


definition: **non-volatile memory** #flashcard
retains stored information even without power
<!--ID: 1784461952196-->


how to UNIX file descriptors work? #flashcard
`open()`only returns an integer called the file descriptor. The actual content is stored in a table in the PCB by the kernel.
*(the content is called an **open file description** in UNIX but the lecture just calls it the same name)*
The integer is the index into the **file descriptor table**.
<!--ID: 1784461952200-->


What meaning to file descriptors **0,1,2** have on UNIX? #flashcard
- 0 = stdin
- 1 = stdout
- 1 = stderr
<!--ID: 1784461952204-->


what does `fork()` do to the file descriptor table #flashcard
It copies the file descriptor table for the new process.
**The entries keep pointing at the same _open file descriptions_  stored by the kernel**.
$\to$ The parent / child view of the files stays in sync even after the fork.
<!--ID: 1784461952208-->


UNIX: hard link #flashcard
Create an entry in a directory that directly has the **inode** of the specified **preexisting** file.
Can only link to files in the same partition, as only these share inodes.
- increments/decrements link count of file if created/deleted
- if link count reaches 0, file is deleted
(you cannot hardlink to a directory: would create loops and other mess)
<!--ID: 1784461952212-->


UNIX: symbolic link #flashcard
Special file that contains a **path as a string**.
Can point to anywhere.
Deleting it does not delete the file.
<!--ID: 1784461952216-->


{{c1::Sectors}} are the physical units a storage device can write to.
<!--ID: 1784461952302-->

Meanwhile {{c1::Blocks}} are the logical units used by the file system.
<!--ID: 1784461952306-->


Drives can be split into {{c1::partitions}} each potentially using a different file system.
<!--ID: 1784461952310-->


MBR / BIOS Disk layout #flashcard
Sector 0 contains the Master Boot Record (MBR):
- Bootstrap code
- Partition table
	- bootable?
	- type (file system)
	- start (first sector)
	- size (number of sectors)
  - Signature
<!--ID: 1784461952220-->


MBR / BIOS boot process #flashcard
Jump into the MBR in Sector 0 and execute the bootstrap code.
The bootstrap code then:
1. finds the bootable partition in the partition table
2. load its first sector
3. execute it, starting the OS boot process
<!--ID: 1784461952224-->



Where is the GUID Partition Table (GPT) stored on a drive? #flashcard
Sector 0 reserved: differentiate from MBR
GPT starts at sector 1 and is duplicated at the end of the drive.
The partition table contains an entry for the **EFI System Partition**
<!--ID: 1784461952228-->


What special partition exists with GPT / UEFI? #flashcard
**EFI System Partition (ESP)** that contains the bootloaders installed
- OS kernels
- generic bootloaders like GRUB
<!--ID: 1784461952232-->


definition: partition #flashcard
A partition is a set of contiguous sectors managed by a file system.
<!--ID: 1784461952236-->



What does a **partition** contain: #flashcard
- superblock with metadata
- Blocks to manage free blocks
- Blocks to manage file metadata (**inode store**)
- blocks that contain the content of the files/dirs
- a root directory
<!--ID: 1784461952239-->


Four schemes to allocate blocks for a file #flashcard
- Contiguous Block Allocation
- Linked List of Blocks
- File Allocation Table (FAT)
- Index Nodes (Inodes)
<!--ID: 1784461952244-->


idea: **contiguous block allocation** #flashcard
Store files in contiguous blocks.
Directory entry:
- first block
- size
<!--ID: 1784461952248-->


pro/con: **contiguous block allocation** #flashcard
pro:
- easy implementation
- great performance on magnetic disk (head movement)
con:
- Growing files is hard (collisions)
- fragmentation
<!--ID: 1784461952251-->


idea: **linked list of blocks** storage allocation #flashcard
each block in storage stores pointer to next one.
Directory Entry:
- location of first block
<!--ID: 1784461952256-->


pro/con: **linked list of blocks** storage allocation #flashcard
pro:
- no fragmentation
- files can grow (no collisions)
con:
- performance drop: head movement to follow list
- can't just access middle of file: traversal needed
- pointers take up space in each block
<!--ID: 1784461952261-->


idea: **File Allocation Table (FAT)** #flashcard
File system maintains a table with an entry for each physical block.
Start at the table entry for a files first block and follow the index stored there through the table.
Directory entry:
- index to start at in the FAT
**The entire FAT is loaded into Memory**.
![[Pasted image 20260719104336.png]]
<!--ID: 1784461952265-->


pro/co: **File Allocation Table (FAT)** #flashcard
pro:
- no fragmentation
- no collisions / files can grow
- good performance: FAT is loaded into memory
con:
- FATs take up a lot of memory:
  multiple GiB for a 1TiB partition
<!--ID: 1784461952269-->


idea: **Index Nodes (Inodes)** #flashcard
A file is defined by its inode, that contains attributes and the locations of the content blocks.
The first blocks of the inode are directly indexed, further blocks use 1-3 levels of **indirecton**. 
File access: look up the inode in the **inode store** on the device and load it into memory.
![[Pasted image 20260719104917.png]]
<!--ID: 1784461952273-->


pro/con: **Index Node (Inodes)** #flashcard
pro:
- no fragmentation
- no collisions / files can grow
- good performance + low memory usage
  (only used inodes loaded in memory)
con:
- complex implementation
<!--ID: 1784461952278-->


How are the indirection layers with **Inodes** implemented? #flashcard
An indirection pointer points to **an entire file system block** of addresses. For example, if a file system has a block size of $4\text{KiB}$ and each address is $4\text{Byte}$ large, a single indirection block stores $1024$ addresses.
<!--ID: 1784461952282-->


What does the directory entry store for each file allocation scheme? #flashcard
- contiguous block allocation: 
	- Start Block
	- Size
	- attributes
- Linked List of Blocks:
	- Start block
	- attributes
- FAT:
	- first index into FAT
	- attributes
- Inodes:
	- Inode number only
	- **NO ATTRIBUTES**
<!--ID: 1784461952286-->


Two ways to store long files names in directory entries #flashcard
- variable sized entries that each list their length
- have names as a heap at the end of the directory block,
  each entry pointing to its name
<!--ID: 1784461952290-->


What do the `rwx` permissions mean on a **directory**? #flashcard
`r`: read the names of the files it contains (`ll` basically)
`wx`: Modify directory entries (create, delete, rename)
`x`: Access the content of the files it contains, but _not the list of entries_
<!--ID: 1784461952294-->


6 common file system optimizations and features
- buffer cache
- journaling
- versioning
- block deduplication
- encryption/compression
- network file systems

What does the **buffer cache** do in Linux? #flashcard
Cache blocks from storage in the **same page cache** as memory pages.
Write back changes when block gets evicted.
Get evicted before memory pages get evicted.
<!--ID: 1784461952298-->


What does **journaling** in a file system do?
Operations are **first** logged into a journal before actually performing them.
Detect and recover from inconsistent states after crashes during file system operations.

