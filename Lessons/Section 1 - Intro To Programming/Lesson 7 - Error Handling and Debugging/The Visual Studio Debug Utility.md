---
aliases:
  - debug
  - debugging
  - breakpoint
cssclasses: []
---
## Beginning the Debugging Process

Visual studio has some built-in utilities for debugging your code whenever you run it. To start debugging, you'll need to use a *breakpoint* to pause the execution of your code.

To create a breakpoint, over over the gray bar to the left of the line you want to add a breakpoint to. A gray circle will appear under your cursor. Click this circle to create a breakpoint on the line that's next to it.

Hovering the gray bar creates a circle you should click to make a new breakpoint:
![[Images/Lesson 7/Screenshot 1.png|500]]

Adding a breakpoint to the line will highlight the line in red like this:
![[Images/Lesson 7/Screenshot 2.png|500]]

The arrow and yellow highlight will indicate that execution has been paused on this line. We can now inspect the state of the program before this line has been executed, and step around to investigate what nearby lines do.
![[Images/Lesson 7/Screenshot 3.png|500]]

## Navigating Through the Program

Once you begin debugging, you should see the below buttons appear in the toolbar at the top of your screen. These buttons allow you to 

| Icon                   | Name                | Description                                                                                                                    |
| ---------------------- | ------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| ![[Screenshot 7.png]]  | Show Next Statement | Jumps to the line that you had paused on in the debugger                                                                       |
| ![[Screenshot 9.png]]  | Step Over           | Runs the line that you're currently paused on, and pauses on the next line.                                                    |
| ![[Screenshot 8.png]]  | Step Into           | Enters the control block<sup>*</sup> that you're currently paused on, and pauses execution before the first line in it.        |
| ![[Screenshot 10.png]] | Step Out            | Steps out of the control block<sup>*</sup> that you're currently paused inside of, and pauses execution immediately afterward. |
\*Note: The 'control block' mentioned here refers to a [[Methods|method]] or [[Control Flow Structures|control flow structure]] of any kind.
## Inspecting Data

At the bottom of your screen, there should be a tab labeled 'Watch', that looks like this:
![[Images/Lesson 7/Screenshot 4.png|600]]

Click the line that says *Add item to watch*. Doing this allows you to write an expression, and display the resulting value in the 'Value' column on the right. This value will update whenever you navigate to different lines in your code, showing a display of important values that you care about.

Here is an example of using the watch to keep an eye on the uppercase value of the variable `x`:
![[Screenshot 6.png]]
