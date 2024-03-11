If statements are control flow structures that perform logic conditionally based on a [[Booleans|boolean]] value provided to them. If statements will only execute the code in their body if the condition provided to it evaluates to **true**.

```csharp
bool someValue = true;

if (someValue) { // here we use 'someValue' as the condition

	// if someValue is true, run the code written here
	
}

// regardless of what was in the if statement, run the code after the block
```

If statements may also have an **else if** or **else** clause, which denotes a block of code to execute if the condition was **false**.

```csharp
bool someValue = true;
bool someOtherValue = false;

if (someValue) {
	// if someValue is true, run the code written here
} else if (someOtherValue) {
	// if someValue is false, and if someOtherValue is true, run the code written here 
} else {
	// if someOtherValue is false, run the code written here
}

// regardless of what was in the if statement, run the code after the block
```

It's important to note that the condition provided to an if statement doesn't necessarily have to be a boolean *variable*, it could also be an expression. Here's an example of using a condition instead of a boolean directly:

```csharp
int x = 3;

if (x > 7) {
	// this will not run, because (x > 7) = false
} else {
	// this will run, because the condition evaluated to true
}
// regardless of what was in the if statement, run the code after the block
```

If statements can use single lines or [[Control Flow Structures#^CodeBlocks|code blocks]] as their body. This means that you don't need the curly braces to make an if statement function, but omitting them will restrict you to using a single line in the statement.

## Ternary If Statements

Inline ternary if statements can be written using the `?` operator. This allows if statements that would normally be multiple lines to be shortened to expression. 

Ternary if statements are expressions that will evaluate to a result value. They are primarily used when assigning variables to minimize the amount of boilerplate code needed to assign conditional values.

Ternary if statements are written using the below format:

```
condition ? valueIfConditionWasTrue : valueIfConditionWasFalse
```


Here is an example of an inline ternary if statement compared to the normal multi-line if statement:

```csharp
int x = 50;

// if x > 10, this will print x / 2.
// if x <= 10, this will print x.
int result;
if (x > 10) {
	result = x / 2;
} else {
	result = x;
}
Console.WriteLine(result);
//> 25

// this ternary statement condenses the above if statement's logic to a single line
Console.WriteLine(x > 10 ? x / 2 : x);
//> 25
```