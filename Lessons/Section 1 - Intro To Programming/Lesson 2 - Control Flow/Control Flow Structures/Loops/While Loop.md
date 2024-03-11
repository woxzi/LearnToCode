---
aliases:
  - while
---
**While loops** are a type of loop that will iterate *until a condition is met*. Conditions used in a while loop must be expressions that evaluate to a [[Booleans|boolean]] value.

## Order of Iteration

While loops will execute using the below steps when encountered:
1. Evaluate the condition expression, and retrieve its boolean value
2. If the condition evaluates to **True**, the execute the [[Control Flow Structures|code block]] in the loop. Return to Step 1.
3. If the condition evaluates to **False**, do not run the [[Control Flow Structures|code block]] in the loop. Continue executing lines below the loop as normal.

## Example Loops

```csharp
int x = 50;

while (x >= 10) { // in this while loop, 'x >= 10' is the condition
	Console.WriteLine(x);
	x /= 2;
}

Console.WriteLine("Final Value: " + x);

// This will print the below values:
//> 50
//> 25
//> 12
//> Final Value: 6
```


If the condition evaluates to false in the first iteration, the loop body will be skipped. 

```csharp
int x = 50;

while (x < 10) { // this condition evaluates to false, so the loop will not run.
	Console.WriteLine(x);
	x /= 2;
}

Console.WriteLine("Final Value: " + x);

// This will print the below value:
//> Final Value: 50
```

## Infinite While Loops

Because while loops iterate until a boolean value of **False** is given. Because of this, if a **False** value is never provided to the loop, it will never end. This can be used to create infinitely running loops to repeat something until the end of the program.

```csharp
// This loop will run infinitely and never complete
while (true) { // in this while loop, the condition will never be false
	Console.WriteLine("Spam");
}

Console.WriteLine("Loop Complete.");
```