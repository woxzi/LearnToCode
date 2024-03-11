`readonly` is a keyword that can be applied to fields and properties within a class. Creating a variable with the readonly property prevents it from being assigned to outside of a constructor. 

Here is an example of it in use below:

```cs
public class Foo {
	public readonly int x = 3; // we can assign values during declaration
	public readonly int y; // we can also just leave it blank, to be assigned later
	
    public Foo() {
	    // this is valid code because the assignment happens in a constructor
        y = 1;
    }

    public void Test() {
	    // this is NOT valid code because we are assigning the value in a method
        y = 1;
    }
}
```