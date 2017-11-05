README:

Group Members: Aryan Samuel, Alan Duncan, Khoa Hoang

Files Modified in Assignment:
proc.h
kern_resource.c
runq.h
sched_ule.c
kern_switch.c
kern_thread.c
syscall.master

Description:
Our group modified the scheduler inside the FreeBSD operating system to utilize 
lottery scheduling along with the default one provided. We also implemented a 
new system call: gift(pid, t), where pid is the processor id and t is the amount
of tickets that process should be gifted by the process that calls gift. To use gift, we use the builtin
syscall function which will take three arguments, the system call id (548), the process id, and the number of 
tickets respecitively:
syscall(548, pid, t);

When the kernel boots up, the lottery scheduler will schedule all user processes, while all root processes are
handled by the default FreeBSD scheduler.

Testing input and output:

We tested our code by implementing several printf statements inside our code to print:
- Random number array
- Ticket amount
- Tickets being gifted
- Several functions such as:
	-runq_lot_choose() : printed which threads were being chosen and if it was a user or root process
	-donice(): Priority and nice value
	
We also were able to test our code for the lottery scheduler by being able to build, install,
and reboot. We then did several git commands and built-in shell commands to traverse through our folders.
Everything worked as normal.