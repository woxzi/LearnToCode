---
tags:
  - Lesson
---
Before completing the exercises below, read through these pages to gain knowledge about some useful utilities for writing method and variables in C#.
- [[Properties]]
- The [[Static]] Keyword
- The [[Readonly]] Keyword
- [[Optional Parameters]]

## Exercises

1. Create a class that has a two numerical properties: $x$ and $y$. Without explicitly writing a method into the class, structure the properties such that $y$ always reflects the value of $x^2$.
2. Create a method `IntSum`. This method can take any number of int parameters, and will print out the sum of each of the provided parameters.
3. Create a class `Foo` that has a method with the signature `void Bar()`. When invoked, the `Bar` method should print the number of instances of `Foo` that have been created. These instances may be created anywhere and do not need to be tracked in any one context.