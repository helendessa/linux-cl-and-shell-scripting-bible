# PART 01: THE LINUX COMMAND LINE

## CHAPTER 01: STARTING WITH LINUX SHELLS

Four main parts make up a Linux system:
- Kernel;
- GNU utilities;
- Graphical desktop enviromental;
- Application software.<br><br>

<div style="text-align:center;">
    <img src="./images/linux-system.png" alt="linux-system" width="500">
</div>

### a. Kernel
Controls all the hardware and software, allocating hardware when necessary and executing software when required.<br/>

Created by Linus Torvalds, who released it to the Internet and solicited suggestions for improving it. Today, not just Linus controls the kernel code, but a team of devs.<br/>

The kernel manages four components:
- System memory;
- Software programs;
- Hardware;
- Filesystem.

#### a.1 System memory management
It manages:
- Physical memory: available on the server
- Virtual memory: using space on hard disk, the swap space. The kernel swaps virtual memory back and forth from the swap space to the physical memory.<br/>

Memory locations are grouped into blocks (pages). The kernel locates each page in the physical memory or the swap space, and maintains a table indicating where which page is.<br/>

Page not being acessed for a long time -> swapped out.<br/>
Request acess -> swap out a different memory page -> swap in the required page.

#### a.2 Software memory management
Process = running program (foreground, displaying output or background).<br/>
The kernel creates the first process (init, on the virtual memory), to start all other processes, that takes a unique area in virtual memory to store the data and code that the process uses.

Popular init processes:

- SysVinit: used in old Linux. Used runlevels to determinate what process to start, the state of the running Linux system and what processes should run in each state.<br/>
To view the current runlevel:
```bash
$ runlevel
N 5
$
```
- systemd: determines what processes to run by linking events to unit files, that defines the programs to start when specified events occurs. Group unit files together into targets, that defines a specific running state (smiliar to SysVinit). System startup -> all unit files starts.</br>
To view current default target:
```bash
$ systemctl get-default
graphical.target
$
```