# Foundations: Complexity

Algorithm analysis is the foundation for choosing between solutions.

| Complexity | Typical idea |
|---|---|
| O(1) | fixed work |
| O(log n) | repeatedly halve the search space |
| O(n) | one pass |
| O(n log n) | divide-and-conquer sorting |
| O(n²) | nested full passes |
| O(2^n) | branching choices |
| O(n!) | permutations |

## Recognition checklist

1. What is n?
2. How many times can each loop execute?
3. Is the search space shrinking?
4. Am I recomputing the same state?
5. What extra memory grows with input?

## Important trap

Nested loops do not automatically mean O(n²). If two pointers together move only forward across the array, total movement can be O(n).

**Complexity measures total work, not visual code complexity.**
