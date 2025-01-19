# A Kernel Seedling
TODO: intro

### General Notes
- we seek to write a kernel module (.ko), that is, a piece of code that can be dynamically added to/removed from the kernel while the system is running

- we can extend the kernel's functionality without requiring a reboot or recompilation of the entire kernel

- 'loading' a module means dynamically inserting the module into the kernel's running memory, then the module's functionality becomes part of the kernel

- the module runs in kernel mode, with direct access to privileged operations

- command: `sudo insmod <module>.ko` loads a module
- command: `sudo rmmod <module>.ko` unloads a module

- when a module is loaded, `module_init` function is executed for setup
- when unloaded, `module_exit` is executed to clean up resources

- what I want to happen:
    - when i run `make` -> `sudo insmod proc_count.ko` -> `cat /proc/count`
    things should work as outlined in the lab


## Building
```shell
TODO: cmd for build
```

## Running
```shell
TODO: cmd for running binary
```
TODO: results?

## Cleaning Up
```shell
TODO: cmd for cleaning the built binary
```

## Testing
```python
python -m unittest
```
TODO: results?

Report which kernel release version you tested your module on
(hint: use `uname`, check for options with `man uname`).
It should match release numbers as seen on https://www.kernel.org/.

```shell
uname -r -s -v
```
TODO: kernel ver?