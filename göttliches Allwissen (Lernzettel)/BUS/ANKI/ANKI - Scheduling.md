TARGET DECK: BUS::OS Scheduling

definition: **Scheduler** #flashcard
OS component that **allocates CPU resources to threads**:
which thread runs on which CPU, when and for how long.
<!--ID: 1783610932189-->


Name the 3 categories of scheduling algorithms #flashcard
1. Batch
2. Interactive
3. Real Time
<!--ID: 1783610932193-->


Use case and preemption for a **Batch** scheduler? #flashcard
For long running calculations.
No preemption: reduce overhead.
<!--ID: 1783610932197-->


Use case and preemption for an **Interactive** scheduler? #flashcard
User and IO interactions
Preemption necessary for **responsiveness**
<!--ID: 1783610932202-->



Use case and preemption for a **Real Time** scheduler? #flashcard
Embedded systems, controlling systems.
May or may not use preemption.
<!--ID: 1783610932206-->


key metrics: **Batch** scheduler? #flashcard
- throughput
- turnaround time
- maximize CPU/resource utilization
<!--ID: 1783610932210-->


key metrics: **Interactive** scheduler? #flashcard
- response time / latency
- user experience / "feel"
<!--ID: 1783610932215-->


key metrics: **Real Time** scheduler? #flashcard
- meeting deadline
- predicability
<!--ID: 1783610932220-->


Name three **batch scheduling** policies: #flashcard
1. First-Come-First-Served (FCFS)
2. Shortest-Job-First (SJF)
3. Shortest remaining time (SRT)
<!--ID: 1783610932224-->


preemption and pro/con of **Shortest-Job-First (SJF)** scheduling? #flashcard
no preemption.
pro: optimal if jobs/arrival times known in advance
con: bad for short jobs arriving late
<!--ID: 1783610932228-->


preemption and pro/con of **Shortest-Remaining-Time (SRT)** scheduling? #flashcard
is a preemptive version of SJF.
pro: short jobs arriving late are not penalized
con: long jobs can starve if new short jobs keep arriving
<!--ID: 1783610932233-->


Name three **interactive scheduling** policies: #flashcard
1. Round Robin
2. Priority Based (multilevel queuing)
3. Fair
4. Lottery
<!--ID: 1783610932237-->


idea and pro/con: **Round Robin scheduling**: #flashcard
time quantum per thread, circe around.
pro: quite fair, easy implementation
con: choice of quantum is complex
<!--ID: 1783610932241-->


idea and pro/con: **Priority based scheduling : multilevel queueing**: #flashcard
one queue per priority.
pro: high priority threads are not hindered by others
con: not fair, tuning priorities is complex
<!--ID: 1783610932245-->



idea and pro/con: **Fair scheduling**: #flashcard
threads sorted by used CPU time. pick lowest one.
pro: very fair
con: complex implementation
<!--ID: 1783610932249-->


idea and pro/con: **Lottery scheduling**: #flashcard
randomly choose a thread (can be weighted).
pro: pretty fair, easy implementation
con: no control over results
<!--ID: 1783610932257-->


What two types of **Real Time Schedulers** exist? #flashcard
1. Hard Real Time: Deadlines **MUST** be met (car brake).
2. Soft Real Time: Deadline can be missed from time to time. (video decoder with 60fps target)
<!--ID: 1783610932261-->

