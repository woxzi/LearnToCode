---
tags:
  - Lesson
  - WIP
---
How to perform recursion using [[Methods]]

- Maybe some FP concepts?
- Could include some kinds of recursion

- Fibonacci
- Tower of hanoi
- Palindromes

## Exercises

1. Write a method that takes an integer parameter 'n', and returns the n<sup>th</sup> number in the [Fibonacci sequence.](https://en.wikipedia.org/wiki/Fibonacci_sequence) Try writing two implementations of this, one using no loops of any kind, and the other using loops.
	- The first number in the Fibonacci sequence is 0.
	- The second number in the Fibonacci sequence is 1.
	- Each number after the first two are equal to the sum of the previous two numbers.
		- For example, the first few numbers should be the following: `0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, ...`

2. Write that method to reverse a string without using loops of any kind. This method accepts a string parameter `input`, and returns a string containing the reversed value.
	- Manipulate the string as if it were an array, by converting it using the `.ToCharArray()` method.
	- Convert the char array back into a string using this statement:
	  `string.Join("", yourCharArrayGoesHere)`

3. Write a method that solves the classic [Tower of Hanoi](https://www.mathsisfun.com/games/towerofhanoi.html) game in the optimal number of moves. 

### How to Play

- Below are the rules for playing Tower of Hanoi:
	- No disk can be placed on top of a 

- This method should meet the below criteria:
	- The method should accept an inpu
	- The optimal number of moves is 2<sup>n</sup> - 1, where n is the number of disks used in the game