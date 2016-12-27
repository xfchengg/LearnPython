# Complete Python Web Course: Build 8 Python Web Apps

![Python logo](https://www.python.org/static/img/python-logo@2x.png)

## Documention
* [Guido van Rossum](https://gvanrossum.github.io/) is the founder of the Python language.
* The **E-Book** is available - <https://www.gitbook.com/book/jslvtr/complete-python-web/details>
* A good Python guide is available for reference. However some of the commands may be based on Python 2.x - <https://www.tutorialspoint.com/python/index.htm>
* This guide uses Python version 3.x.

## How to install Python on a MAC
1. **pip** - Install or update pip <https://packaging.python.org/installing/>. 
Download [pip] (https://bootstrap.pypa.io/get-pip.py)
	```
	pip install --upgrade setuptools
	```
2. **Virtual Environments** - Install virtual environments before you use Python. Else different versions may conflict with one another. <http://docs.python-guide.org/en/latest/dev/virtualenvs/> also see <https://www.youtube.com/watch?v=N5vscPTWKOk>

	```
	sudo pip install virtualenv
	sudo pip install virtualenv --upgrade
	pip list # To see all the globally installed packages.
	```
3. **Install** Python 2.x and 3.x version [here] (https://www.python.org/downloads/)

4. Create Virtual Environments for version 2.x and 3.x
	
		```
		# CHECK VERSION OF PYTHON
		which python
		
		# CREATE A FOLDER TO CONTAIN VIRTUAL ENVIRONMENTS.
		mkdir env
		cd !$ # or cd enviornments
		
		# CREATE VIRTUAL ENVIRONMENT. (DO NOT RUN THESE STEPS) 
		virtualenv ver3x # Creates a virtual enviornment. DO NOT USE. JUST FYI.
		source ver3x/bin/activate # to activate the environment. DO NOT USE. JUST FYI.
		which python # To see which environment we are in. DO NOT USE. JUST FYI.
		which pip 
		pip list # This will list the components we have installed in the virtual environment. Does not include the global packages. 
		
				
		# CREATE AN ENVIRONMENT FOR 2.x
		virtualenv -p  /Library/Frameworks/Python.framework/Versions/2.7/bin/python2.7 venv2
		which python
		# CREATE AN ENVIRONMENT FOR 3.x
		virtualenv -p  /Library/Frameworks/Python.framework/Versions/3.5/bin/python3.5 venv3
		which python
		

		# LOGIN TO A VIRTUAL ENVIRONMENT.
		source env/venv3/bin/activate
		# OR
		source env/venv2/bin/activate
		
		# OPTIONALLY WE CAN INSTALL ADDITIONAL PACKAGES.
		pip install requests
		pip install boto
		pip install botocore
		pip install boto3
		pip install pytz
		pip install numpy
		pip install psutil
		# Try pip list now. These packages are different.
		
		# TO EXPORT THE PACKAGES INSTALLED AND REUSE THEM IN FUTURE:
		pip freeze --local > requirements.txt
		cat requirements.txt
		
		# TO EXIT A VIRTUAL ENVIRONMENT
		deactivate 
		
		# DELETE A VIRTUAL ENVIRONMENT. 
		rm -rf venv2
		
		# CREATE A NEW VIRTUAL ENVIRONMENT BASED ON THE CAPTURED REQUIREMENTS.
		virtualenv -p  /Library/Frameworks/Python.framework/Versions/3.5/bin/python3.5 venv3
		source env/venv3/bin/activate
		which python
		python --version
		pip install -r requirements.txt
		pip list
		deactivate
		
		```







## Basics
1. **Method** - Is a function, which is a member of a class. E.g print() method to print. We give to the print method, by adding "text" inside the print method.
	
	In Python, a __method__ is a function that is available for a given object __because of the object's type.__
	
	For example, if you create `my_list = [1, 2, 3]`, the append method can be applied to `my_list` because it's a Python list: `my_list.append(4)`. All lists have an append method simply because they are lists.
	
	Another example, if you create `my_string = 'some lowercase text'`, the upper method can be applied to `my_string` simply because it's a Python string: `my_string.upper()`.
	
	Lists don't have an `upper` method, and strings don't have an `append` method. Why? Because methods only exist for a particular object if they have been __explicitly defined for that type of object__, and Python's developers have (so far) decided that those particular methods are not needed for those particular objects.
	
	To call a method, the format is `object_name.method_name()`, and any arguments to the method are listed within the parentheses. The method implicitly acts on the object being named, and thus some methods don't have any stated arguments since __the object itself__ is the only necessary argument. For example, `my_string.upper()` doesn't have any listed arguments because the only required argument is the object itself, `my_string`.
	
	One common point of confusion regards the following:
	
	```
	import math
	math.sqrt(81)
	```
	
	Is sqrt a method of the `math` object? __No__. This is how you call the sqrt function from the math module. The format being used is `module_name.function_name()`, instead of `object_name.method_name()`. In general, the only way to distinguish between the two formats (visually) is to look in the rest of the code and see if the part __before the period__ (`math, my_list, my_string`) is defined as an object or a module.

2. **Interactive Python Development Environment (IDLE)** - Is the Python shell.

## PyCharm
1. Download **PyCharm IDE** from [**JetBrains**] (http://www.jetbrains.com/). The community edition should be suffient.
2. To change the **interpreter** (2.x, 3.x or virtual environment), Go to **PyCharm > Preferences > Project:xxxxxx > Project Interpreter** and then change the interpreter version at any point. 
3. To add **author** information. Settings (or Default Settings) >> Editor >> File and Code Templates >> File type (e.g.: Python Script). Read [here](http://stackoverflow.com/questions/14416887/how-to-change-the-author-variable-in-pycharm)
4. **Projects** Start by creating **File > New Project ... (Give your project a name. Right click the project) > New > Python Package. > (Give it a name src)** Now you can create all the python and related files inside this folder. E.G Create a **data.json** file inside the src folder that contains meta data information that could be referred by the code.
5. **Reformat Code** - Highlight code and then from the menu bar select **Code > Reformat Code**. This will take care of the indentation.



## JSON
- The main advantage of JSON is that it is RESTful and light weight.
- **Dictionary** - Always starts and ends with **{ }**. Contains key value pairs.
- **""** are used to describe key and again "" to describe values. One key can have only one value and not more.
- **Lists** - Can be defined using [ ]. May contain values or key values.
- The demo code contains several v.json files with samples.
- **XML** is also similar.





## Python Variable Types
Read more about **variables** [here](https://www.tutorialspoint.com/python/python_variable_types.htm)


```
counter = 100          # An integer assignment
miles   = 1000.0       # A floating point
name    = "Rohan"      # A string
```
We could run a simple calculation as follows:

```
a=2
b=3
print(a+b)
```
> 5

However if we did somethign like this:

```
a=2
b="3"   # notice the double quotes. We could also use '3'
print(a+b)
```
> TypeError: unsupported operand type(s) for +: 'int' and 'str'

This is because b is a string here. We could do something like this.


```
print("a" + "b")
```
> ab

Next example

`a, b, c = 1, 2, "john"`

`a`
> 1

`b`
> 2

`c`
> 'john'


## Argument

- You can use `#` to argument a line.
- You can also use ` """ some text """ ` to argument a line.


## Print

```
print(5)
print ('This is my office')
OR
print ("This is my office")
```
> 5
> 
> This is my office

**IMPORTANT** - Print can only print string values. Any other types such as int, float etc would have to be either converted into str or formated before printing.



## str()
Converts a non string value to a string.

```
x = 10
print ("The value of x is " + "x" )
```
> The value of x is x

But if we do

```
x = 10
print ("The value of x is " +  str(x) )
```
> The value of x is 10

## int()
Converts a string into an integer.

```
y = "100"
z = y + 50
```
> TypeError: Can't convert 'int' object to str implicitly

Instead if we do

```
y = "100"
z = int(y) + 50
print ("The value of integer y + 50 is " + str(z))
```
> The value of integer y + 50 is 150

## format()
Works like a place holder when printing. Helps us replace {} with values without having to format them first before printing.


```
age = 12
print ("I am " + age + " years old.")
```
> TypeError: Can't convert 'int' object to str implicitly

Instead we have to do this

```
age = 12
print ("I am " + str(age) + " years old.")
```
This is a hassle to each time mention str every time. It would be easier to instead use format as follows.

```
age = 12
print ("I am {} years old.".format(age))
```
> I am 32 years old.

We can instead do the following

```
age = 12
print ("I am {} years, {} month\s and {} days old.".format(age, 1, 10))
```
> I am 32 years, 1 month\s and 10 days old.


And also the following

```
age = 12
print ("I am {age} old. Are you {age} years old too?".format(age=age))
```
> I am 12 old. Are you 12 years old too?

**IMPORTANT** -  The first age in the format method is the placeholder and the second age is the value of the age variable. The programmer have to help with the intelligence.

Some more examples are listed here

```
>>> my_string="Hello, my name is {}"
>>> my_string.format("Karthik")

>>> name="Chandy"
>>> my_string.format(name)
>>> print(my_string.format(name))

```

> 'Hello, my name is Karthik'
> 
> 'Hello, my name is Chandy'
> 
> Hello, my name is Chandy


```
>>> my_string="Hey {} can you read the number {}?"
>>> my_string.format("Karthik",54)

```
> 'Hey Karthik can you read the number 56?'

In the below example we can give each placeholder a name, for more readability.

```
>>> s="Hello, my name is {name} and I am {age} years old.”
>>> s.format(name="Chandy", age=32)
>>> # OR
>>> s.format(age=32,name="Chandy")
```
> 'Hello, my name is Chandy and I am 32 years old.'


In the below example, we can use format to also restrict decimal points.

```
>>> student_grade=19.2/25
>>> s="Tom scored {grade} in the test."
>>> s.format(grade=student_grade)
>>> 
>>> s="Tom scored {grade:.2%} in the test."
>>> s.format(grade=student_grade)
```
> 'Tom scored 0.768 in the test.'
> 
> 'Tom scored 76.80% in the test.'

Last example

```
item_name = 'Chair'
item_price = 169.99
item_details="Item name: {item_name}, price: {item_price}".format(item_name, item_price)
```
> KeyError: 'item_name'

This is because it does not understand what value needs to be assigned to item_name and item_price.

We we have to therefore do the following.

```
item_name = 'Chair'
item_price = 169.99
item_details="Item name: {item_name}, price: {item_price}".format(item_name=item_name, item_price=item_price)
```
> 'Item name: Chair, price: 169.99'

More format() examples can be found [here](https://docs.python.org/2/library/string.html#format-examples)


## input()
Receive input values from the user.

```
>>> input("What is your name: ")
What is your name: Karthik Chandy
'Karthik Chandy'
```

Input values can be assiged to a variable.

```
>>> age = input("What is your age: ")
What is your age: 32
>>> print("Your age is : " + age)
Your age is : 32
```

**IMPORTANT** Input values are always in a string format. This is similar to the print() method. Therefore if you need to perform a matematical operation on a input value, first convert the string to an integer and then perfrom a matematical operation.

```
>>> age = input("What is your age: ")
What is your age: 32
>>> print("Your age in ten years would be : " + str(int(age) + 10))
Your age in ten years would be : 42
>>> seconds = int(age) * 365 * 24 * 60 * 60
>>> print("Your age is seconds is {}".format(seconds))
Your age is seconds is 1040688000
>>> print("Your age is {} seconds.".format(int(age)*365*24*60*60))
Your age is 1040688000 seconds.
```

## def()
- Helps define a new **function\method**. The defined method can be invoked multiple times when needed.
- Similar to a built-in function like print()
- More information can be found [here](https://www.tutorialspoint.com/python/python_functions.htm)
- **Scope of variables** - Anyting defined inside the funciton is a local variable. Global variables are accessible inside the function too.
- Any values defined or calculated within a function are not available out of the function. If you need access to a variable\value defined in the function, specify what values should be available using the **return** option at the end of the function.


```
>>> def age_in_seconds():
...     user_age = input("Enter your age: ")    # Important to ensure that you manually add indentation. You have to start this line, exactly under the function name.     
...     age_seconds = int(user_age) * 365 * 24 * 60 * 60 # Indentation
...     print("Your age in seconds is {}.".format(age_seconds)) # Indentation
...     return age_seconds # The return parameter is important as values defined within the function would not be available out of the function. Return gives us the option to specify what values should be passed on to the caller.
...  	# You have to type enter twice to exit your function definition.
>>> 
>>> 
>>> age_in_seconds() # Invoking your function.
Enter your age: 32
Your age in seconds is 1009152000.
>>>
```


## If...Elif...Else Statements

**Syntax**

```
if expression1:
   statement(s)
elif expression2:
   statement(s)
elif expression3:
   statement(s)
else:
   statement(s)
```

Imagine you wanted to buy a chair only if the price is less than $100. 
Create a simple function as follows.

```
def buy_or_not():
    price = int(input("Enter the price of a chair you like: "))
    if price < 100:
        print("Buy the chair!")
    else:
        print("The chair is expensive. Do not buy the chair.")
```
Invoke the function as follows.

> ` >>> buy_or_not()`

> Enter the price of a chair you like: 566

> The chair is expensive. Do not buy the chair.


But what do we do if the price is 100 ?
We could try this.

```
def buy_or_not():
    price = int(input("Enter the price of a chair you like: "))
    if price < 100:
        print("Buy the chair!")
    elif price == 100: # Single = assigns a value, where as == checks if left and right are equal.
        print("Buy the chair!")
    else:
        print("The chair is expensive. Do not buy the chair.")
```

> ` >>> buy_or_not()`

> Enter the price of a chair you like: 100

> Buy the chair!




















## Ctrl + L
Clears the screen in Python.


## quit()
`quit()`

Quits the Python console.

## Exercises
1. **Creating methods and functions**


	```
		# Create a function, user_name(), that returns the name of a person: "Rolf"
	def user_name():
	    name="Rolf"
	    return name
	
	# Using your user_name function create another function, greeting(), that
	# takes a name as an argument and returns a greeting phrase:
	# "Hello, NAME, how are you?"
	def greeting(name):
	    name=user_name() # Can be optionally commented based on what the requirement is.
	    return "Hello," + name + ", how are you?"
	
	# Finally, create a function, divisible(), that will take two numbers and return whether
	# the first argument is divisible by the second argument
	# For example, a number is divisible by 2 when the remainder is 0
	# For example, 2, 4, 10, 256
	# The modulus operator, %, might be handy! Do some research online if necessary.
	def divisible(value1, value2):
	    value1=int(value1)
	    value2=int(value2)
	    if value1 % value2 == 0:
	        # print("{} is divisible by {}".format(value1, value2))
	        return "TRUE"
	    else:
	        # print("{} is not divisible by {}".format(value1, value2))
	        return "FALSE"	
	```
	**Output Below**
	
	> user_name()
	> 
	>'Rolf'
	
	> greeting("Karthik Chandy")
	>
	> 'Hello,Karthik Chandy, how are you?'
	
	
	> divisible(15,10)
	> 
	> 'FALSE'
	> 
	> divisible(20,10)
	> 
	> 'TRUE'

2. **If statements**

	```
	# The method must ask the user for a number, and then return print "It's even" if the number is even, or "It's odd" otherwise.
	def divisible(num1, num2):
		return num1 % num2 == 0 # Is the mod value equal to 0. Would only be true if even.

	def user_even():
		# Ask the user for a number.
		num1 = int(input("Enter a number: "))
		# Print "It's even" if the number is even, or "It's odd" otherwise.
		answer = divisible(num1,2)
		if answer == False:
		   print ("It's odd")
		elif answer == True:
		   print("It's even")
	
	```
	> ` >>> user_even()

	> Enter a number: 565

	> It's odd
	
	> ` >>> user_even()

	> Enter a number: 346

	> It's even
 
	
3. **Random number test**

	```
# Generate a random number between 1 and 10, called the maagic_number.
# Ask the user to enter a number between 1 and 10.
# If the user entered number matches the magic_number, inform them "You won." If the user number does not match the magic number ask them to try again.
# Requied to generate a random number.
def magic_test():
    import random
    magic_number = random.randint(1, 10) # Generates a random number between 1 and 10 <https://docs.python.org/2/library/random.html>
    user_number = int(input("Pick a number between 0 and 10: "))
    if user_number > 10:
        return magic_test()
    elif magic_number == user_number:
        return "You won."
    else:
        print("Try again. The magic nummer is {}".format(magic_number))
        magic_test()
	
	```
	
	