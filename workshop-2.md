---
layout: page
title: "Workshop 2"
use_math: true
--- 
# Introduction to Python programming -2- 
 
By the end of this workshop you should be able to:

* use complex numbers, boolean variables, strings and lists in the creation of
short programs
* iterate through the items of a list using the **for** loop 
 
## Let's get started 
 
Following the same procedure seen in Workshop 1, start the Jupyter notebook,
navigate to the Desktop folder and create a new notebook. Name the new notebook
*Workshop 2*.

Let's also import all the libraries needed by typing and executing the code in
the following cell. 

**In [1]:**

{% highlight python %}
%pylab inline
from matplotlib import *
{% endhighlight %}

    Populating the interactive namespace from numpy and matplotlib
    
 
## More about variables 
 
### Complex numbers 
 
During [Workshop 1](workshop-1) we introduced numerical variables of **integer** and
**floating point** types.

In Python we can also use **complex numbers**. A complex number variable can be
defined using the form shown for variable **a** in the cell below.
The imaginary unit, which is the square root of -1, is represented by the letter
**j**. This differs from what you may have seen in maths, where usually the
imaginary unit is represented by the letter **i**. Python follows the
engineering (especially electrical and electronic engineering) and physics
notation, where the letter **i** has been historically used for other
quantities, such as the intesity of electrical current.

Define the variable **a** and print it value and its type to screen, by typing
the code shown below in the next empty cell, and running the code. 

**In [2]:**

{% highlight python %}
a = 3 + 2j  
print a
print type(a)
{% endhighlight %}

    (3+2j)
    <type 'complex'>
    
 
Once the complex variable **a** has been defined, we can also access its *real*
and its *imaginary* parts separately. For example, print the real and imaginary
part of **a** to screen by typing and running the code shown below. 

**In [3]:**

{% highlight python %}
print a.real
print a.imag
{% endhighlight %}

    3.0
    2.0
    
 
Alternatively we can define the real and imaginary part of the complex number as
two separate variables, and then use these to define the complex variable 

**In [4]:**

{% highlight python %}
b = 4.1
c = 3.4
d = complex(b,c)
print d
{% endhighlight %}

    (4.1+3.4j)
    
 
We can add, multiply and divide complex number. We can also carry out basic
arithmetic between complex numbers and integer or real numbers. Carry out the
operations:

    a + d
    a * d
    a / d
    3 * a

and output the results to screen. 

**In [5]:**

{% highlight python %}
print a + d
print 3 * a
print a / d
print a * d
{% endhighlight %}

    (7.1+5.4j)
    (9+6j)
    (0.673246387029-0.0704970038773j)
    (5.5+18.4j)
    
 
The absolute value of a complex number is defined as
$\sqrt{\mathrm{real}^2+\mathrm{imag}^2}$, where **real** and **imag** represent
the real and imaginary part of the complex number. In Python, the absolute value
of a complex number can be evaluated with the:

    abs()

function.
Evaluate the absolute value of **a** with the code shown below. 

**In [6]:**

{% highlight python %}
print abs(a)
{% endhighlight %}

    3.60555127546
    
 
In Python, the **math** module deals with mathematical functions for real
numbers, while **cmath** deals with the same mathematical functions for complex
numbers. The functions in the *math* module always return a real number, while
those in *cmath* always return complex results.

In the first cell of this notebook, when we initialised the matplotlib module,
we also loaded the NumPy module, and this makes our life much easier. We do not
have to choose whether to use the real or complex version of a mathematical
function: NumPy will make that choice for us, depending on the data type of the
argument of the mathematical function. 

**In [7]:**

{% highlight python %}
print sin(pi/2)
print sin(a)
{% endhighlight %}

    1.0
    (0.530921086249-3.59056458999j)
    
 
### Booleans 
 
**Boolean** variables that can be either True or False. 

**In [8]:**

{% highlight python %}
b1 = True
b2 = False
print b1
print type(b1)
{% endhighlight %}

    True
    <type 'bool'>
    
 
While this type of variable may not seem particularly useful right now, in
programming we need a way to control the flow of the program, to allow a program
to react differently to different situations. To do this in Python, we use a
combination of boolean variables, which evaluate to either True or False, and
certain statements (we'll see these later on), that control the flow of the
program depending on boolean values. 
 
### Strings 
 
Strings are another type of variable; strings are lists of printable characters,
and can be defined using either single or double quotes. Define the following
string variables and print their value and their type to screen, as shown below. 

**In [9]:**

{% highlight python %}
a_string = 'This is a string'
another_string = "and this is another string"
print a_string
print another_string
print type(a_string)
{% endhighlight %}

    This is a string
    and this is another string
    <type 'str'>
    
 
We can concatenate (join) strings with the **+** operator. The following code
will generate a new string made up by the two string variables we defined
earlier, and it will assign this new string to a new variable.


Note that we manually have to add the space between the strings to separate them
and we can do this by adding the string **" "** (a space enclosed by quotation
marks) between the other 2 strings. 

**In [10]:**

{% highlight python %}
yet_another_string = a_string + " " + another_string
print yet_another_string
{% endhighlight %}

    This is a string and this is another string
    
 
We can replace a substring in a string with something else using the
**replace(s1, s2)** method, where **s1** is the string that we want to replace
and **s2** is the string we want to replace **s1** with. 

**In [11]:**

{% highlight python %}
str1 = "Hello, everyone!"
print str1
str2 = str1.replace("Hello", "Hi")
print str2
{% endhighlight %}

    Hello, everyone!
    Hi, everyone!
    
 
We can find the length of a string with the **len** operator.

The length of a string is the number of its characters. 

**In [12]:**

{% highlight python %}
print len(str1)
{% endhighlight %}

    16
    
 
We can denote the position of a character in a string with a positive number (or
index), counting from the beginning of the string and **starting at 0**; the
first character in a string is identified by:

    s[0]


where **s** is the name of the string variable. Similarly we could identify the
second character with **[1]**, the third with **[2]** and so on.
Print to screen the first character of the string **str1** that we defined
earlier. 

**In [13]:**

{% highlight python %}
print str1[0]
{% endhighlight %}

    H
    
 
We have 2 ways to identify the last character in a generic string **s**: we
could either use **[len(s)-1]** or the short-hand version **[-1]**.

Print to screen the last character of **str1**. 

**In [14]:**

{% highlight python %}
print str1[len(str1)-1]
print str1[-1]
{% endhighlight %}

    !
    !
    
 
Python allows us to carry out many complex operations on strings. One of the
most useful one is the **slice** opertion: we can slice a string into a
substring by defining the index of the first character that we want and the
index of the first character we do not want.
For example we can define a new string variable **s1** and assign to this
variable the value **"Hello"**, that we can obtaining by slicing the correct
part of the string **str1** that we defined earlier.
Use the following code to accomplish this: 

**In [15]:**

{% highlight python %}
s1 = str1[0:5]
print s1
{% endhighlight %}

    Hello
    
 
### Lists 
 
Lists are very similar to strings, except that each element is not limited to a
single character, but can be of any of the data types that we previously
defined.
In the following code we define a list variable **days_of_the_week**. The
elements of the lists are enclosed in square brackets and separated by commas.
Type the following code in your notebook and run it. 

**In [16]:**

{% highlight python %}
days_of_the_week = ["Sunday","Monday","Tuesday","Wednesday","Thursday","Friday","Saturday"]
print days_of_the_week
print type(days_of_the_week)
{% endhighlight %}

    ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday']
    <type 'list'>
    
 
The following code defines another list **l**, which contains only numerical
elements. 

**In [17]:**

{% highlight python %}
l = [0, 1, 2, 3, 4, 5]
print l
{% endhighlight %}

    [0, 1, 2, 3, 4, 5]
    
 
Lists do not have to be homogeneous: they can contain elements of different
types.
Type and run the following code. 

**In [18]:**

{% highlight python %}
l1 = [1, 'a', 1.0, 1-1j]
print l1
{% endhighlight %}

    [1, 'a', 1.0, (1-1j)]
    
 
Some of the operations we can carry out on lists are identical to those we have
seen previously for strings. For example, we can concatenate lists, using the
**+** operator, as with strings.
Run the following code, which will join the two lists we created earlier and
assign the joined list to a new list variable **l2** 

**In [19]:**

{% highlight python %}
l2 = l + l1
print l2
{% endhighlight %}

    [0, 1, 2, 3, 4, 5, 1, 'a', 1.0, (1-1j)]
    
 
The way we access list's elements is also identical to what we have seen in the
case of strings. We can use indexing and slicing exactly in the same way.

Type and run the following code and check that it behaves as you would expect. 

**In [20]:**

{% highlight python %}
print l[0]
print l[-1]
print l[1:4]
{% endhighlight %}

    0
    5
    [1, 2, 3]
    
 
An empty list can be defined as **[]** (square brackets without elements).

We can add elements to a list with the **append** or **insert** methods.
**append** adds an element to the end of the list. **insert** add an element at
a given position, as identified by an index.

Let's create an empty list. Then we populate by appending the names of some
programming languages (as strings). Finally, we insert a new element in the 3rd
position of the list. 

**In [21]:**

{% highlight python %}
languages = []
print languages
languages.append("C")
languages.append("C++")
languages.append("Python")
print languages
languages.insert(2,"Java")
print languages
{% endhighlight %}

    []
    ['C', 'C++', 'Python']
    ['C', 'C++', 'Java', 'Python']
    
 
Using programming to solve scientific problems we'll often need to generate
large lists of numerical values. This could quickly become a very tedious typing
exercise, if we were to manually hard-code such long lists in our programs.
Luckily we can use **range(n)**, which is a convenient way to make sequential
lists of whole numbers from 0 to n-1.

Try the following code out: 

**In [22]:**

{% highlight python %}
list_of_numbers =  range(10)
print list_of_numbers
{% endhighlight %}

    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    
 
We can also specify the starting point of the list with **range(start,stop)**

Type and execute the following example: 

**In [23]:**

{% highlight python %}
list_of_numbers = range(1,6)
print list_of_numbers
{% endhighlight %}

    [1, 2, 3, 4, 5]
    
 
The lists created above with **range** have a step of 1 between elements. We can
also specify a different step-size via a third argument **range(start, stop,
step)**

Test this with the following example: 

**In [24]:**

{% highlight python %}
even_numbers = range(0, 20, 2)
print even_numbers
{% endhighlight %}

    [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]
    
 
Here's one more useful thing we can do with strings and lists: we can split
strings into substrings and the result of the operation is a list of substrings.
The method used to achieve this is **split()**. If no argument is specified,
then the string will be split every time a space character is found.
Alternatively we can specify which character should be used as delimiter. This
operation is particularly useful when we read data from a text file, as we will
show in a later workshop.

Test this out with the following code. 

**In [25]:**

{% highlight python %}
s = "Hi, this is a string."
l1 = s.split()
l2 = s.split(",")
print l1
print l2
{% endhighlight %}

    ['Hi,', 'this', 'is', 'a', 'string.']
    ['Hi', ' this is a string.']
    
 
### Other data types
There are other variable types in Python, such as tuples and dictionaries, as
well as more advanced and complex data types, but we won't be using them in this
module. If you want to find out more about Python and all the other available
data types, please check out the recommended e-books. 
 
## Iteration 
 
One of the most useful things you can do with lists is to iterate through them,
i.e. to go through each element one at a time. To do this in Python, we use the
**for** loop: 

**In [26]:**

{% highlight python %}
for day in days_of_the_week:
    print day
{% endhighlight %}

    Sunday
    Monday
    Tuesday
    Wednesday
    Thursday
    Friday
    Saturday
    
 
This code goes through each element of the list called **days_of_the_week** and
assigns it to the variable **day**. It then executes everything in the indented
block (in this case only one line of code, the **print** statement). When the
program has gone through every element of the list, it exits the block.

Every programming language defines blocks of code in some way. In C, C++, C# and
Java, one uses curly braces {} to define these blocks.

Python uses a colon (":"), followed by indentation level to define code blocks.
This mean that whitespace is significant in Python. In  the first example the
**print** statement is indented 4 whitespaces to the right. Everything at a
higher level of indentation is taken to be in the same block. In the above
example the block was only a single line, but we could have had longer blocks as
well. Type and run the following example, which contains two statements inside
the **for** loop block: 

**In [27]:**

{% highlight python %}
for day in days_of_the_week:
    sentence = "Today is " + day
    print sentence
{% endhighlight %}

    Today is Sunday
    Today is Monday
    Today is Tuesday
    Today is Wednesday
    Today is Thursday
    Today is Friday
    Today is Saturday
    
 
Now try the following code. Can you work out why the output is different? 

**In [28]:**

{% highlight python %}
for day in days_of_the_week:
    sentence = "Today is " + day
print sentence
{% endhighlight %}

    Today is Saturday
    
 
The output is different because in the second example the **print** statement is
executed only once, since it's not part of the **for** loop block, as shown by
the indentation. 
 
We can also iterate character by character through a string.
Run the following example: 

**In [29]:**

{% highlight python %}
for character in "Introduction to Python":
    print character
{% endhighlight %}

    I
    n
    t
    r
    o
    d
    u
    c
    t
    i
    o
    n
     
    t
    o
     
    P
    y
    t
    h
    o
    n
    
 
We can also iterate through a list of numbers. Type and code the following
example. 

**In [30]:**

{% highlight python %}
for i in range(20):
    print "The square of " + str(i) + " is " + str(i**2)
{% endhighlight %}

    The square of 0 is 0
    The square of 1 is 1
    The square of 2 is 4
    The square of 3 is 9
    The square of 4 is 16
    The square of 5 is 25
    The square of 6 is 36
    The square of 7 is 49
    The square of 8 is 64
    The square of 9 is 81
    The square of 10 is 100
    The square of 11 is 121
    The square of 12 is 144
    The square of 13 is 169
    The square of 14 is 196
    The square of 15 is 225
    The square of 16 is 256
    The square of 17 is 289
    The square of 18 is 324
    The square of 19 is 361
    
 
Note that in order to join **i** and **i\*\*2** to the rest of the string we had
to convert them from integer to string type (this operation is called
**casting**). This is done with the **str()** operator.

An attempt to concatenate the integer values without prior conversion would
result in an error.

There are other ways to obtain the same output without explicitly casting the
integers to strings. One such way is shown in the following example. Type the
code and run it. You'll see that the output is identical to that of the previous
example. 

**In [31]:**

{% highlight python %}
for i in range(20):
    print "The square of %s is %s"  %(i, i**2) 
{% endhighlight %}

    The square of 0 is 0
    The square of 1 is 1
    The square of 2 is 4
    The square of 3 is 9
    The square of 4 is 16
    The square of 5 is 25
    The square of 6 is 36
    The square of 7 is 49
    The square of 8 is 64
    The square of 9 is 81
    The square of 10 is 100
    The square of 11 is 121
    The square of 12 is 144
    The square of 13 is 169
    The square of 14 is 196
    The square of 15 is 225
    The square of 16 is 256
    The square of 17 is 289
    The square of 18 is 324
    The square of 19 is 361
    
 
## Applications 
 
1) Given a list **x=[-10, -9, -8, -7, -6, -5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5,
6, 7, 8, 9, 10]**, use a **for** loop to create a new list y that contains the
value

$a \sin(10 a)$
for each value **a** in the list **x**.

then plot the results using **plot(x,y)** (we'll explain this in more details
later in the course). 
 
2) Given the list **days_of_the_week =
["Sunday","Monday","Tuesday","Wednesday","Thursday","Friday","Saturday"]**, use
a slicing operation to prepare a new list containing only workdays.

Then loop through each element of the workdays list and print the name of each
workday. 
 
3) The Fibonacci sequence is a sequence that starts with 0 and 1, and then each
successive entry is the sum of the previous two. Therefore, the sequence goes
0,1,1,2,3,5,8,13,21,34,55,89,...

Starting from the list **sequence = [0,1]**, compute and print the Fibonacci
sequence up to 89. Hint: use a **for** loop. 
