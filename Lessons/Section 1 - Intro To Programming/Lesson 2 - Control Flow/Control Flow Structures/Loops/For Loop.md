---
aliases:
  - for
---

**For loops** are a type of loop that are typically used to iterate *a specific number of times*. 

The for loop has three parts: [[For Loop#^Initialization|initialization]], [[For Loop#^Condition|condition]], and [[For Loop#^Update|update]]. For loops are written using the below syntax:

```csharp
// expressions before the loop
for (initialization; condition; update) {
	// loop body goes here
}
// expressions after loop
```

#### Initialization
^Initialization
The initialization part of a for loop initializes or instantiates any variables necessary to perform the loop logic. This section may be left empty if desired.

The most common usage of this section is to declare an iterator variable (usually named `i` or `index`). Generally these will have a starting value of 0.

#### Condition
^Condition
The condition part of a for loop does exactly what the name implies: it is a [[Booleans|boolean]] condition used very much like an [[If Statements|if statement]]. The value here can be any expression that evaluates to a boolean, and the expression will be reevaluated every time the loop executes. If the condition is evaluated to **true**, the [[Control Flow Structures|code block]] in the loop's body will run. If the condition is evaluated to **false**, then the loop will exit, and any code below the loop will continue execution.

The most common usage of this section is to compare an iterator variable (usually named `i` or `index`) to a number used to designate the number of times the loop should execute.

#### Update
^Update
The update part of a for loop contains a statement to be executed after each iteration of the for loop is complete. This section may be left empty if desired.

The most common usage of this section is to increment an iterator variable when using it to loop a specified number of times.


## Example

This pattern is one of the most common for loops you will see. It specifies an exact number of times the loop will run, and iterates until that number is reached.

```csharp
var timesToRun = 7;

Console.WriteLine("Before the loop");
for (int i = 0; i < timesToRun; i++) {
	Console.WriteLine(i);
}
Console.WriteLine("After the loop");

// this will concatenate i to the string before printing
Console.WriteLine("Final Value of 'i': " + i); 


// this code will print out the values below:
//> Before the loop
//> 0
//> 1
//> 2
//> 3
//> 4
//> 5
//> 6
//> After the loop
//> Final Value of 'i': 7
```