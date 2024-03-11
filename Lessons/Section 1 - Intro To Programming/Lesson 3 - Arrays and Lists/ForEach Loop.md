---
aliases:
  - foreach
  - foreach loops
---
For-Each loops are a type of loop that can only be used on types that inherit from [[The IEnumerable Interface]]. These loops are fairly simple versions of loops, designed to allow for easy of iteration over elements in a collection.

For-Each loops can be written using the format below:

```csharp
foreach (type name in enumerableVariable) {
	// loop body goes here
}
```

Both [[Arrays]] and [[Lists]] inherit from [[The IEnumerable Interface]], so you can try using foreach loops on them. Here is an example of using each of them in a foreach loop:

```csharp
var array = new int[] { 1, 2, 3 };
var list = new List<int>() { 1, 2, 3 };

foreach (var item in array) {
	Console.WriteLine("Array Value: " + item);
}
//> Array Value: 1
//> Array Value: 2
//> Array Value: 3

foreach (var item in list) {
	Console.WriteLine("List Value: " + item);
}
//> List Value: 1
//> List Value: 2
//> List Value: 3
```

### Order of Execution

In each iteration of the loop, the foreach loop will assign the next value from the [[The IEnumerable Interface|IEnumerable]] to the variable declared in the loop. This value can be read from, but not directly assigned to.

```csharp
var list = new List<int>() { 7, 2, 1 };

foreach (var element in list) {
	// element is 7 here during the first iteration
	// element is 2 here during the second iteration
	// element is 1 here during the third iteration
}
```