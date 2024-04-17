---
tags:
  - Lesson
---
Before attempting the exercises in this lesson, you will need to understand the basics of how to implement [[Recursion|recursive algorithms]] when solving complex problems.
## Exercises

1. Write a method that takes an integer parameter 'n', and returns the n<sup>th</sup> number in the [Fibonacci sequence.](https://en.wikipedia.org/wiki/Fibonacci_sequence) Try writing two implementations of this, one using no loops of any kind, and the other using loops.
	- The first number in the Fibonacci sequence is 0.
	- The second number in the Fibonacci sequence is 1.
	- Each number after the first two are equal to the sum of the previous two numbers.
		- For example, the first few numbers should be the following: `0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, ...`

2. Write a method that checks if a string is a palindrome without using loops of any kind. A palindrome is a string that is spelled the same reversed as it is normally. For example, the word 'racecar' is a palindrome because the reverse of 'racecar' is still 'racecar'.

3. Write a method to reverse a string without using loops of any kind. This method accepts a string parameter `input`, and returns a string containing the reversed value.
	- Manipulate the string as if it were an array, by converting it using the `.ToCharArray()` method.
	- Convert the char array back into a string using this statement:
	  `string.Join("", yourCharArrayGoesHere)`

4. Write a method that solves the classic *[[Lesson 2 - Recursion#^HowToPlay|Tower of Hanoi]]* game in the optimal number of moves. This method should meet the below criteria:
	- The method should accept an integer parameter 'disks', which describes the number of disks used to play the game.
	- The method should print each move used to arrive at the solution, in the below format:
		- `Move #<move number here>: <starting peg> -> <ending peg>`
		- When printing a peg, use the value 'L', 'M', or 'R' to represent which peg is being described. These represent the left, middle, and right peg respectively.
	- Each move printed must be valid under the rules of the game *Tower of Hanoi*. The rules for this game can be found below.
	- The method must complete the game in the lowest number of moves possible. The optimal number of moves is 2<sup>n</sup> - 1, where n is the number of disks used in the game.

### How to Play - Tower of Hanoi
^HowToPlay
##### Setup
There are three 'pegs' that make up the board, with any number of differently sized disks stacked on top of each other. These disks begin the game stacked on a single peg, sorted by size. The largest disks are on the bottom of the peg, and the smallest disks are on the top.

##### Rules
- Each 'move' consists of moving a disk to another peg.
- Each disk cannot be placed on top of a disk that is smaller than itself.
- Only one disk can be moved at a time.

##### How to Win
The player 'wins' the game when all of the disks have been moved to a different peg than the one they started on. All disks must be on the same peg.

##### Play Online!
You can find an in-browser version of this game online [here.](https://www.mathsisfun.com/games/towerofhanoi.html)

