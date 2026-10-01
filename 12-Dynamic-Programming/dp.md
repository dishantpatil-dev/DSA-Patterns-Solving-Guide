# Dynamic Programming

DP stores solutions to overlapping subproblems so repeated states are not recomputed.

## The 5-step method

1. **Define the state:** write exactly what dp[i] or dp[i][j] means.
2. **Find the transition:** how does the current state come from smaller states?
3. **Base cases:** what are the smallest valid states?
4. **Evaluation order:** which states must already exist?
5. **Complexity:** number of states multiplied by transition work.

## Climbing Stairs

~~~cpp
int climbStairs(int n) {
    if (n <= 2) return n;

    int a = 1, b = 2;

    for (int i = 3; i <= n; ++i) {
        int c = a + b;
        a = b;
        b = c;
    }

    return b;
}
~~~

State: dp[i] = number of ways to reach step i.

Transition: dp[i] = dp[i-1] + dp[i-2].

## Debugging checklist

1. state definition
2. transition
3. base case
4. iteration order
5. initialization
6. state compression correctness

Recursion explores the state tree; DP recognizes repeated states and stores them.
