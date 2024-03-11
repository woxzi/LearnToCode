---
aliases:
  - switch
  - switch case
  - switch statement
---
[[Switch Case Statements|Switch Case Statements]] are control flow structures that are used to quickly define cases for when a variable is equal to specified discrete values. Values used in switch statements are limited to values of primitive [[Data Types|types]], and [[Strings]].

Switch case statements do not use [[Control Flow Structures|code blocks]] in their body, unlike most other control flow structures. They are instead written using `case`, `break`, and `default` statements using the format in the block below.

`case` - The case statement denotes a specific value for which we are going to run conditional logic.
`break` - The break statement will move the control flow to the statement after the switch case, ending the switch case.
`default` - The default statement denotes logic that should run whenever no case is found for the input value.

```csharp
var x = 3;

switch (x) {
	case 1:
		Console.WriteLine("x was one");
		break;
	
	// you can put as many statements in a line as you want
	case 2:
		Console.WriteLine("x was two");
		Console.WriteLine("we can print multiple lines in a case like this");
		break;
	
	// you can have multiple values assigned to a case like this
	case 3:
	case 4:
		Console.WriteLine("x was either three or four");
		break;
		
	default:
		Console.WriteLine("x was not one, two, three, or four");
		break;
}
```