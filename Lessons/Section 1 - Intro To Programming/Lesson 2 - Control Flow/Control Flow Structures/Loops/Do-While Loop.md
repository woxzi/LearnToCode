---
aliases:
  - do while
  - do-while
  - do while loop
---
**Do-While loops** are a type of loop that will iterate *at least once, until a condition is met*. Conditions used in a do-while loop must be expressions that evaluate to a [[Booleans|boolean]] value.

## Order of Iteration

While loops will execute using the below steps when encountered:
1. Run the [[Control Flow Structures|code block]] in the loop.
2. Evaluate the condition expression, and retrieve its boolean value
3. If the condition evaluates to **True**, return to Step 1.
4. If the condition evaluates to **False**, the loop ends. Continue executing lines below the loop as normal.
## Example Loops

```csharp
int x = 50;

do {
	Console.WriteLine(x);
	x /= 2;
} while (x >= 10); // in this do-while loop, 'x >= 10' is the condition

Console.WriteLine("Final Value: " + x);

// This will print the below values:
//> 50
//> 25
//> 12
//> Final Value: 6
```


If the condition evaluates to false in the first iteration, the loop body will still have executed the first time. 

```csharp
int x = 50;

do { // this condition evaluates to false, so the loop will not run.
	Console.WriteLine(x);
	x /= 2;
} while (x < 10);

Console.WriteLine("Final Value: " + x);

// This will print the below values:
//> 50
//> Final Value: 25
```
