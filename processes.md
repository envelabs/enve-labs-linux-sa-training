# Processes in linux
a process refers to a program in execution; it is a running instance of a program. It is made up of the program instruction, data read from files, other programs or input from a system user

### types of processes
there are fundamentally two types of processes in linux

* foreground processes (also referred to as interactive processes) – these are initialized and controlled through a terminal session. In other words, there has to be a user connected to the system to start such processes; they haven’t started automatically as part of the system functions/services

* background processes (also referred to as non-interactive/automatic processes) – are processes not connected to a terminal; they don’t expect any user input

#### ps
list process running owned by the user running the command
```
$ ps
  PID TTY          TIME CMD
 2485 pts/1    00:00:00 bash
 2943 pts/1    00:00:00 ps
```

#### ps -a
list all the process running in the system

#### pgrep
the pgrep command allows you to obtain the process id of a running program by specifying the name
```
$ pgrep ssh
466
969
32694
```

#### kill
a process can be terminated using the `kill` command plus the process `id`
```
$ kill 466
```

#### pkill
the pkill command allows you to kill a program specifying the program's name: ex. `ssh`
```
$ pkil ssh
```
