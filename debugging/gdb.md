```
gcc -ggdb -mpreferred-stack-boundary=4 -fno-stack-protector -o meet meet.c
```

### start 
```
gdb -q meet
```

### toggle between Intek and AT&T format
```
(gdb) set disassembly-flavor <intel/att>
```

### disassemble <function name>
```
(gdb) disassemble <function name>
```
  
### + opcodes and operands  
``` 
(gdb) disassemble /r <function name>
```
  
### run
```
(gdb) run <arg>
```
  
### set breakpoint at function
```
(gdb) b/break <function name>
```
  
### display the value of an expression
```
(gdb) p/print <var name>
```

### execute next program line (after stopping); step into any function calls in the line
```
(gdb) s/step
```
  
### Execute next program line (after stopping); step over any function calls in the line
```
(gdb) n/next
```
  
### Display info about breakpoints/registers/variables/functions
```
(gdb) info b/reg/variables/functions
```
  
