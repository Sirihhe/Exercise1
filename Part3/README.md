# Reasons for concurrency and parallelism


To complete this exercise you will have to use git. Create one or several commits that adds answers to the following questions and push it to a repository to complete the task. Remember to also submit your answers to Blackboard

When answering the questions, remember to use all the resources at your disposal. Asking the internet isn't a form of "cheating", it's a way of learning.

 ### What is concurrency? What is parallelism? What's the difference?
 > Concurrency means that several computations are happening at the same time. They start, run and complete in overlapping time periods. But they are not necessarily progressing simultaneously.
Parallelism is many calculation or execution of a process that are carried out simultaneously. This can be done with CPU’s in parallel. 
The difference between concurrency and parallelism is that concurrency is about dealing with a lot in the same time, when parallelism is about doing a lot at the same time. 

 
 ### Why have machines become increasingly multicore in the past decade?
 > With time each single core has been developed to be smaller in size. They run on lower frequencies compared to the single processing unit, which reduces the power dissipation or temperature. The single processing unit is therefore replaced with multiplies new cores in the same chip, due to smaller size and less energy consumptions.  
 
 ### What kinds of problems motivates the need for concurrent execution?
 (Or phrased differently: What problems do concurrency help in solving?)
 > Pthread_create() create a new thread.

Threading.thread() create a new thread.

Go create a coroutine.

 
 ### Does creating concurrent programs make the programmer's life easier? Harder? Maybe both?
 (Come back to this after you have worked on part 4 of this exercise)
 > It is both harder and easier. Harder because we still have to consider the problem with parallelism. However it still makes it possible to split complex algorithms into separated tasks, which makes the job easier. 
 
 ### What are the differences between processes, threads, green threads, and coroutines?
 > Process: instance of a program that is executed by one or many threads. The process contains the program code and its activities.
Threads: the program is split into small sequence of program instruction which is turned into multiple simultaneously running tasks.
Green threads: is threads that are scheduled by a runtime library or virtual machine instead of natively by the underlying OS.
Coroutines: Generalize subroutines (Sequence of program instruction that performs a specific task) for non-preemptive multitasking, by allowing executions to be suspended and resumed. 

 
 ### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
 > Pthread_create() create a new thread.

Threading.thread() create a new thread.

Go create a coroutine.

 
 ### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
 > The GIL makes it only possible that one thread can be in s state of execution at any point in time. The impact is not visible when executing single-threaded programs, but it can be a bottleneck in CPU-bound and multi-threaded code. 
 
 ### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
 > A workaround for the Gil is to use a multiprocessing module. The concept is that multiple processes is used instead of threads. Then each process gets its own Python interpreter and memory space so Gil won’t be any problem. 
 
 ### What does `func GOMAXPROCS(n int) int` change? 
 > This function sets the maximum number of the CPUs that can be executing simultaneously and returns the previous setting. When n < 1 the current setting does not change. 
