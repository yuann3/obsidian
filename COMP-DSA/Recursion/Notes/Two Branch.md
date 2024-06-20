**RELATED**: [[Recursion]]

Lets make an example - fibonacci sequence. Generally, the formula to calculate the 𝑛𝑡ℎ fibonacci number in math is to take the $𝑛−1$ and $𝑛−2$ number and add them together. It is given that $𝐹(0)=0$ and $𝐹(1)=1$, which, in a recursive function, this would be our base case.

So the formula would be like:

				$fib(n)=fib(n−1)+fib(n−2)$

## Visualisation

![[Pasted image 20240619183640.png]]

```c++
// Recursive implementation to calculate the n-th Fibonacci number
int fibonacci(int n) {
    // Base case: n = 0 or 1
    if (n <= 1) {
        return n;
    }
    // Recursive case: fib(n) = fib(n - 1) + fib(n - 2)
    return fibonacci(n - 1) + fibonacci(n - 2);
}
```

We have our base case, we know the function calls itself in the last return statement, and we know that at some point when the base case is reached, we will have to travel back "up" to calculate the ultimate answer. To calculate `fibonacci(5)`, we get `fibonacci(4) + fibonacci(3)`. Now, both of these will execute the function from line 1. Looking at our tree, `fibonacci(4)` will call `fibonacci(3) + fibonacci(2)` and so on, until `n` hits `1` or `0` after which it will return the result, and keep going back up all the way until `fibonacci(4)` which will give us an answer of 33. Now, we have the answer to `fibonacci(4)` and do the same for `fibonacci(3)` which results in 22. Add the two together, and the 5𝑡ℎ5th fibonacci number is 55.

## Time Complexity
  
$𝑂(2𝑛)$

![[Pasted image 20240619184133.png]]