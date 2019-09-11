![python switch case](./img/python_switch_case.png?raw=true)

This is Python version 3.9.0 alpha 0 with Switch Case!!
====================================

By: Alex Comerford (alexanderjcomerford@gmail.com)

To read the original readme for cpython, build instructions, and more go to [README.rst](./README.rst)

##  What is this fork?

This fork of `cpython` adds two new statements to the python core language, `switch` and `case`. Requisite changes have been made to the python grammar, asdl, and AST compiler to support execution of these statements.

The new syntax for these statements is

``` python
switch EXPR:
    case EXPR:
        SUITE
    case EXPR:
        SUITE
    else:
        SUITE
```

Sample code

``` python
var = 1
switch var:
    case 0:
        print("it's zero!")
    case 1:
        print("it's one!")
    else:
        print("it's something else!")
```
evaluates to

``` python
it's one!
```

## Why do this?

There have been previous PEP's proposing switching on multiple values [here](https://www.python.org/dev/peps/pep-0275/) and [here](https://www.python.org/dev/peps/pep-3103/) which have been subsequently denied in favor of using if/elif chains. However `switch` `case` can be extremely handy in some situations in which if/elif chains might feel a little verbose.

Example:

``` python
switch input(">"):           x = input(">")
    case 'hello':            if x == 'hello':
        SUITE                    SUITE
    case 'bye':              elif x == 'bye':
        SUITE                    SUITE
    case 'how are you':      elif x == 'how are you':
        SUITE                    SUITE
    else:                    else:
        SUITE                    SUITE
```

Using `switch` and `case` as the statements of choice were selected from several proposed syntax variants in [PEP 275](https://www.python.org/dev/peps/pep-0275/).

## How do I try it?!

Follow the build instructions in [README.rst](./README.rst) and run the resulting executable `pythonsc`.

or simply

``` shell
./configure
make
```
