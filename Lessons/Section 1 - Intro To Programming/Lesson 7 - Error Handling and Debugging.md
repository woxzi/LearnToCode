---
tags:
  - Lesson
---
 NOTE: This lesson describes features available in Visual Studio 2022. This section may not be accurate for different versions of Visual Studio, or different integrated development environments.

Please read about the following topics before working on the exercises below:
- [[Exceptions|Try / Catch statements]]
- [[The Visual Studio Debug Utility|Debugging]]
- [[Common Errors]]

## Exercises

1. The code below should print out a sorted version of the input array. Something is not working properly with the `Sort` method, and is instead printing out an incorrect result. Find the bug using the visual studio debugger and fix it.

```cs
var input = new int[] { 15, 4, 1, 9, 19 };

Sort(input);
foreach (int i in input) {
    Console.WriteLine(i);
}

// ONLY EDIT CODE BELOW THIS LINE
void Sort(int[] arr) {
    for (int i = 0; i < arr.Length - 1; i++) {
        for (int j = 0; j < arr.Length - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                int temp = arr[j];
                arr[j + 1] = temp;
                arr[j] = arr[j + 1];
            }
        }
    }
}
```

2. The code below should print out a reverse version of the input string. Something is not working properly with the `Reverse` method, and is instead throwing an exception. Find the bug using the visual studio debugger and fix it.

```cs
var input = "foobarbaz";

Console.WriteLine(Reverse(input));

// ONLY EDIT CODE BELOW THIS LINE
string Reverse(string text) {
    char[] charArray = text.ToCharArray();
    string output = String.Empty;
    for (int i = charArray.Length; i > -1; i--) {
        output += charArray[i];
    }
    return output;
}
```