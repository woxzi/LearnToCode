---
aliases:
  - loop
  - loops
  - code block
  - code blocks
  - control flow structure
---

## Overview

Control flow structures are structures that modify the order in which lines are executed in a program. These are typically used to make branching, decision-making logic when writing code. 

There are three types of control flow structures in C#: **If Statements**, **Switch Case Statements** and **Loops**.

## If Statements

[[If Statements]] are control flow structures that perform logic conditionally based on a [[Booleans|boolean]] value provided to them. If statements will only execute the [[Control Flow Structures#^CodeBlocks|code block]] in their body if the condition provided to it evaluates to **true**.

## Switch Case Statements
[[Switch Case Statements|Switch Case Statements]] are control flow structures that are used to quickly define cases for when a variable is equal to specified discrete values.

## Loops

Loops are control flow structures that allow programs to execute the same [[Control Flow Structures#^CodeBlocks|code block]] repeatedly. There are three types of basic loops: [[For Loop|for]], [[While Loop|while]], and [[Do-While Loop|do-while]]. Each of these loops changes the control flow differently, so it's important know the order in which expressions are executed in each type of loop.

#### Special Keywords for Loops

There are two keywords that can be used inside of loops: `break` and `continue`. 

`break` - When a break statement is encountered (and is not a part of a [[Switch Case Statements|switch case]]), the innermost loop that the current line is inside of will be considered finished. This will immediately end the current iteration of the loop, and not attempt to execute any future loop iterations.

`continue` - When a continue statement is encountered, the innermost loop that the current line is inside of will end its current iteration. The the loop will then immediately attempt to begin another iteration of its containing code if possible.

```csharp
var x = 5;

for (int i = 0; i < x; i++) {
	Console.WriteLine("Running iteration: " + i);
	
	// if i is an odd number, this below section will end the loop
	if (i % 2 == 1) {
		break;
	} 
}
// The above loop will print out the below:
//> Running iteration: 0
//> Running iteration: 1

for (int i = 0; i < x; i++) {
	// if i is an odd number, this below section skip the current iteration
	if (i % 2 == 1) {
		continue;
	} 
	Console.WriteLine("Running iteration: " + i);
}
// The above loop will print out the below:
//> Running iteration: 0
//> Running iteration: 2
//> Running iteration: 4

```

## Code Blocks
^CodeBlocks

Whenever a structure uses curly braces (`{` and `}` ) to describe a block of code, that code can be considered a **Code Block**. These blocks aren't necessary to create a structure, they simply group a collection of lines into one statement.

Here is an example of using an if statement without a code block:

```csharp
var foo = true;

// there is no code block containing the body of this if statement, but it still works
if (foo)
	Console.WriteLine("Hello World!");

// there is a code block surrounding the body of this if statement
if (foo) {
	Console.WriteLine("Hello World!");
}
```

Code blocks are only necessary when you have multiple statements that you would like to execute as a part of your control flow structure. You can visualize the difference between using a code block and not using one by looking at the example below:

```csharp
bool condition = false;

Console.WriteLine("Before the if statement");
if (true) {
	Console.WriteLine("This is line 1");
	Console.WriteLine("This is line 2");
} 
Console.WriteLine("After the if statement");
// the above section would print the below lines:
//> Before the if statement
//> After the if statement

// if we remove the curly braces, we end up with a section like below:

if (true) 
	Console.WriteLine("This is line 1");
	Console.WriteLine("This is line 2");
Console.WriteLine("After the if statement");
// the above section would print the below lines:
//> Before the if statement
//> This is line 2
//> After the if statement
```

In the above example, `"This is line 2"` is printed to the console because the line `Console.WriteLine("This is line 2");` is not considered a part of the if statement. This is because the if statement only considers the code block directly in front of it, which is simply `Console.WriteLine("This is line 1");` because there are no curly braces.

## Nesting Statements

Control flow structures can be nested inside of code blocks that are a part of control flow structures. 

Here is an example of nesting [[If Statements]]:

```csharp
var potato = true;
var salad = false;

// this if statement would print "Potato Salad" only if both 
// 'potato' and 'salad' are true.
if (potato) {
	if (salad) {
		Console.WriteLine("Potato Salad");
	}
}
```


Below is an example of nesting [[For Loop|For Loops]]. The outer loop will execute the inner loop multiple times. The inner loop is comparing `j` to `i`, which will run the inner loop an increasing number of times.

```csharp
for (int i = 1; i <= 3; i++) {
	for (int j = 0; j < i; j++) {
		Console.WriteLine(j);
	}
	Console.WriteLine("Inner Loop Complete");
}
Console.WriteLine("Outer Loop Complete");

// The above block will run the inner loop multiple times, 
// resulting in the below output:
//> 0
//> Inner Loop Complete
//> 0
//> 1
//> Inner Loop Complete
//> 0
//> 1
//> 2
//> Inner Loop Complete
//> Outer Loop Complete
```