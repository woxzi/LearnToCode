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

Point2D val3 = new Point2D {
	x = 15;
	y = 30;
}

class Point2D {
	public int x;
	public int y;
}
```

When running the above code, the variables will reserve memory in the heap in a way vaguely like this:

| **Address** | ... | \[val1\] | ... | \[val2\] | ... |
| ----------- | --- | -------- | --- | -------- | --- |
| **Value**   | ... | 3        | ... | c        | ... |
Each variable will receive its own reserved addresses in memory, according to its size. It's important to note that memory allocations cannot change their size. This is why low-level reference types like [[Strings|strings]] and [[Arrays|arrays]] that can be of any size will have an immutable size once initially set, and will not be able to be resized without creating a new value of that type to transfer the data over to.

### Value Types
All primitive types (except strings) are *value types*, which means they store their value directly in memory. 

Below are the types that behave as value types:
- [[Data Types|Primitive types]] (Except String)
- [[Structs|Struct]]
- [[Enums|Enum]]

### Reference Types
Reference types are types that are not directly stored in memory


Below are some common reference types. you can find a more detailed set of reference types in the Microsoft docs [here](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/reference-types):
- [[Strings|String]]
- [[Classes and Objects|Class]]



| ... | \[val3\] |       | ... | \[x\] | \[y\] | ... |
| --- | -------- | ----- | --- | ----- | ----- | --- |
| ... | x: 15    | y: 15 | ... | 15    | 30    | ... |
## Pointers

- Pass-by-Reference and Pass-by-Value
	- out params
	- ref params