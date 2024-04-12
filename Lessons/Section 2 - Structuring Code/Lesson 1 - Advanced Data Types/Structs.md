---
aliases:
  - struct
---
Structs are [[How Variables Are Stored Internally|value types]] that can be defined similarly to [[Classes and Objects|classes]]. They can have properties and fields just like classes, but are not [[How Variables Are Stored Internally|reference types]]. To write a struct, simply write a class like you normally would, but use the keyword `struct` instead of `class` like so:

```cs
struct TheClass {
    private int theVariable = 0;
    public int anotherVariable { get; set; }

    public void Method1() {
        theVariable = 5;
    }

    public bool Method2() {
        return theVariable > 3;
    }

    public TheClass(int val, int val2) {
        theVariable = val;
        anotherVariable = val2;
    }
}
```

When writing a struct like a class, there are a few differences you need to consider:

- If the struct has a field that is assigned a value on initialization, the struct MUST have a constructor that assigns a value to that field.
- If the struct has a property, the struct MUST have a constructor that assigns a value to that property.

### Typical Usage Of Structs

Structs are normally used when writing smaller models, because their values are grouped together in memory. Having large structs be passed around can have a negative impact on the performance of your code. However, utilizing small structs can bypass the need for additional lookups that would normally happen when using classes, which can improve performance. 

