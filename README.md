# multi-t-p

In this repository there's a project where the difference between `multi-processing` and `multi-threading` in `Python`.

## What is Python GIL? 

Because of GIL (Global Interpreter Lock), Python is allowed that only one thread takes control over the interpreter, in other words, just one thread can be executing at time. 

### Why does GIL exists?
Python has something called reference counting which allows the interpreter to know when an object is being used and when it is not.

If the object is not being used, the trash collection comes into scene and free up memory. 

If there was no GIL, the problem comes when a thread could be not using an object, so it tells the trash collection that it can pick it, but it turns out that another thread is using it. 

Here is where the GIL appears, allowing that only one thread takes control at the time. 

## Multiprocessing
The multiprocessing library uses separate memory space, multiple CPU cores, bypasses GIL limitations in CPython, child processes are killable (ex. function calls in programs) and is much easier to use. 

Some caveats of the module are a larger memory footprint and IPC's a little more complicated with overhead. 