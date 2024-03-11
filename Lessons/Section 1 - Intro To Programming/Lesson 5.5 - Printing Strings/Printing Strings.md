---
aliases:
  - ToString
---
## Escape Characters

When writing strings, there are some characters that may seem difficult to write, like new line characters, tabs, double quotes, and the like.

To do this, simply use write a backslash and an escape character to insert that character into the string. Microsoft has a full list of escape characters [here](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/strings/#string-escape-sequences), but I've written some of the more useful ones below. 

- `\n` - New line
- `\t` - A tab character used for spacing
- `\'` - A single quote
- `\"` - A double quote
- `\\` - A backslash

## The .ToString() Method

The `.ToString()` method is a *virtual* method that exists on all objects that [[Future Lesson - Inheritance|inherit]] from the `Object` class. Inheritance will be covered in a future lesson. For now, you just need to understand that the *virtual* keyword means that you can *override* the logic of the previously existing method. 

Because all classes/objects inherit from the `Object` class, the `.ToString()` method can be overridden in any user-defined class. Here is an example of how to do this:

```cs
public override string ToString() {
	return /* your result here */;
} 
```

#### Why does this matter?

The `.ToString()` method is *implicitly* called whenever we print out an object. Most objects print out some odd-looking value including namespace and class names. Overriding this method allows any implicit conversions to use the logic specified in the method, which can print out more user-friendly messages.

Below is an example of how this logic might be implemented:

```cs
public class Potato {
	public int TestValue;
	
	public Potato(int TestValue) {
		this.TestValue = TestValue;
	}
	
	public string ToString() {
		return $"Potato: {TestValue}";
	}
}
```

```cs
var potato = new Potato(7);
Console.WriteLine(potato); // .ToString() is called here before the print statement
//> Potato: 7
```