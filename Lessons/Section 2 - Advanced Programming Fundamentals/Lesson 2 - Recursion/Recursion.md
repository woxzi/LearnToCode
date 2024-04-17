---
aliases:
  - recursion
  - recursive
  - induction
---
Recursion is a problem solving strategy where your logic will call *itself* repeatedly to solve a problem. While the terms 'recursion' and 'induction' are often used interchangeably, they actually refer to different sides of the same type of problem solving.

**Recursion** - This strategy is used when the (n) case of a problem is able to be determined using an (n - 1) case. It will then repeat the same logic on each case, simplifying the cases down until an atomic case is reached. This case is often referred to as the 'base case', and is used to determine an initial value that is then used to determine the value of all the intermediary cases up until we reach the very top.

**Induction** - This type of strategy is often used in math proofs to prove that for every (n) case, then the (n + 1) case must be true for all numbers in a set. This type of proof is called a proof by *induction*. When applied to programming, this often refers to the logical step in the recursive process that determines the value of each case based on its previous cases.

## How to Implement Recursive Algorithms

When applying recursive logic to problems, your solutions must always have at least one base case, and at lease one inductive step in order to function properly. Much like while loops, if no stopping point is provided (your base case), then your code will iterate infinitely without end. Similarly, if no inductive step is provided, then the case you recurse over will always remain the same and will never reach a base case.
### Base Case
The *base case* is a case that is directly solvable without any additional steps. Usually it's something that you already know the answer for, but it can be something that's directly calculated based on an input. Base cases are unique in that they are pieces of logic that do not call the recursive block.
### Inductive Step
An inductive step is a piece of logic that calls the recursive function. To successfully recurse, the inductive step will need to simplify the case it's trying to solve, bringing it closer to the base case. 

To write an inductive step, consider any arbitrary case of the problem you're trying to solve. This is the (n) case. If you can find a way to make that case simpler and easier to solve in a way that trends towards a base case, you could solve the problem for that case instead. This case that has been simplified once is the (n - 1) case. We can keep simplifying the problem until we reach a base case that we can solve, and use that answer to determine the rest of the results.
## Example of a Recursive Implementation

Consider the following mathematical expression:
$$\begin{flalign}\sum_{k=0}^{n}k\:,\quad n\geq0&&\end{flalign}$$
To implement this logic as a method, normally we'd write a loop that might look something like this:

```cs
int SumOfAllNumberLessThan(int n) {
    int sum = 0;
    for (int i = 0; i <= n; i++) {
        sum += i;
    }
    return sum;
}
```

This simply loops over all numbers starting from zero up to n (inclusive), and adds them to determine a sum. Finally, the sum is returned as the result value.

If we wanted to implement this recursively, we could try breaking down the problem into some recursive components. Doing so results in

```cs
int SumOfAllNumberLessThan(int n) {
    if (n < 0) {
        throw new NotSupportedException();
    } else if (n == 0) {
        return 0;
    } else {
        return n + SumOfAllNumberLessThan(n - 1);
    }
}
```