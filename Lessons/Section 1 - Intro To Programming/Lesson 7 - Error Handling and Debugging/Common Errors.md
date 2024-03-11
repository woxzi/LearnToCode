---
tags: 
aliases:
  - errors
  - syntax errors
  - runtime errors
  - logical errors
  - exception
  - exceptions
  - error
---
## Types of Errors

All errors encountered when writing code can be divided into three categories: Syntax, Runtime, and Logical errors.

### Syntax Errors

Syntax errors are occurred when writing code that is improperly structured. Things like forgetting a semicolon, mistyping a variable name, or otherwise breaking the general structure of code will result in a syntax error. These syntax errors will be shown in Visual Studio as red underlines beneath the problem section of code. Hovering over these underlines will show details about them and usually let you know what you need to do to fix them.

### Runtime Errors

Runtime errors are occurred during the execution of your code. Usually this has to do with some unexpected value or otherwise unexpected circumstance occurring within your program. These types of errors are generally referred to as *Exceptions* within most programming languages. Here are a few examples of common exception types you may encounter while writing C# code:

- `NullReferenceException` aka 'Null Pointer Exception'
	- This exception is thrown whenever we attempt to access something using a reference-type that is set to null. This is most often triggered by calling a method or field using a null object.

- `IndexOutOfRangeException`
	- This type of exception will occur whenever we try to access an index of an [[Arrays|array]] or [[Lists|list]] that is outside the normal range of indexes. For example, an array of length 3 would have locations available using the indexes 0, 1, and 2. Accessing your array at location 3 would throw an `IndexOutOfRangeException`.

- `System.DivideByZeroException`
	- Like the name implies, this exception occurs whenever our program attempts to divide by zero.

- `System.FormatException`
	- This exception is usually caused by attempting to parse an improperly formatted string. For example, attempting to parse the string `potato` as an integer would throw this kind of exception, because `potato` does not represent an integer value.

### Logical Errors

Logical errors can be encountered whenever statements are written that do not logically arrive at the intended result. This can happen for a number of reasons, but most often is the result of a careless developer writing code without arriving at a truly complete solution. To avoid this, try to consider edge cases and follow best practices when writing code.

Here are some common logical errors that can be encountered often when writing code:

- ***Off-by-one***
	- This kind of error will surface whenever index values are off by one value. This can happen often because indexes are available starting from 0, 1, 2, etc. Outside of code, people usually count starting from 1, so oftentimes logic that counts starting from 1 will be written accidentally and cause this issue.
	
- ***Forgetting to update variables, or updating the wrong one***
	- This can cause all sorts of weird behavior. Forgetting to update a variable can prevent behavior from happening later in your code, which might prove difficult to spot. Updating the wrong variable can have similar consequences, so keep an eye out for 

- ***Ignoring order of operations***
	- This can cause some statements to evaluate before others, resulting in wildly different results than the expected outcome.

Logical errors are a type of error that is very difficult for computers to infer. Because of this, they are usually not identified until an issue with the program is noticed by a user. This kind of error is the type that most commonly results in a 'bug' in the program. It's important to keep an eye out for these kinds of issues as you write code, because you usually won't be warned about them while writing them into your code.

