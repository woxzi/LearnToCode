---
aliases:
  - pass by reference
  - pass by value
  - ref
  - out
---
## Pass by Value

When passing in arguments to a method, the values of those arguments are copied over. Consider the below methods:

```cs
void ChangeStuff(int val) {
    val = 10;
}

void Print(int val) {
    Console.WriteLine($"Val - {val}");
    Console.WriteLine(); // create an empty line to separate printed blocks
}
```

The `ChangeStuff` method here changes any variable sent in to it. Because [[Integers|int]] is a [[How Variables Are Stored Internally|value type]], we simply copy any value passed through the method to a new local variable and change that variable. This means that we're changing a value that is not used outside the scope of the method, so if we run the code below, nothing will change between the print statements.

```cs
int val = 15;

Console.WriteLine("Before:");
Print(val); //> 15

ChangeStuff(val);

Console.WriteLine("After:");
Print(val); //> 15
```

C# uses **Pass-By-Value** by default whenever passing arguments into a method. This means that the value of any argument is copied into a new local variable, to be used inside of the method. Directly assigning values to this variable will have no impact outside of the scope of the method.

## Pass By Reference

Instead of directly copying the value, we can instead pass a reference to the original value into parameters. Doing this allows us to change values inside the method and impact the original arguments outside of the method. This process is called **Pass-By-Reference**, and can be performed by adding the `ref` keyword before any parameter that should be passed by reference. Here is an example of this happening:

```cs
void ChangeStuff(ref int val) {
    val = 10;
}

void Print(int val) {
    Console.WriteLine($"Val - {val}");
    Console.WriteLine(); // create an empty line to separate printed blocks
}
```

```cs
int val = 15;

Console.WriteLine("Before:");
Print(val); //> 15

ChangeStuff(ref val);

Console.WriteLine("After:");
Print(val); //> 10
```

### Out Params

We can also create parameters that are similar in nature to `ref`, but do not originally pass in a value by using the `out` keyword. Using the `out` keyword requires that you create a new variable in which the output value will be stored. This new variable can then be used outside the scope of the method. Here's an example of how the `out` keyword might be used when avoiding returning a value:

```cs
void ChangeStuff(out int val) {
    val = 10;
}

void Print(int val) {
    Console.WriteLine($"Val - {val}");
    Console.WriteLine(); // create an empty line to separate printed blocks
}
```

```cs
ChangeStuff(out var val); // we create a new variable 'val' here
Print(val); //> 10
```