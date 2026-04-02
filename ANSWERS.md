# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**
A process is a stand-alone program that is running and has its own memory and system resources. A thread, on the other hand, is a small unit of execution that runs inside a process and shares memory and resources with other threads. Because each process needs to allocate its own memory and system resources, creating processes comes with additional overhead. Because they share an address space, threads may be created more quickly and facilitate effective discussion. Because the simulation required several tasks to run simultaneously while sharing the same ready queue and scheduler data structures, threads were employed in place of processes in this assignment. As a result, threads become more effective and appropriate for CPU scheduling simulation.

[Write your answer here. Consider: What is a process? What is a thread? How do they differ in terms of memory, resources, creation overhead? Why are threads more suitable for this simulation?]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:A process is withdrawn from the CPU and put back at the end of the ready queue in Round-Robin scheduling if it does not complete within its time quantum. After that, the scheduler chooses the next process in line and allots CPU time to it. The incomplete procedure waits until it is once more at the front of the line. Because every process has an equal opportunity to run, this guarantees fairness. When a process, such P1, does not finish inside its time slice in my program's output, it is queued up and run again at a later time.**

[Write your answer here. Describe the specific behavior - where does the process go? When does it run again? Give an example from your actual program output showing a process that was re-queued.]

Example from my output:
```
P1 executing for 200ms
P1 not finished, remaining time: 300ms
P1 added back to ready queue
P2 executing for 200ms


```

**Explanation of example:**
Process P1 utilized its time quantum in this instance, yet there was still burst time left. P1 was pushed to the end of the ready queue by the scheduler. P2 was then chosen to run after that. P1 will ultimately restart until it has completed its execution after other processes have received CPU time.


---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

1.	New: P1 is in the New state when the thread object is created but before the start() method is called. At this point, the thread exists but has not yet been scheduled for execution.
	2.	Runnable: P1 enters the Runnable state after start() is called. The thread is ready to run and waiting for the CPU scheduler to assign it execution time.
	3.	Running: P1 moves to the Running state when the scheduler selects it from the ready queue and the CPU starts executing its run() method.
	4.	Waiting: P1 enters the Waiting state when it is paused after using its time quantum or when join() is called. It waits until it is scheduled again by the Round-Robin algorithm.
	5.	Terminated: P1 reaches the Terminated state after completing its execution and its remaining burst time becomes zero. At this stage, the thread finishes and is removed from scheduling.


---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: web server
**Description**: Multiple client requests are handled simultaneously by a web server Every request is handled by a different thread.

**Why Round-Robin works we ll here**: Round-Robin scheduling guarantees equity for every request No request can prevent the execution of others By giving each thread a defined time slice, starvation is avoided and responsiveness is enhanced When numerous users connect to the server at once, this is helpful.



### Example 2:   Operating System Task Scheduling

**Description**:

Operating systems schedule multiple user applications such as browsers, editors, and media players.


**Why Round-Robin works well here**: 
Round-Robin allows each application to receive CPU time equally. This improves user experience because all applications remain responsive. The predictable time quantum ensures that interactive programs do not freeze. Threads help the system switch quickly between tasks.

## Summary

**Key concepts I understood through these questions:**
1.	Difference between processes and threads
	2.	Round-Robin scheduling behavior
	3.	Thread lifecycle and states

**Concepts I need to study more:**
 1.	Advanced thread synchronization
	2.	Deadlocks and race conditions 
