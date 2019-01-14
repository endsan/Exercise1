Results from part 4:

The expected output from these codes are 0, because we are incrementing and decrementing "i" with the same number.
The incrementation is not atomic, i.e. program operations that doesn't run completely independently of any other processes.
Because of this we mostly get weird output, that is not zero.

Python: The Python implementation uses regular threads, which implies that it gives strange values, both positive and negative

C: The C implementation also uses regular thread, which gives the same behavior as for Python.

Go: The Go implementation uses coroutines, which are executed in different threads as handled by runtime. 

