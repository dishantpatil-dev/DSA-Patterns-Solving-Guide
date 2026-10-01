# Binary Search

The deeper pattern is not merely “sorted array”. It is an **ordered answer space with monotonic feasibility**.

## Standard search

~~~cpp
int l = 0, r = n - 1;

while (l <= r) {
    int m = l + (r - l) / 2;

    if (a[m] == target) return m;
    if (a[m] < target) l = m + 1;
    else r = m - 1;
}

return -1;
~~~

## Binary search on answer

~~~cpp
long long l = low, r = high;

while (l < r) {
    long long mid = l + (r - l) / 2;

    if (feasible(mid))
        r = mid;
    else
        l = mid + 1;
}

return l;
~~~

## Recognition

1. Is the data sorted?
2. If not, is the answer ordered?
3. Can I write a feasibility function?
4. Does feasibility change only once?

If feasibility is not monotonic, binary search has no reason to work.
