# A Kernel Seedling
TODO: intro
I modified the proc_count function in the given proc_count.c skeleton as follows:

1. initialized a counter at zero, this updates every time a process is counted, called 'count'

2. intialized a task_struct pointer 'task.' I learned that this is a kernel data structure in Linux that represents a process.

3. used the kernel macro for_each_process and passed the 'task' pointer to it to iterate through every running process. loop updates 'count' at every iteration

4. used 'seq_prinf' to display the value of the counter to the terminal

5. return 0!

## Building
```shell
make
```

## Running
```shell
sudo insmod proc_count.ko
cat /proc/count
```
When I run 'cat /proc/count,' the shell outputs an integer value. 
When I run it, I get numbers around the range of 78-81, corresponding to the number of processes.

## Cleaning Up
```shell
sudo rmmod proc_count
make clean
```

## Testing
```python
python -m unittest
```
When I run the above command, the following appears in the shell:
```shell
...
--------------------------------------------
Ran 3 tests in 12.845s

OK
```
This means my kernel module passes all given tests.

Report which kernel release version you tested your module on
(hint: use `uname`, check for options with `man uname`).
It should match release numbers as seen on https://www.kernel.org/.

```shell
uname -r -s -v
```
When I run the uname command I get the following output:

Linux 5.14.8-arch1-1 #1 SMP PREEMPT Sun, 26 Sep 2021 19:36:15 +0000