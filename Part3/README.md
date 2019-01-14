# Reasons for concurrency and parallelism


To complete this exercise you will have to use git. Create one or several commits that adds answers to the following questions and push it to your groups repository to complete the task.

When answering the questions, remember to use all the resources at your disposal. Asking the internet isn't a form of "cheating", it's a way of learning.

 ### What is concurrency? What is parallelism? What's the difference?
 > Concurrency is when progress is made to multiple tasks at the same time. Each task is not completely finish before it starts on the next task. In parallelism the tasks is divided into subtasks, which then get processed in parallel, at the exact same time for instance on multiple CPU's. We can say that the difference between concurrency and parallelism is that in parallel, the tasks are running at the same time, and concurrent it looks like it runs at the same time.
 
 ### Why have machines become increasingly multicore in the past decade?
 > To improve processing performance multicore processors have been introduced, as a part of parallel computing. This is an consequence of slower clock speed rate improvements. Earlier, to improve speed, the chip are made smaller with minimal distance within the chip. Multiple cores will allow execution to happen in parallel, which will make calculations faster. A remark to this is that actual processing units will not be guaranteed to be faster overall.
 
 ### What kinds of problems motivates the need for concurrent execution?
 (Or phrased differently: What problems do concurrency help in solving?)
 > Anything but small, weak systems will have the need for concurrent execution. More servers can be tossed in the case of gaining customers. If the program needs tasks to be done simultaniously, concurrent execution has to be made. Elsewhere, concurrency is useful if the problem can be divided into multiple processor cores, if this makes the computations better.
 
 ### Does creating concurrent programs make the programmer's life easier? Harder? Maybe both?
 (Come back to this after you have worked on part 4 of this exercise)
 > This can be separated into multiple views. Concurrent programs make the programmer's life eaiser for task that will run simultanously, but at the same time it will lead to several bug that is hard to spot, and sometimes impossible to spot, especially in while compiling. Examples of this is if two threads wait for each other to continue the execution (called dreadlocks) and where the order of the executed individual threads matter on how the concurrent computations will be (race conditions).
 
 ### What are the differences between processes, threads, green threads, and coroutines?
 > Processes are possibly OS-managed and are truly concurrent. It is the instance of a computer program that is being executed, and it excist within its own adress space. Threads are OS-managed and possibly truly concurrent. It is within the same adress space as other threads and the parent, and multitasking is pre-emptive. Green threads are not OS-managed, with the same consept as threads, but are user-space projections. It is (probably) truly not concurrent. Coroutines are exactly fibers, which means not OS-managed, not truly concurrent, with exactly threads, without co-operatively multitasking.
 
 ### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
 > Threads are created by pthread_create() and threading.Thread(). Coroutines are created by go.
 
 ### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
 > GIL (which is a mutex) prevents multiple Python threads from accessing the same object at the same time. Then they have to wait for the object to be availible before it can be accessed. Python's memory management is not thread-safe. Python's bytecode execution is effectively limited by the GIL, to a single core, dependent of how many Python threads that are divided. 
 
 ### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
 > The multiprocessing library can be used instead of threads to avoid the GIL. Instead of using threads to run the program, processes are created.
 
 ### What does `func GOMAXPROCS(n int) int` change? 
 > How many processors that can execute the code in the program simultanously.
