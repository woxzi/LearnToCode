---
aliases:
  - list
---
Lists are built-in [[Reference Types]] that allow for storage of multiple variables of a specified type. These lists are functionally similar to [[Arrays]], but they have a mutable length. This means that you do not have to specify a length like with an array, and can continuously insert elements into the list without hitting any maximum.

### Basic Usage

#### Initializing a List

Like [[Arrays]], lists must be initialized using the `new` keyword. Initializing a new list follows the below format:

```csharp
// this initializes a new variable 'myList' and uses 
// it to create an empty list of type 'type' 
var myList = new List<type>();

// this initializes a new variable 'myList' and uses 
// it to create a list of type 'type' with all of the provided values 
var myList = new List<type>() { value1, value2, value3, ... valueN };
```

#### Reading and Updating Elements

Elements can be read from and set using the same notation available when using [[Arrays]]. They also have a `Count` property, which displays the current number of elements in the list, much like how an array would use its `Length` property.

```csharp
var list = new List<int>() { 5, 9, 1 };

Console.WriteLine(list[2]);
//> 1

list[2] = 3;
Console.WriteLine(list[2]);
//> 3

Console.WriteLine(list.Count);
//> 3
```

#### Inserting and Removing Elements

Unlike arrays, lists aren't locked into having a specified number of elements. Elements can be added and removed from a list at will, allowing lists to change their size dynamically as needed. This is accomplished by the `.Add(T)`, `.Insert(int, T)`, `.RemoveAt(int)`, and `.Remove(T)` [[Methods]]. Take a look at an example of each of these below:

```csharp
var someList = new List<string>() { "Potato", "Salad", "Apple", "Orange" };

someList.Add("Foo"); // adds 'Foo' to the end of the list

foreach (var item in someList) {
	Console.Write(item + ", ");
}
Console.WriteLine();
//> Potato, Salad, Apple, Orange, Foo, 

someList.Insert(3, "Bar"); // inserts 'Bar' at position 3

foreach (var item in someList) {
	Console.Write(item + ", ");
}
Console.WriteLine();
//> Potato, Salad, Apple, Bar, Orange, Foo, 

someList.RemoveAt(4); // removes the element in position 4, which is 'Orange'
foreach (var item in someList) {
	Console.Write(item + ", ");
}
Console.WriteLine();

someList.Remove("Bar"); // finds and removes 'Bar' from the list
foreach (var item in someList) {
	Console.Write(item + ", ");
}
Console.WriteLine();
```


### Internal Functionality

It's important to note that each instance of a List operates using an [[Arrays|array]] behind the scenes. Lists follow the below rules when managing a collection of elements internally:
- Initially, the list uses an array of size zero. 
- When you add your first element, the the array will be replaced with an array of size 4. 
- Every time you add an element that would exceed the maximum length of the internal array, a the List will transfer all elements over to a new internal array that has double the length.

This internal behavior means that [[Arrays]] are more efficient to execute in your program, but lists have better utility for writing code quickly.

Here is a code example of this behavior, to help visualize how it works more easily:

```csharp
var exampleList = new List<int>();

// the .Capacity property here returns the size of the internal list
Console.WriteLine();
Console.WriteLine("Internal Capacity: " + exampleList.Capacity);
Console.WriteLine("List Length: " + exampleList.Count);
//> Internal Capacity: 0
//> List Length: 0

// adding the first element sets the internal array size to 4
exampleList.Add(1337);
Console.WriteLine();
Console.WriteLine("Internal Capacity: " + exampleList.Capacity);
Console.WriteLine("List Length: " + exampleList.Count);
//> Internal Capacity: 4
//> List Length: 1

// adding 3 more elements fills the internal array but does not exceed it
// this will not expand the internal array
exampleList.Add(420);
exampleList.Add(69);
exampleList.Add(13);
Console.WriteLine();
Console.WriteLine("Internal Capacity: " + exampleList.Capacity);
Console.WriteLine("List Length: " + exampleList.Count);
//> Internal Capacity: 4
//> List Length: 4

// adding the next element will exceed the number of available slots internal array
// this will cause the list to copy all elements to an internal array of double the size
exampleList.Add(42);
Console.WriteLine();
Console.WriteLine("Internal Capacity: " + exampleList.Capacity);
Console.WriteLine("List Length: " + exampleList.Count);
//> Internal Capacity: 8
//> List Length: 5

exampleList.Add(420);
exampleList.Add(69);
exampleList.Add(13);
exampleList.Add(42);
Console.WriteLine();
Console.WriteLine("Internal Capacity: " + exampleList.Capacity);
Console.WriteLine("List Length: " + exampleList.Count);
//> Internal Capacity: 16
//> List Length: 9
```