---
tags:
  - Lesson
---
[[Lists]] are complex types that allow you to store multiple things in one variable. They are [[Classes and Objects]] that have internal [[Arrays]], and use methods to perform their normal operations. You will need to read through and understand [[Lists]], [[Arrays]], and [[ForEach Loop|For-Each Loops]] before being able to complete this lesson's exercises.
[[Lists]] are complex types that allow you to store multiple things in one variable. They are [[Classes and Objects]] that have internal [[Arrays]], and use methods to perform their normal operations. You will need to read through and understand [[Lists]], [[Arrays]], and [[ForEach Loop|For-Each Loops]] before being able to complete this lesson's exercises.

### Exercises

***Problem 1:*** Populate the elements of an array containing all values from 1-100 raised to the 3rd power. Print out the array afterward.

***Problem 2:*** Ask the user if they would like to store a word. If they say 'yes', then ask them for a word and store it. Keep repeating this until they no longer wish to store a word. Print out all of the stored words once they stop wanting to store words.

***Problem 3:*** Ask the user for a lowercase word or phrase. Convert the provided string to a [[Characters|char]] array by writing `yourString.ToCharArray()` and saving the result. Then, encode the char array by performing the below operation on the char array. Convert your char array back to a string using `new string(yourCharArray)`. Print out the encoded string. Decode the string by performing the process in reverse and print out the decoded string. 

**Process for encoding a string:**
'Shift' the characters in the array up by an amount based on their position, as described below. To do this, add the amount you want to shift to the ASCII value of the character.

First Character: Shift up by 1
Second Character: Shift up by 2
Third Character: Shift up by 3
Next Character: Start again at the first character step, continuing downward for each character

Here is a visual example of this:
```
Character Index: 0    1    2    3    4    5    6 ...         
Transformation:  1 -> 2 -> 3 -> 1 -> 2 -> 3 -> 1 ...
```

NOTE: If the original character to shift is a non-alphabetical character, do not perform any transformations to it. Additionally, if a character would be adjusted to an ASCII value above 172 (lowercase 'z'), then 'wrap around' and start counting from 97 (lowercase 'a').

***Problem 4:*** Store the 3 x 3 matrix below in your code using a two-dimensional array. Multiply the matrix by a scalar value of 4. Print out the array after the transformation. 
$$ \begin{pmatrix} 
121 & -19 & 12 \\
413 & 2 & 156 \\
-200 & 7 & 34
\end{pmatrix} \times 4 $$

***Problem 5:*** Given the below jagged two-dimensional array, print out the sum of all elements in each row. Then, print out the sum of all elements in the array.
$$ \begin{matrix} 
121 & 19 \\
413 & 2 & 56 & 37 & 15 \\
201 & 7 & 34 \\
12 \\
29 & 47
\end{matrix} $$