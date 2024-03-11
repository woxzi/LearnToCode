---
tags:
  - Lesson
---
## Top Level Statements

Up until now, you have likely been writing code using the newly-added [console app template used for top-level statements.](https://learn.microsoft.com/en-us/dotnet/core/tutorials/top-level-templates) This template greatly simplifies how you begin writing code, but it abstracts away some things that are valuable to know once you understand [[Classes and Objects|Objects]] and [[Methods]]. 

Whenever you write code, you would normally write it into a block like the below: 

```cs
// your code would go here
```

Writing code like the above will actually compile down to the old console app format below. You can still copy/paste this format to your program file to try it for yourself.

```cs
using System;

namespace ConsoleApp1 
{
    internal class Program 
    {
        static void Main(string[] args) 
        {
	        // your code would go here
        }
        
    }
}
```

All of the code that you have been writing up to this point is code that has been placed inside of the `Main` method, which is the only method that would be invoked whenever a project is run. All other classes and objects will need be called by this method in some way if they are going to be executed in your programs.

## Using Multiple Files to Code

Let's try creating a new file and writing some code to be used in our original program file. First, navigate to the Solution Explorer in your Visual Studio.

![[Images/Lesson 5/Screenshot 1.png|500]]

The Solution Explorer view will look something like the above picture. Next, right-click on your project to open the context menu for that project.

![[Images/Lesson 5/Screenshot 2.png|300]] 

Select Add > New Item...

![[Images/Lesson 5/Screenshot 3.png|300]]

A dialog window should pop up, providing you with options to create a new file in your project. Select Class (C# Items), and provide a name for your [[Classes and Objects|class]] in the bar on the bottom. I'll leave mine as the default `Class1.cs` value.

![[Images/Lesson 5/Screenshot 4.png]]
You should now have multiple classes available to you in the solution explorer view. Let's try writing a [[Methods|method]] in the new file, and calling its logic from the original `Program.cs` file.

To do this, let's put the following method inside of the new class we created.

```cs
public void TestMethod() {
	Console.WriteLine("This line was printed from Class1!");
}
```

Now, we will want to call the object from inside of the original `Program.cs` file. To do so, you can simply write the below lines:

```cs
var obj = new Class1(); // this line creates a Class1 object
obj.TestMethod(); // this line executes the TestMethod using that object
```

Running the program now will print the expected line, `This line was printed from Class1!`.

## Exercises

1. Create "Rectangle" a class with width and height attributes. Use a method to calculate the area and perimeter of the rectangle.
2. Create a class called "Circle" with a private radius attribute. Create three different Circle objects, and calculate the area and circumference of the circle for each object by invoking a method.
3. Create a class called "Triangle" with base and height attributes. The value of these attributes should be externally accessible, but not externally modifiable. Create three Triangle objects in your `Program.cs` file. Calculate the area of the triangle for each object.
4. Create a "Deck" class, filled with "Cards".
   - Each "Card" will have a number and suit attribute. The number will be an integer value from 1-13. The suit will be represented by an integer value from 0-3.
   - Each "Deck" will have a method that chooses a random card from the deck and returns it.
   - Each "Deck" will be populated with 52 different cards.
   - Write logic in your `Program.cs` file to create three decks of cards. Pull two random cards from each deck and print out the sum of the 'number' attribute from all six cards.