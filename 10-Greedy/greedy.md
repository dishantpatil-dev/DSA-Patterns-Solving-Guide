# Greedy Algorithms

Greedy means making a local choice according to a rule and proving that the choice can be extended to an optimal solution.

It is **not** “pick what looks biggest”.

## Recognition signals

- interval scheduling
- repeated cheapest/earliest/highest-priority valid choice
- sorting creates a useful order
- an exchange argument can justify a local choice

## Solving method

1. Define the objective.
2. Identify a candidate local choice.
3. Determine what that choice eliminates.
4. Try an exchange argument.
5. Show the remaining problem has the same structure.
6. Then implement.

## Example shape

For interval scheduling, sorting by finishing time lets us repeatedly choose the next compatible interval.

The important skill is proving why that local choice preserves the possibility of an optimal solution.

## Greedy vs DP

Ask: **after making the local choice, does future reasoning still have all information it needs?**

If not, state-based methods may be necessary.
