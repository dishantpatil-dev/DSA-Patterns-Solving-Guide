# Arrays: Core Patterns

## Two Pointers

**Recognize:** sorted arrays, pair/triplet relations, opposite ends, in-place partitioning.

**Invariant:** pointers describe the remaining candidate region.

~~~cpp
int l = 0, r = n - 1;

while (l < r) {
    long long cur = 1LL * a[l] + a[r];

    if (cur == target) {
        ++l;
        --r;
    } else if (cur < target) {
        ++l;
    } else {
        --r;
    }
}
~~~

Do not force two pointers onto an unsorted problem without a structural reason.

## Sliding Window

**Recognize:** contiguous subarray/substring plus a condition that can be updated as the window changes.

~~~cpp
int l = 0;
for (int r = 0; r < n; ++r) {
    add(a[r]);

    while (!valid()) {
        remove(a[l]);
        ++l;
    }

    ans = max(ans, r - l + 1);
}
~~~

For a fixed window of size k, add the right element and remove the element leaving the window.

## Prefix Sum

**Recognize:** repeated range sums.

~~~cpp
vector<long long> pref(n + 1);
for (int i = 0; i < n; ++i)
    pref[i + 1] = pref[i] + a[i];

long long sum = pref[r + 1] - pref[l];
~~~

Mental model: **right boundary minus left boundary**.

## Difference Array

**Recognize:** many range additions followed by final reconstruction.

~~~cpp
vector<long long> diff(n + 1);
diff[l] += x;
if (r + 1 < n) diff[r + 1] -= x;

long long cur = 0;
for (int i = 0; i < n; ++i) {
    cur += diff[i];
    a[i] += cur;
}
~~~

Prefix sum optimizes range queries; difference arrays optimize repeated range updates.

## Kadane

**Recognize:** maximum contiguous sum.

~~~cpp
long long best = a[0], cur = a[0];

for (int i = 1; i < n; ++i) {
    cur = max<long long>(a[i], cur + a[i]);
    best = max(best, cur);
}
~~~

At each index ask: **does the previous segment help, or should I restart here?**

## Hashing / Frequency

**Recognize:** membership, frequency, complement lookup, duplicate detection, grouping.

~~~cpp
unordered_map<int, int> freq;
for (int x : nums)
    ++freq[x];
~~~

Hashing is generally expected O(1) for lookup, but it does not preserve ordering.
