---
aliases:
  - char
  - character
---
The 'Char' type is a [data type](Data%20Types.md) used for storing a single text character.

**Operators of Note:** `+`\*, `-`\* 

## Example Usage

Chars are typically used to store a single character in a variable, like so:

```csharp
char myCharacter = 'h';

Console.WriteLine(myCharacter);
//> h
```

Char literals must be written using single quotes ( ' ), instead of double quotes ( " ). Double quotes are exclusively used for writing literals of [[Strings]].

## Internal usage
Chars are stored internally using a positive integer. These integer values can be found on the [ASCII Table](https://www.ascii-code.com/)

The `+` and `-` operators may be used on chars, but these will always return an integer. This happens because internally the chars are actually just [[Integers|int]] values, so the int operators are always used.

#### Example Uses of Operators

Retrieving the distance between two chars
```csharp
var char1 = 'a';
var char2 = 'c';

var output = char2 - char1;

Console.WriteLine(output);
//> 2
```

Shifting chars numerically
```csharp
var myChar = 'a';

// this is going to result in an integer
var resultCharValue = myChar + 3;

// this line casts (converts) the resulting integer to a char type
var output = (char)resultCharValue;

Console.WriteLine(output);
//> d
```