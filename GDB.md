# GDB

List the running processes based on process name
```bash
ps ax | grep <process>
```

Open and attach GDB to running process by PID
```bash
gdb -p <pid>
```

List all breakpoints
```
info break
```

Delete the breakpoint with id ´number´ in the list
```
del <number>
```

Delete breakpoint in file `filename` at line `linenum`
```
clear <filename>:<linenum>
```

Send signal to proccess being debugged
```
signal <SIGNAL>
```
