# Backtracking

Backtracking explores a decision tree and abandons a branch as soon as it cannot produce a valid solution.

## Recognition

- all combinations
- all permutations
- subsets
- arrangements
- constraint satisfaction
- “return all possible”
- choose / skip / place / remove

## Template

~~~cpp
void backtrack(int idx) {
    if (/* complete */) {
        // record answer
        return;
    }

    for (int choice = 0; choice < choices; ++choice) {
        if (!valid(choice)) continue;

        apply(choice);
        backtrack(idx + 1);
        undo(choice);
    }
}
~~~

Mental model:

**Choose → Explore → Undo → Continue**

Good backtracking usually depends on pruning invalid branches early.

Often the complexity is exponential; state the actual branching/depth rather than hiding it behind loop syntax.
