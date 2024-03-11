---
aliases:
  - params
---
Methods can be differentiated by their signatures when they are created. Often times, we want to create multiple versions of a method that has similar logic, but may be missing one or many parameters. The best solution for accomplishing this task is by using *optional parameters*.

Let's use the code below as an example:

```cs
public void PrintValues(string value1, string value2) {
	Console.WriteLine(value1);
	Console.WriteLine(value2);
}

public void PrintValues(string value1, string value2, string value3) {
	Console.WriteLine(value1);
	Console.WriteLine(value2);
	Console.WriteLine(value3);
}
```

When we write the above, we repeat the code for printing `value1` and `value2`. To combine these methods and reduce code duplication, we can use an *optional parameter*.

Assigning a value to a parameter will designate that parameter as an optional parameter. The value assigned serves as a *default value* for the parameter. 

Designating a parameter as an optional means that the parameter does not need to be specified when invoking the method. When omitting a parameter, the parameter value is set to whatever is assigned in the method header.

Here is an example of how we might combine our logic into a single method:

```cs
public void PrintValues(string value1, string value2, string value3 = null) {
	Console.WriteLine(value1);
	Console.WriteLine(value2);
	
	if(value3 != null) {
		Console.WriteLine(value3);
	}
}
```

## The Params Keyword

The params keyword allows any number of parameters to be passed in to a method. To be able to accept any number of arguments, you must do the following:
- Add a parameter to the end of the list of parameters
- Prefix the newly created parameter with the `params` keyword
- Add `[]` to the end of your parameter's type to convert it to an array

Here is an example of `params` in use:

```cs
public static void PrintAllParams(params int[] list) {
    for (int i = 0; i < list.Length; i++) {
        Console.Write(list[i] + " ");
    }
    Console.WriteLine();
}
```