---
aliases:
  - string
---
Strings are represented in memory as a sequence of characters, stored using an array.

Operators of Note: `+`, `+=`, and [[String Functions|some additional functions]].

#### Writing Strings

String literals are denoted using a double quote character (`"`). These are not to be confused with [[Characters|chars]], which use literals denoted by single quotes (`'`).

```csharp
string someVariable = "potato";

var x = "c";
var y = 'c';
```

#### Operators

- `x + y` - concatenates two strings
	- This places the contents of x before the contents of y. See the example code block below.
- `x += y` - concatenates x and y, then saves the results to x
	- Equivalent to `x = x + y`

```csharp
string a = 'potato';
string b = 'salad';

Console.WriteLine(a + b);
//> potatosalad
```