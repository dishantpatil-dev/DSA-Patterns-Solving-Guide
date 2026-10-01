# Heaps & Priority Queues

Priority queues are useful when the next operation repeatedly needs the current minimum/maximum or another priority.

## Recognition

- Top-K
- next best candidate
- scheduling
- merge of sorted streams
- repeated minimum/maximum extraction

~~~cpp
priority_queue<int> maxHeap;
priority_queue<int, vector<int>, greater<int>> minHeap;
~~~

## Top-K

For K largest, keep a min-heap of size K.

~~~cpp
priority_queue<int, vector<int>, greater<int>> pq;

for (int x : nums) {
    pq.push(x);
    if ((int)pq.size() > k)
        pq.pop();
}
~~~

Complexity: O(N log K) time and O(K) extra space.

**Question:** do I need the entire sorted order, or only a small frontier of best candidates?
