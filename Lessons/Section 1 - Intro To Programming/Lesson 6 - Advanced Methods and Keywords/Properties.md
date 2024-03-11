
Normally when writing fields, we create 'getter' and 'setter' methods to manage the access control for our variables. C# provides some syntax sugar for writing these methods, by allowing the use of *properties*.

Here is an example of a property:

```cs
public class Foo {
	public int SomeProperty { get; set; } = 3; // this is a property
}
```

Properties are written very similarly to fields, and can be directly assigned values the same way. It's important to note that properties have the `{ get; set; }` portion after their name. This is the most typical way to write a property, and is simply shorthand for making a getter and setter.

The above property will be compiled down to the below code when executed:

```cs
public class Foo {
	private int _SomeProperty = 3; // note the leading underscore here
	
	public int GetSomeProperty() {
		return _SomeProperty;
	}
	
	public void SetSomeProperty(int SomeProperty) {
		_SomeProperty = SomeProperty;
	}
}
```

#### How the getters and setters work

The `{ get; set; }` section of a property is fully customizable. The behavior of getters and setters can be changed, or even outright removed by manipulating this section. 

The access specifiers can be set for getters and setters by simply adding them as a prefix before the getter or setter, like so:

```cs
public class Foo {
	public int SomeProperty { get; private set; }
}
```

The above code would create a property that is readable from everywhere, but only modifiable from within the class.

Taking the customization a step further, let's create some properties that have custom getter and setter behavior. When customizing getters and setters, both methods *must have a body*, if they exist.

```cs
public class Foo {
    public int SomeProperty { 
	    get { return SomeProperty / 2; } 
	    set { SomeProperty = value; } 
    }
}
```

```cs
var foo = new Foo();
foo.SomeProperty = 4;
Console.WriteLine(foo.SomeProperty);
//> 2
```

The above block of code would store the value `4` passed into the setter directly in the property. However, the getter specifies that it will return the whatever the stored value is value divided by two. That means that whenever we access `SomeProperty`, we will get the stored value divided by two.

#### Calculated Properties

Properties don't necessarily need a setter method, and can be calculated based on the value of another field or property value. These kinds of properties are called *calculated properties*. They are used for calculations that are often accessed directly, like the `List.Count` property.

```cs
public class Circle {
    public double Radius;
    public double Circumference { get { return 2 * Math.PI * Radius; } }
}
```

In this example, `Radius` is a normal field that we would store a value in, and `Circumference` is a calculated property. The value of `Circumference` will be calculated every time it's accessed, so there is no need to manually update it each time the radius is changed.