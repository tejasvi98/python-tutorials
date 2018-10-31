## Interpreted language ##
* Python is an interpreted language
* Instead of compiling the whole code it directly executes the code line by line in the given order
* The program thats getting executed When you call `python` in the terminal is actually the interpreter

## Dynamically typed language ##
* Python is a dynamically typed langugage
* The type (integer/string/object etc) are associated with the run-time values, and not the named variables
* If you see other languages like java you have to specify what type each variable is, here it is not needed
* So you have the freedom to assign any value to any variable

```
>>> a = 10
>>> type(a)
<type 'int'>
>>> 
>>> a = 'Maria'
>>> type(a)
<type 'str'>
>>>
```

## How python works ##
* First your code (`.py` files) is parsed for syntax errors. Then it gets translated into the byte code (`.pyc` files)
* These byte codes are then executed by the python virtual machine

![Python Internals](https://raw.githubusercontent.com/akhilputhiry/python-for-maria/master/images/python-internals.png)
