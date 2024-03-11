---
aliases:
  - math
  - math functions
---
There are a collection of static functions provided in C# as a part of the Math class, which can be found [here](https://learn.microsoft.com/en-us/dotnet/api/system.math?view=net-8.0). Below is a list of commonly used properties and functions that can be used when performing calculations.

## Properties

- `Math.E` - Represents the value of the mathematical constant e.
- `Math.PI` - Represents the value of the mathematical constant π.
- `Math.Tau` - Represents the value of the mathematical constant τ.

## Commonly Used Functions
- `Math.Abs(num)` - Returns the absolute value of a number
- `Math.Sqrt(num)` - Returns the square root of a number
- `Math.Pow(baseNum, exponentNum)` - Returns the value of the base raised to the exponent's power
- `Math.Ceiling(num)` - Returns the smallest whole number that is greater than the provided decimal number
- `Math.Floor(num)` - Returns the largest whole number that is less than the provided decimal number
- `Math.Max(num1, num2)` - Returns the larger of the two provided numbers
- `Math.Min(num1, num2)` - Returns the smaller of the two provided numbers
- `Math.Round(num, [places])` - Returns the value of num rounded to the nearest whole number if `places` is not provided. If places is provided, it instead rounds to the nearest number with the amount of decimal places specified in `places`.

## Parsing

Strings can be parsed into any primitive type to be used within a C# environment. To do this, you will need to call the built-in `.Parse(string)` method from the [[Data Types|data type]] that you're trying to parse the string into.

#### Parseable Data Types

All primitive [[Data Types]] except for char and string are able to be parsed from strings. Do do this, you simply need to call one of the two methods below:
- `.Parse(yourStringInput)` - Parses the string directly to an int and throws an exception if the string was not the correct format for an integer.
- `.TryParse(yourStringInput, out var someResultVariable)` - Attempts to parse the string to an int the same way `.Parse` would work, but instead returns a [[Booleans|bool]] that represents whether or not the parse was successful. The result is then stored in a newly defined out variable to be used later.

```csharp
string input1 = "42"; // this will be able to parse properly to an integer
string input2 = "potato"; // this will not be able to parse properly to an integer

int parseResult1 = int.Parse(input1);
Console.WriteLine("Input 1 - Parse:");
Console.WriteLine(parseResult1.GetType().Name);
Console.WriteLine(parseResult1);

Console.WriteLine("Input 1 - TryParse:");
if (int.TryParse(input1, out var tryParseResult1)) {
	Console.WriteLine(tryParseResult1.GetType().Name);
	Console.WriteLine(tryParseResult1);
} else {
	Console.WriteLine("Could not parse");
}

// Input 2 is not a number, so the below line will throw an 
// exception and crash the program. Comment out this block if 
// you want to test the result of the TryParse logic. 
int parseResult1 = int.Parse(input2);
Console.WriteLine("Input 2 - Parse:");
Console.WriteLine(parseResult2.GetType().Name);
Console.WriteLine(parseResult2);

Console.WriteLine("Input 2 - TryParse:");
if (int.TryParse(input2, out var tryParseResult2)) {
	Console.WriteLine(tryParseResult2.GetType().Name);
	Console.WriteLine(tryParseResult2);
} else {
	Console.WriteLine("Could not parse");
}
```

## Random Numbers

Pseudorandom numbers can be generated using the **Random** class. To do this, we must first create an [[Classes and Objects|object]] using the Random class. We can then use this object to repeatedly get different values.

```csharp
var rand = new Random();

Console.WriteLine(rand.Next());
Console.WriteLine(rand.Next());
Console.WriteLine(rand.Next());
// this would print three different numbers.
```

#### Seed Values

The random class can be instantiated using a *seed value*, which can be used to reproduce the values generated using that specific random object.

```csharp
int someSeedValue = 69420;

var rand1 = new Random(someSeedValue);

Console.WriteLine(rand1.Next());
Console.WriteLine(rand1.Next());
Console.WriteLine(rand1.Next());

var rand2 = new Random(someSeedValue);

Console.WriteLine(rand2.Next());
Console.WriteLine(rand2.Next());
Console.WriteLine(rand2.Next());

// Both of the above blocks of print statements will print the same numbers


var randWithNoSeedValue = new Random();

Console.WriteLine(rand2.Next());
Console.WriteLine(rand2.Next());
Console.WriteLine(rand2.Next());

// These print statements will be different values, 
// because a different (random) seed will be used 
// when constructing the Random object
```