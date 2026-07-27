TARGET DECK: BUS::OS IPC

Two invariants of a mutex #flashcard
1. only one thread at a time can hold it
2. only the lock owner can unlock it
<!--ID: 1784742267296-->


What is the difference between `pthread_mutex_lock(&myMutex);` and `pthread_mutex_trylock(&myMutex);` #flashcard
`lock`: if the mutex is unavailable, the thread is blocked
`trylock`: if the mutex is unavailable, the function simply returns`EBUSY`without blocking -> thread can decide itself what to do: retry later and do something else in the meantime.
<!--ID: 1784742267310-->


semaphore: producer consumer pattern: #flashcard
Producer uses `signal()/post()` to increment number of available resources.
Consumer uses `wait()` to wait until the number of resources is $\ge 0$
<!--ID: 1784742267314-->



TL:DR: **mutex** #flashcard
- stops more than one thread being in the critical section
- only owner can unlock
- does **not** need any other variables
<!--ID: 1784742267319-->


TL:DR: **semaphore** #flashcard
- represents **number** of available resources, stores this number internally
- `wait()` atomically decrements, `signal()` increments
<!--ID: 1784742267325-->


TL:DR:  **condition variable** #flashcard
- waiting for something to change
- state is stored in **separate user variable**
	- this variable has to be protected by a **mutex**
- always needs `while(!myOwnCondition) cond_wait(); ` loop
<!--ID: 1785154227640-->
