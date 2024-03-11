---
aliases:
  - bool
  - boolean
---
 The 'Bool' type is a [data type](Data%20Types.md) used for storing a True or False value.

Booleans are primarily used in [[If Statements]], which will be covered in a future lesson.

All [numeric](Numeric%20Types.md) comparison operators will return a boolean as a result.
```csharp
var x = 3;
var y = 5;

var result = ( x > y );
Console.WriteLine(result);
//> False
```

#### Operators

Booleans have multiple mathematical operators available to them:
- `!x` - the 'not' operator, which inverts the value of the boolean
- `x & y` - the 'and' operator, which results in True if both values are True
- `x | y` - the 'or' operator, which results in True if any of the values are True
- `x && y` - the 'and' operator, which results in True if both values are True (short circuits)
- `x || y` - the 'or' operator, which results in True if any of the values are True (short circuits)
- `x ^ y` - the 'xor' operator (short for exclusive or), which results in True if exactly one of the values is True

Booleans also have two comparison operators available to them:
- `x == y` - the 'equals' operator, which checks if two values are equal
- `x != y` - the 'not equals' operator, which checks if two values are equal

```csharp
bool x = true;
bool y = true;
bool z = false;

Console.WriteLine(!x);
//> False

Console.WriteLine(x == y);
//> True

Console.WriteLine(x && y);
//> True

Console.WriteLine((!x != y) == z);
//> False
```

#### Short Circuit Operators 

Short Circuit operators are a special kind of operator that calculates its results differently than other operators. These operators do not evaluate the variable right-hand variable if it would not be able to change the result.

Cases where short circuiting will happen:
- `x && y` - If x is False, the result will always be False. This means that the runtime will not evaluate y.
- `x || y` - If x is True, the result will always be True. This means that the runtime will not evaluate y.

Here are some examples of short-circuiting at work:
```csharp
bool x = false;

// This will not wait for user input, because x was False. 
// The && can never evaluate to True, so it skips running the last half of the operator.
bool result = x && (Console.ReadLine() == "y");
Console.WriteLine(result);
//> False


x = true; // Let's set x to true and rerun the code for the next test.

// This will wait for user input, because x was True. 
// The && might be able to evaluate to True, so it runs last half of the operator.
bool result = x && (Console.ReadLine() == "y");
Console.WriteLine(result);
// The answer here will depend on whether or not you enter 'y' into the console.
```

