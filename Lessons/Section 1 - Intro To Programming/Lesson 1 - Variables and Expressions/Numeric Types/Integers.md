---
aliases:
  - int
  - integer
---
Integer is a signed, integral [numeric type](Numeric%20Types.md) that is used for representing whole numbers. They can represent any whole number in the range -2,147,483,648 to 2,147,483,647.

Because it is a numeric type, integers may use any of the operators available to [[Numeric Types]].

## Integer Division
^IntegerDivision

When dividing two integers, most programming languages 'truncate' any resulting decimal points. C# does this logic whenever division is performed on two integral types. When truncating remainder values, C# never rounds to the nearest whole number. It simply drops whatever would come after the decimal point.

```csharp
int x = 7;
int y = 2;

var z = x / y; 
// mathematically this should be 3.5, but in code it results in a 3.
// this result will be an integer

Console.WriteLine(z);
//> 3
```

If any of the variables used in division is a floating-point numeric type like a [[Doubles|double]], then regular division will be performed.
```csharp
double x = 7;
int y = 2;

var z = x / y; 
// this result will be a double

Console.WriteLine(z);
//> 3.5
```

If two integers are used for division, the result will be a truncated integer. If we want to divide two integers normally, we can cast one of the operands to a floating-point type like [[Doubles|double]].
```csharp
int x = 7;
int y = 2;

// casting any of the variables involved in the division to double 
// will make the program use normal division instead of integer division
var z = x / (double) y; 
// this result will be a double

Console.WriteLine(z);
//> 3.5
```

