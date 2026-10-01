# Advanced Patterns

## Disjoint Set Union

Useful for dynamic connectivity and Kruskal's MST.

~~~cpp
class DSU {
    vector<int> p, sz;

public:
    DSU(int n) : p(n), sz(n, 1) {
        iota(p.begin(), p.end(), 0);
    }

    int find(int x) {
        return p[x] == x ? x : p[x] = find(p[x]);
    }

    bool unite(int a, int b) {
        a = find(a);
        b = find(b);

        if (a == b) return false;
        if (sz[a] < sz[b]) swap(a, b);

        p[b] = a;
        sz[a] += sz[b];
        return true;
    }
};
~~~

## Sorting as a tool

Sorting can expose order so another pattern becomes possible: two pointers, grouping duplicates, greedy order, chronological processing, or adjacent relationships.

The source book covers insertion sort, Shellsort, heapsort, quicksort, radix sort, and external sorting. For interview work, first understand what ordering changes about the problem.

## Divide & Conquer

Recognition: split into smaller subproblems, solve recursively, then combine.

1. Divide
2. Solve
3. Combine

Typical recurrence: T(n) = aT(n/b) + f(n).

The key question is often: **what does the combine step cost?**

## Do not force patterns

Do not use DSU just because a graph exists. Do not use binary search just because numbers exist. Do not use greedy because sorting looks convenient. Pattern choice must follow structure.
