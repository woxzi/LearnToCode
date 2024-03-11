---
tags: 
aliases:
  - variable
---
[[Variables]] are a feature of C# that allow programmers to store data in the computer's temporary memory. 

### Data Types

Each variable stores data in different ways depending on the [[Data Types|type]] of the variable. There are many data types available in C# which may be used.

### Variable Definitions
To define a new variable, you simply write the [[Data Types|type]] and name of the variable, like in the below example:
```csharp
// this line follows the below format:
// type name;
int x; 
// in this line, the type of the variable is 'int' and the name of the variable is 'x'.
// you can name your variable anything you like, as long as the 
// name does not already exist in the scope you defined it in.
```

When defining a new variable, you can also assign a value to the variable like below:
```csharp
int x = 3; // in this line, we are declaring a new variable x, and giving it an initial
```

##### Terminology

- ***Variable Definition*** - Ex: `int x;` 
	- Defining a variable creates a new variable in the scope that you define it in.
	
- ***Variable Initialization*** - Ex: `x = 3;`
	- Initializing a variable sets its value for the first time. If a value has not been set, it is considered uninitialized.

 You can use the `var` keyword instead of a type whenever you're creating a new variable *and assigning a value*. This keyword will tell the compiler to infer the type of your variable from the type of value you're assigning to it.

### Variable Assignment

The primary usage of variables is to store and retrieve data. In the code block below, we are storing the value `3` into the line. When we use `myVariable` in the `Console.WriteLine` statement, it accesses the value stored in myVariable and passes that value into the `Console.WriteLine` function.

```csharp
var myVariable;
myVariable = 3;
Console.WriteLine(myVariable);
//> 3
```

When assigning a value, you must use the assignment operator `=`, which takes the value to the right of the operator and stores the value in the variable to the left of the operator.

```csharp
int x = 3;
int y = 2;

x = y; // this operator assigns the left side to the value of the right side

Console.WriteLine(x);
//> 2
Console.WriteLine(y);
//> 2
```