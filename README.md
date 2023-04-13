# Concurrency Issues

## Quick Explanation
Concurrency is the competition for resources between two or more running processes. This competition occurs when two or more processes compete to use the same resources such as I/O equipment, memory, clocks, and others. The absence of an information exchange mechanism between these processes can cause processes that are denied access to be slowed down. As a result, the process becomes perpetually blocked so that it never accesses resources. Problems that arise due to concurrency can be categorized into two problems namely Producer-Consumer Problem and Reader-Writer Problem.

Producer-Consumer Problem is a problem where there are two or more processes that interact using the same buffer. In this problem, there is a process that acts as a Producer and a process that acts as a Consumer. Producer produces values in the buffer, while Consumer takes/reduces the contents of the buffer. 

The conditions that must be met in the Producer-Consumer Problem are that at one time only one process can modify the buffer, if the buffer is full then production must be stopped, and if the buffer is empty then consumption must be stopped. To manage this condition, a critical section setting is used that allows producers and consumers not to be interrupted while modifying the buffer.

Race condition is a situation where multiple processes access and manipulate shared data at the same time. The way to avoid race conditions is to involve shared memory, shared files, and other shared resources in order to find a solution to prevent more than one process from writing and reading to shared data at the same time. This can be achieved by mutual exclusion, which prevents two or more processes from being in a critical section at the same time.

Critical Section occurs when multiple processes have a code segment that, if executed, can change variables, update a table, write to a file, and so on. The code segment is called the Critical Section. There are three parts in Critical Section, namely Entry Section, Exit Section, and Remainder Section. The solution to the critical section problem is to apply mutual exclusion, so that no two processes are in the critical section at the same time. In addition, there is progress and a limited waiting time limit, so that only processes in the entry section can compete to work on the critical section.

Startvation and Deadlock problems also arise due to concurrency. Startvation is a situation where a process is constantly blocked from accessing a needed resource because another process holds the resource continuously. Deadlock, on the other hand, is a situation where multiple interconnected processes wait for resources held by other processes, so that neither process can continue execution. Both of these problems can be avoided

## Meaning and How to handle it of Mutual Exclusion, Deadlock, Startvation and Coherence Data

### Mutual Exclusion
A mechanism where only one process can access a resource at a time. This is done to prevent two or more processes from accessing a resource at the same time which can cause conflicts.

Handling:
Mutual Exclusion handling is to ensure that the resources needed by one process cannot be accessed by another process simultaneously. The technique used to handle Mutual Exclusion is to use a locking mechanism or semaphore. In a locking mechanism, a process will lock the resources being used so that other processes cannot access them until the process has finished using the resources. Whereas in semaphores, the process will change the predefined semaphore value so that other processes wait until the resource is available.

### Deadlock
A situation where two or more processes wait for each other without either process being able to complete. A deadlock situation can occur when two processes hold resources that are needed by another process, so none of the processes can continue.

Handling: Handling deadlock is by using techniques such as deadlock avoidance, deadlock detection, and recovery from deadlock. Deadlock avoidance is done by avoiding conditions that can cause deadlocks to occur, for example by ensuring that all processes only request available resources, or by ensuring that processes only request one resource at a time. Deadlock detection is done by identifying the presence of a deadlock, and deadlock recovery is done by freeing blocked resources or terminating one of the processes involved in the deadlock.

### Startvation
A state in which a process constantly experiences delays in obtaining the resources it needs to complete its task, even though those resources are available. This condition can occur if the priority of the process that requires the resource is lower than other processes that require the same resource.

Handling: Handling starvation is done by organizing the allocation of resources so that each process gets access to the necessary resources fairly. The technique used is to use a scheduling mechanism that takes into account the priority and time of resource assignment to each process. In addition, the operating system can also implement a queue management mechanism that regulates the order of resource assignment so that starvation does not occur.

### Coherence Data
The concept where all systems or units within a computer system access the same data at the same time and maintain the correctness of that data. This is done by ensuring that any changes to data in one unit are also reflected in other related units, so that the data seen by all units is always the same and consistent.

Handling: Coherence data handling is done using a data synchronization mechanism. This is done to ensure that the data used by each process is always consistent and no data conflicts occur. The technique used is to implement a locking mechanism on resources that allows multiple processes to read data, but only one process can write data at a time. In addition, it is also possible to set up a data communication flow that takes into account the order of data access to prevent data conflicts.
