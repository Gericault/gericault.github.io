---
layout: post
title: Introduction to Python
date: 2024-10-20 15:30:00 +0930
---
## What is Python?
Python is an interpreted language, no compiler, instead program is run through an intepreter.
Is very widely used, simple and lots of documentation and help available.

Before reading I recommend having basic programming language knowledge.

Python is simple and easier to write code in compared to low level languages, trade-off is because things like memory management are handled for you, there is a cost under the hood - this may impact performance depending on code as this code is still run when you call built-in functions.
Although in the modern age this is rarely a consideration unless programming with very limited hardware.

<a href="https://docs.python.org/3/library/functions.html">Python documentation</a>


## Variables

You do not need to declare the type of variable, Python can infer this for you.
While each variable does have a type, we do not need to explicitly state which type it is when we create the variable.

{% highlight python %}
int counter = 0;
#becomes
counter = 0
{% endhighlight %}

**Common variable types**

**bool** - A value that is either true of false
**float** - a decimal number
**int** - an integer
**str** - a string.

Long and double are automatically handled via int - Python knows what data type should be used for larger and smaller numbers.

**Python collections (Arrays)**

**list** - Ordered, changeable and allow for duplicate values.
created with square brackets
Stores any variable type, elements can be referenced by index [0] starting from 0.

{% highlight python %}
list = ["cale", "user", "admin"]
{% endhighlight %}

**tuple** - An ordered and unchangeable collection of data, allows for duplicate values.
Usually used to store just 2 or 3 values together, such as co-ordinates.
Created with round brackets.

{% highlight python %}
tuple = (12.3, 10.7)
{% endhighlight %}

**set** - unordered, unindexed and unchangeable.
Stores each value only once.
Created with curly brackets

{% highlight python %}
set = {"user", "admin"}
{% endhighlight %}

**dict** - Ordered and changeable, no duplicates.
Can be used to store data in key:value pairs.
written with curly brackets; 

{% highlight python %}
dict = {
"username": "admin"
"password": "123456"
"created": "20241013"
}
{% endhighlight %}

Dictionaries cannot have two items with the same key; duplicate values will overwrite existing values.
Dictionariy values can be of any data type, including array data types.

{% highlight python %}
dict = {
"username" : "admin"
"device_id" : ["pc_1", "mobile_phone", "laptop_3"] 
}
{% endhighlight %}
## Comments

\# (hashtag) - starts a line that contains a Python comment

{% highlight python %}
#prints approved usernames
{% endhighlight %}

Contains a comment that indicates that the purpose of the code that follows it is to print approved usernames.

""" (documentation strings)
starts and ends a multi line string that is used as a Python comment; multi line comments are used when you need more than the 79 character single line comment.

{% highlight python %}
"""
This program is designed to ask the user for input on a user name.
It then checks the approved_users data base to see if the entered name is present, 
If the name is found it returns a print statement declaring the user is valid, 
otherwise it will return an error message indicating the user has not been found in the approved list.
"""
{% endhighlight %}

A multi line function that indicates the purpose of the program.
## Conditional statements

**if** - starts a conditional statement

{% highlight python %}
if device_id != "fg314jh":
{% endhighlight %}

Starts a conditional statement that evaluates whether the device_id variable contains a value that is not equal to "fg314jh".

{% highlight python %}
if user in approved_users:
{% endhighlight %}

starts a conditional statement that evaluates if the user variable contains a value that is also found in the approved_users variable.

**elif** - Only evaluated when previous conditions evaluate to false. 

{% highlight python %}
elif status == 500:
{% endhighlight %}

when previous conditions return false, evaluates if the status variable contains a value equal to 500.

**else** - If all conditions before it return false, this condition is used instead.

{% highlight python %}
else:
{% endhighlight %}

when all previous conditions evaluate to false, Python executes the code within this else statement.

**and** - requires both conditions on either side of the operator to evaluate to true.

{% highlight python %}
if username == "cale" and login attempts < 5:
{% endhighlight %}

Returns true if the value in username is equal to "cale" and the value of login attempts is less than 5.

**or** - requires only one of the conditions on either side of the operator to be true.

{% highlight python %}
if status == 100 or status == 102:
{% endhighlight %}

Returns true and executes indented code if the value in status variable is equal to 100 or 102.

**not** - negates a condition so that it evaluates to false if the condition is true or vice-versa.

{% highlight python %}
if not account_status == "removed"
{% endhighlight %}

returns false if the value in account status is equal to "removed" and returns true if the value is not equal to removed.
## Iterative statements (Loops)

There are no do-while loops in Python, while loop is convention.

**While** - used to iterate based on a condition

{% highlight python %}
while login_attempts < 5:
{% endhighlight %}

iterates as long as the condition that the value of login_attempts is less than 5 returns True.

**For** - Used to iterate through a specified sequence.

{% highlight python %}
for username in ["cale", "admin", "user"]:
{% endhighlight %}

iterates throught the lements in the list, using the loop variable username.

{% highlight python %}
for i in range(10):
{% endhighlight %}

iterates through each number created by range(10) using the loop variable i.

**Break** - used to break out of a loop.

**Continue** - Skip a loop iteration and continue with the next one.
## User-defined functions

**def** - placed before a function name to define a function

{% highlight python %}
def main():
	bark(3)
#bark some number of times
def bark(n):
	for i in range(n):
		print("bark")
main()
{% endhighlight %}

A function abstracts away the barking.
A main function is defined at the top of the file, at the bottom the main function is called.
It is convention to create a main function in Python, but not necessary.

**return** - used to return information from a function, when executed, Python exits the function after returning the information

{% highlight python %}
def calculate(x, y):
	total = x + y
return total
{% endhighlight %}

returns the value of the total variable from the calculate function.
## Built-in functions

Python is object orientated, properties, attributes and functions are known as objects.
Functions in python can belong to a specific object, this is known as a method.
For example, strings can have built-in methods;

{% highlight python %}
s = washington.upper()
print(s)
#returns WASHINGTON
{% endhighlight %}

the value of s is overwritten with the result of .lower(), a built in method of strings.

Lots of useful functions and methods are already built-in Python and ready to use.
Below are some commonly used functions, more can be found in the documentation.

**print()** - outputs a specified object to the screen

**(f"") (formatted strings)** - by adding f before the quotation mark we indicate we are using a formatted string, this allows embedded expressions using {} (curly braces)

{% highlight python %}
print(f"Username is {input("User: ")}")
{% endhighlight %}

**type()** - returns the data type of its input

**range()** - generates a sequence of numbers

**max()** - returns the largest numeric input passed into it.

**min()** - returns the smallest numeric input passed into it.

**sorted()** - sorts the components of a iterable.

**str()** - converts the input object into a string

**len()** - returns the number of elements in an object.


Average of three numbers using a list;

{% highlight python %}
\# logins per day
logins = [6, 7, 7]
\# print the average
average = sum(logins) / len(logins)
print(f"Average: {average}")
{% endhighlight %}

The built in sum and len methods make this program simple.

## Importing modules and libraries

As projects becomes larger, it will become useful to write functions in one file and run them in another.
We can create one file called functions.py with the below

{% highlight python %}
def square(x)
	return x * x
{% endhighlight %}	

and another file called square.py with the code

**import** - searches for a module or library in a system and adds it to the local python environment.

{% highlight python %}
from functions import square
for i in range(10)
	print(f"the square of {i} is {square(i)}")
{% endhighlight %}

we could alternatively import the entire functions module and use dot notation to access the square function

{% highlight python %}
import functions
for i in range(10)
	print(f"the square of {i} is {functions.square(i)}")
{% endhighlight %}

Many in-built libraries such as math or csv are available, additionally Python has many community libraries allowing for lots of complex functionality to be abstracted away from you as you work off the shoulders of those before you.

The sys library has built in methods that are very useful in the command line.
You can print all command line arguments using the below; 

{% highlight python %}
from sys import argv

for arg in argv:
	print(arg)
{% endhighlight %}

The first argument is the name that of the file that you are running.

{% highlight python %}
from sys import argv

if len(argv) == 2:
	print(f"hello, {argv[1]}")
else:
	print("hello")
{% endhighlight %}

Print hello to the first user argument (second arg value) if it exists.

**sys.exit()** - exits the program with specified exit code.

{% highlight python %}
import sys

if len sys.argv != 2:
	print ("missing command-line argument")
	sys.exit(1)
print(f"hello, {sys.argv[1]}")
sys.exit(0)
{% endhighlight %}

Notice that methods (dot notation) are used to utilize the built in functions of sys.

## File operations

**open()** - returns a file object.
open() takes 2 parameters, filename and mode.
there are 4 modes; 
"r" - read - returns error if file does not exist
"a" - append - creates file if it does not exist
"w" - write - creates file if it does not exist
"x" - create - returns error if the file exists

files can be read as binary "b" or text "t".

default value for mode is "rt" (read, text), you do not need to specify this.

{% highlight python %}
file = open("accesslog.txt",  "r")
{% endhighlight %}

If the file is located in a different location than the python program, you will have to specify the full pathname.

**.read()** - returns the file content
**.write()** - writes the specified string to the file
**.close()** - closes the file when you are finished with it, this is best practice when you are done with the file.

Another way to handle the opening and closing of a file is to encase it inside a with condition;

{% highlight python %}
with open('access_log.txt') as logs:
	if banned_user in logs:
		# further processing goes here
{% endhighlight %}

The with statement handles closing of the file once it leaves the with block, even if there is an error.
This allows for cleaner code and makes handling of unexpected errors easier.
## Regular expressions

Regular expressions (RegEx for short) are a means to ensure that user-provided data fits a specific format.
Python has a build in library called re which can be used to work with regular expressions.

**import re** - Uses expression symbols to find patterns in strings.

**re.findall()** - returns a list containing all matches

**re.fullmatch**(pattern, string, flags) - returns object only if the whole string matches the pattern, else returns none.

**re.compile()** - compiles a pattern into a regex object; useful for effeciency when pattern matching more than once.

**Metacharacters, special sequences and sets** - A special sequence is a \ followed by a character, a set is a set of characters inside a pair of brackets \[]. Special sequences, Metacharacters and sets all have a special meaning.

### Case study: Valid email
When taking an input from a user we may want to validate an email address for a variety of reasons; this could be done simply with;

(username)@(domain name).(at least 2 letters - top level domain name)

The above can be represented as a regex in Python with the below;
```
r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$'
```
This is very cryptic, some syntax is explained below;

**r** - used to prefix a regex string where you want to ignore \ (backslash) normally used in python; this is to prevent you having to write \\\\ (four backlashes) to match a single backslash since the regex version is \\ but each backslash must be escaped with another backslash per Python's usage of the escape character.

**^** - starts with

**[A-Z]** - returns a match for any upper-case character alphabetically

**[a-z0-3]** - returns a match for any lower-case character alphabetically and numbers 0-3

**\.** - is a wildcard for any character except newline

**\+** - returns one or more occurrences

**{}** - returns the exact specified number of occurrences

**$** - ends with

*Most use-cases for regexes have already been solved by those before you, search engines and AI are your friends here.*

Let's use the above and create a simple function to check if a email is valid or not;

{% highlight python %}
import re
regex = re.compile(r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$')

def checkemail(email):
    if re.fullmatch(regex, email):
      print("Valid email")
    else:
      print("Invalid email")
{% endhighlight %}

The proposed so far while cryptic is in fact very simple, to mitigate security risks and handle a wider range of valid email addresses it is best to adhere to RFC 5322

**RFC5322** - the document that specifies the internet message format (IMF), a syntax for text messages that are sent via E-mail.

This document contains the definition of what an email should look like; when conforming to this definition you will have a regex like below;
```
(?:[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*|"(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21\x23-\x5b\x5d-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])*")@(?:(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?|\[(?:(?:(2(5[0-5]|[0-4][0-9])|1[0-9][0-9]|[1-9]?[0-9]))\.){3}(?:(2(5[0-5]|[0-4][0-9])|1[0-9][0-9]|[1-9]?[0-9])|[a-z0-9-]*[a-z0-9]:(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21-\x5a\x53-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])+)\])
```
This RFC5322 compliant regex expression is more clearly readable as a diagram


![RFC5322-compliant-regex](https://emailregex.com/wp-content/uploads/sites/2/2014/06/General-Email-Regex-Railroad-Diagram-emailregex.com_.png)
###### Taken from <a href="https://emailregex.com/wp-content/uploads/sites/2/2014/06/General-Email-Regex-Railroad-Diagram-emailregex.com_.png">https://emailregex.com/wp-content/uploads/sites/2/2014/06/General-Email-Regex-Railroad-Diagram-emailregex.com_.png</a>.

While an improvement, this is not foolproof. Email addresses can be complex and subject to various rules and standards, best practice is to consider additional factors such as MX record checks, server-side validation and DNS validation to ensure accuracy and security.

Regex has many more use-cases, consider passwords - you can create rules such as minimum length, mix of uppercase and lowercase letters.

This is far more efficient than creating a series of if-else statements or custom functions.
regex functions such as search() and split() can help determine what specific improvements a user needs to make, such as "Password not long enough".

Always remember to think of the end-user, avoid overly restrictive rules that impede their experience.
## Further reading
More information and discussion about <a href="https://emailregex.com">Email regex</a>.

Python has lots to offer, far more than can be covered here, consider free resources such as;

- *Harvard University's introduction to programming - <a href="https://cs50.harvard.edu/x/">https://cs50.harvard.edu/x/</a>*
- *W3 schools -<a href="www.w3schools.com/python">www.w3schools.com/python</a>* 
- *Python documentation - <a href="https://docs.python.org">https://docs.python.org</a>*

Need some direction? try learning about the below as a next step;

- *Classes*
- *Lambda functions*
- *Decorators*
- *String methods*
- *List, set, tuple and dict methods.*