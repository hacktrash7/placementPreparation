# Operating Systems

The second-most-asked CS subject after DBMS. Focus heavily on **process management, scheduling, synchronisation, and memory**.

## Concept tree

1. **OS basics** — what an OS is, functions, types (batch, time-sharing, real-time, distributed).
2. **Process vs program**, **process states**, **PCB** (process control block).
3. **Threads** — user vs kernel, multithreading models.
4. **Process scheduling** — FCFS, SJF, SRTF, Round Robin, Priority, Multilevel queue.
5. **Inter-process communication** — pipes, shared memory, message passing.
6. **Synchronisation** — race conditions, critical section, mutex, semaphore.
7. **Classical synchronisation problems** — producer-consumer, readers-writers, dining philosophers.
8. **Deadlock** — necessary conditions, prevention, avoidance (Banker's), detection, recovery.
9. **Memory management** — contiguous allocation, paging, segmentation.
10. **Virtual memory** — demand paging, page faults, replacement (FIFO, LRU, Optimal, LRU clock).
11. **Thrashing**, **working set model**.
12. **File systems** — files, directories, allocation methods (contiguous, linked, indexed).
13. **Disk scheduling** — FCFS, SSTF, SCAN, C-SCAN, LOOK, C-LOOK.
14. **I/O systems** — DMA, interrupts (concept level).

## Must-know definitions

- **Process**: program in execution, with its own address space and PCB.
- **Thread**: lightweight execution unit sharing the process address space.
- **PCB**: data structure storing process state, PC, registers, scheduling info, memory info.
- **Context switch**: saving state of one process and loading another's.
- **Race condition**: result depends on unpredictable interleaving of threads.
- **Critical section**: code accessing shared resource that must be executed atomically.
- **Mutex**: lock allowing only one thread in critical section at a time.
- **Semaphore**: integer counter with wait()/signal() operations.
- **Deadlock**: set of processes each waiting on a resource held by another.
- **Paging**: dividing memory into fixed-size pages and frames; uses a page table.
- **Page fault**: required page not in memory → OS loads it from disk.
- **Virtual memory**: illusion of more memory than physically present, via paging & swap.
- **Thrashing**: excessive paging due to over-commitment of memory.

## Top 35 interview questions with model answers

**1. What is an operating system?**
Software between the hardware and user/applications. It manages CPU, memory, files, I/O, and security, providing a clean API to programs.

**2. Process vs thread?**
A process has its own address space and resources; a thread is a unit of execution inside a process and shares the process's memory. Threads are cheaper to create and switch.

**3. What is a PCB?**
A kernel data structure for each process holding its state, program counter, registers, memory info, scheduling info, accounting, open files.

**4. Process states?**
New → Ready → Running → (Waiting if blocked) → Ready → … → Terminated. Some OS also distinguish Suspended states.

**5. What is context switching? Cost?**
Saving the CPU state of one process and loading another's. Costs CPU time + cache & TLB invalidation — pure overhead.

**6. CPU-bound vs I/O-bound processes?**
CPU-bound spends most time computing; I/O-bound spends most time waiting for I/O. Scheduler design favours mixing them for throughput.

**7. Scheduling algorithms — explain briefly.**
- **FCFS**: non-preemptive; simple but convoy effect.
- **SJF**: shortest job first; optimal avg wait but needs burst-time knowledge; can starve long jobs.
- **SRTF**: preemptive SJF.
- **Round Robin**: time-slice based; fair, good for time-sharing.
- **Priority**: highest priority first; starvation possible; fix with aging.
- **Multilevel feedback queue**: multiple queues with different priorities; jobs migrate between queues.

**8. Preemptive vs non-preemptive scheduling?**
Preemptive can interrupt a running process; non-preemptive lets it run to completion (or until I/O).

**9. What's the formula for waiting time, turnaround time?**
- Turnaround time = Completion time − Arrival time.
- Waiting time = Turnaround time − Burst time.
- Response time = First scheduled time − Arrival time.

**10. What is a critical section?**
A code region that accesses shared variables; must be executed by only one process at a time to avoid race conditions.

**11. What is a semaphore? Types?**
An integer with `wait(s)` (decrement, block if < 0) and `signal(s)` (increment, wake waiter). Binary semaphore = 0 or 1 (like mutex); counting semaphore = any non-negative integer.

**12. Mutex vs semaphore?**
Mutex is strictly binary and has *ownership* (only the locker can unlock). A binary semaphore lacks ownership and can be signalled by any thread.

**13. Classical synchronisation problems?**
- **Producer-Consumer**: bounded buffer + 2 semaphores (`empty`, `full`) + mutex.
- **Readers-Writers**: many readers OR one writer.
- **Dining Philosophers**: 5 philosophers, 5 forks — illustrates deadlock & starvation.

**14. Necessary conditions for deadlock (Coffman conditions)?**
1. **Mutual exclusion**, 2. **Hold and wait**, 3. **No preemption**, 4. **Circular wait**. Break any one to prevent deadlock.

**15. Deadlock prevention vs avoidance?**
*Prevention* eliminates one of the four conditions structurally (e.g., resource ordering). *Avoidance* dynamically checks whether granting a resource keeps the system in a safe state (Banker's algorithm).

**16. What is the Banker's algorithm?**
A deadlock-avoidance algorithm: each process declares its maximum needs; the OS only grants a request if the resulting state is *safe* (some ordering of completion exists).

**17. What is paging? Why used?**
Memory divided into fixed-size pages (process) and frames (RAM). Avoids external fragmentation and supports virtual memory. Uses a page table per process; translation can use a TLB cache.

**18. Segmentation vs paging?**
Segmentation divides memory into *variable-sized logical segments* (code, data, stack). Paging is fixed-size. Modern systems use paging; segmentation is mostly legacy.

**19. What is virtual memory?**
An abstraction giving each process its own large address space, paged on demand from disk. Lets programs exceed physical memory.

**20. What's a page fault?**
Access to a page not currently in RAM. OS handler loads the page from disk (or zero-fills), updates page table, restarts instruction.

**21. Page replacement algorithms?**
- **FIFO** — simple; suffers from Belady's anomaly.
- **LRU** — replaces the least recently used; closer to optimal in practice.
- **Optimal** — replace the page used furthest in the future (theoretical baseline).
- **Clock (Second Chance)** — circular FIFO with reference bit.

**22. What is thrashing? How to mitigate?**
When a process spends more time paging than computing because its working set doesn't fit in memory. Mitigate by reducing degree of multiprogramming, working set model, or page-fault frequency control.

**23. What is the working set?**
The set of pages a process actively uses in a recent time window. Keeping each process's working set in memory avoids thrashing.

**24. Fragmentation — internal vs external?**
- **Internal**: wasted space *inside* an allocated block (fixed-size allocation).
- **External**: free memory split into small unusable holes (variable-size allocation). Solved by compaction or paging.

**25. File allocation methods?**
- **Contiguous** — fast, but suffers external fragmentation.
- **Linked** — flexible, but slow random access.
- **Indexed** — index block of pointers; supports random access.

**26. Disk scheduling algorithms?**
FCFS (simple, unfair), SSTF (shortest seek, may starve), SCAN/Elevator (sweep), C-SCAN (one-way sweep), LOOK / C-LOOK (variants).

**27. What is DMA?**
Direct Memory Access — a device transfers data to/from memory without CPU mediation, freeing the CPU.

**28. What is an interrupt? Types?**
Hardware signal to CPU to handle an event. Types: hardware (I/O), software (syscalls), trap (exceptions), and maskable vs non-maskable.

**29. System call vs library function?**
A system call requests the kernel via a software interrupt (context switch to kernel mode). A library function may or may not invoke a system call; e.g., `printf` ultimately calls `write`.

**30. User mode vs kernel mode?**
User mode has limited privileges; kernel mode can execute any instruction and access any memory. A bit in the CPU's status register distinguishes them. Transition via syscalls/traps.

**31. What is a zombie process?**
A child that has finished execution but whose parent has not yet read its exit status — it stays in the process table until `wait()` is called.

**32. What is an orphan process?**
A process whose parent has exited. It's adopted by `init` (PID 1) on Unix-like systems.

**33. Multiprogramming vs multitasking vs multiprocessing?**
- **Multiprogramming**: many programs in memory; CPU switches when one blocks (improves CPU utilisation).
- **Multitasking**: time-sharing; user perceives simultaneous execution.
- **Multiprocessing**: multiple CPUs running in parallel.

**34. Spinlock vs mutex?**
Spinlock busy-waits in a loop until the lock is free (good for very short critical sections on multi-core). Mutex blocks the thread and yields the CPU (good for longer waits).

**35. What is a TLB?**
Translation Lookaside Buffer — a small fast cache of recent virtual→physical page-table entries; massively reduces address-translation time.

## Numerical you must be able to solve

These appear in TCS NQT pseudocode/MCQ sections too:

1. Compute **average waiting time** and **turnaround time** for FCFS / SJF / RR given arrival & burst times. Practice 5 different schedules.
2. Apply **page replacement** (FIFO, LRU, Optimal) on a given reference string and count page faults.
3. Walk through **Banker's algorithm** on a small example (3 processes, 3 resource types).
4. Compute disk head movement for **SCAN, SSTF, C-SCAN** given a request queue.

## Diagrams you should be able to draw

- Process state diagram.
- Five layers of memory hierarchy (registers → cache → RAM → SSD → disk).
- Paging address translation: virtual address → page no + offset → frame no + offset.
- Producer-consumer using semaphores (pseudocode).
- Resource-allocation graph for deadlock.

## Quick revision card

- OS manages CPU, memory, I/O, files, security.
- Process states: New, Ready, Running, Waiting, Terminated.
- Scheduling: FCFS, SJF, SRTF, RR, Priority, MLFQ.
- Synchronisation: mutex (ownership) vs semaphore (no ownership); counting vs binary.
- Coffman conditions for deadlock: mutex, hold-and-wait, no preemption, circular wait.
- Paging: fixed-size; segmentation: variable-size logical units.
- Page replacement: FIFO, LRU, Optimal, Clock.
- Disk scheduling: FCFS, SSTF, SCAN/LOOK, C-SCAN/C-LOOK.
- DMA frees CPU from I/O copying; TLB caches page table lookups.
