# Stack & Queue Patterns

Stacks and queues are basic ADTs and also appear inside many algorithms.

## Stack

Think **LIFO** and “most recent unresolved item”.

Signals:
- bracket matching
- undo-like state
- next greater/smaller
- monotonic stack

~~~cpp
stack<int> st;

for (int x : nums) {
    while (!st.empty() && st.top() > x)
        st.pop();
    st.push(x);
}
~~~

The comparison determines the required monotonic property.

## Queue / BFS

Think **FIFO** and layer-by-layer expansion.

~~~cpp
queue<int> q;
q.push(start);
vis[start] = true;

while (!q.empty()) {
    int u = q.front();
    q.pop();

    for (int v : adj[u]) {
        if (!vis[v]) {
            vis[v] = true;
            q.push(v);
        }
    }
}
~~~

**Stack = last unresolved thing. Queue = first discovered thing. Priority queue = best current candidate.**
