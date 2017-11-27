---
title: "Python Intro"
excerpt: "Intro to Python"
categories: blog
author_profile: false
tags:
- python
---

# Welcome to Python 101

<a href="http://pyladies.org"><img align="right" src="http://www.pyladies.com/assets/images/pylady_geek.png" alt="Pyladies" style="position:relative;top:-80px;right:30px;height:50px;" /></a>

Welcome! This notebook is appropriate for people who have never programmed before. A few tips:

- To execute a cell, click in it and then type `[shift]` + `[enter]`
- This notebook's kernel will restart if the page becomes idle for 10 minutes, meaning you'll have to rerun steps again
- Try.jupyter.org is awesome, and <a href="http://rackspace.com">Rackspace</a> is awesome for hosting this, but you will want your own Python on your computer too. Hopefully you are in a class and someone helped you install. If not:
    + [Anaconda][anaconda-download] is great if you use Windows
      or will only use Python for data analysis.
    + If you want to contribute to open source code, you want the standard
      Python release. (Follow
      the [Hitchhiker's Guide to Python][python-guide].)


## Outline

- Operators and functions
- Data and container types
- Control structures
- I/O, including basic web APIs
- How to write and run a Python script

[anaconda-download]: http://continuum.io/downloads
[python-guide]: http://docs.python-guide.org/

### First, try Python as a calculator.

Python can be used as a shell interpreter. After you install Python, you can open a command line terminal (*e.g.* powershell or bash), type `python3` or `python`, and a Python shell will open.

For now, we are using the notebook.

Here is simple math. Go to town!


```python
1 + 1
```


```python
3 / 4  # caution: in Python 2 the result will be an integer
```


```python
7 ** 3
```

## Challenge for you
The arithmetic operators in Python are:  
```python
    +   -   *   /   **   %   //
```
Use the Python interpreter to calculate:

- 16 times 26515
- 1835 [modulo][wiki-modulo] 163


<p style="font-size:smaller">(psst...)
If you're stuck, try</p>

```python
help()
```
<p style="font-size:smaller">and then in the interactive box, type <tt>symbols</tt>
</p>

[wiki-modulo]: https://en.wikipedia.org/wiki/Modulo_operation


```python
16*26515
1835 % 163
```

## More math requires the math module


```python
import math

# print("The square root of 3 is:", math.sqrt(3))
# print("pi is:", math.pi)
print("The sin of  90 degrees is:", math.sin(math.radians(90)))
```

- The `import` statement imports the module into the namespace
- Then access functions (or constants) by using:  
```python
<module>.<function>
```      
- And get help on what is in the module by using:  
```python
    help(<module>)
```

## Challenge for you
Hint: `help(math)` will show all the functions...

- What is the arc cosine of `0.743144` in degrees?


```python
from math import acos, degrees  # use 'from' sparingly
help(math)
# int(degrees(acos(0.743144)))  # 'int' to make an integer
```

## Math takeaways
- Operators are what you think
- Be careful of unintended integer math
- the `math` module has the remaining functions

# Strings

(Easier in Python than in any other language ever. Even Perl.)

## Strings
Use `help(str)` to see available functions for string objects. For help on a particular function from the class, type the class name and the function name: `help(str.join)`

String operations are easy:
```
s = "foobar"

"bar" in s
s.find("bar")
index = s.find("bar")
s[:index]
s[index:] + "  this is intuitive! Hooray!"
s[-1]  # The last element in the list or string
```

Strings are **immutable**, meaning they cannot be modified, only copied or replaced. (This is related to memory use, and interesting for experienced programmers ... don't worry if you don't get what this means.)


```python
# Here's to start.
s = "foobar"

"bar" in s
```


```python
# You try out the other ones!
s.find("bar")
```

## Challenge for you
Using only string addition (concatenation) and the function `str.join`, combine `declaration` and `sayings` :

```python
declaration = "We are the knights who say:\n"
sayings = ['"icky"'] * 3 + ['"p\'tang"']
# the (\') escapes the quote
```

to a variable, `sentence`, that when printed does this:

```python
>>> print(sentence)
We are the knights who say:
"icky", "icky", "icky", "p'tang"!
```


```python
help(str.join)
```


```python
declaration = "We are now the knights who say:\n"
sayings = ['"icky"'] * 3 + ['"p\'tang"']

# You do the rest -- fix the below  :-)
print(sayings)
```

### Don't peek until you're done with your own code!


```python
sentence = declaration + ", ".join(sayings) + "!"
print(sentence)
print()    # empty 'print' makes a newline
```


```python
# By the way, you use 'split' to split a string...
#  (note what happens to the commas):
print(" - ".join(['ni'] * 12))
print("\n".join("icky, icky, icky, p'tang!".split(", ")))
```

## String formatting
There are a bunch of ways to do string formatting:
- C-style:
```python
"%s is: %.3f (or %d in Indiana)" % \
        ("Pi", math.pi, math.pi)
# %s = string
# %0.3f = floating point number, 3 places to the left of the decimal
# %d = decimal number
#
# Style notes:
#     Line continuation with '\' works but
#     is frowned upon. Indent twice
#     (8 spaces) so it doesn't look
#     like a control statement
```


```python
print("%s is: %.3f (well, %d in Indiana)" % ("Pi", math.pi, math.pi))
```

- New in Python 2.6, `str.format` doesn't require types:
```python
"{0} is: {1} ({1:3.2} truncated)".format(
        "Pi", math.pi)
# More style notes:
#    Line continuation in square or curly
#    braces or parenthesis is better.
```       


```python
# Use a colon and then decimals to control the
# number of decimals that print out.
#
# Also note the number {1} appears twice, so that
# the argument `math.pi` is reused.
print("{0} is: {1} ({1:.3} truncated)".format("Pi", math.pi))
```

- And Python 2.7+ allows named specifications:
```python
"{pi} is {pie:05.3}".format(
        pi="Pi", pie=math.pi)
# 05.3 = zero-padded number, with
#        5 total characters, and
#        3 significant digits.
```


```python
# Go to town -- change the decimal places!
print("{pi} is: {pie:05.2}".format(pi="Pi", pie=math.pi))
```

## String takeaways
- `str.split` and `str.join`, plus the **regex** module (pattern matching tools for strings), make Python my language of choice for data manipulation
- There are many ways to format a string
- `help(str)` for more

# Quick look at other types


```python
# Boolean
x = True
type(x)
```

## Python has containers built in...

Lists, dictionaries, sets. We will talk about them later.
There is also a library [`collections`][collections] with additional specialized container types.

[collections]: https://docs.python.org/3/library/collections.html


```python
# Lists can contain multiple types
x = [True, 1, 1.2, 'hi', [1], (1,2,3), {}, None]
type(x)
# (the underscores are for special internal variables)
```


```python
# List access. Try other numbers!
x[1]
```


```python
print("x[0] is:", x[0], "... and x[1] is:", x[1])  # Python is zero-indexed
```


```python
x.append(set(["a", "b", "c"]))

for item in x:
    print(item, "... type =", type(item))
```

If you need to check an object's type, do this:

```python
isinstance(x, list)
isinstance(x[1], bool)
```


```python
# You do it!
isinstance(x, tuple)
```

## Caveat
Lists, when copied, are copied by pointer. What that means is every symbol that points to a list, points to that same list.

Same with dictionaries and sets.

### Example:
```python
fifth_element = x[4]
fifth_element.append("Both!")
print(fifth_element)
print(x)
```

Why? The assignment (`=`) operator copies the pointer to the place on the computer where the list (or dictionary or set) is: it does not copy the actual contents of the whole object, just the address where the data is in the computer. This is efficent because the object could be megabytes big.



```python
# You do it!
fifth_element = x[4]
print(fifth_element)

fifth_element.append("Both!")
print(fifth_element)

# and see, the original list is changed too!
print(x)
```

### To make a duplicate copy you must do it explicitly
[The copy module ] [copy]

Example:

```python
import copy

# -------------------- A shallow copy
x[4] = ["list"]
shallow_copy_of_x = copy.copy(x)
shallow_copy_of_x[0] = "Shallow copy"
fifth_element = x[4]
fifth_element.append("Both?")

def print_list(l):
   print("-" * 10)
   for elem in l:
       print(elem)
   print()


# look at them
print_list(shallow_copy_of_x)
print_list(x)
fifth_element
```

[copy]: https://docs.python.org/3/library/copy.html


```python
import copy

# -------------------- A shallow copy
x[4] = ["list"]
shallow_copy_of_x = copy.copy(x)
shallow_copy_of_x[0] = "Shallow copy"
fifth_element = x[4]
fifth_element.append("Both?")
```


```python
# look at them
def print_list(l):
   print("-" * 8, "the list, element-by-element", "-" * 8)
   for elem in l:
       print(elem)
   print()

print_list(shallow_copy_of_x)
print_list(x)
```

## And here is a deep copy

```python
# -------------------- A deep copy

x[4] = ["list"]
deep_copy_of_x = copy.deepcopy(x)
deep_copy_of_x[0] = "Deep copy"
fifth_element = deep_copy_of_x[4]
fifth_element.append("Both?")

# look at them
print_list(deep_copy_of_x)
print_list(x)
fifth_element
```


```python
# -------------------- A deep copy

x[4] = ["list"]
deep_copy_of_x = copy.deepcopy(x)
deep_copy_of_x[0] = "Deep copy"
fifth_element = deep_copy_of_x[4]
fifth_element.append("Both? -- no, just this one got it!")

# look at them
print(fifth_element)
print("\nand...the fifth element in the original list:")
print(x[4])
```

## Common atomic types

<table style="border:3px solid white;"><tr>
<td> boolean</td>
<td> integer </td>
<td> float </td>
<td>string</td>
<td>None</td>
</tr><tr>
<td><tt>True</tt></td>
<td><tt>42</tt></td>
<td><tt>42.0</tt></td>
<td><tt>"hello"</tt></td>
<td><tt>None</tt></td>
</tr></table>

## Common container types

<table style="border:3px solid white;"><tr>
<td> list </td>
<td> tuple </td>
<td> set </td>
<td>dictionary</td>
</tr><tr style="font-size:smaller;">
<td><ul style="margin:5px 2px 0px 15px;"><li>Iterable</li><li>Mutable</li>
       <li>No restriction on elements</li>
       <li>Elements are ordered</li></ul></td>
<td><ul style="margin:5px 2px 0px 15px;"><li>Iterable</li><li>Immutable</li>
       <li>Elements must be hashable</li>
       <li>Elements are ordered</li></ul></td>
<td><ul style="margin:5px 2px 0px 15px;"><li>Iterable</li><li>Mutable</li>
    <li>Elements are<br/>
    unique and must<br/>
    be hashable</li>
       <li>Elements are not ordered</li></ul></td>
<td><ul style="margin:5px 2px 0px 15px;"><li>Iterable</li><li>Mutable</li>
      <li>Key, value pairs.<br/>
      Keys are unique and<br/>
      must be hashable</li>
       <li>Keys are not ordered</li></ul></td>
</tr></table>

### Iterable
You can loop over it

### Mutable
You can change it

### Hashable
A hash function converts an object to a number that will always be the same for the object. They help with identifying the object. A better explanation kind of has to go into the guts of the code...


# Container examples

## List
- To make a list, use square braces.


```python
l = ["a", 0, [1, 2] ]
l[1] = "second element"

type(l)
```


```python
print(l)
```

- Items in a list can be anything: <br/>
  sets, other lists, dictionaries, atoms


```python
indices = range(len(l))
print(indices)
```


```python
# Iterate over the indices using i=0, i=1, i=2
for i in indices:
    print(l[i])
```


```python
# Or iterate over the items in `x` directly
for x in l:
    print(x)
```

## Tuple
To make a tuple, use parenthesis.


```python
t = ("a", 0, "tuple")
type(t)
```


```python
for x in t:
    print x
```

## Set
To make a set, wrap a list with the function `set()`.
- Items in a set are unique
- Lists, dictionaries, and sets cannot be in a set


```python
s = set(['a', 0])
if 'b' in s:
    print("has b")
```


```python
s.add("b")
s.remove("a")

if 'b' in s:
    print("has b")
```


```python
l = [1,2,3]
try:
    s.add(l)
except TypeError:
    print("Could not add the list")
    #raise  # uncomment this to raise an error
```

## Dictionary
To make a dictionary, use curly braces.
- A dictionary is a set of key,value pairs where the keys
  are unique.
- Lists, dictionaries, and sets cannot be dictionary keys
- To iterate over a dictionary use `items`


```python
#   two ways to do the same thing
d = {"mother":"hamster",
     "father":"elderberries"}
d = dict(mother="hamster",
         father="elderberries")
```


```python
d['mother']
```


```python
print("the dictionary keys:", d.keys())
print()
print("the dictionary values:", d.values())
```


```python
# When iterating over a dictionary, use items() and two variables:
for k, v in d.items():
    print("key: ", k, end="  ... ")
    print("val: ", v)
```


```python
# If you don't you will just get the keys:
for k in d:
    print(k)
```

## Type takeaways
- Lists, tuples, dictionaries, sets all are base Python objects
- Be careful of duck typing
- Remember about copy / deepcopy

```python
# For more information, use help(object)
help(tuple)
help(set)
help()
```

## Function definition and punctuation

The syntax for creating a function is:

```python
def function_name(arg1, arg2, kwarg1=default1):
    """Docstring goes here -- triple quoted."""
    pass  # the 'pass' keyword means 'do nothing'
    

# The next thing unindented statement is outside
# of the function. Leave a blank line between the
# end of the function and the next statement.
```

- The **def** keyword begins a function declaration.
- The colon (`:`) finishes the signature.
- The body must be indented. The indentation must be exactly the same.
- There are no curly braces for function bodies in Python — white space at the beginning of a line tells Python that this line is "inside" the body of whatever came before it.

Also, at the end of a function, leave at least one blank line to separate the thought from the next thing in the script.


```python
def function_name(arg1, arg2, kwarg1="my_default_value"):
    """Docstring goes here -- triple quoted."""
    pass  # the 'pass' keyword means 'do nothing'
```


```python
# See the docstring appear when using `help`
help(function_name)
```

## Whitespace matters
The 'tab' character **'\t'** counts as one single character even if it looks like multiple characters in your editor.

**But indentation is how you denote nesting!**

So, this can seriously mess up your coding. The [Python style guide][pep8] recommends configuring your editor to make the tab keypress type four spaces automatically.

To set the spacing for Python code in Sublime, go to **Sublime Text** → **Preferences** → **Settings - More** → **Syntax Specific - User**

It will open up the file **Python.sublime-settings**. Please put this inside, then save and close.

```
{
    "tab_size": 4,
    "translate_tabs_to_spaces": true
}
```

[pep8]: https://www.python.org/dev/peps/pep-0008/

## Your first function
Copy this and paste it in the cell below
```python
def greet_person(person):
    """Greet the named person.

    usage:
        >>> greet_person("world")
        hello world
    """
    print('hello', person)
```


```python
# Paste the function definition below:

```


```python
# Here's the help statement
help(greet_person)
```


```python
# And here's the function in action!
greet_person("world")
```

## Duck typing
Python's philosophy for handling data types is called **duck typing** (If it walks like a duck, and quacks like a duck, it's a duck). Functions do no type checking — they happily process an argument until something breaks. This is great for fast coding but can sometimes make for odd errors. (If you care to specify types, there is a [standard way to do it][pep484], but don't worry about this if you're a beginner.)

[pep484]: https://www.python.org/dev/peps/pep-0484/

## Challenge for you
Create another function named `greet_people` that takes a list of people and greets them all one by one. Hint: you can call the function `greet_person`.


```python
# your function
def greet_people(list_of_people)
    """Documentation string goes here."""
    # You do it here!
    pass
```

### don't peek...


```python
def greet_people(list_of_people):
    for person in list_of_people:
        greet_person(person)
```


```python
greet_people(["world", "awesome python user!", "rockstar!!!"])
```

## Quack quack
Make a list of all of the people in your group and use your function to greet them:

```python
people = ["King Arthur",
          "Sir Galahad",
          "Sir Robin"]
greet_people(people)

# What do you think will happen if I do:
greet_people("pyladies")
```


```python
# Try it!

```

## WTW?
Remember strings are iterable...


<div style="text-align:center;">quack!</div>
<div style="text-align:right;">quack!</div>

## Whitespace / duck typing takeways

- Indentation is how to denote nesting in Python
- Do not use tabs; expand them to spaces
- If it walks like a duck and quacks like a duck, it's a duck 

# Control structures

### Common comparison operators
<table style="border:3px solid white;"><tr>
<td><tt>==</tt></td>
<td><tt>!=</tt></td>
<td><tt>&lt;=</tt> or <tt>&lt;</tt><br/>
    <tt>&gt;=</tt> or <tt>&gt;</tt></td>
<td><tt>x in (1, 2)</tt></td>
<td><tt>x is None<br/>
        x is not None</tt></td>
</tr><tr style="font-size:smaller;">
<td>equals</td>
<td>not equals</td>
<td>less or<br/>equal, etc.</td>
<td>works for sets,<br/>
           lists, tuples,<br/>
           dictionary keys,<br/>
           strings</td>
<td>just for <tt>None</tt></td>
</tr></table>

### If statement

The `if` statement checks whether the condition after `if` is true.
Note the placement of colons (`:`) and the indentation. These are not optional.

- If it is, it does the thing below it.
- Otherwise it goes to the next comparison.
- You do not need any `elif` or `else` statements if you only
  want to do something if your test condition is true.

Advanced users, there is no switch statement in Python.


```python
# Standard if / then / else statement.
#
# Go ahead and change `i`
i = 1

if i is None:
    print("None!")
elif i % 2 == 0:
    print("`i` is an even number!")
else:
    print("`i` is neither None nor even")
```


```python
# This format is for very short one-line if / then / else.
# It is called a `ternary` statement.
#
"Y" if i==1 else "N"
```

### While loop

The `while` loop requires you to set up something first. Then it
tests whether the statement after the `while` is true. 
Again note the colon (`:`) and the indentation.

- If the condition is true, then the body of
  the `while` loop will execute
- Otherwise it will break out of the loop and go on
  to the next code underneath the `while` block


```python
i = 0
while i < 3:
    print("i is:", i)
    i += 1

print("We exited the loop, and now i is:", i)
```

### For loop

The `for` loop iterates over the items after the `for`,
executing the body of the loop once per item.


```python
for i in range(3):
    print("in the for loop. `i` is:", i)

print()
print("outside the for loop. `i` is:", i)
```


```python
# or loop directly over a list or tuple
for element in ("one", 2, "three"):
    print("in the for loop. `element` is:", element)

print()
print("outside the for loop. `element` is:", element)
```

## Challenge for you
Please look at this code and think of what will happen, then copy it and run it. We introduce `break` and `continue`...can you tell what they do?

- When will it stop?
- What will it print out?
- What will `i` be at the end?

```python
for i in range(20):
    if i == 15:
        break
    elif i % 2 == 0:
        continue
    for j in range(5):
        print(i + j, end="...")
    print()  # newline
```


```python
# Paste it here, and run!
```

# You are done, welcome to Python!

## ... and you rock!

### Now join (or start!) a friendly PyLadies group near you ...

[PyLadies locations][locations]
[locations]: http://www.pyladies.com/locations/

<div style="font-size:80%;color:#333333;text-align:center;">
<h4>Psst...contribute to this repo!</h4>

<span style="font-size:70%;">
Here is the 
<a href="https://github.com/jupyter/docker-demo-images">
link to the github repo that hosts these
</a>.
Make them better!
</span>
</div>
