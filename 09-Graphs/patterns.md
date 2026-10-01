# Graph Patterns

For graph problems, identify V = vertices and E = edges before estimating complexity.

## DFS

Use for reachability, connected components, structural exploration, and many cycle checks.

~~~cpp
void dfs(int u, vector<vector<int>>& adj, vector<int>& vis) {
    vis[u] = 1;

    for (int v : adj[u])
        if (!vis[v])
            dfs(v, adj, vis);
}
~~~

## BFS

Use for minimum number of edges in an unweighted graph and layer expansion.

## Topological sort

Recognition: directed graph + dependencies/prerequisites.

~~~cpp
vector<int> indeg(n);
queue<int> q;

for (int i = 0; i < n; ++i)
    if (indeg[i] == 0) q.push(i);

vector<int> order;

while (!q.empty()) {
    int u = q.front();
    q.pop();
    order.push_back(u);

    for (int v : adj[u])
        if (--indeg[v] == 0)
            q.push(v);
}
~~~

If fewer than V nodes are produced, a complete topological ordering is impossible.

## Shortest-path recognition

| Graph | Candidate |
|---|---|
| Unweighted | BFS |
| Non-negative weights | Dijkstra |
| Negative weights possible | Bellman-Ford |
| All-pairs | Floyd-Warshall |

## MST

Need to connect all vertices with minimum total edge weight. Common approaches: Kruskal + DSU, or Prim + priority queue.
