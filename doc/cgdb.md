## cgdb
> Warning: Do Not Type layout src

### Compile source file for debugging

```makefile
g++ -Wall -g3
    > -g3 must be assigned
    > -O must be all removed (Shift + o, optimized for short)
```

### reverse-next
> Step program backward, proceeding through subroutine calls
<https://sourceware.org/gdb/wiki/ProcessRecord>
<https://stackoverflow.com/questions/7517236/how-do-i-enable-reverse-debugging-on-a-multi-threaded-program>

For multi-thread reverse debugging
You need to active the instruction-recording target, by executing the command record

#### reverse - Example

```vim
record
next
reverse-next

record stop
```
### finish
> continue until hit a return

Upon return, the value returned is printed and put in the value history.

### break
```
break main
break 334
```
### until
> can be used to jump out of function

```
until + 3
until <Line_Number>

Execute until the program reaches a source line greater than the current
or a specified location (same args as break command) within the current frame))
```

### condition
> (gdb) help condition
Specify breakpoint number N to break only if COND is true.
Usage is `condition N COND', where N is an integer and COND is an
expression to be evaluated whenever breakpoint N is reached.

```vim
break <Function>
info breakpoints
condition 3 i == 3
```

### info
```vim
info line
info line -- Core addresses of the code for a source line
```

### logging
> You may want to save the output of GDB commands to a file. There are several commands to control GDB’s logging.

#### logging - Example
```vim
set logging file ~/dpvs.log
set logging on
set trace-commands on
show logging

set logging on
Enable logging.

set logging off
Disable logging.

set logging file file
Change the name of the current logfile. The default logfile is gdb.txt.

set logging overwrite [on|off]
By default, GDB will append to the logfile. Set overwrite if you want set logging on to overwrite the logfile instead.

set logging redirect [on|off]
By default, GDB output will go to both the terminal and the logfile. Set redirect if you want output to go only to the log file.

show logging
Show the current values of the logging settings.
```

### shortcut key
> only support >= v0.7.0, refer <http://cgdb.github.io/docs/cgdb.html>

```
When you are in the source window, you are implicitly in CGDB mode. All of the below commands are available during this mode.
i
Puts the user into GDB mode.

s
Puts the user into scroll mode in the GDB mode.

Ctrl-T
Opens a new tty for the debugged program.
```

### cgdb usage
> Jump to cgdb source window, like VIM, type command below to switch to horizontal split

```
set winsplitorientation=vertical
set winsplitorientation=horizontal
```