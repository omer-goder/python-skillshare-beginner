## Functions

### Function
- A function is a block of organized, reusable code that is used to perform a single, related action. 
- Functions provide better modularity for your application and a high degree of code reusing.
- syntex: `def func_name (args):`<br>
  - the function can work with 0 arguments

##### example:
```
def printme(str):
	"""This is a documentation string or 'docstring' for short"""
	print(str)
			
	str = 'Hello World'
	printme(str)
```
The output will be:
```
Hello World!
```
	
### Function Arguments
- You can call a function by using the following types of formal arguments:

1. Required arguments<br>
2. Keyword arguments<br>
3. Default arguments<br>
4. Variable-length arguments<br><br>

#### Required arguments
- Required arguments are the arguments passed to a function in correct positional order.
- Here, the number of arguments in the function call should match exactly with the function definition.

###### example:	
```
def printme( str ):
   """This prints a passed string into this function"""
   print(str)
				
   str = 'Hello World!!!'
   printme(str)
```


#### Keyword arguments
  - Keyword arguments are related to the function calls.
  - When you use keyword arguments in a function call, the caller identifies the arguments by the parameter name.
  - If the name of the parameters in the function call is the same as in writing the function, than the order does not matter
*	syntex:	`def func_name(arg1, arg2, ...):`

##### example_1:
```
def printme( str ):
	"This prints a passed string into this function"
	print(str)
	printme( str = "My string")
```
The output will be: 
```
My string
```
	
##### example_2: (Note that the order of parameters does not matter)
```
def printinfo( name, age ):
	"This prints a passed info into this function"
	print("Name: " + name)
	print("Age: " + age)

	printinfo(age=50, name="miki")
```
The output will be:
```
Name: miki
age: 50
```


#### Default arguments
  - A default argument is an argument that assumes a default value<br>
  if a value is not provided in the function call for that argument.

##### example:
```
def printinfo( name, age = 35 ):
	"This prints a passed info into this function"
	print("Name: " + name)
	print ("Age: " +  age)

	printinfo(age=50, name="miki")
	printinfo(name="miki")
```
The output will be:
```
Name: miki
Age: 50
Name: miki
Age: 35
```

#### Variable-length arguments (*args)
  - You may need to process a function for more arguments than you specified while defining the function.
  - These arguments are called variable-length arguments and are not named in the function definition,<br>
	unlike required and default arguments.
- An asterisk (*) is placed before the variable name that holds the values of all non-keyword variable arguments.
- syntex:
```
def functionname([formal_args,] *var_args_tuple ):
	"function_docstring"
	function_suite
	return [expression]
```

##### example:
```
def printinfo( arg1, *vartuple ):
	"This prints a variable passed arguments"
	print("Output is: ")
	print(arg1)
	for var in vartuple:
		print(var)
		
	printinfo(10)
	printinfo(70, 60, 50)
```
The output will be: `10`
The output will be:
```
70
60
50
```

#### Keyword variable-length arguments (**kwargs)
- The special syntax **kwargs in function definitions in python is used to pass a keyworded, variable-length argument list.
- We use the name kwargs with the double star. The reason is because the double star<br>
allows us to pass through keyword arguments (and any number of them).

- A keyword argument is where you provide a name to the variable as you pass it into the function.
- One can think of the kwargs as being a dictionary that maps each keyword to the value that we pass alongside it. 
- Once in the function, the **kwargs acts as a dictionary

example:
```
def print_kwargs(**kwargs):
	for key, value in kwargs.items():
	print(key.title() + " : " + str(value))

print_kwargs(Pi = 3.141592654, avogadro = 6.0221*10**23, string = 'Hello World!!!')
```


#### The Anonymous Functions (Lambda)
- These functions are called anonymous because they are not declared in the standard manner by using the def keyword. 
- You can use the lambda keyword to create small anonymous functions.
- Lambda forms can take any number of arguments but return just one value in the form of an expression. 
- They cannot contain commands or multiple expressions.
- An anonymous function cannot be a direct call to print because lambda requires an expression

- Lambda functions have their own local namespace and cannot access variables other than those<br>
	in their parameter list and those in the global namespace.
	
- syntax:<br>syntax of lambda functions contains only a single statement, which is as follows:<br>
`lambda [arg1 [,arg2,.....argn]]:expression`

example:
```
sum = lambda num_1, num_2: num_1 + num_2
print(sum(10,5))
```
	
The output will be: `15`


The return Statement
- The statement return [expression] exits a function, optionally passing back an expression to the caller. 
- A return statement with no arguments is the same as return None (or no return at all).
- syntex: `return arg`

example:
```
def power(num1, num2):
	po = num1 ** num2
	return po
				
po = power(10,3)
print(po)
```
The output will be: `1000`


#### Global vs. Local variables
- Variables that are defined inside a function body have a local scope, and those defined outside have a global scope.
- This means that local variables can be accessed only inside the function in which they are declared,<br>
 whereas global variables can be accessed throughout the program body by all functions. 
- When you call a function, the variables declared inside it are brought into scope.
