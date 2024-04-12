---
aliases:
  - enum
---
Enums are a performant way to define groups of constant values as a type. Enums can be created using the below format:

```cs
enum TheEnum {
	Value1,
	Value2,
	Value3,
	//... more values can be entered as needed
}
```

The values entered into the enum will be assigned
### Underlying Types

Enum values will be stored in memory as a single value of whatever the specific underlying type is for that enum. The type of an enum can be specified using the below syntax, but can be left blank. If left unspecified, enums will default to an [[Integers|int]] underlying type. The underlying type used can be [[Characters|char]] or any integral numeric type.

Here is the syntax for writing an enum with a specific underlying type, which will be using a [[Characters|char]] in this case.

```cs
enum TheEnum : char {
	Value1,
	Value2,
	Value3,
	//... more values can be entered as needed
}
```

### Value Assignment

Once specified, values can be assigned to enums like so:

```cs
enum TheEnum {
	Value1 = 1,
	Value2 = 2,
	Value3, // this will be auto-assigned a value if one is not provided
}
```

Generally these values will be automatically assigned, incrementing in the order they are defined. Here is an example of what values might be assigned to if left partially specified or completely unspecified:

```cs
Fruit x = Fruit.Orange;
Colors y = Colors.Orange;

Console.WriteLine(x); //> Orange
Console.WriteLine((int)x); //> 6

Console.WriteLine(x); //> Orange
Console.WriteLine((int)x); //> 1

enum Fruit {
    Apple = 5,
    Orange,
    Pear,
    Kiwi
}

enum Colors : short {
    Red,
    Orange,
    Green
}
```