---
aliases:
  - pointer
  - reference type
  - reference types
  - value type
  - value types
  - pass by reference
  - pass by value
---
## Storing Values In Memory

When running code, we store computed values in variables. These variables are stored in your RAM, which we will be calling 'memory'. Most of the time these variables will be stored in the 'heap', which is a bit of memory reserved for arbitrary dynamic memory allocations in your program.

Imagine memory as if it's one really long strip of 'slots' to enter data into. Each slot has an 'address', which describes its location in memory. Whenever we create a new variable, that variable will reserve a number of locations in memory based on how large it is. 

```cs
int val1 = 3;
char val2 = 'c';

Line val3 = new Line {
	start = new Point2D {
		x = 15,
		y = 30,
	},
	end = new Point2D {
		x = 45,
		y = 45,
	}
};

class Line {
	public Point2D start;
	public Point2D end;
}

class Point2D {
	public int x;
	public int y;
}
```

When running the above code, the variables will reserve memory in the heap in a way vaguely like this:

![[Memory Allocation Of Objects|1000|center]]

Each variable will receive its own reserved block of memory to store data, which can be of any size. These memory blocks can allocated anywhere in memory that the operating system decides, so there isn't any specific structure or location to how these blocks are placed in memory. Instead, each block has an assigned address, which is an integer value that is used to describe where in memory the beginning of the reserved memory block is located. 

It's important to note that memory allocations can have any size, but cannot change their size. This is why low-level reference types like [[Strings|strings]] and [[Arrays|arrays]] that can be of any size will have an immutable size once initially set, and will not be able to be resized without creating a new value of that type to transfer the data over to.

### Value Types

In the above code and diagram, you may notice that `val1` and `val2` have their values directly stored in blocks of memory. This is because [[Integers|int]] and [[Characters|char]] are **value types**. All primitive types (except strings) are value types, which means they store their value directly in memory. 

Below are the types that behave as value types:
- [[Data Types|Primitive types]] (Except String)
- [[Structs|Struct]]
- [[Enums|Enum]]

### Reference Types
**Reference types** are types that do not directly store their values in memory. They will instead store an address value that references the location of another block of memory. This separate block of memory will store the value of whatever the variable contains.

When an address value is stored in memory, it is called a *pointer*. Pointers are often used to refer to existing values stored elsewhere in the program. These can be used to quickly pass around large object values without directly copying every value to a new block of memory.

In the code and diagram above, `val3` is an object that contains another object. Because all objects created from classes are reference types, each time we assign a variable to an object value a pointer is created that refers to the block in memory where the value actually resides. This pointer is then saved in the block of memory reserved for the original variable.

Below are some common reference types. you can find a more detailed set of reference types in the Microsoft docs [here](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/reference-types):
- [[Strings|String]]
- [[Arrays|Array]]
- [[Classes and Objects|Class]]

### Manipulating Shared References

For the next example, consider the following code:

```cs
// initialize a variable here
var var1 = new Point2D {
    x = 3,
    y = 6,
};

// now we copy the value to another variable
var var2 = var1;

// let's change the value in var2 and see what happens
var2.x = 5;

Console.WriteLine($"Var 1 - x: {var1.x}, y: {var1.y}");
Console.WriteLine($"Var 2 - x: {var2.x}, y: {var2.y}");

class Point2D {
    public int x;
    public int y;
}
```

<center>When initializing var1, it would be stored using a pointer, like in the diagram below. Note that the values are note directly stored in the variable, and are instead stored in a separate location in memory.</center>

![[Step 1|150|center]]

<center>Now let's assign var2 to the value of var1. Because var1 stores a pointer to the block with the object's value instead of the object itself, the <i>pointer</i> will be copied to var2. This means that the object will be shared between both variables.</center>

![[Step 2|300|center]]

<center>Let's change the x value stored in var 2. To do this, we follow the pointer in var 2 and change the stored value.</center>

![[Step 3|300|center]]

Changing the stored value will update the value at the destination of the pointer. Because this is pointed to by both variables, the `x` value in var 1 and var 2 reference the same thing. When we change var 2's value, var 1 will be changed as well as long as their pointers reference the same object.

#### Pass By Value vs Pass By Reference



## Pointers

- Pass-by-Reference and Pass-by-Value
	- out params
	- ref params