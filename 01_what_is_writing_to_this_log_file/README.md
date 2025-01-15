# Exercise 01

The developer created a program that doesn't work very well and keeps writing data to /var/log/bad.log that fills up the disk. (tail -f /var/log/bad.log). This program is no longer needed. Find it and stop it.

# Solution

## 1. Find which script write data to bad.log and kill the process

```bash
lsof /var/log.bad.log		# which process is writing to a file (list open files)
fuser /var/log/bad.log		# show PIDs of processes accessing a file
ps -fp <PID>			# which script or command is being run
pstree -ap <PID>		# show hierarchy of processes
kill <PID>
```
