Numeric types are [[Data Types]] used for storing numbers. There are two types of numeric types: Integers and Floating Points.

## Integral vs Floating Point Numeric Types

Integral types like [[Integers]] are stored as numbers without a decimal point, while floating point numbers like [[Doubles]] are stored with a decimal.

Here is a visual example of how two variables might display differently based on their types, even if they had the same exact values.

```csharp
int x = 3;
double y = 3;

Console.WriteLine(x);
//> 3
Console.WriteLine(y);
//> 3.0, but the '.0' may be stripped off depending on your print settings

// the below line throws an error because you 
// can't save a floating point value to an integer
int x = 3.5; 
double y = 3.5;

Console.WriteLine(y);
//> 3.5
```

For more information on numeric types, read the MSDN article for [integral](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/integral-numeric-types) and [floating point](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/floating-point-numeric-types) types. 

## Operators on Numeric Types

All numeric types have the same basic operators for performing regular mathematical functions:
- `+` - for addition
- `-` - for subtraction
- `*` - for multiplication
- `/` - for regular division, and [[Integers|integer]] division
- `%` - the modulus operator (gets the remainder of division)

Additionally, numeric types can be compared using **comparison operators**, which will all return [[Booleans|boolean]] result values:
- `==` - equal to
- `!=` - not equal to
- `>` - greater than
- `>=` - greater than or equal to
- `<` - less than
- `<=` - less than or equal to

All of the above operators do not save their values to any variables you use in them, and will instead output a result to wherever you are using the value.

```csharp
double x = 6.5;
double y = 2.5;

var z = x % y; // gets the remainder of 6.5 divided by 2.5

// the highest multiple of 2.5 that is less than 6.5 is 5
// 6.5 - 5 = 1.5
// the result of the modulus operator should be 1.5

Console.WriteLine(z);
//> 1.5
```

There are also a few useful [[Math Functions]] that can be used in the future.

#### Assignment Operators

All mathematical operators have assignment versions. These assignment versions of operators all perform their respective mathematical function and then update the value store in the left-hand variable.
- `x += y` - add x and y and save the result in x
- `x -= y` - subtract y from x and save the result in x
- `x *= y` - multiply x and y and save the result in x
- `x /= y` - divide x by y and save the result in x
- `x %= y` - divide x by y and save the remainder in x

Two other types of operators exist that assign values: The increment and decrement operators.
- `x++` - Add 1 to x and save the result in x (postfix operator, executes *after* the line is run)
- `++x` - Add 1 to x and save the result in x (prefix operator, executes *before* the line is run)
- `x--` - Subtract 1 from x and save the result in x (postfix operator, executes *after* the line is run)
- `--x` - Subtract 1 from x and save the result in x (prefix operator, executes *before* the line is run)

Here are some examples of assignment operators in use:
```csharp
var x = 0;
var y = 5;

x++;
Console.WriteLine(x);
//> 1

x += 2;
Console.WriteLine(x);
//> 3

x -= y;
Console.WriteLine(x);
//> -2

// The above operator was not an assignment operator.
// This means that the result will not be saved in x, so the program 
// will still print -2 from the previous result.

// The below code will use the result of x * 15, without saving the value back to x.
Console.WriteLine(x * 15);
//> -30

// x is -2 before running this
var a = ++x; // adds 1 to x BEFORE the line is run, saving the changed version to a
Console.WriteLine(x);
//> -1
Console.WriteLine(a);
//> -1

// x is -1 before running this
var b = x++; // adds 1 to x AFTER the line is run, saving the unchanged version to b
Console.WriteLine(x);
//> 0
Console.WriteLine(b);
//> -1
```


#### Order of Operations

Mathematical operators all follow the order of operations as used in any everyday math class. This means that you don't have to worry about expressions on the same line being evaluated from left-to-right, because the C# compiler already takes this into account.

```csharp
int x = 2;
int y = 7;

// order of operations (PEMDAS) dictates that 3 * x will be evaluated before y
Console.WriteLine(y + 3 * x);
//> 13

// here we force y + 3 to be evaluated first using parentheses
Console.WriteLine((y + 3) * x);
//> 20
```

Microsoft has some documentation on order of operations for operators [here](https://learn.microsoft.com/en-us/cpp/c-language/precedence-and-order-of-evaluation?view=msvc-170). This documentation includes operators not covered in this class.

#### Integer Division

It's important to note that division performed on two integral numbers behaves differently than division using any other combination of numeric types.

[[Integers#^IntegerDivision|Integer division]] is a special case where all remainders are discarded. Because of this, the resulting values are always integers.

## Signed vs Unsigned Types

***This is interesting information on how numeric types work behind the scenes. It is not necessary for you to understand this right now, but it's good foundational knowledge to pick up.***

***I will assume that you already have some basic knowledge of binary here, but if you are interested in learning this and do not already understand binary, there is a quick guide [here](http://www.steves-internet-guide.com/binary-numbers-explained/)

Most numeric types are 'signed types', like [[Integers|int]] and [[Doubles|double]]. **Signed types** may have a positive or negative value, up to whatever their maximum or minimum values are. **Unsigned Types** must always be positive or zero. They do not support negative values.

Storing a value as a signed type will typically restrict the number of possible values to about half of what the unsigned version would normally allow. This is because when the number is being stored in memory, the leading bit is used to denote the sign of the stored number, instead of extending its value.

Here is an example of this using the 'short' and 'ushort' (unsigned short) data types. Shorts store their values in only 8 bits, so they are easy to visualize.
```
Short
1 0 1 0 0 1 0 1
|   |     |   |
128 32    4   1
-------------------
Represents Value: 165

Unsigned Short (ushort, using sign-magnitude representation for simplicity) 
1 0 1 0 0 1 0 1
|   |     |   |
-   32    4   1
-------------------
Represents Value: -37
```
The two numbers above are stored using the exact same string of bits, but the two numbers represent different values. This is because the first bit on the left is the 'leading bit', which represents the positive or negative sign in a signed type. When using an unsigned type, the leading bit is simply a continuation of the other bits, allowing for more possible values to be represented.

You can read more about the sign-magnitude representation used above [here](https://en.wikipedia.org/wiki/Signed_number_representations#Sign%E2%80%93magnitude), but it shouldn't be needed to understand the topics covered in this lesson.