# Trees

## DFS

Use recursion when the answer naturally depends on a subtree.

~~~cpp
void dfs(TreeNode* node) {
    if (!node) return;

    dfs(node->left);
    dfs(node->right);
}
~~~

Before coding, define what solve(node) means, its base case, and how child answers combine.

## BFS / level order

Use a queue for depth, levels, and nearest-node questions.

~~~cpp
queue<TreeNode*> q;
q.push(root);

while (!q.empty()) {
    int sz = q.size();

    while (sz--) {
        TreeNode* node = q.front();
        q.pop();

        if (node->left) q.push(node->left);
        if (node->right) q.push(node->right);
    }
}
~~~

## BST

Exploit left < node < right. Inorder traversal of a valid BST produces sorted order.

## Recursion checklist

- What does the function return?
- What is the base case?
- How are child answers combined?
- What state goes downward?
- What state comes upward?
