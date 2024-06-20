**RELATED**: [[Recursion]]

Recursion is a function that calls itself with a smaller output, achieving the same result as iterative functions using loops, until a base case is reached

> Recursive functions have two parts:
> 
> 1. The base case
> 2. The function calling itself with a different input.

## About

Take $n$ factorial from math, the formula for which is:
				$n!=n*(n-1)*(n-2)*...1$
$n!$ is just a short way of representing the cumulative product of all numbers from $n$ to $1$. A shorter way of writing this would be as 
			   $n!=n*(n-1)!$ i.e. $5! = 5*4!$. 

```c++
// Recursive implementation of n! (n-factorial) calculation
int factorial(int n) {
    // Base case: n = 0 or 1
    if (n <= 1) {
        return 1;
    }
    // Recursive case: n! = n * (n - 1)!
    return n * factorial(n - 1);
}
```

### Time Space Complexity Analysis

In total, 𝑛 calls are being made to the `factorial` function, making the time complexity $𝑂(𝑛)$. Furthermore, the space complexity will also be in 𝑂(𝑛). Recursion operates off of a stack, and because there are 𝑛n recursive calls, there will be 𝑛 stacks, which results in 𝑂(𝑛) space.

### Iteration and Recursion

Any recursive algorithm can be written iteratively, and the other way around. The iterative implementation of this is the following:

```c++
int n = 5;
int res = 1;
while (n > 1) {
    res = res * n;
    n--;
}
```
