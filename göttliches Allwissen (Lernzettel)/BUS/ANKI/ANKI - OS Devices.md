TARGET DECK: BUS::OS Files

definition: I/O device #flashcard
A physical device that enables communication with the "outside" world
<!--ID: 1784557257716-->


Where is the current state (CPU registers, stack/instruction pointers) saved to before starting an ISR? #flashcard
Kernel stack
<!--ID: 1784557257723-->


Why do we *need* maskable interrupts #flashcard
Some kernel code cannot be interrupted for safety reasons.
<!--ID: 1784557257727-->


two key properties a device driver should have #flashcard
- **reentrancy**: can be interrupted by their device at any time
- **device hot-plug**: Cleanup code, cancel pending requests, ...
<!--ID: 1784557257731-->


How does UNIX represent devices #flashcard
As files. Each device is also given a 
- **mayor number**: associated to the required driver
- **minor number**: differentiate devices using the same driver
<!--ID: 1784557257735-->


