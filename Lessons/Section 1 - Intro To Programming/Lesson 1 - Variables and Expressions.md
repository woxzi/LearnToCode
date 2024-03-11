---
tags:
  - Lesson
---
## Getting Started

#### Create a new project
1. Launch Visual Studio
2. On the screen that pops up when you boot the application, click 'Create a new project'
3. Select 'Console App' and make sure it has 'C#' in the tags on the bottom
4. Click 'Next' and name it whatever you want
5. If you have the option, select .NET 6.0 LTS as the target framework

## Useful Functions

There are two functions that are globally available which are typically used when writing applications. 

```csharp
Console.WriteLine(someVariable)
```
This line will print text to the console window based on that value of whatever variable you pass in. In this case, I am passing in a variable `someVariable`

```csharp
Console.ReadLine()
```
This statement will pause the program and wait for user input. Once the user has entered data, the string that the user entered will be returned as a string.

## Variables

Variables are a feature of C# that allow programmers to store data in the computer's temporary memory. You will need to understand how to utilize [[Variables]] and their various [[Data Types|types]] in order to complete the questions below.

## Basic Structure of Code

- All expressions must end with a semicolon (a `;` character)
- A value is *returned* whenever it is the result of a statement (a section of code)
	- Return values replace the statement that produced them
- Everything written in a line after a `//` statement will be considered a comment. Comments will not affect code in any way.
	- Block comments can be written between `/*` and `*/`. These comments can

```csharp
// This is a comment. it won't affect your code at all

/*
* This is a block comment.
* You can write as many lines in this comment as you want.
* They will not affect your code in any way.
*/

var input = Console.ReadLine(); // user inputs 'potato' here
Console.WriteLine(input);

// the above runs like the below:

var input = "potato";
Console.WriteLine(input);
//> potato
```

### Questions

```csharp
// Q1
// Write the code necessary to print out the phrase 'Hello World!'

// Q2
// Determine what the below block of code will print without executing it.
int x = 3;
double y = -7;
int z = -1;

var q2 = x + z * -y % 5;

Console.WriteLine(q2);

// Q3
// Create a variable named 'q3' and store the result of a / b in the variable.
// Make sure to check that a / b is mathematically correct. 
int a = 4;
int b = 3;

// Q4
// Ask the user for a phrase, then attach the word 'potato' to the end of it. 
// Print out the result.
```