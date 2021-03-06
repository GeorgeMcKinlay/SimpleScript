# SimpleScript Concept

## IMPORTANT:
This file should not be used as documentation as the concept is a little different from the actual language! Check out the [wiki](https://github.com/GeorgeMcKinlay/CCJam/wiki) instead.

## Language structure:

### General:
//, # and -- can be used to comment out lines.
Every script is supplied with "function packages".
Examples for such packages are:
* move - Contains basic movement functions for turtles.
* turtle - Turtle functions.
* terminal - Contains terminal functions.
* computer - Contains computer functions like file management or checking what computer family it belongs to.
* network - A rednet interface.

Lines are ended with either a new line or a semicolon.

### Blocks and Statements:
Statements include:
* perchance / if - 'if' equivalent.
* otherwise / else - 'else' equivalent.
* perhaps / maybe - 'elseif' equivalent.
* repeat / do - 'for' equivalent.

Blocks are ended Python-style by indenting its contents.
E.g:
```
perchance { computer: isAdvanced[] }
	terminal: print ["Hello World. This computer is very advanced."]
```

perchance example:
```
perchance { turtle: detect[] }
	terminal: print ["Found a block in front!"]
```
	
#### repeat examples:
Repeat five times:
```
repeat { 5 }
	terminal: print ["Yo."]
```

While loop:
```
repeat while !{ turtle: detectDown[] }
	move: forward[]
```

### Functions:
Functions are called with this syntax (<> = required, {} = optional):
```
<function package>: <function name> [<parameters>] {*<amount of times to repeat>}[, ..., ...]
```

For example:
```
move: down[] *2, forward[] *4
terminal: print ["Parameters!"] *4
```

**To keep things simple there are no user-defined functions!**

## Example program:
```
perchance { computer: isTurtle[] }
	move: forward[] *2, up[] *4, down[]
otherwise:
	terminal: print ["This program can only run on a turtle!"]
```

